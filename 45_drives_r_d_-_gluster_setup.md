# Gluster Setup

## General Tips


*  When using ZFS as underlying FS, ** BE ABSOLUTELY SURE** the brick you create is located on a data-set and not on the root zpool. If the zpool fails to mount properly on boot up it will cause significant problems.

*  To get a zpool to properly auto-import on reboot the following services must be started
     * **systemctl enable zfs-import-cache.service** - This will import the pool on reboot
     * **systemctl enable zfs-mount.service** - This will mount all pool & children data-sets

*  Do not use **systemctl enable zfs-import-scan.service** as it seems to fail inconsistently.
 
## Hardware


*  Minimum of n nodes needed for Dist-Replica n Volume. (i.e a 2 way replica needs 2 nodes, a 3 way needs 3 and so on)

*  Minimum of one node needed for Distributed Volume

*  Minimum of 64GB of RAM

*  E5-2620 cpu or better

*  Dual CPU is overkill if only using the server as a gluster node, if running other services off the node as well (hyper-converged), dual CPU is recommended

## Software Installation

Requires CentOS 7.2
Our repo: https://github.com/bkelly16/45Drives

**NOTE** when downloading a file from the git repo make sure you use the "raw" tab rather than simply copying the main link. 
Or else the file will not be a plaintxt file as expected but a html file.

*  Setup network on each node, Internet connection required.

*  Update OS to latest version (yum update)

*  Download preconfig script in git repo onto each node.
    * wget https://github.com/bkelly16/45Drives/raw/master/preconfig

*  Set preconfig as executable 
    * chmod +x preconfig

*  Run as root user. You can pass "-y" as an option if you don't want to be prompted for each package installed
    * sudo ./preconfig {-y}

*  This installs following packages:
    * Kernel Development Packages
    * EPEL Repo
    * Official CentOS Gluster Repo
    * Gluster 3.8
    * Gluster FUSE
    * Gluster Server
    * ZFS Repo
    * ZFS (DKMS Packages)

## Automated Gluster Build Tools

Building a gluster volume is not difficult, but there are a lot of layers and services that must be started and configured to have a proper production ready gluster volume.


*  Configure NTP

*  Nagios Plugin for monitoring {optional}

*  Enable zfs-import and zfs-mount services

*  Map drive alias'

*  Create zpool

*  Add firewall ports ( 24007-24008/tcp , 111/tcp , 49152-49XXX/tcp )

*  Create volume

To assist in the process there are two methods: 

 1.  gdeploy + dmap + zcreate ( fully automated after configuring initial .conf file)
 2.  gtools2.0 ( not as automated as ^, but walks user through drive mapping, zpool creation and gluster volume creation)

### 1. gdeploy + dmap + zcreate

This method heavily relies on a tool called gdeploy.

*  git : https://github.com/gluster/gdeploy

*  rpm : https://download.gluster.org/pub/gluster/gdeploy/LATEST/CENTOS7/gdeploy-2.0.1-1.el7.centos.noarch.rpm

*  docs: http://gdeploy.readthedocs.io/en/latest/howitworks.html

#### Pre-Deploy

 1.  Ensure all nodes can communicate with each other by hostname resolution. It is best to just use "/etc/hosts" entries so DNS issues do not cause gluster failure.

    * Place an entry for each node in the "/etc/hosts" on each node
    * OR if using a DNS add relevant entries for each node (not recommended for gluster nodes)  
 2.  Download and install the gdeploy rpm on one of the gluster nodes.
 3.  Generate a passwordless ssh key 

     * ssh-keygen -t rsa -N ''
 4.  Copy the key to each participating node in the cluster

     * ssh-copy-id root@node{N}

#### Conf Generation

   - Example conf file found here

     * https://github.com/bkelly16/45Drives/blob/master/gdeploy_example.conf
   - Read the docs linked above for full list of features that can be included.
   - To edit the gdeploy_example.conf file for a specific build the following sections need to be changed to reflect the environment.

     * [hosts]
       * Put every nodes Hostname in the cluster. IP addresses are acceptable as well
     * [update-file1]
       * Change "line" to whatever NTP server you want to use. Defaults to CentOS public NTP
     * [script1]
       * This calls a script **dmap** that creates drive aliasing. You must edit this file top have the correct options for card and chassis. See the section "Drive Mapping" below for more options
       * This script should contain nothing but "#!/bin/bash" and the dmap command
       * **dmap -c {HBA Card} -s {Chassis} -q**
       * You can technically put this script anywhere on the filesystem as long as the full path is given in the .conf file. It is recommended to put it in /opt/gtools/bin/map.sh
     * [script2]
       * This calls a script **zcreate** that builds the underlying zpools. You must edit this file to have the correct options. See the section "Storage Array Creation" below for more options
       * This script should contain nothing but "#!/bin/bash" and the zcreate command.
       * **zcreate -q -B {brick_count} -v {vdev_count} -l {raid_level} -b**  
       * You can technically put this script anywhere on the filesystem as long as the full path is given in the .conf file. It is recommended to put it in /opt/gtools/bin/z.sh
     * [firewalld]
       * You must adjust the "ports" option to match the number of bricks used.
       * ** DO NOT TOUCH ** ports 111/tcp,24007-24008/tcp
       * The first brick on a node should always be assigned port 49152. Then one port for every other brick in the node.
       * For example, 4 bricks on a node would need ports **49152-49155/tcp** opened.
     * [volume]
       * Main thing to edit here is make sure you have the correct number of bricks listed under **brick_dirs**. Follow the same directory structure as the example.
       * Name can be changed by changing "volname"
       * Check out the docs to get a full picture of your options here: http://gdeploy.readthedocs.io/en/latest/features/volume.html#rst-glusterfsvolume
     
