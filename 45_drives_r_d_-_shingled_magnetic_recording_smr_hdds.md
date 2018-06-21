# R&D Shingled Magnetic Recording (SMR) HDDs



*  Principles of SMR Operation [http://www.pdl.cmu.edu/PDL-FTP/Storage/CMU-PDL-11-107.pdf](http://www.pdl.cmu.edu/PDL-FTP/Storage/CMU-PDL-11-107.pdf)


*  SMR drives in summary use a data-destructive write process. This is similar to writing to a SSD- writing to a free area of space on the disk is fine, but as the disk starts to get full, the controller will have to find an open spot, delete the data off of that spot, then write the new piece of data into it, then take the data it had to delete and write it elsewhere. So over time essentially scaling performance just for capacity.


*  SMR drives may not belong in a 45Drive machine as there is already room for a large amount storage. Using lower performance SMR HDDs just to pack more room in a unit seems unnecessary. These drives will be good for very large static files and not so much for small random writes
    

*  This article points out a big issue with SMR [http://www.zdnet.com/competition-heats-up-smr-drives-7000024222/](http://www.zdnet.com/competition-heats-up-smr-drives-7000024222/) "SMR drives are very sensitive to vibration - only 2 can run concurrently in a 30 drive shelf - which is probably why there's no marketing aimed at consumer or enterprise prospects", it then references this paper [http://opencompute.org/assets/download/Open-Compute-Project-Cold-Storage-Specification-v0.5.pdf](http://opencompute.org/assets/download/Open-Compute-Project-Cold-Storage-Specification-v0.5.pdf) However i have not found any other docs backing up this vibration claim yet 



*  Whitepaper discussing **SMR drives and RAID configs** [http://www-users.cselabs.umn.edu/classes/Fall-2013/csci8980-adv/slides/Reports/Group%202.pdf](http://www-users.cselabs.umn.edu/classes/Fall-2013/csci8980-adv/slides/Reports/Group%202.pdf)
       * Interesting notes:
              - The title calls them SWD(shingled Writing devices) but by their definition a SWD is a HDD that employs SMR technology(tl;dr SEMANTICS)
              - With a wider write head and the same read device as current HDD larger areal densities can be obtained. however *"this wider write head also incurs some write limitation: write data to a track will destroy data previously written on the subsequent tracks, which is the so-called write interference. **This forces SWD to be a largely sequential write device, but it remains an unrestricted random access device when dealing with read operations**"*



