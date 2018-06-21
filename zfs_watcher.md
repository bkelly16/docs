## ZFS Watcher

#### Installing necessary packages

- Use preconfig to install zfs packages

     wget images.45drives.com/gtools/preconfig
     chmod +x preconfig
     ./preconfig -zvf   (NOTE: you'll run this command, the server will reboot and then you'll run the same command again upon reboot)

- Once these are installed, install the zfs watcher package

     yum install http://images.45drives.com/tools/zfswatcher-0.4.5-1.x86_64.rpm


#### Configuring ZFS Watcher

- The configuration file is located at /etc/zfs/zfswatcher.conf

- In here is where you can set up email alerts, and configure the port which will control the web UI.

     vim /etc/zfs/zfswatcher.conf

- Below is a list of lines of the file with content that needs to be configured.

     Line 186 - enabling email alerts. --> change "enabled = false" to "enabled = true"
     Line 194 - attaching to customer's email server --> change "server = smtp.example.com:587" to the provided server name and port.
     Line 202 - setting up the from email --> change "from = zfswatcher@example.com" to a provided "from" email from the customer.
     Line 206 - setting up the to email --> change "to = root@example.com sysadm@example.com" to the provided emails from the customer.
     Line 223 - enabling webUI access --> change "enabled = false" to "enable = true" 
     Line 235 - changing port to access webUI --> default is set to port 80 - we suggest changing to a higher value like 8081.
     Line 286 - enable root user to access webUI --> change to "enabled = true" 
     Line 290 - change root password to access webUI --> default is "toor". See changing password section below.
     Line 292 - additional user to access webUI --> default is "wwwuser "otheruser"" change to "wwwuser "name""
     Line 293 - enable user access to webUI --> change to "enabled = true" 
     Line 294 - change user password to access webUI --> default is "hello", but is commented out. You'll need to delete the leading ; before the word "password". See changing password section below.

- Once you've saved and exited from the configuration file, you must start and enable the zfswatcher service.

    systemctl enable zfswatcher && systemctl start zfswatcher

#### Changing password

- To change either the root password or a user's password to access the webUI, you need to run the following command to encrypt the password. You will be prompted to enter you desired password. Below i'll use "password" as my example:

    [root@localhost ~]# zfswatcher -P
    Password (will echo): password
    Hash: $1$GjA3n1tB$MRy9SmLHfasBdJ.ng9jmf0

- You'll need to copy the output of the "Hash" line and paste it in Line 290 or 294 to change the password.

- Once done restart the zfswatcher service if it's already running.

     systemctl restart zfswacther

#### Accessing WebUI

- To access the WebUI, just point your browser to the Ip address of the server followed by :8081 (if that is the port you used) for example:

     192.168.16.94:8081

- You should be prompted to enter a username and password which is what was configured in the configuration file.


