# 45 Drives R&D - HA NFS

## Packages Needed

Each ceph client (VM's) that will be used to share out this RBD image will need the following packages:

    * pacemaker               -   **yum install pacemaker**

    * corosync                -   **yum install corosync**

    * pcs                     -   **yum install pcs**

    * ceph-resource-agents    - **yum install ceph-resource-agents**


We need to make sure that these ceph clients are running the **3.10.0-862.3.2.el7.x86_64 kernel** on **CentOS 7.5.1804**. 

Once these packages are installed, start the pcsd service (**systemctl start pcsd**), and then we can start the configuring.

**NOTE:** Ensure that the nfs-ganesha service is stopped and disabled if you're using the nfs-server service.

## Authenticating each node and creating our pacemaker cluster

We need to have a user on each node named **"hacluster"** who is the admin user for the pcs cluster. We need to set the password for this user, it works best if it's the same on each node.

    * **passwd hacluster**  (enter password when prompted, do this on all nodes) 

Once this is done, we need to do the authentication:

    * **pcs cluster auth -u hacluster $hostname1 $hostname2**   (you will be prompted to enter the password for user hacluster)

Next we need to create our cluster:

    * **pcs cluster setup --name ha-ceph $hostname1 $hostname2**  (note there are 2 -'s before name)


## Creating resources the achieve the HA NFS server

In this example, our RBD pool is called "rbd_hdd" and our image name is "nfs-test1".
The order in which these resources are created / run is:

1. Map the RBD device
2. Mount the RBD device to the specified directory w/ specified filesystem
3. Export the RBD device 
4. Create the VIP
5. Start the nfs-server
6. Start the rpcbind 
7. Group the RBD resources
8. Group the NFS resources
9. Disable STONITH
10. Make NFS Active/Active

Below are the commands:

1. **pcs resource create rbd_map_1 ocf:ceph:rbd.in user="admin" pool="rbd_hdd" name="nfs-test1" cephconf="/etc/ceph/ceph.conf"
     op monitor interval="10s" timeout="20s"**

2. **pcs resource create fs_rbd_1 ocf:heartbeat:Filesystem
     directory="/mnt/ceph-block" fstype="xfs" device="/dev/rbd/rbd_hdd/nfs-test1"
     op monitor interval="20s" timeout="40s"
     op start interval="0" timeout="60s"
     op stop interval="0" timeout="60s"**

3. **pcs resource create export_rbd_1 ocf:heartbeat:exportfs
     directory="/mnt/ceph-block" clientspec="192.168.0.1/16"
     options="rw,async,no_subtree_check,no_root_squash" fsid="2"
     op monitor interval="10s" timeout="20s"
     op start interval="0" timeout="40s"**

4. **pcs resource create vip_1 ocf:heartbeat:IPaddr2
     ip="192.168.16.50" cidr_netmask="32" 
     op monitor interval="5"**

5. **pcs resource create nfs_server systemd:nfs-server
     op monitor interval="10s" timeout="30s"**

6. **pcs resource create rpcbind systemd:rpcbind 
     op monitor interval="10s" timeout="30s"**

7.  **pcs resource group add rbd_share_1 
      rbd_map_1 
      fs_rbd_1 
      export_rbd_1 
      vip_1 **

8.  **pcs resource group add create nfs
      rpcbind 
      nfs_server**

9. **pcs property set stonith-enabled=false**

10 . ** pcs resource clone nfs 
        meta globally-unique="false" target-role="Started"**


**NOTE:** As of right now, we need to have a VIP per resource group. Meaning if you have 3 different RBD images that you need to share out, you'll need to create 3 VIPs to allow for proper fail over.


## Watching Pacemaker Cluster status

Once you've run all the commands above, you should have a highly available RBD block exported via NFS.

You can use the command **pcs status** to monitor this, showing which VM is currently hosting the storage.

You can start and stop the cluster manually by: (**NOTE:** there are 2 -'s in front of all)

**pcs cluster start --all**

**pcs cluster stop --all**
