# IOmeter

**The goal for each test is to investigate Maximum data throughput (MB/s) and Maximum IO's (IOps) of different hardware configurations for different applications.**

To get maximum throughput:

*  Use a large transfer request size (64KB+)

*  100% Read

*  100% Sequential

To get maximum IO's:

*  Use small transfer request size (512bytes)

*  100% Read

*  100% Sequential


**A typical database workload consists of both read and write operations typically using small files with complete Random access.\\

The test I use:**

*  2KB transfer Request Size

*  67% Read

*  33% Write

*  100% Random Access

**Currently developing a test to simulate a file transfer that a video editor would use.**

**All Tests performed must include:**

*  Max IO Test

*  Max Throughput Test(1 & 2)

*  Application specific tests
      * Database
      * Video
      * Backup Server

*  15 minute Test for each parameter

*  120 second Ramp-up








 
