# 45Drives R&D - CephFS

## Snapshots

Enable snapshots with 

*  ceph mds set allow_new_snaps true --yes-i-really-mean-it

### Manual Snapshots

To take a snapshot:

*  From a client where the cephFS is mounted, navigate to diretcory you wnat to snapshot. cd /mnt/cephfs/data

*  cd .snap

*  mkdir new_snap_03-02-18

To recover files from snapshot:

*  From a client where the cephFS is mounted, navigate to directory you want to recover the file.cd /mnt/cephfs/data

*  cd .snap

*  Find the correct snapshot, cd new_snap_03-02-18

*  Find the file(s) you want to recover

*  cp -R {file(s)} /mnt/cephfs/data

To delete snapshot:

*  cd /mnt/cephfs/data/.snap

*  rmdir new_snap_03-02-18

### Automated Snapshots

Use [cephfs-snap](http://images.45drives.com/ceph/cephfs/cephfs-snap) to automatically create and delete old snapshots.

Usage Example:
    cephfs-snap /mnt/server hourly 24
    would make a snapshot in /mnt/server/.snap/ called hourly_`<date>`_`<time>`
    where `<date>` is on the form YYYY-MM-DD and `<time>` is on the form
    HH:MM:SS. This format makes shure snapshot names sort correctly in
    cronological order even when sorted alphabetically. The 24 newest
    snapshots matching the prefix are kept around. The rest are deleted.

Designed to be used with /etc/cron.{hourly,daily,weekly,monthly}

Usage Example:
    To take hourly snaps, and delete the old ones after 24, create a file "/etc/cron.hourly/cephfs-snap"
    And place
    #!/bin/bash
    cephfs-snap / hourly 24

##  Multiple Cephfs Namespaces

To mount specify which namepasace with If you have more than one filesystem, specify which one to mount using the mds_namespace option, e.g. -o mds_namespace=myfs.
    192.168.16.100,192.168.16.101,192.168.16.102:6789:/ /ceph/ovirt   ceph    dirstat,name=admin,secretfile=/root/.ceph/admin.secret,noatime,_netdev,mds_namespace=cephfs   0 2
    192.168.16.100,192.168.16.101,192.168.16.102:6789:/ /ceph/ssdfs   ceph    dirstat,name=admin,secretfile=/root/.ceph/admin.secret,noatime,_netdev,mds_namespace=ssdfs    0 2


## vfs_cephfs

**WARNING: NOT CURRENTLY WORKING**

**ACTIVE DEVELOPMENT**

Samba 4.8.X and onwards has the vfs_ceph object included.

The most recent package in the CentOS repos is 4.6. 

To use vfs_ceph to have smb share a ceph_fs volume without mounting in userspace first, you have to install samba 4.8.X from source.

### Installation From Source


Get the most recent 4.8.X release from the samba git page.

    wget https://github.com/samba-team/samba/releases

Install dependancies:

    yum install python-devel libacl-devel openldap-devel pam-devel

Configure Smaba for installation. Use "./configure --help" for full list of options. By default we exclude the packages needed for this install to function as a Domain Controller

    ./configure --without-ad-dc

Compile source

    make

To install compiled source

    make install

Export samba to PATH file

    export PATH=/usr/local/samba/bin/:/usr/local/samba/sbin/:$PATH

Create systemd service files

    WIP


## Troubleshooting

If you get a message like the following:

   2018-03-09 15:12:20.458881 [INF]  Cluster is now healthy
   2018-03-09 15:12:20.458821 [INF]  Health check cleared: MDS_CLIENT_RECALL (was: 1 clients failing to respond to cache pressure)
   2018-03-09 15:12:20.445771 [INF]  MDS health message cleared (mds.0): Client cephsmb1.45lab.com failing to respond to cache pressure
   2018-03-09 15:11:56.495660 [WRN]  Health check failed: 1 clients failing to respond to cache pressure (MDS_CLIENT_RECALL)
   2018-03-09 15:11:56.445334 [WRN]  MDS health message (mds.0): Client cephsmb1.45lab.com failing to respond to cache pressure 

First check the kernel. The cephfs kernel driver in the 3.10 kernel is fairly out of date.
Use the el repo kernel-ml to update to most recent linux kernel.

If running updated kernel and messages persist, see the following:



