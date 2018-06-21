- Preforming Standard Performance Measurements

 1.  Single drive performance (SDP) testing is run on the drive in test and 2 other simlairly known and tested drives. This way any inconsistencies can be noticed easier.
 2.  SDP testing runs the following four tests:

     * 100% Random Write     ; Block size=128kB ; QD=1
     * 100% Random Read      ; Block size=128kB ; QD=1
     * 100% Sequential Write ; Block size=64kB  ; QD=1
     * 100% Sequential Read  ; Block size=64kB  ; QD=1
 3.  If no issues are noted during the single drive test Move on to RAID testing. MultiDrive Performance (MDP)
     - Block Level Benchmark 

       * Partition drives; RAID0 mdadm
       * Run same fio tests as above
     - File-system Level Benchmark

       * ZFS RAIDZ1
       * IOzone Filesystem test
 4.  If both SDP & MDP are positive, then record results in HDD compatibility matrix and add drive to qualified HDD list.
