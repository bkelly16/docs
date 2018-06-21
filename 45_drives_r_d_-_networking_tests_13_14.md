# 10 Gigabit Ethernet


*  June 30, 2014

### Setup


*  2 Storinator pods connected via 10 GBE copper
    * X9SCM-F motherboards ( 2 pci-e 3.0 at 8x and 2 pci-e 2.0 running at 4x on 8x slots )
    * CentOS 6.5 ( All updates applied )
    * 2 Rocket 750 cards ( plugged into the pci-e 3.0 ports )

*  Netgear PROSAFE XS70BE switch 

*  Chelsio 10GBE network adapter in each system

*  FreeNAS server - 10 drive Stripe 0 - UFS

*  CentOS 6.5 client - 10 drive Stipe 0 - Ext4

### Speed (Samba/CIFS)


*  126 MB/s - 10g file from client to server

*  135 MB/s - 10g file from server to client


### Setup


*  2 Storinator pods connected via 10 GBE copper
    * X9SCM-F motherboards ( 2 pci-e 3.0 at 8x and 2 pci-e 2.0 running at 4x on 8x slots )
    * CentOS 6.5 ( All updates applied )
    * 2 Rocket 750 cards ( plugged into the pci-e 3.0 ports )

*  Netgear PROSAFE XS70BE switch 

*  Chelsio 10GBE network adapter in each system

*  FreeNAS server - 11 drive RAIDZ3 - ZFS

*  CentOS 6.5 client - SSD data drive

### Speed (Samba/CIFS)


*  130 MB/s - 10g file from client to server

*  135 MB/s - 10g file from server to client


### Speed (FTP)


*  Download from server to client:  450 - 500 MB/s  - 10GB file

*  Upload from client to server:  1 GB/s  - 10GB file

##### USING ZFS


*  Download from server to client: 525 MB/s - 100GB file

*  Upload from client to server: 656 MB/s - 100GB file

### Speed (NFS)

    Setup change - XFS on client ZFS on server ( 10 drive striped arrays )


*  Upload from client to server: 660 MB/s - 10GB file

*  Upload from client to server: 512 MB/s - 100GB file


*  Download from server to client 741 MB/s - 10GB file

*  Download from server to client 690 MB/s - 100GB file

### IPERF

{{:iperf.png|}}
