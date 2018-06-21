##### Packages Needed

   * Gluster version = 3.12
       * centos-release-gluster312
       * glusterfs-3.12, glusterfs-api-3.12, glusterfs-server-3.12, glusterfs-libs-3.12, glusterfs-client-xlators-3.12, glusterfs-fuse-3.12, glusterfs-cli-3.12, glusterfs-geo-replication-3.12, python2-gluster-3.12


*  NFS-Ganesha version = 2.5.5 
       * nfs-ganesha-2.5.5
       * nfs-ganesha-gluster-2.5.5


*  HAPROXY version = 1.5.18
       * haproxy-1.5.18


*  keepalived version = 1.3.5
       * keepalived-1.3.5

##### Steps

1. After you've already created your gluster volume, install all necessary packages listed above. You'll also need to make sure that nfs.disable is "on" on your gluster volume. 

2. Create the ganesha export file on all nodes. (NOTE: __hostname__ is to be the IP Address of the node that you're configuring)

/etc/ganesha/export.conf

	
	EXPORT{
	    Export_Id = 1 ;   # Export ID unique to each export
	    Path = "/tank";  # Path of the volume to be exported. Eg: "/test_volume"
	    FSAL {
	        name = GLUSTER;
	        hostname = "192.168.16.95";  # IP of one of the nodes in the trusted pool
	        volume = "tank";  # Volume name. Eg: "test_volume"
	    }
	    Access_type = RW;    # Access permissions
	    Squash = No_root_squash; # To enable/disable root squashing
	    Disable_ACL = TRUE;  # To enable/disable ACL
	    Pseudo = "/tank";  # NFSv4 pseudo path for this export. Eg: "/test_volume_pseudo"
	    Protocols = "3","4" ;    # NFS protocols supported
	    Transports = "UDP","TCP" ; # Transport protocols supported
	    SecType = "sys";     # Security flavors supported
	}


3. Edit the ganesha.conf file on all nodes to include your export.conf file (NOTE: __Bind_addr__ is the IP of the node you're configuring)

/etc/ganesha/ganesha.conf

	
	NFS_Core_Param  {
	        Bind_addr=192.168.16.95;
	        NFS_Port=2049;
	        MNT_Port=20048;
	        NLM_Port=38468;
	        Rquota_Port=4501;
	}
	%include "/etc/ganesha/export.conf"


4. We need to configure the haproxy.conf file on all nodes, each config file will be identical so you can just copy and paste. (NOTE: the __frontend nfs-in bind__ IP address is to be your Virtual IP to make this Highly Available)

/etc/haproxy/haproxy.conf

	
	#---------------------------------------------------------------------
	# Example configuration for a possible web application.  See the
	# full configuration options online.
	#
	#   http://haproxy.1wt.eu/download/1.4/doc/configuration.txt
	#
	#---------------------------------------------------------------------
	
	#---------------------------------------------------------------------
	# Global settings
	#---------------------------------------------------------------------
	global
	    # to have these messages end up in /var/log/haproxy.log you will
	    # need to:
	    #
	    # 1) configure syslog to accept network log events.  This is done
	    #    by adding the '-r' option to the SYSLOGD_OPTIONS in
	    #    /etc/sysconfig/syslog
	    #
	    # 2) configure local2 events to go to the /var/log/haproxy.log
	    #   file. A line like the following can be added to
	    #   /etc/sysconfig/syslog
	    #
	    #    local2.*                       /var/log/haproxy.log
	    #
	    log         127.0.0.1 local2
	    stats       socket /var/run/haproxy.sock mode 0600 level admin
	    #chroot      /var/lib/haproxy
	    #pidfile     /var/run/haproxy.pid
	    maxconn     4000
	    user        haproxy
	    group       haproxy
	    daemon
	    debug
	
	    # turn on stats unix socket
	    # stats socket /var/lib/haproxy/stats
	
	#---------------------------------------------------------------------
	# common defaults that all the 'listen' and 'backend' sections will
	# use if not designated in their block
	#---------------------------------------------------------------------
	defaults
	    mode                    tcp
	    log                     global
	    option                  dontlognull
	    option                  redispatch
	    retries                 3
	    timeout http-request    10s
	    timeout queue           1m
	    timeout connect         10s
	    timeout client          1m
	    timeout server          1m
	    timeout http-keep-alive 10s
	    timeout check           10s
	    maxconn                 3000
	
	#---------------------------------------------------------------------
	# main frontend which proxys to the backends
	#---------------------------------------------------------------------
	frontend nfs-in
	    bind 192.168.20.20:2049
	    mode tcp
	    option tcplog
	    default_backend nfs-back
	
	#---------------------------------------------------------------------
	# static backend for serving up images, stylesheets and such
	#---------------------------------------------------------------------
	backend nfs-back
	    mode tcp
	    balance     roundrobin
	    server      gluster11.45lab.com     gluster11.45lab.com:2049 check
	    server      gluster12.45lab.com     gluster12.45lab.com:2049 check
	
	#---------------------------------------------------------------------
	# round robin balancing between the various backends
	#---------------------------------------------------------------------


5. We need to configure the keepalived.conf file on all nodes. Choose one node as your master node, and the rest will be the backup nodes.

/etc/keepalived/keepalived.conf          - __MASTER NODE__

	
	vrrp_script chk_haproxy {
	  script "killall -0 haproxy"           # check the haproxy process
	  interval 2                            # every 2 seconds
	  weight 2                              # add 2 points if OK
	}
	
	vrrp_instance VI_1 {
	  interface eno1                        # interface to monitor
	  state MASTER                          # MASTER on haproxy1, BACKUP on haproxy2
	  virtual_router_id 51
	  priority 101                          # 101 on haproxy1, 100 on haproxy2
	  virtual_ipaddress {
	    192.168.20.20/16                        # virtual ip address
	  }
	  track_script {
	    chk_haproxy
	  }
	}


/etc/keepmealived/keepalived.conf        - ___SLAVE NODE___

	
	vrrp_script chk_haproxy {
	  script "killall -0 haproxy"           # check the haproxy process
	  interval 2                            # every 2 seconds
	  weight 2                              # add 2 points if OK
	}
	
	vrrp_instance VI_1 {
	  interface eno1                        # interface to monitor (could be bond0, eno1, etc)
	  state SLAVE                          # MASTER on haproxy1, BACKUP on haproxy2
	  virtual_router_id 51
	  priority 100                          # 101 on haproxy1, 100 on haproxy2
	  virtual_ipaddress {
	    192.168.20.20/16                        # virtual ip address
	  }
	  track_script {
	    chk_haproxy
	  }
	}


6. echo this string into the /etc/sysctl.conf file to allow haproxy to bind to VIP

    * echo "net.ipv4.ip_nonlocal_bind=1" >> /etc/sysctl.conf
    * sysctl -p

7. Start Services in the order below:

    * systemctl start keepalived
    * systemctl start haproxy
    * systemctl start nfs-ganesha

8. Check to see that your gluster volume is exporting

    * showmount -e

9. Check to see that the MASTER node has the VIP listed under its interfaces.

	
	[root@gluster11 ~]# ip a
	1: lo: `<LOOPBACK,UP,LOWER_UP>` mtu 65536 qdisc noqueue state UNKNOWN qlen 1
	    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
	    inet 127.0.0.1/8 scope host lo
	       valid_lft forever preferred_lft forever
	    inet6 ::1/128 scope host
	       valid_lft forever preferred_lft forever
	2: ens2f0: `<BROADCAST,MULTICAST>` mtu 1500 qdisc noop state DOWN qlen 1000
	    link/ether 00:0a:f7:c5:37:f0 brd ff:ff:ff:ff:ff:ff
	3: ens2f1d1: `<BROADCAST,MULTICAST>` mtu 1500 qdisc noop state DOWN qlen 1000
	    link/ether 00:0a:f7:c5:37:f1 brd ff:ff:ff:ff:ff:ff
	4: eno1: `<BROADCAST,MULTICAST,UP,LOWER_UP>` mtu 1500 qdisc mq state UP qlen 1000
	    link/ether 0c:c4:7a:d9:1d:8a brd ff:ff:ff:ff:ff:ff
	    inet 192.168.16.94/16 brd 192.168.255.255 scope global eno1
	       valid_lft forever preferred_lft forever
	    inet 192.168.20.20/16 scope global secondary eno1
	       valid_lft forever preferred_lft forever
	    inet6 fe80::ec4:7aff:fed9:1d8a/64 scope link
	       valid_lft forever preferred_lft forever

