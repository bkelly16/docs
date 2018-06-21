#  45 Drives R&D - GlusterFS HA NFS GAnesha

## Packages Needed

We need to make sure that node are running the **3.10.0-862.3.2.el7.x86_64 kernel** on **CentOS 7.5.1804**. 


Each node must have the following list of packages to makes this work. Must be using **gluster 3.10** packages, as well as **nfs-ganesha-2.5.2-1**.
Below is an output of all of the packages I have installed.

   [root@gluster11 ~]#rpm -qa | grep gluster
   glusterfs-libs-3.10.12-1.el7.x86_64
   python2-gluster-3.10.12-1.el7.x86_64
   glusterfs-extra-xlators-3.10.12-1.el7.x86_64
   glusterfs-fuse-3.10.12-1.el7.x86_64
   glusterfs-server-3.10.12-1.el7.x86_64
   glusterfs-geo-replication-3.10.12-1.el7.x86_64
   glusterfs-coreutils-0.2.0-1.el7.x86_64
   centos-release-gluster310-1.0-1.el7.centos.noarch
   glusterfs-3.10.12-1.el7.x86_64
   glusterfs-api-3.10.12-1.el7.x86_64
   glusterfs-events-3.10.12-1.el7.x86_64
   glusterfs-resource-agents-3.10.12-1.el7.noarch
   glusterfs-rdma-3.10.12-1.el7.x86_64
   nfs-ganesha-gluster-2.5.2-1.el7.x86_64
   glusterfs-client-xlators-3.10.12-1.el7.x86_64
   glusterfs-cli-3.10.12-1.el7.x86_64
   glusterfs-devel-3.10.12-1.el7.x86_64
   glusterfs-api-devel-3.10.12-1.el7.x86_64
   glusterfs-ganesha-3.10.12-1.el7.x86_64

   [root@gluster11 ~]# **rpm -qa | grep ganesha**
   nfs-ganesha-2.5.2-1.el7.x86_64
   nfs-ganesha-gluster-2.5.2-1.el7.x86_64
   glusterfs-ganesha-3.10.12-1.el7.x86_64

To Install the gluster packages - first you need to install **centos-release-gluster310**. Then you can just run **yum install glusterfs* ** to install the rest of the gluster packages.

## Installing NFS-Ganesha

When using Gluster 3.10, it will try and download nfs-ganesha-2.4.X, which means that we need to manually install the RPM for nfs-ganesha-2.5.2, as well as libntirpc-1.5.3-1 and nfs-ganesha-gluster-2.5.2.

Check to see which version of libntirpc is currently installed:

    rpm -qa | grep libntirpc

If it is anything other than libntirpc-1.5.3-1, remove it using:

    yum remove libntirpc

Then to install the correct version:

    yum install ftp://mirror.switch.ch/pool/4/mirror/centos/7.5.1804/storage/x86_64/gluster-3.12/libntirpc-1.5.3-1.el7.x86_64.rpm

Once, we have that installed, we can now proceed and install nfs-ganesha-2.5.2 and nfs-ganesha-gluster-2.5.2:

    yum install ftp://mirror.switch.ch/pool/4/mirror/centos/7.5.1804/storage/x86_64/gluster-3.12/nfs-ganesha-2.5.2-1.el7.x86_64.rpm
    yum install ftp://mirror.switch.ch/pool/4/mirror/centos/7.5.1804/storage/x86_64/gluster-3.12/nfs-ganesha-gluster-2.5.2-1.el7.x86_64.rpm

Double check that **glusterfs-ganesha-3.10.12-1.el7.x86_64** is installed by running:

    rpm -qa | grep glusterfs-ganesha  --> if there is no output install it -->  yum install glusterfs-ganesha


## Installing Pacemaker Corosync and PCS

Pacemaker, Corosync and pcs are the tool that will allow us to have a Highly available NFS export.

    yum install pacemaker corosync pcs

Once these are installed, start and enable pcs

    systemctl enable pcsd && systemctl start pcsd

## Creating the Highly available setup

This is assuming you already have a gluster volume in which you want to export.

1. We need to have a user on all nodes named **hacluster**. The pcs cluster uses this as its admin user, so to create this user and setup a password for it run the following command:

    passwd hacluster   -> enter your password.  NOTE: Do this on all nodes.

2. Once this user is setup on all nodes, from one node we need to authorize all nodes through pcs to allow the cluster to be built:

    pcs cluster auth -u hacluster $node1 $node2 ... $nodeN  --> You will be prompted for the password, and then you should be Authorized for every node.

3. We need to enable shared storage on the gluster volume. 

    gluster volume set all cluster.enable-shared-storage enable

This will create a new gluster volume called **gluster_shared_storage** and it is used to store all of the nfs-ganesha export information. Wait until it is mounted on all nodes to proceed. Check by running "df -H" you should see it mounted at **/run/gluster/shared_storage**

4. Next we'll make a directory in this shared storage volume from **one** node.  
    mkdir /run/gluster/shared_storage/nfs-ganesha

5. We need to create 3 files within this new nfs-ganesha directory - **export.conf** **ganesha.conf** and **ganesha-ha.conf** 

