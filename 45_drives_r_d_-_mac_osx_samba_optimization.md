# Mac OSX Samba Optimization

[Explanation of why samba and finder are so slow](https///lists.samba.org/archive/samba/2014-September/184761.html)

The following performance tunes have been found and tested with OSX High Sierra. Previous versions should benefit as well but trial and error is recommended.

### SMB Signing

SMB Signing has been enabled by default by Apple dating back since the release of OS X 10.11.5

SMB Signing digitally signs at the packet level of the SMB communication. This enables the receiver of the packets to confirm the point of origination and it’s authenticity. This security mechanism helps avoid issues like tampering and “man in the middle” attacks. As long as you're on a secure network, this should not be an issue. In addition, this causes poor performance

To disable do this on each Mac OSX client:

   * **echo "[default]" >> /etc/nsmb.conf**
   * **echo "[default]" >> /etc/nsmb.conf**

Reboot client

To verify it worked run:

   * **smbutil statshares -a**
     * If "SIGNING_ON                    TRUE" is not present, then signing is disabled



### VFS FRUIT

Use the vfs fruit object to enhance OS X performance. [vfs_fruit man page](https///www.mankier.com/8/vfs_fruit)

fruit in combination with streams_xattr significantly enhances performance/compatiblity of samba network shares and OSX. This should be always used whenever the enviroment contains OSX clients. It is safe to use with a mixed enviroment of windows, and OSX clients.


*  Add to smb.conf [SHARE] definitions that will be used by osx clients:
    * **vfs objects = fruit streams_xattr**
    * **ea support = yes**

*  If using glusterfs, fruit is stackable just make sure glusterfs is last
    * **vfs objects = fruit streams_xattr glusterfs**
   
### Veto AppleDouble Files

Veto the creation of ._ and .DS_Store files on the network fileshare to increase directory performance.

**NOTE that certain OSX applications require these files to function correctly.** 
**Test workflow with these disabled to verify.**


*  Add to smb.conf [SHARE] definitions that will be used by osx clients
      * **veto files = /._*/.DS_Store/**
      * **delete veto files = yes**
*  Delete existing ._ and .DS_Store files on the share
      * **cd /FILE/SHARE ; find \( -name ".DS_Store" -or -name ".Trashes" -or -name "._*" -or -name ".TemporaryItems" \) -delete**

*  On each OSX client, disable the creation of .DS_Store and ._ on network shares 
      * **defaults write com.apple.desktopservices DSDontWriteNetworkStores true**
----

**Example smb.conf for a glusterfs volume. Bolded are options added for enhanced OS X compatibility**


>[fileshare]
>comment = For samba share of volume fileshare
>vfs objects = **fruit streams_xattr** glusterfs
>glusterfs:volume = fileshare
>glusterfs:logfile = /var/log/samba/glusterfs-fileshare.%M.log
>glusterfs:loglevel = 7
>path = /
>read only = no
>guest ok = yes
>kernel share modes = No
>valid users = @45D,root
>ea support = yes
>**veto files = /._*/.DS_Store/**
>**delete veto files = yes**


