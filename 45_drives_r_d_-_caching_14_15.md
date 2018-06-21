# 45 Drives R&D - Caching 14 15

## THINGS TO CONSIDER
Change the IO scheduler for the SSD devices from CFQ to Deadline (or NOOP) as documented in this page...

[http://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/tree/Documentation/block/switching-sched.txt?id=HEAD](http://git.kernel.org/cgit/linux/kernel/git/torvalds/linux.git/tree/Documentation/block/switching-sched.txt?id=HEAD)

Idea for this came from this paper...[http://iopscience.iop.org/1742-6596/513/6/062023/pdf/1742-6596_513_6_062023.pdf](http://iopscience.iop.org/1742-6596/513/6/062023/pdf/1742-6596_513_6_062023.pdf)

"Due to the fact that SSDs are not subject to the I/O timings required for efficient access to rotating media, the “deadline”
or “noop” kernel I/O schedulers should be used with these drives. During our tests, we set the
kernel I/O scheduler to “deadline” for the SSD"

http://events.linuxfoundation.org/sites/events/files/slides/Wheeler_LinuxForum_Korea_2013.pdf

# Caching

This page is dedicated to the documents and research leading up to the understanding and implementation of a caching scheme in a 45Drives Machine


## Setup

benchmarking results & scripts to make and destroy bcache, dm-cache & enhcanceIO. [https://www.redhat.com/archives/dm-devel/2013-June/msg00026.html](https///www.redhat.com/archives/dm-devel/2013-June/msg00026.html)

## dm-cache

* dm-cache and bcache setup guide
{{:linuxblockcaching_1_.pdf|}}

* dm-cache Documentation [https://www.kernel.org/doc/Documentation/device-mapper/cache.txt](https///www.kernel.org/doc/Documentation/device-mapper/cache.txt)

* dm-cache through LVM [http://rwmj.wordpress.com/2014/05/22/using-lvms-new-cache-feature/](http://rwmj.wordpress.com/2014/05/22/using-lvms-new-cache-feature/)

*This is a quick and dirty cheat sheet on LVM using Linux, I have highlighted many of the common attributes for each command however this is not an extensive list, make sure you look up the command. [http://www.datadisk.co.uk/html_docs/redhat/rh_lvm.htm](http://www.datadisk.co.uk/html_docs/redhat/rh_lvm.htm)

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

	
	[root@45Drives btier-1.2.6]# modprobe btier
	#then check to make sure it worked run the follwoing command...
	[root@45Drives btier-1.2.6]#ls -l /dev/tiercontrol
	#Output will look like this.....
	crw-rw---- 1 root root 10, 50 2013-01-23 10:21 /dev/tiercontrol
	#then run the btier_setup command as seen in the post linked


## Benchmarks

BEST PART OF BTIER IS how ridiculously easy it is to set up... assuming you already have you fast and slow volumes already configured how you want them it takes a single command to create the tiered volume. Of course configuring it to certain applications is more in depth but still relatively easy and fairly well documented.

[Btier prelim benchmarks](Btier prelim benchmarks)

Btier was used to create a two tiered storage volume ( 40 disk RAID 6, 5 RAID 0 SSD).

Fio was used to benchmark -> script containing test parameters [TierBM.sh](TierBM.sh)

Results = Very Promising

	
	Btier 1.3.3 CENTOS 6.6 Kernel version = 2.6.32
	
	100% SEQUENTIAL READ/WRITE;block size = 64K
	
	read : io=819200MB, bw=1341.6MB/s, iops=21464, runt=610633msec
	write: io=819200MB, bw=161453KB/s, iops=2522, runt=5195683msec
	
	100% RANDOM READ/WRITE;block size = 4k
	
	read : io=819200MB, bw=514365KB/s, iops=128591, runt=1630868msec
	write: io=819200MB, bw=281657KB/s, iops=70414, runt=2978305msec


Currently rerunning tests with CentOS 7 and 3.10 kernel as the author of btier has a few options/ optimaztions only available in kernels > 3.0
-Make sure to enable trim/discard.....and to figure out a way to change the writeback/writethrough

	

	**CENTOS 7 Kernel version = 3.10
	
	100% SEQUENTIAL READ/WRITE;block size = 64K
	
	read : io=819200MB, bw=7571.1MB/s, iops=121137, runt=108201msec
	write: **need to run again; cancelled test prematurely by accident**
	
	100% RANDOM READ/WRITE;block size = 4k
	
	read : io=819200MB, bw=1677.3MB/s, iops=429378, runt=488416msec
	
	write: io=819200MB, bw=197039KB/s, iops=49259, runt=4257334msec
	


****SADLY when copying real data the system(centos 7) crashed hard**** 

Went back to centos 6.6 and successfully transferred a 5GB movie. Approx. 1.5GB/s instantly then falls off considerably. kept doing this until btier reported I/O error and failed. Unable to access btier volume and all data is lost. THIS IS UNACCEPETABLE.

 
However all is not lost... Now going to downgrade to version 1.2.6.. btier author says its the most stable release. All is not lost yet...but __**TAKE ABOVE BENCHMARKS WITH A GRAIN OF SALT**__

In process of redoing this with a different version of btier
----

Btier 1.2.6 is stable enough to use real data transfers!!!!!!!!

Benchmarks give ridiculously good numbers however they ARE NOT repeatable with real files.

HOWEVER still seeing transfer speeds of approximately 350MB/s (approx data transfer reported by GUI) Actually timing the transfer gives ~400MB/s

It would now be worth it to put on a 10Gb Network and see the speeds we get.

It is also explicitly stated on the btier blog that it supports PCI-e SSD cache cards... Very interested to try the ones steve ordered 
