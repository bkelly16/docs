# NAS Video Project



*  A 30 Drive Unit is currently being used in-house for video editing over a 10 gigabit Network.


*  The Unit is setup with 6-5Drive RaidZ1 on zfs file system with freenas.


*  The network protocol is a samba windows share.


*  We are currently using 1 of the 6 pools for transferring video files:
       * 5 Drive RAIDZ1 using 3TB Hitachi Drives.
       * Total space of 10.7 TB.
    note: RAID Z1 is essentially a RAID5 in terms of redundancy, however zfs allocates more space for the filesystem.


*  Theoretical transfer speed which would saturate a 10Gbit Network: 1280MB/s.


*  For a 8 GB video file, we are seeing: 110-120 MB/s.
       * This speed currently saturates a 1 Gbit Network but not yet 10.
       * We believe that the Samba Protocol is our bottleneck.
       * NFS Protocol was used initially but was found to be unusably slow.


*  A 10 Drive RAIDZ2 was setup and tested with same situation above, there is no throughput change when using a different RAID Level.


#### Our video editing experience in general:


*  When taking video footage from the FreeNAS server and editing it on the local PC (10 Gbit Network), the video editing software started, & 8GB video clip was loaded in almost instantly (5-10 seconds). It was usable right there after.

*  When taking video footage from the local server (Public on PROTO) & editing on local PC (1 Gbit Network), the software starts, takes about the same time to initialize/ become usable.





    * NEXT: Investigate other Networking Protocols.
    * NEXT: Try to do multiple video transfers simultaneously and see how it effects throughput.
    
    

 