**export.conf** - This file has that actual export information, below is an example.

   EXPORT{
       Export_Id = 1 ;   # Export ID unique to each export
       Path = "/tank";  # Path of the volume to be exported. Eg: "/test_volume"
       FSAL {
           name = GLUSTER;
           hostname = "192.168.16.94";  # IP of one of the nodes in the trusted pool
           volume = "tank";  # Volume name. Eg: "test_volume"
       }
       Access_type = RW;    # Access permissions
       Squash = No_root_squash; # To enable/disable root squashing
       Disable_ACL = TRUE;  # To enable/disable ACL
       Pseudo = "/tank";  # NFSv4 pseudo path for this export. Eg: "/test_volume_pseudo"
       Protocols = "3","4";    # NFS protocols supported
       Transports = "UDP","TCP" ; # Transport protocols supported
       SecType = "sys";     # Security flavors supported
   }

**ganesha.conf** - this is a very simple file, you only need 1 line in it, shown below:

    %include "/run/gluster/shared_storage/nfs-ganesha/export.conf"

**ganesha-ha.conf** - this file has the information in which pcs will create the highly available cluster.

    HA_NAME="ha-gluster"  # Name of the pcs cluster
    HA_VOL_SERVER="gluster11"  # hostname of 1 of the nodes
    HA_CLUSTER_NODES="gluster11,gluster12"  # hostnames of all nodes in cluster
    VIP_gluster11="192.168.14.100"  # Virtual IP for this specific node
    VIP_gluster12="192.168.14.101"  # Virtual IP for this specific node

6. Enable ganesha

    gluster nfs-ganesha enable


7. We need to put a delay on the start up of NFS-Ganesha to ensure all other services are started first. This is to be done on all nodes. To do this we need to edit a file:

    vim /usr/lib/systemd/system/nfs-ganesha.service

Once in there you must add this line __right above__ **ExecStart=**

    ExecStartPre=/bin/sleep 10

This will ensure that when a server is rebooted, it will automatically start exporting the volume again.


This should start everything for you. You can run **showmount -e** on all nodes and should see:

      [root@gluster12 ~]# showmount -e
      Export list for gluster12.45lab.com:
      /tank (everyone)

Also to monitor the PCS cluster, run **pcs status**

      [root@gluster11 ~]# pcs status
      Cluster name: ha-gluster
      Stack: corosync
      Current DC: gluster11 (version 1.1.18-11.el7_5.2-2b07d5c5a9) - partition with quorum
      Last updated: Fri Jun  8 10:21:23 2018
      Last change: Fri Jun  8 08:33:58 2018 by root via cibadmin on gluster12

      2 nodes configured
      12 resources configured

      Online: [ gluster11 gluster12 ]

      Full list of resources:

      Clone Set: nfs_setup-clone [nfs_setup]
          Started: [ gluster11 gluster12 ]
      Clone Set: nfs-mon-clone [nfs-mon]
          Started: [ gluster11 gluster12 ]
      Clone Set: nfs-grace-clone [nfs-grace]
          Started: [ gluster11 gluster12 ]
      Resource Group: gluster11-group
          gluster11-nfs_block        (ocf::heartbeat:portblock):     Started gluster11
          gluster11-cluster_ip-1     (ocf::heartbeat:IPaddr):        Started gluster11
          gluster11-nfs_unblock      (ocf::heartbeat:portblock):     Started gluster11
      Resource Group: gluster12-group
          gluster12-nfs_block        (ocf::heartbeat:portblock):     Started gluster12
          gluster12-cluster_ip-1     (ocf::heartbeat:IPaddr):        Started gluster12
          gluster12-nfs_unblock      (ocf::heartbeat:portblock):     Started gluster12

      Daemon Status:
          corosync: active/disabled
          pacemaker: active/disabled
          pcsd: active/enabled


Check **ip a** which you should see the Virtual IP that you set listed. Below you can see 192.168.14.101/32 as the Virtual IP on gluster12.

     2: enp2s0f0: `<BROADCAST,MULTICAST,UP,LOWER_UP>` mtu 1500 qdisc mq state UP group default qlen 1000
    link/ether 00:0a:f7:c5:22:b0 brd ff:ff:ff:ff:ff:ff
    inet 192.168.16.95/16 brd 192.168.255.255 scope global noprefixroute enp2s0f0
       valid_lft forever preferred_lft forever
    inet 192.168.14.101/32 brd 192.168.255.255 scope global enp2s0f0
       valid_lft forever preferred_lft forever
    inet6 fe80::16f5:28f:3f62:f5e2/64 scope link noprefixroute
       valid_lft forever preferred_lft forever

Try mounting the volume using one of the virutal IP's on a linux client:

    mount -t nfs 192.168.14.101:/tank /mnt/tank

    [root@localhost ~]# df -H
    Filesystem                     Size  Used Avail Use% Mounted on
    /dev/mapper/cl-root             43G  1.9G   41G   5% /
    devtmpfs                       917M     0  917M   0% /dev
    tmpfs                          930M     0  930M   0% /dev/shm
    tmpfs                          930M  9.1M  921M   1% /run
    tmpfs                          930M     0  930M   0% /sys/fs/cgroup
    /dev/sda1                      1.1G  298M  766M  28% /boot
    /dev/mapper/cl-home             21G   34M   21G   1% /home
    192.168.16.50:/mnt/ceph-block  1.1G   34M  1.1G   4% /mnt/nfs
    tmpfs                          186M     0  186M   0% /run/user/0
    192.168.14.100:/tank            99T  1.1T   98T   2% /mnt/gluster



