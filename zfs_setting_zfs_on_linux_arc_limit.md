# Setting ZFS on Linux ARC Limit

ZFSonLinux defaults to use only 50% of available RAM in the system.

This should be bumped up to 90% in a sole ZFS server, and 80% if other tasks (non ZFS) are running as well.

The RAM varible below should be in bytes. Total avaible RAM in kb can be found by running the following command. Convert to bytes by multiplying by 1024.

*  RAM_kb = ${cat /proc/meminfo | grep -i memtotal}

*  RAM = RAM_kb * 1024

 1.  Create file "/etc/modprobe.d/zfs.conf"
 2.  echo "options zfs zfs_arc_max=${90% * RAM}
 3.  echo "options zfs zfs_arc_min=${33% * RAM}
 4.  Reboot
 5.  Verify with
    - cat /sys/module/zfs/parameters/zfs_arc_max
    - cat /sys/module/zfs/parameters/zfs_arc_min
