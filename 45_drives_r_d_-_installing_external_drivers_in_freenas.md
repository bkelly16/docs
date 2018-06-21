# Installing External Drivers in FreeNAS

Drivers external to the official FreeNAS release can be installed by compiling on the equivalent version of FreeBSD and copying to FreeNAS system, edit to conf files required to make install persist.

Requirements:

*  physical/virtual machine running FreeBSD. 

*  FreeBSD source tree must be installed. be sure to select "src" during BSD install.

*  if [ $FreeNAS_kernel_version != $FreeBSD_kernel_version ]; then \ echo YOU'RE FUCKED \ fi

Below steps use the ixl driver for 40gbe Intel NIC.

How to compile driver in fresh FreeBSD11.1

    root@LABBSD:~ # ping google.ca  <----- Verify internet connection
    root@LABBSD:~ # portsnap fetch update
    root@LABBSD:~ # cd /usr/ports/ftp/wget/
    root@LABBSD:/usr/ports/ftp/wget # make install clean
    root@LABBSD:~ # wget 'DRIVER SOURCE CODE'
    root@LABBSD:~ # tar -zxvf ixl_9.5.0.tar.gz
    root@LABBSD:~ # cd ixl-x.x.x/src
    root@LABBSD:~/ixl-x.x.x/src # make

    the 'if_ixl.ko" file will be created in the /src folder. Copy over to the FreeNAS server    
    root@LABBSD:~/ixl-x.x.x/src # scp if_ixl.ko root@FREENAS:~/


How to install compiled module in FreeNAS11.1

    root@LABNAS:~ # cp if_ixl.ko /boot/kernel/if_ixl.ko
    root@LABNAS:~ # echo 'if_ixl_load=\"YES\"' >> /boot/loader.conf
    root@LABNAS:~ # grub-mkconfig > /boot/grub/grub.cfg
    root@LABNAS:~ # reboot
    
    Verify you are running 1.9.5
    root@LABNAS:~ # dmesg | grep ixl
