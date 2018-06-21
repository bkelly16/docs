# 3rd Party Software Support

## Avid Media Composer

*  To have NAS drives show up in media composer Open the Avid Media Composer Console (Tools->Console) and type "alldrives". This will allow Avid to see NAS volumes.


## Final Cut Pro X

*  Using a NFS share allows the system to use the mounted network drive as a local device, which will allow it to work with FCPX. 

*  The default NFS mount settings in OSX do not include the necessary options for maximum throughput nor do they allow for the proper locking of files that FCPX requires. To enable your NFS mounts to use these settings you will need to add the following lines to the file "/etc/nfs.conf".
      * nfs.client.mount.options=nfssvers=3,tcp,async,locallocks,rw,rdirplus,rwsize=65536
      * nfs.client.allow_async=1



