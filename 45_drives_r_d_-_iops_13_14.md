# 45 Drives R&D - IOps 13 14

//
//
## IOps Info

#### What are IOps

An I/O operation is simply some kind of work the disk subsystem has to do at the request of a host and/or some internal process.\\  
IOps (Input/Output Operations Per Second) is an performance measurement used to benchmark various methods of computer storage (HDD, SSD, SAN). (1.)\\

#### Why an IOP number alone is meaningless?

Given only an IOps rating, there is inadequate information to justify device performance.  It's like saying that vehicles top speed is 200... 200 what? Kilometers per hour? Miles per hour? Meters per second?  Unless your're given specifics on how that unit was achieved, it's meaningless. 

IOps differ greatly between machines, system configurations, and processes being performed.  Most manufacture claims are rubbish, and do not accurately describe the performance of the product.  Therefore IOPS calculations should never be accepted unless accompanied other important elements, such as throughput, Block Size latency figures.  (2.)
\\
#### Latency IOPS and Throughput (Bandwidth)

Latency is a measure of how long it takes for a single I/O request to happen from the application’s viewpoint. High latency may just about
the least desirable trait in data storage systems, in databases especially. Reducing latency will
universally improve performance, making latency the first criteria to look at when examining storage
performance.
\\
\\
Throughput is the number of such actions executed or results produced per unit of time. This is
measured in bits per second (bit/s), kilobits per second (kbit/s), megabits per second (Mbit/s) and
gigabits per second (Gbit/s). The term "memory bandwidth" is sometimes used to specify the
throughput of memory systems. Throughput is usually calculated by dividing the file size by the
transfer time; in megabits, kilobits, or bits per second. 1 Byte = 8 bits (1.)
\\
#### Performance Characteristics & Latency inducers

Generally, sequential access usually deal in large data transfer sizes while random access deal in
small sizes. (2.)\\
\\
{{:sequential_random_access.png|}}\\
\\

For HDDs & similar devices, random IOPS usually dependent on drive seek time, while SSDs
mostly dependent on internal controller and memory interface speeds. HDD are not best suited for
random reads it takes time to move the read/write head of a disk into position, thus increasing latency.
Sequential IOPS numbers indicate the maximum sustained bandwidth that the storage device can
handle. In a SSD, a controller is responsible for a finite number of chips. (1.) Some SSDs have
multiple controllers, some have only one. Either way, a controller can only pull data off of the device so
fast. As requests queue up, latency can be introduced. The PCI-Express bus can even become lagged.
The PCI-E bus is shared among I/O controllers, network controllers, and other expansion cards. If a
few of these devices are active at once, it can very well induce latency.
\\
### Calculating IOps

