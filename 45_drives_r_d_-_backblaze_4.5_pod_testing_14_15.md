# Backblaze 4.5 POD Testing

## Hardware Components

The Backblaze 4.5 POD has the following major hardware components:\\

**Motherboard:**\\
Supermicro MBD-X9SCL-F (MicroATX)\\

**RAM:**\\
2x 2GB DDR3 RAM\\
240P PC3-10600 CL9 18C 256X8 DD - \\
Total RAM: 4GB\\

**HBA /SATA3 Card:**\\
3x 4-PORT PCIe Express (Marvell 9235 chipset) - A-5404PORTSATN-RAID\\

**CPU:**\\
Intel Core i3 processor i3-2120\\

**Power Supply:**\\
760 Watt Power Supply\\
Zippy PSM-5760V Power Supply\\

**Backplane:**\\
Port Multiplier Backplanes\\
5 Port Backplane (Marvell 9715 Chipset) - Sunrich S330\\

**Boot Drive:**\\
Sandisk 128 GB SSD\\

**OS:**\\
CentOS 7 MATE\\


## Initial Testing

Upon initial boot a 45 drive 1TB RAID 6 was synced inside the machine. This took about 14 hours to complete. There were no issues.\\
The machine was left running idle for 24 hours with the RAID 6 fully synced. - No issues\\
Next, 9 5-drive 1TB RAID6 were synced inside the machine. - This was done to simulate a large amount of communication between the SATA 3 cards and the Port Multiplier Backplanes - again there was no issues wth this.\\

## Benchmarking

The Backblaze POD 4.5 was bench-marked against the 45Drives Storinator s45lite, s45 and s45 w/ LSI Cards, detailed results can be found in this living document: 

[[smb://proto/public/45Drives/Research%20&%20Development/Throughput%20&%20IO%20Experiments/Backblaze%20POD%204.5%20Comparison]

As a summary, the Storinator is over 2 times as fast as the Backblaze POD 4.5 shown in the images below:\\

#### Parameters


NOTE: The following benchmarks were performed using the following parameters:\\

Disks: 45x Seagate Constellation ES.3 – ST1000NM0033 1TB Enterprise Drive\\

RAID Type:  RAID0 (Stripe)\\

RAID Size: 45 TB\\

Benchmark Interface: CentOS Benchmark Utility\\

Sample Size: 100MB\\

Number of Samples: 1000\\

Number of Samples for Access Time: 10000\\




{{:allbenchmarks.png?1500}}
