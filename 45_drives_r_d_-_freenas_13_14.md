# 45 Drives R&D - freenas 13 14


*  [http://doc.freenas.org/index.php/Useful_Command_Line_Utilities](http://doc.freenas.org/index.php/Useful_Command_Line_Utilities)

### Installation


*  Installing FreeNAS to hard drive takes about 5 minutes

*  After installation it is managed via web browser from remote machine ( some configuration can be done via cli on the system itself )

### RAID / Filesystem tests

##### UFS


*  Set up 2 x 10 drive striped arrays - took only a few minutes each to create ( 3TB Hitachi drives )

*  Transfer 4.5GB file between folders on same RAID volume == 300 MB/s

*  Transfer 4.5GB file (same file) between volumes == 512 MB/s

### Network tests

#####  UFS with Samba

 

*  Copy 4.5GB file 1 gig network 
     - 50 MB/s  ( Linux -> FreeNAS )
     - 50 MB/s  ( FreeNAS -> Linux )
     - 100 MB/s ( Windows -> FreeNAS )
     - 100 MB/s ( FreeNAS -> Windows )

### Back To:

[45drives_innovation_priorites ](45drives_innovation_priorites )\\
[45_drives](45_drives)

