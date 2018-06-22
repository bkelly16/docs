##### Turn On ZFS ACL


*  set zfs aclinherit=passthrough

*  set zfs acltype=posixacl

##### Configure CTDB

/etc/sysconfig/ctdb

	
	#UNIVERSAL SETTINGS
	CTDB_RECOVERY_LOCK=/mnt/ctdb/.ctdb-lockfile
	CTDB_NODES=/etc/ctdb/nodes
	CTDB_PUBLIC_ADDRESSES=/etc/ctdb/public_addresses
	
	#SAMBA - AD
	CTDB_MANAGES_SAMBA=yes
	CTDB_MANAGES_WINBIND=yes
	CTDB_SAMBA_SKIP_SHARE_CHECK=yes
	
	#NFS
	CTDB_MANAGES_NFS=no
	
	#FAILOVER SETTINGS
	CTDB_SET_MonitorInterval=5
	CTDB_SET_TakeoverTimeout=5
	CTDB_SET_ElectionTimeout=2
	CTDB_SET_KeepaliveLimit=3
	CTDB_SET_KeepaliveInterval=1
	CTDB_SET_ControlTimeout=15


/etc/krb5.conf

	
	[libdefaults]
		default_realm =45LAB.COM
		dns_lookup_realm = false
		dns_lookup_kdc = true

	
Set AD as primary DNS of each node (use nmtui)

/etc/hosts for FDQN

	
	...	
	192.168.16.4    gluster1.45lab.com      gluster1
	192.168.16.5    gluster2.45lab.com      gluster2
	...



/etc/samba/smb.conf

	
	[global]
	        security = ADS
	        workgroup = 45LAB
	        realm = 45LAB.COM
	
	        template homedir = /home/%U
	        template shell = /bin/bash
	        winbind use default domain = yes
	        winbind enum users = yes
	        winbind enum groups = yes
	
	        map acl inherit = yes
	        store dos attributes = yes
	        #clustering = yes
	        # Winbind fails to start if clustering is specificed
	
	        idmap config * : backend = tdb
	        idmap config * : range = 1000000-1999999
	
	[Storage]
	        comment = SAMBA share for Public CLustered Storage
	        vfs objects = glusterfs
	        glusterfs:volume = tank
	        glusterfs:logfile = /var/log/samba/Storage.log
	        glusterfs:loglevel = 7
	        path = /storage
	        public = no
	        writable = yes
	        guest ok = no
	        valid users = @"domain users",administrator
	        kernel share modes = no
	[Lab]
	
	        comment = SAMBA share for Lab Clustered Storge
	        vfs objects = glusterfs
	        glusterfs:volume = tank
	        glusterfs:logfile = /var/log/samba/Lab.log
	        glusterfs:loglevel = 7
	        path = /lab
	        public = no
	        writable = yes
	        guest ok = no
	        valid users = @"lab",administrator
	        kernel share modes = no

		
Join DOMAIN

	
	net ads join -U administrator

	
/etc/nsswitch.conf 

	
	...
	passwd:     files winbind
	shadow:     files sss
	group:      files winbind
	...

	
Start CTDB
	systemctl start ctdb
	watch ctdb status until OK
	
Test AD connection

	
	wbinfo --ping-dc ## ping AD
		
	wbinfo -g ##list AD groups
			
	getext groups ##List AD groups in system


Mount volume via FUSE, set ownership/persmissions. Umount when done.

	
	mount -t glusterfs //localhost:$VOLUME /mnt/$VOLUME
	chown root:"domain users" /mnt/$VOLUME ## change ownership accordingly
	chmod -R 775 /mnt/$VOLUME ## change permission accordingly
	umount /mnt/$VOLUME

	
Now able to login from any computer on the DOMAIN


