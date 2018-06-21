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

## Throughput Tests Over 10Gbit NIC


*  Two identical Storinators were setup:
       * 40 Drive RAID 6 with 5 Drive SSD RAID 0 configured with btier.
       * Mounted on XFS.
       * Connection is between 2 Intel ixgbe-t2 10Gbit Network Controllers.
       * FTP Share was setup between machines. (this is the fastest protocol we are aware of)
       * An 8.4 GB video file was used for all data transfers.
       * A number of parameters in btier were adjusted in order to determine the greatest throughput. (Barriers, Sequential Landing, Write-through)
       * In this test case one btiered machine was set up as the Host (FTP Server) and the other machine was set up as the Client.
       * For all tests files were downloaded onto the Client machine from the Host machine (FTP Server)

#### Test 1


*  8.4 GB Video File Downloaded from FTP server.

*  Barriers: On

*  Sequential Landing: Off

*  Write-through: On

*  73 MB/s

#### Test 2


*  8.4 GB Video File Downloaded from FTP server.

*  Barriers: On

*  Sequential Landing: Off

*  Write-through: Off

*  250 MB/s

#### Test 3


*  8.4 GB Video File Downloaded from FTP server.

*  Barriers: On

*  Sequential Landing: On

*  Write-through: Off

*  300 MB/s

#### Test 4


*  8.4 GB Video File Downloaded from FTP server.

*  Barriers: Off

*  Sequential Landing: **On**

*  Write-through: Off

*  400 MB/s

**A 40 drive RAID 6 was created on each machine without any tiering or SSDs, this was done to compare numbers with the tiering tests.**

*  The same 8.4 GB file was downloaded from FTP server over a 10 Gbit Network .

*  Throughput peaked at 320 MB/s; Average throughput of 150 MB/s.

## Initial BTRFS Testing with Tiering

 
#### Test Setup

 1.  2 identical machines
 2.  40 Drive RAID 6.
 3.  5 Drive RAID 0 SSD Tier.
 4.  FTP Share over 10 Gbit Network

#### Results




*  8.4 GB Video File Downloaded from FTP server.

*  Barriers: Off

*  Sequential Landing: **On**

*  Write-through: Off

*  215 MB/s