IOps calculations can vary depending on the workload being delt. In general, there are three performance categories related to IOps, random
performance, sequential performance, and a combination of the two. 
 | Average IOps: Divide 1 by the sum of the average latency in ms and the average seek time in ms (1 / (average latency in ms + average seek time in ms)|\\
 | --------------------------------------------------------------------------------------------------------------------------------------------------------
Depending on the type of raid there can be a penalty on IOps performance. With the exception
of RAID 0, Other RAID configurations have multiple writes to the array, reducing IOps.  Calculating can become tricky, so it's best to use software such as IOmeter, IOzone or an online IOps calculator tool.\\
http://www.iometer.org/\\
http://www.iozone.org/\\
http://www.wmarow.com/strcalc/\\

**CURRENTLY ONLY IOMETER v2006.07.27 WORKS WITH CENTOS 6.5**\\
**IOMETER v1.1.0 WORKS WITH CENTOS 7, WAITING ON HIGHPOINT 750 DRIVERS**\\
\\
### How to create a raid array

[http://www.45drives.com/wiki/index.php/Configurations](http://www.45drives.com/wiki/index.php/Configurations)\\
#### mdadm commands

[http://www.linuxmanpages.com/man8/mdadm.8.php#lbAL](http://www.linuxmanpages.com/man8/mdadm.8.php#lbAL)\\
#### Raid array creation

**Make sure drives are clean before starting raid array creation**\\
**This can be done through the CentOS disk utility**\\
\\
''mdadm --create --verbose /dev/md0 --level=0 --raid-devices=3 /dev/sda /dev/sdb /dev/sdc\\''
\\

**Level** indicates raid type\\
**/dev/sd_** indicates which drive\\
#### File system

''mkfs.xfs -L Data /dev/md0\\''
#### Monitor raid creation

''cat /proc/mdstat/''

### Disabling firewalls on Centos 6.5

How Do I Disable Firewall?\\
\\
First login as the root user.\\
\\
Next enter the following three commands to disable firewall.\\
''# service iptables save\\
# service iptables stop\\

# chkconfig iptables off\\''
\\
If you are using IPv6 firewall, enter:\\
''# service ip6tables save\\
# service ip6tables stop\\

# chkconfig ip6tables off\\''
\\
### How to install Dynamo (IOmeter)

[http://greg.porter.name/wiki/HowTo:iometer](http://greg.porter.name/wiki/HowTo:iometer)
{{:how_to_install_dynamo.png|900}}\\

**Ask Darrell about hostname change if IOmeter crashes**

### How to run dynamo

{{:run_dynamo.png|}}
\\

### IOmeter user manual

[http://csis.pace.edu/~lombardi/sciences/computer/systems/windows/docs/iometer.pdf](http://csis.pace.edu/~lombardi/sciences/computer/systems/windows/docs/iometer.pdf)

#### Sources

1: Lowe, Scott (2010-02-12). "Calculate IOPS in a storage array". techrepublic.com. Retrieved
2011-07-03.\\
2. Smith, Kent (2009-08-11). "Benchmarking SSDs: The Devil is in the Preconditioning Details".
SandForce.com. Retrieved 2012-08-28.\\
3. Jeremiah Peschka (September 11, 2013)
http://www.brentozar.com/archive/2013/09/iops-are-a-scam/
\\
\\

## Test Units specifications

25 June 2014\\
Tested Equipment:


 | Test Machine 1||                                                                                           
 | ----------------                                                                                           
 | Chassis: 		|4.0 Storinator|                                                                                
 | Website:		|http://www.45drives.com/|                                                                       
 | Motherboard:           |Supermicro X9SCM-F|                                                                
 | Website:		|http://www.supermicro.com/products/motherboard/Xeon/C202_C204/X9SCM-F.cfm|                      
 | Processor:		|Intel Core i3-3240 Processor (3M Cache, 3.40 Ghz)|                                            
 | Website:               |http://ark.intel.com/products/65690/Intel-Core-i3-3240-Processor-3M-Cache-3_40-Ghz|
 | Sata Cards:		|2 x (rocket 750's (Only one is use))|                                                        
 | Website:		|http://www.highpoint-tech.com/USA_new/series_r750-specifications.htm|                           
 | Ram: 			|2 x (4GB DDR3 PC3-12800 1600MHz)|                                                                 
 | Boot Drive:		|WD Blue 500GB WD5000LPVX|                                                                    
 | Website:		|http://www.wdc.com/global/products/specs/?driveID=1261&language=1|                              
 | Drives Tested:		|Toshiba 1TB DT01ACA100|                                                                   
 | Website:		|http://storage.toshiba.eu/cms/en/hdd/computing/product_detail.jsp?productid=447|                
 | Software:		|IOmeter 2006.07.27 (New version not compatible with centos 6)|                                 
 | Website:		|http://www.iometer.org/doc/downloads.html|                                                      
 | Test machine OS:	|Centos 6.5(final)|                                                                       
 | Website:		|http://www.centos.org/|                                                                         
 | Host machine OS:	|Windows 7 SP1|                                                                           
\\
 | Test Machine 2||                                                                                           
 | ----------------                                                                                           
 | Chassis: 		|3.0 TeraStore|                                                                                 
 | Website:		|http://www.45drives.com/|                                                                       
 | Motherboard:           |Supermicro X9SCM-F|                                                                
 | Website:		|http://www.supermicro.com/products/motherboard/Xeon/C202_C204/X9SCM-F.cfm|                      
 | Processor:		|Intel Core i3-3240 Processor (3M Cache, 3.40 Ghz)|                                            
 | Website:               |http://ark.intel.com/products/65690/Intel-Core-i3-3240-Processor-3M-Cache-3_40-Ghz|
 | Sata Cards:		|http://www.sybausa.com/productInfo.php?iid=530|                                              
 | Ram: 			|2 x (4GB DDR3 PC3-12800 1600MHz)|                                                                 
 | Boot Drive:		|WD Blue 320GB WD5000LPVX|                                                                    
 | Drives Tested:		|Toshiba 1TB DT01ACA100|                                                                   
 | Website:		|http://storage.toshiba.eu/cms/en/hdd/computing/product_detail.jsp?productid=447|                
 | Software:		|IOmeter 2006.07.27 (New version not compatible with centos 6)|                                 
 | Website:		|http://www.iometer.org/doc/downloads.html|                                                      
 | Test machine OS:	|Centos 6.5(final)|                                                                       
 | Website:		|http://www.centos.org/|                                                                         
 | Host machine OS:	|Windows 7 SP1|                                                                           

## Results (old driver redundant)

27 June 2014\\
For single drive.\\
{{:single_drive_read.png|}}\\
{{:single_drive_write.png|}}\\
{{:system_performance_evaluation_in_progress_.pdf|}}



Current Iometer version does not support file system testing




## Results Driver v1.0.11 4k sequential&random reads&writes

{{:iops_4k_v1.0.11_.png|}}\\

**Using IOmeter 2006.07.27**
\\
{{:iops_mbs_v1.0.11_.png|}}\\

**Using Cent0S disk utility**


