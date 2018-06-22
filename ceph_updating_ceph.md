# Updating Ceph

See [here](http://docs.ceph.com/docs/mimic/releases/schedule/#understanding-the-release-cycle) for the detailed explanation of the Ceph release cycle

To summarize there are (2) types of a ceph cluster update. 

Both can be completed without cluster downtime, but release notes should be reviewed in both cases.

 1.  Minor Updates
 2.  Major Updates

**Major Updates** are released every 9 months, they are the most invasive of the update procedures. Editing of ansible group_vars required. It is reccomended to read the release notes and highlight any potential problem areas in your enviroment.

Ansible is required to complete an automated install. It updates each service one at a time, one node at a time

Services are updated in the following order:
 1.  Monitor services
 2.  OSD services
 3.  MDS services
 4.  RGW services

**Minor Updates** are minor bug fixes released every 4-6 months. These updates are quick and can be done safely with "yum update"
 
## Minor Updates

To apply minor ceph cluster updates run:

    yum update

If a new kernel is installed a reboot will be required to take affect. If there is no kernel update you can stop here !!

Set osd flasg noout and norebalance to prevent teh rest of teh cluster from trying to heal itself while the node reboots

    ceph osd set flag noout
    ceph osd set flag norebalance

Then reboot each node one at a time. Do not reboot the next node until the one before is back up and in the cluster.

    reboot

After each node is rebooted unset the flags set earlier and you are all done.

    ceph osd unset flag noout
    ceph osd unset flag norebalance  

## Major Updates

Major updates are applied with ansible.

To upgrade to the next major release edit the **//group_vars/all.yml//** in your ceph-ansible-45d directory.

In the **INSTALL** heading, find the line **ceph_stable_release**, replace the existing release with the next stable release.

    For example - Updating from Luminous (12.2.X) to Mimic (13.2.X)
    vim ~/ceph-ansible-45d/group_vars/all.yml
    > Change "ceph_stable_release: luminous"
    > To     "ceph_stable_release: mimic" 
    

Now run the "rolling-updates.yml" playbook

    cd ~/ceph-ansible-45d/
    ansible-playbook infrastructure-playbooks/rolling_update.yml

It will take some time but all data is up and accessable during update. For detailed infomration on what anisble is doing see this [blog](https///ceph.com/geen-categorie/ceph-rolling-upgrades-with-ansible/)

**NOTE** updating from Luminous to Mimic will require manual intervention to get the dashboard back up and running.

## Verify Update


Verify you are running the new version with the following command:

    ceph versions