#### Usage 

    * Run gdeploy and point it to the .conf file you created
      * gdeploy -c /opt/gtools/bin/deploy.conf
    * When the process finishes, check run **gluster volume status** to verify volume is created
    * Mount volume using terminal or fstab
       * **Temporary Mount**  : mount -t glusterfs localhost:{volname} /mount/dir/
       * **/etc/fstab Mount** : echo "localhost:{volname} /mount/dir glusterfs defaults,_netdev 0 0

### 2. gtools2.0

#### Drive Mapping

You must first configure the drive aliases before doing anything else.

Using a custom udev rule built into the zfs packages, drives can be referenced using an alias that matches the labels silk screened on the grids.

By using the "by-path" names it can be guaranteed that a drive plugged into that drive bay will always be called by the same name

So users only need to know that they can reference the drive by either "/dev/disk/by-vdev/1-1" or in some situations (i.e zpool administration) by just the alias "1-1"


*  Use **dmap** to configure drive aliases.
{{:dmap_help.png|}}

*  If running **dmap** without any inputs it will prompt for controller and chassis size.Possible options are:
    * Controller:
      * R750,r750,r (HighPoint R750)
      * LSI,lsi,l (LSI 9201 -24i)
      * Adaptec,adaptec,a (Adaptec HBA-1000i, ASR-81605Z)
      * rr3740,rr (HighPoint RR3740)
    * Chassis Size:
      * 30,45,60

*  Unless the quiet flag is given, **dmap** will output the vdev_id.conf.

*  Run **lsdev** to verify that **dmap** finished correctly
{{:lsdev.png|}}

#### Storage Array Creation

Create a zpool on each node

When using zpool administration cli tools or gtools, drives can be referenced only by their alias (1-1)


*  Use **zcreate** to build storage pools
{{:zcreate_help.png|}}

*  Running zcreate with no input will automatically create a pool based on # of drives in the system, chassis size. It defaults to RAIDZ2.

*  To actually build a pool the **-b** flag must be given, otherwise it will just output the zpool create command.

*  If no VDEV count given with the **-v** option, **zcreate** will guess at ideal VDEV count based on the size of the chassis and the number of drives present.

*  It starts at the below values for each chassis, checks if the count of drives present is divisble by the VDEV count. If yes then done, if no then increment by one and check again.  
    * q30  = 3
    * s45  = 5
    * xl60 = 5

*  When using only a small number of disks, the above default values can cause issues. (if using a q30 with 8 drives it will try to build a 4VDEV raidz2 of 2 disks each, This is impossible and will throw an error).

*  To avoid this be sure to give a VDEV count when running **zcreate** in a system with a small amount of disks.

*  **zcreate -c ** will launch the custom layout menu where the user can explicitly choose which disk to use in each VDEV
{{:zcreate_custom.png|}} 


*  To ensure that the volume will mount on reboot run the following command: 
    * "echo "zpool import -d /dev/disk/by-vdev {poolname}" >> /etc/rc.local
    * Where {poolname} is the name of the zpool created on the node. Unless otherwise specified when building the default name is "zpool"
    * Although this works, it is not the proper way to solve this problem. According to developers is highly advisable to create own systemd services or udev rules to run scripts during boot instead of using this file. **Need to update**

    * **UPDATE DEC15/16** 
    * To get a zpool to properly auto-import on reboot the following services must be started
     * **systemctl enable zfs-import-cache.service** - This will import the pool on reboot
     * **systemctl enable zfs-mount.service** - This will mount all pool & children data-sets
 
#### Gluster Volume Creation

gcreate can be run from any of the nodes in trusted pool.

{{:gcreate.png|}}


*  required input:
    * **-b Brick count** Any number for a dist, and must be even for a dist rep volume.
    * **-n NodeName** Each peer that is **not** the node you are running this script on.
      * ex. a four node cluster {node1,node2,node3,node4}, with node1 as the working node would use ** gcreate -n node2 -n node3 -n node4 **
    * **-v VolumeType** Type of gluster volume you want to create
      * Distributed Replica "Linked"list" = **linkedlist**
      * Distributed Replica "Traditional" = **distrep**
      * Distributed                       = **dist**



