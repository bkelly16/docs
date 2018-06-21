# Ovirt Open Virtualisation Platform 

### Installing OVirt

-https://www.ovirt.org/release/4.1.1/

-http://www.linuxtechi.com/install-configure-ovirt-4-0-on-centos7-rhel7/

TL;DR Don't enable all of EPEL on oVirt machines.

The ovirt-release package enables the epel repositories and includes several specific packages that are required from there. It also enables and uses the CentOS OpsTools SIG repos, for other packages.

EPEL currently includes collectd 5.7.1, and the collectd package there includes the write_http plugin.

OpsTools currently includes collectd 5.7.0, and the write_http plugin is packaged separately.

ovirt-release does not use collectd from epel, so if you only use it, you should be ok.

If you want to use other packages from EPEL, you should make sure to not include collectd. Either use includepkgs and add those you need, or use excludepkgs=collectd*.

## Disable Multipathing

- dm-multipath continues to run, but all devices are blackisted.
https://www.mail-archive.com/users@ovirt.org/msg26402.html

### VDSM Hooks

Ovirt which is really just a management UI layer for VDSM & KVM. 

*  VDSM is the management daemon, which oversees everything from VM admin tasks, host system resources (storage, mem and cpu) to stat keeper and log gatherer.

*  KVM is the virtualisation infrastructure vdsm works with. 

Since the user is one layer away from the vm(libvirt) config, customisation further than what the UI allows is unsupported.

The way around this is to use VDSM hooks, python scripts that run at predefined events. Complete list [ here](http://www.ovirt.org/develop/developer-guide/vdsm/hooks/ )

Most useful one is "//before_vd_start//"

	
	These are executed before vdsmd passes a VM start command to libvirt, and afterwards. 
	The flow is as follows: Engine is ordered to start a VM, it gathers the required parameters, 
	and passed a createVM command to vdsmd on a host vdsmd gathers the parameters provided by Engine, and then executes the before_vm_start hook. 
	At this point it is possible to alter the VM configuration on the fly, that will be discussed later on. 
	After the hook is done running, vdsmd will start the VM by passing the parameters down to libvirt. 
	Once the VM is started, vdsmd can execute an after_vm_start hook, usually a good place to finalise VM startup flows




