# Tested Desktop Environments:


## CentOS 7 XFCE 3.10


*  Very Minimal install.

*  Came without some necessary packages and applications. (Disk Utility, Graphical Terminal, System Monitor)

*  Does not look at all like previous versions of CentOS .

*  However this environment appears stable and does not overload the graphics capabilities on our standard machine.

## CentOS 7 MATE 3.10 Kernel


*  Has All features of CentOS 6.6 

*  Looks very similar to previous versions of CentOS.

*  This environment appears stable and does not overload the graphics capabilities on our standard machine.

*  A bare metal dd data test was performed to a 45 drive RAID0:
      * 100 GB was transferred 10 times with block of 1KB 
      * Seeing a consistent write speed of 600+ MB/s.
      * During the transfer the cpu monitor was observed and found that the cpu usage was balanced better than that of CentOS 6.6
      * Documentation on results can be found Here: [CentOS 7 Final Development](//proto/public/45Drives/Research & Development/Miscellaneous)

## CentOS 7 MATE 3.18 Kernel


*  The same bare metal data test was completed on the newer kernel and write speeds constant at 700+ MB/s

*  It seems that the newer the linux kernel manages the cpu better during the data transfer.

*  To compare our current configuration of CentOS 6.6 ; 2.6 kernel, the same data test will yield about 450 MB/s to the 45 Drive RAID 0. 

# Installing CentOS 7 MATE


As operating systems become more mature most are opting for prettier GUIs. However storage servers are not typically suited for graphic heavy loads and when paired with these newer OS' CPU performance can be wasted powering the GUI. The common solution is use a dedicated graphics card, however this may not be an ideal solution for the Storinator as it consume a needed PCI-e slot. Therefore it would be ideal to compromise and install a lightweight GUI. That way you get the less demanding GUI freeing up the CPU for more important calculations but still get a appealing Desktop Environment.

The CentOS 7 default GUI is very graphic heavy,and therefore is too much of a load on the CPU and negatively affects IO performance.

To avoid this you should install the MATE desktop environment. Note that there are other lightweight GUIs you can choose such as XFCE, however we chose MATE due its simplicity to install and the feel felt the most similar to the default CentOS 7 GUI.

The following steps will walk through the installation of the MATE desktop environment on CentOS 7.



##### Installation & Configuration

Note: This guide assumes you have a CentOS 7 minimal installation (NO GUI) with the development tools installed. If the Development Tools are not installed  they can be by simply running ''yum groupinstall "Development Tools"'' in a terminal as root user.

[700px](File/MATE.png)
DO A YUM UPDATE\\
# First install the EPEL-repositories then install the X Window System\\

#::[root@45Drives ~]$ yum install epel-release\\
#::[root@45Drives ~]$ yum groupinstall "X Window system"\\

# Install the MATE packages. This will take a few minutes\\
#::[root@45Drives ~]$ yum groupinstall "MATE Desktop"\\

# Tell your system to start the Graphical Interface\\
#::[root@45Drives ~]$ systemctl isolate graphical.target\\

# To have MATE boot up as the default desktop enviroment, enter the following command (the last two lines will spit out into the terminal when you run the first line).\\
#::[root@45Drives ~]$ systemctl set-default graphical.target\\

#::rm '/etc/systemd/system/default.target'\\
#::ln -s '/usr/lib/systemd/system/graphical.target' '/etc/systemd/system/default.target'\\

# You will most likely want the Gnome Disk Utility as it the easiest way to interface with your disks. This is as simple as a single\\ command. Once installed it can be found in: Applications -> Accessories -> Disks\\
#::[root@45Drives ~]$ yum install gnome-disk-utility\\










