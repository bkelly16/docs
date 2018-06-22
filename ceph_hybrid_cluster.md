# 45 Drives R&D - Ceph Hybrid Cluster

## Client Side Caching

flashcache + rbd improves performance and is relatively easy to setup. does not require custom kernel. Currently works fine in CentOS 7.4. forked to our github in case it gets removed.

Using SSD on client side to speed up rbd block devices reads/writes is useful.
Physical SSDs client side is kinda annoying though.
No easy failure protection, and each physical machine requires a separate SSD.

Possible solution is to use a hybrid ceph cluster. A SSD pool and a HDD pool. (3 rep for spinners, and 2 rep for SSD).

Create RBD pool for each media type, rbd-ssd and rbd-hdd.

Create the number of images required and mount on client. one ssd and one hdd

Create a hybrid block device client side with flashcache using the ssd block dev and the HDD.

encryption can be used with LUKS.
--- Is it better to encrypt the raw devices or the flashcache dev ????

Combine with iSCSI (LIO) if necessary for windows clients

[CEPH CLUSTER] --->{rbd}-->[LINUX CLIENTS]-->{LIO>iSCSI}--->[WINDOWS CLIENTS]

## SSD Pools

##### USE THIS FOR LUMINOUS (v12.X) and above


You can set device class on the osd {hdd,sdd,nvme} system will set by default.


Create ruleset and speicfy class {hdd,sdd,nvme}

ceph osd crush rule create-replicated {rule-name} {root} {failure-domain} {class}

Tell pool to use the new rule-set

ceph osd pool set pool-name crush_rule rule-name



##### USE THIS PRE LUMINOUS V12.X

SSDs and HDD can be utilised in the same cluster, as two spearte "fast" and "slow" pools.

Create OSDs out of all HDDs and SSDs. Then need to edit the CRUSH map to route fast and slow io.

Step by step guide [here](https///www.suse.com/documentation/ses-4/book_storage_admin/data/op_mixed_ssd_hdd.html) & [here](https///www.sebastien-han.fr/blog/2014/08/25/ceph-mix-sata-and-ssd-within-the-same-box/)

Note that some of the steps are out of date. Below is the updated steps. Refer to the links for more info on the concept of why this works.

Create a secondary entry point into the cluster for CRUSH to store objects. $SSD_ROOT is used for the SSD osds and the default root will be used for HDD

	
	ceph osd crush add-bucket $SSD_ROOT root


Edit ceph.conf on each osd node, this ensures osds do not reset back to their original configuration.

	
	echo "osd crush update on start = false" >> /etc/ceph/ceph.conf


Create a "fake" host for each osd node and move them into the secondary entry point $SSD_ROOT

	
	ceph osd crush add-bucket $OSD_NODE-ssd host
	ceph osd crush move $OSD_NODE-ssd root=$SSD_ROOT


Move each SSD osd into $SSD_ROOT and assign them to their respective host

	
	ceph osd crush add osd.$OSD_ID 1 root=$SSD_ROOT
	ceph osd crush set osd.$OSD_ID 1 root=$SSD_ROOT host=$OSD_NODE-ssd


Create custom rule set that targets SSD_ROOT

	
	ceph osd crush rule create-simple $SSD_RULESET $SSD_ROOT host


Create a Object Pool $SSD_POOL on the cluster, and assign the custom ruleset to point object IO towards $SSD_ROOT

	
	ceph osd pool create $SSD_POOL 128
	ceph osd pool set $SSD_POOL crush_rule $RULESETNAME


