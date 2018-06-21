
Overall guide using qemu: https://davidyat.es/2016/09/08/gpu-passthrough/#part-1-setting-up-passthrough

### CLIENT SIDE

How to connect client to VM with GPU: https://www.mail-archive.com/users@ovirt.org/msg40422.html



### SERVER SIDE


*  Append the following to GRUB_CMDLINE_LINUX in /etc/default/grub:

	
	  $ vim /etc/default/grub
	  ...
	  GRUB_CMDLINE_LINUX="... intel_iommu=on pci-stub.ids=$VIDEO-ID,$AUDIO-ID rdblacklist=nouveau"
	  ...


*  Refresh grub with " grub2-mkconfig -o /boot/grub2/grub.cfg"

*  reboot

Where $VIDEO_ID & $AUDIO_ID are the 8 digit ID below **[XXXX:XXXX]**

	
	  $ lspci -nn
	  ...
	  01:00.0 VGA compatible controller [0300]: NVIDIA Corporation GM107GL [Quadro K2200] [10de:13ba] (rev a2)
	  01:00.1 Audio device [0403]: NVIDIA Corporation Device [10de:0fbc] (rev a1)
	  ...



Verify with:

	
	  $ lspci -nnk
	  ...
	  01:00.0 VGA compatible controller [0300]: NVIDIA Corporation GM107GL [Quadro K2200] [10de:13ba] (rev a2)
	          Subsystem: NVIDIA Corporation Device [10de:1097]
	          Kernel driver in use: pci-stub
	  01:00.1 Audio device [0403]: NVIDIA Corporation Device [10de:0fbc] (rev a1)
	          Subsystem: NVIDIA Corporation Device [10de:1097]
	          Kernel driver in use: pci-stub 
	  ...


### ENGINE/HOST SIDE

Use the ovirt-engine webUI to attach GPU to host VM

It seems like you cant remote into a win7 VM with a GPU attached.

See this: https://www.reddit.com/r/VFIO/comments/5074ur/gpu_passthrough_cannot_install_nvidia_driver_in/

Using virsh to edit VM manually

*  https://serverfault.com/questions/507151/virsh-cant-connect-to-ovirt-hypervisor

*  https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_Linux/7/html/Virtualization_Deployment_and_Administration_Guide/sect-Managing_guest_virtual_machines_with_virsh-Editing_a_guest_virtual_machines_configuration_file.html


Dont use virsh to alter vm XML files if using ovirt. You have to create a [vdsm hook](45_drives_r_d_-_ovirt)





