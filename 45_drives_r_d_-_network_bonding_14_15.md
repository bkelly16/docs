# Network Bonding

## To Date Summary


*  Linux NIC Bonding works seamlessly from machine to machine.
    * All 7 modes were tested, and work, each presents a unique feature, explained below.
    * The only mode that allows bandwidth greater than 10 Gbit/s is mode 0 (balence-rr).
      * Highest recorded bandwidth in this mode is 13.7 Gbit/s.
      * This mode also provides fault tolerance; meaning that if a bonded cable gets unplugged in the middle of a file transfer, the transfer will complete at a network speed of 10Gbit/s.
    * All tests were completed with both Intel & Chelsio NIC Cards.
    * The bonded machines were identical, with the following major hardware components:
      * X9SRL-f Motherboard
      * Intel E5-2620 Processor
      * 32 GB ECC DDR3 RAM
      * SSD Boot Drive
      * Chelsio T420-BT Unified Wired Ethernet Controller
      * Intel X540-T2 Ethernet Converged Network Adapter


*  Linux Bonding through 10 Gigabit Netgear ProSafe XS708E Switch.
    * Linux Bonding modes will work with the switch.
    * The switch has a configuration Utility, however it is only available in Windows.
       * There is a LAG (link aggregation) parameter inside the utility where you can set LAG members but it does not seem to improve bandwidth at all. It appears that the utility does not recognize the linux bonding. 
    * Firmware Update and Switch Reset allows for bandwidth of 11.7 Gbit/s in round robin mode.
    * When you enable jumbo frames on mode 0 through the switch we see a bandwidth increase of 2 Gbit/s. Total of 13.7 Gbit/s. the same as bandwidth directly machine to machine.
    
   

## What is Network Bonding?

Network bonding is a method of combining two or more network interfaces together into a single interface. It will increase the network throughput, bandwidth and will give redundancy. If one interface is down or unplugged, the other one will keep the network traffic up and alive. Network bonding can be used in situations wherever you need redundancy, fault tolerance or load balancing networks.

Linux allows us to bond multiple network interfaces into single interface using a special kernel module named bonding. The Linux bonding driver provides a method for combining multiple network interfaces into a single logical “bonded” interface. The behavior of the bonded interfaces depends upon the mode; generally speaking, modes provide either hot standby or load balancing services.

## Types of Network Bonding

**mode=0 (balance-rr)**

Round-robin policy: It the default mode. It transmits packets in sequential order from the first available slave through the last. This mode provides load balancing and fault tolerance.

**mode=1 (active-backup)**

Active-backup policy: In this mode, only one slave in the bond is active. The other one will become active, only when the active slave fails. The bond’s MAC address is externally visible on only one port (network adapter) to avoid confusing the switch. This mode provides fault tolerance.

**mode=2 (balance-xor)**

XOR policy: Transmit based on [(source MAC address XOR’d with destination MAC address) modulo slave count]. This selects the same slave for each destination MAC address. This mode provides load balancing and fault tolerance.

**mode=3 (broadcast)**

Broadcast policy: transmits everything on all slave interfaces. This mode provides fault tolerance.

**mode=4 (802.3ad)**

IEEE 802.3ad Dynamic link aggregation. Creates aggregation groups that share the same speed and duplex settings. Utilizes all slaves in the active aggregator according to the 802.3ad specification.

Prerequisites:

- Ethtool support in the base drivers for retrieving the speed and duplex of each slave.
– A switch that supports IEEE 802.3ad Dynamic link aggregation. Most switches will require some type of configuration to enable 802.3ad mode.

**mode=5 (balance-tlb)**

Adaptive transmit load balancing: channel bonding that does not require any special switch support. The outgoing traffic is distributed according to the current load (computed relative to the speed) on each slave. Incoming traffic is received by the current slave. If the receiving slave fails, another slave takes over the MAC address of the failed receiving slave.

Prerequisite:

- Ethtool support in the base drivers for retrieving the speed of each slave.

**mode=6 (balance-alb)**

Adaptive load balancing: includes balance-tlb plus receive load balancing (rlb) for IPV4 traffic, and does not require any special switch support. The receive load balancing is achieved by ARP negotiation. The bonding driver intercepts the ARP Replies sent by the local system on their way out and overwrites the source hardware address with the unique hardware address of one of the slaves in the bond such that different peers use different hardware addresses for the server.

## Bonding in CentOS 7


*  Intel's Ethernet converged network adapter X540-T2 was placed in 2 identical machines (Storinator s45).

*  The NIC's were connected together via 2 cat7 network cables.

*  Both machines are running CentOS 7 MATE. 

*  In order to bond the network ports, the first thing needed is to create a bonding config file called: **ifcfg-bond0** in the network-scripts directory.

*  The following lines were added to the config file:\\

	
	DEVICE=bond0
	NAME=bond0
	BONDING_MASTER=yes
	IPADDR=192.168.3.3*
	PREFIX=24
	ONBOOT=yes
	BOOTPROTO=none
	BONDING_OPTS="mode=0 miimon=100"*
	

	  * The IP address can be changed to whatever you wish.
	  * The mode can be any number from 0 to 6 - the bonding modes are described above.
	
	Note: Different bonding modes require various configurations ie: drivers, switch support. The default mode is 0 (Round Robin) this is the mode in which you can reach speeds greater than 10Gbits/s.



*  Next, we need to modify the existing individual network connections in order to make them part of the bond (slaves). The image below shows the edited config file for one of the slaves.

 
{{:nicbonding4.png?1000}}



*  Once both network connections have been modified, you must restart the network.

	
	# systemctl restart network




*  To check to see if the bonding interface you just created is running we can type:

	
	# cat /proc/net/bonding/bond0



*  If everything was configured correctly, the output should look like this:

{{:nicbonding2.png?1000}}

### Testing the Bandwidth


*  Once the NIC's are successfully bonded, it must be verified that in fact we are utilizing it.

*  Iperf was used to determine this. - Iperf is a commonly used network testing tool that can create Transmission Control Protocol (TCP) and User Datagram Protocol (UDP) data streams and measure the throughput of a network that is carrying them.

*  The output looks like this:

{{:nicbonding1.png?1000}}

## Bonding with Netgear XS708E 10Gbe Switch












