# Caching

This page is dedicated to the documents and research leading up to the understanding and implementation of a caching scheme in a 45Drives Machine
## Setup

## dm-cache

* dm-cache and bcache setup guide
{{:linuxblockcaching_1_.pdf|}}

* dm-cache Documentation [https://www.kernel.org/doc/Documentation/device-mapper/cache.txt](https///www.kernel.org/doc/Documentation/device-mapper/cache.txt)

* dm-cache through LVM [http://rwmj.wordpress.com/2014/05/22/using-lvms-new-cache-feature/](http://rwmj.wordpress.com/2014/05/22/using-lvms-new-cache-feature/)
## bcache

* Bcache Userspace Tools (.rpm) {{:bcache-tools-0.0-0.1.20130815git0b57e1.fc19.src.rpm|}}

* more bcache info
[http://pommi.nethuis.nl/ssd-caching-using-linux-and-bcache/](http://pommi.nethuis.nl/ssd-caching-using-linux-and-bcache/)

* Reconfigure/compile kernels (This is needed to activate bcache, as kernels >= 3.10 have bcache support but is not activated as a module by default)
[http://www.tecmint.com/kernel-3-5-released-install-compile-in-redhat-centos-and-fedora/](http://www.tecmint.com/kernel-3-5-released-install-compile-in-redhat-centos-and-fedora/)[http://wiki.centos.org/HowTos/BuildingKernelModules](http://wiki.centos.org/HowTos/BuildingKernelModules)
Following the steps linked above when you get to the "make menuconfig"

	
	      Device Drivers ----->
	         Multiple devices driver support (RAID and LVM) ----->
	              `<M>`Block device as cache


## Benchmarking/Performance

* The Effect of Flashcache and Bcache on I/O Performance
[https://indico.cern.ch/event/214784/session/8/contribution/64/material/slides/0.pdf](https///indico.cern.ch/event/214784/session/8/contribution/64/material/slides/0.pdf)

* Enhance IO, Bcache and dm-cache were compared [http://www.phoronix.com/scan.php?page=news_item&px=MTM4ODA](http://www.phoronix.com/scan.php?page=news_item&px=MTM4ODA)
 --->To summarize in "write-through" mode EnhanceIO has the best throughput..In "write-back" mode dm-cache had best throughput followed by EnhanceIO and then bcache. Due to the nature of how each technique works however EnhanceIO and bcache provide higher data integrity at a cost of performance.

### dm-cache results

dm-cache was implemented using a 70GBcache device 750MB metadata device and a 54TB 20 Drive RAID 6. 
----
HDDs used are 3 TB Hitachis.
SSD used is a 128GB Sandisk Ultra Plus 


*  Using IOzone. This was more or less a prelim test to see what iozone could do. 

*  This is the command used to generate the results(./iozone -a -g 24G -b {filename}.xls -f /location/of/device)

*  results are in kB/s
       - SSD results       ----->{{:ssd.xls|}}
       - dm-cache LVM ----->{{:dmcache.xls|}}

----

*  More appropriate benchmarks including thru-put & iops 

*  [Script used for test](Script used for test)
        - dm-cache ------>{{:4k_24gthrudmcache.xls|}}{{:4k_24gdmcache_ops.xls|}}
        Record size = 4 kBytes		
Output is in kBytes/sec		
    Initial write 		231822.4844
        Rewrite 		257013.25
           Read 		105729.9063
        Re-read 		96919.1875
    Random read 		3617.67334
   Random write 		85474.03906

Output is in IO/sec		
    Initial write 		111723
        Rewrite 		113436
           Read 		93307
        Re-read 		91174
    Random read 		1006
   Random write 		22902







# Block Tiering


bteir --->  http://www.lessfs.com/wordpress/
The setup in this post does work however after installing you must load the btier module to make the btier_setup command work.
To do this......

NOTE i am using 1.2.6 as the guys who wrote btier say it is the most stable at the moment. Newer versions will explored if this doesn't pan out

	
	[root@45Drives btier-1.2.6]# modprobe btier
	#then check to make sure it worked run the follwoing command...
	[root@45Drives btier-1.2.6]#ls -l /dev/tiercontrol
	#Output will look like this.....
	crw-rw---- 1 root root 10, 50 2013-01-23 10:21 /dev/tiercontrol
	#then run the btier_setup command as seen in the post linked


## Benchmarks

The following output from the command line are initial benchmarks using the command...

	
	hdparm -t /dev/devname

this explains what is being measured...

        * Perform timings of device reads for benchmark and comparison purposes. For meaningful results, this operation should be repeated 2-3 times on an otherwise inactive system (no other active processes) with at least a couple of megabytes of free memory. This displays the speed of reading through the buffer cache to the disk without any prior caching of data. This measurement is an indication of how fast the drive can sustain sequential data reads under Linux, without any filesystem overhead. 

Essentially the theoretical max thru-put of the volume minus a filesystem: a 100% sequential read..

Intuition would say that this is a poor test for benchmarking a cacheing scheme as a well implemted cache will skip big sequential reads because HDDs are already quite fast at this.

However interesting numbers were reported....

Note this was done on unmounted volumes with no filesystem. when both of these conditions are applied this same command will likely show smaller numbers

	
	[user@45Drives btier-1.2.6]$ su
	Password: 
	[root@45Drives btier-1.2.6]# modprobe btier
	[root@45Drives btier-1.2.6]# ls -l /dev/tiercontrol
	crw-rw----. 1 root root 10, 56 Nov 15 14:43 /dev/tiercontrol
	[root@45Drives btier-1.2.6]# ./btier_setup -f /dev/md125:/dev/md124 -B -c
	bash: ./btier_setup: No such file or directory
	[root@45Drives btier-1.2.6]# btier_setup -f /dev/md125:/dev/md124 -B -c
	
	Device size (raw)              : 0x3b8f000000 (255802212352)
	Device size (rnd)              : 0x3b8f000000 (255802212352)
	Clearing bitlist of device     : /dev/md125
	     offset                    : 0x3b8ef00000 (255801163776)
	     device size               : 0x3b8f000000 (255802212352)
	     bitlist size              : 0x100000 (1048576)
	
	Device size (raw)              : 0x82fcbc00000 (9001374842880)
	Device size (rnd)              : 0x82fcbc00000 (9001374842880)
	Clearing bitlist of device     : /dev/md124
	     offset                    : 0x82fcb300000 (9001365405696)
	     device size               : 0x82fcbc00000 (9001374842880)
	     bitlist size              : 0x900000 (9437184)
	
	Total device size              : 0x86b4b100000 (9256913862656)
	Clearing blocklist of device   : /dev/md125
	     list size                 : 0xec00000 (247463936)
	     starting from offset      : 0x3b80300000 (255553699840)
	
	write_device_magic device      : 0
	     size                      : 0x86b4b100000 (9256913862656)
	write_device_magic device      : 1
	     size                      : 0x86b4b100000 (9256913862656)
	[root@45Drives btier-1.2.6]# 
	[root@45Drives btier-1.2.6]# cat /sys/block/sdtiera/tier/device_usage
	   TIER               DEVICE         SIZE MB    ALLOCATED MB   AVERAGE READS  AVERAGE WRITES     TOTAL_READS    TOTAL_WRITES
	      0                md125          243713               0               0               0               0               0
	      1                md124         8584369               0               0               0               0               0
	
	[root@45Drives btier-1.2.6]# cat /sys/block/sdtiera/tier/device_usage
	   TIER               DEVICE         SIZE MB    ALLOCATED MB   AVERAGE READS  AVERAGE WRITES     TOTAL_READS    TOTAL_WRITES
	      0                md125          243713               0               0               0               0               0
	      1                md124         8584369               0               0               0               0               0
	
	[root@45Drives btier-1.2.6]# cat /sys/block/sdtiera/tier/migration_policy 
	   tier               device         max_age hit_collecttime
	      0                md125           86400           43200
	      1                md124           86400           43200
	####### MAX THEORTICAL THRU-PUT SEQUNCIAL READ#################
	######## /dev/sdtiera  (the tiered device...RAID01SSDs + 6 RAID6 3TB HDDS)##########
	[root@45Drives btier-1.2.6]# hdparm -t /dev/sdtiera
	
	/dev/sdtiera:
	 Timing buffered disk reads: 7628 MB in  3.00 seconds = 2542.41 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/sdtiera
	
	/dev/sdtiera:
	 Timing buffered disk reads: 8678 MB in  3.00 seconds = 2892.51 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/sdtiera
	
	/dev/sdtiera:
	 Timing buffered disk reads: 7982 MB in  3.00 seconds = 2660.28 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/sdtiera
	
	/dev/sdtiera:
	 Timing buffered disk reads: 8702 MB in  3.00 seconds = 2900.56 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/sdtiera
	
	/dev/sdtiera:
	 Timing buffered disk reads: 8596 MB in  3.00 seconds = 2864.86 MB/sec
	
	######## /dev/md124 (the 6RAID 6 3TB HDDs) ##################
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md124
	
	/dev/md124:
	 Timing buffered disk reads: 724 MB in  3.00 seconds = 241.30 MB/sec
	
	/dev/md124:
	 Timing buffered disk reads: 788 MB in  3.00 seconds = 262.51 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md124
	
	/dev/md124:
	 Timing buffered disk reads: 860 MB in  3.00 seconds = 286.25 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md124
	
	/dev/md124:
	 Timing buffered disk reads: 790 MB in  3.00 seconds = 263.24 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md124
	
	/dev/md124:
	 Timing buffered disk reads: 802 MB in  3.00 seconds = 267.15 MB/sec
	[root@45Drives btier-1.2.6]#
	
	######## /dev/md125 (the RAID01 SSDs ) ##################
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md125
	/dev/md125:
	 Timing buffered disk reads: 1736 MB in  3.00 seconds = 578.02 MB/sec
	
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md125
	
	/dev/md125:
	 Timing buffered disk reads: 1726 MB in  3.00 seconds = 575.23 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md125
	
	/dev/md125:
	 Timing buffered disk reads: 1726 MB in  3.00 seconds = 575.29 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md125
	
	/dev/md125:
	 Timing buffered disk reads: 1722 MB in  3.00 seconds = 573.87 MB/sec
	[root@45Drives btier-1.2.6]# hdparm -t /dev/md125
	
	/dev/md125:
	 Timing buffered disk reads: 1714 MB in  3.00 seconds = 570.89 MB/sec
	[root@45Drives btier-1.2.6]#


