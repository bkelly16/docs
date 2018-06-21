# This Page is Dedicated for Information Regarding Setup of Various Network Services ie: FTP, NFS, SMB

## FTP


*  FTP server package: vsftpd


*  FTP client package: ftp

 1.  An exception must be added to the firewall of the ftp server and clients or disable it.
 2.  SELinux should be turned off or set to permissive.
    

After the required packages have been installed, a few changes have to be made in the vsftpd config file in: /etc/vsftpd.

 1.  Uncomment anonymous_enable=NO - if it says yes change it to NO
 2.  Uncomment local_enable=YES - make sure this is changed to YES
 3.  Be sure that chroot_local_user=YES is commented out.


*  Save the changes to the config file.

*  Restart the vsftpd service.

*  Allow vsftpd to run on startup by typing: "chkconfig vsftpd on" in the terminal.\

*  To connect a client use ftp with login credentials.








