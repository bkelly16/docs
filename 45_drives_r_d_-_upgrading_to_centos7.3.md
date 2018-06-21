# Upgrading to CentOS7.3

** EDIT 1/26/2018 **
This is obeslete. Fixed since CentOS7.4


When updating to 7.3 it sets the default boot kernel to the debugging mode. This will cause a mess of systemd messages to flood the terminal.
 1.  Microcode Service failing to start the following error can be seen in dmesg or the system terminal

    * ERROR: 
    
    [  250.646739] systemd[1]: microcode.service lacks both ExecStart= and ExecStop= setting. Refusing.
    [  250.648407] systemd[1]: Failed to load configuration for microcode.service: Invalid argument

    * Solution:

    In the file "/usr/lib/systemd/system/microcode.service" Replace the outer quotes with single apostrophes:
   -ExecStart=/usr/bin/bash -c "grep -l GenuineIntel /proc/cpuinfo | xargs grep -l "model.*79" > /dev/null || echo 1 > /sys/devices/system/cpu/microcode/reload"
   +ExecStart=/usr/bin/bash -c 'grep -l GenuineIntel /proc/cpuinfo | xargs grep -l "model.*79" > /dev/null || echo 1 > /sys/devices/system/cpu/microcode/reload'
 
 2.  Debug Kernel set by default

    * Solution:

    In the file "/etc/sysconfig/kernel", change  "MAKEDEBUG=yes" to "MAKEDEBUG=no"
    Regenerate grub:  grub2-mkconfig -o /boot/grub2/grub.cfg
    reboot

