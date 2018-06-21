# Gluster Performance Tuning

When using GlusterFS mount on a client be sure to add "direct-io-mode=disable" in fstab

*  {node}:/{volumename} {mount/location} glusterfs defaults,_netdev,direct-io-mode=disable 0 0
    

## Kernel Tuning

*  **vm.swappiness=0**
    * vm.swappiness is a tunable kernel parameter that controls how much the kernel favors swap over RAM.At the source code level, it’s also defined as the tendency to steal mapped memory.
    * Higher vm.swappiness = more likely to unmap mapped pages.
    * High system swapping ( moving files in and out of RAM into swap on the boot device) causes significant performance reduction. So set vm.swappiness to 0. 
    * Heavily loaded, streaming applications should ALWAYS use swappiness=0
    * More detail here: https://lwn.net/Articles/100978/

*  **net.core.r(w)mem_max=67108864**
    * Socket send and receive buffers, bigger buffers usually mean better large streaming through (10gbe) but less efficient small file communication.
    * This number highly depends on the specific application and should be experimented with to get best value

*  **net.ipv4.tcp_(w)rmem=33554432**
    * Increase linux tcp autotuning buffer limit.
    * This number highly depends on the specific application and should be experimented with to get best value

*  **net.core.netdev_max_backlog=30000**
    * increase the length of the processor input queue
    * May be irrelevant to change in kernels 3.10 and >

*  **net.ipv4.tcp_congestion_control=htcp**
    * recommended default congestion control is htcp

## Gluster Volume Tuning

More info on all options here: https://gluster.readthedocs.io/en/latest/Administrator%20Guide/Managing%20Volumes/#tuning-options


*  **performance.cache-size 1GB**
    * Default is 32MB, increasing this will increase read performance at the cost of RAM

*  **nfs.disable on**
    * Enabled by default.

*  **performance.io-cache on**
    * Enabled by Default

*  **performance.io-thread-count 16**
    * 16 is the default value, possible values 0-65
    * Increasing this should increase performance with increased users as long as the CPU/NIC can keep up. 

*  **performance.write-behind-window-size: 1MB**
    * Increasing this will increase write performance noticeably
    * There must be a trade off we have not uncovered. My guess is the bigger the write cache the bigger chuck of data that can possibly be lost should catastrophic failure occur.

## Speed Up Directory Operations for SMB Clients

Set these two settings by default when using SMB access into a glusterfs volume.

    * **Enable MetaData Caching on the gluster volume**
       * gluster vol set {VOLNAME} group metadata-cache
    * **Jack up the number of inode entries that can be cached**
       * gluster vol set {VOLNAME} network.inode-lru-limit 1000000

These two settings alone will significantly speed up directory operations in windows.

For Mac OS X clients, see [Mac OSX Samba Optimization](45_drives_r_d_-_mac_osx_samba_optimization)






