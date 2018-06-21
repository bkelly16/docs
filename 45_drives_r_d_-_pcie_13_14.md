27 June 2014\\
\\
# 45 Drives R&D - PCIe 13 14

27 June 2014\\
## Summarization of peak Rocket 750 performance

\\
MB/s = mega bytes per second\\							
Mb/s=mega bits per second\\							
GB/s=giga bytes per second\\							
Gb/s=giga bits per second\\							
1 Megabyte = 0.0078125 Gigabits 0.00781\\						
\\							
 | PCI Express 2.0 8x||\\    
 | ----------------------    
 | 500	^ MB/s Per Lane        | \\
 | 8	^ Lanes                  | \\
 | 4000	^ MB/s Max Throughput | \\
\\						
 | Rocket 750||\\                      
 | --------------                      
 | 6	^ Gb/s Sata 3                      | \\
 | 8	^ 8bits= 8Bytes                    | \\
 | 0.75	^ GB/s Sata 3                   | \\
 | 1024	^ 1GB= 1024MB                   | \\
 | 768	^ MB/s Per Port                  | \\
 | 10	^ 10 Ports                        | \\
 | 4	^ 4 Drives Per port                | \\
 | 192	^ MB/s Per Drive Max Theoretical | \\
\\						
 | Rocket 750 Max Theoretical Throughput per drive in a PCI Express 2.0 8x slot||\\
 | --------------------------------------------------------------------------------
 | 4000.00^MBytes/s Max Throughput                                                  | \\
 | 45.00	^# of Drives                                                               | \\
 | 88.89	^Per drive                                                                 | \\
 | 2.00	^2 Rocket 750s                                                              | \\
 | 177.78	^MBytes/s Per Drive Max Theoretical                                       | \\
\\
\\

## PCI express capabilities

MB/s = mega bytes per second\\							
Mb/s=mega bits per second\\							
GB/s=giga bytes per second\\							
Gb/s=giga bits per second\\							
1 Megabyte = 0.0078125 Gigabits 0.00781\\
\\							
 | MB/s Per Lane | 1    | 4    | 8     | 16                      | Lanes| \\
 | ------------- | -    | -    | -     | --                      | ---------
 | 250           | 250  | 1000 | 2000  | 4000 	^PCI Express 1.0  | \\       
 | 500           | 500  | 2000 | 4000  | 8000		^PCI Express 2.0  | \\       
 | 985           | 985  | 3940 | 7880  | 15760		^PCI Express 3.0 | \\       
 | 1969          | 1969 | 7876 | 15752 | 31504		^PCI Express 4.0 | \\       
\\			
 | MB/s Per Lane | Gb/s Per Lane | 1.00  | 4.00  | 8.00   | 16.00                    | Lanes| \\
 | ------------- | ------------- | ----  | ----  | ----   | -----                    | ---------
 | 250           | 1.95          | 1.95  | 7.81  | 15.63  | 31.25		^ PCI Express 1.0 | \\       
 | 500           | 3.91          | 3.91  | 15.63 | 31.25  | 62.50		^ PCI Express 2.0 | \\       
 | 985           | 7.70          | 7.70  | 30.78 | 61.56  | 123.13	^ PCI Express 3.0 | \\       
 | 1969          | 15.38         | 15.38 | 61.53 | 123.06 | 246.13	^ PCI Express 4.0 | \\       

