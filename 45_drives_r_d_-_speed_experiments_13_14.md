#  45 Drives R&D - Speed Experiments 13 14

## Caching Experiments

#### BCache

*  Requires kernel 3.10 or higher

*  Bcache does not work natively with the current versions of CentOS that we are shipping

*  To use bcache requires updating to kernel 3.10 or higher

*  According to some documentation, it is possible to compile bcache into older kernels, but my attempts to do so have been unsuccessful

*  Attempting to install latest kernel ( 3.17 ) for use on CentOS to continue this experiment

#### DM-Cache

*  dm-cache is new than bcache and also requires much newer kernels than CentOS provides - will test this when I have a new working kernel

*  lvm has added support on top of dm-cache as well which I haven't tested yet


## Benchmarks

#### CentOS 6.5 - Raid 0 - Raw Raid ( no file cache ) Read Only

{{:read.png?500}}


#### CentOS 6.5 - Raid 0 - Raw Raid ( no file cache ) Read/Write

{{:read_write.png?500}}

## June 9 2014


*  **Need to add components used and plot the results** 

#### RAMDISK

4.5 GB file
RAM DISK ( 10GB Ram Drive – limited to amount of RAM in the machine )
3 seconds – Read from and write to array – about 1.5 GB/s

9 GB file
9 seconds – Read from and write to array – 1 GB/s

#### CentOS

CentOS 6.5
XFS – 2 10 disk RAID 0 Arrays

50 GB (same array) = 315 MB/s

4.5 GB file = 4.5 seconds
1 GB/s – array to array

9 GB file = 9 seconds
1 GB/s – array to array

12.5 GB ( 3 file in a folder ) = 14.09 seconds
887 MB/s per second

25 GB ( 2 folder 12.5 GB each ) = 28 seconds
893 MB/s

99.9 GB ( Many files of 4.5 GB each ) =  2 minutes 41 seconds
620 MB/s

### Back To:

[45drives_innovation_priorites ](45drives_innovation_priorites )\\
[45_drives](45_drives)

