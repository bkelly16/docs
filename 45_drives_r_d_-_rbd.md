# RBD

### Feature Disable:

For CentOS7 3.10 kernel some features must be disabled on each image before you can map.

    rbd feature disable $IMAGE_NAME exclusive-lock object-map fast-diff deep-flatten -p $POOL


### LVM + RBD

By Default LVM will filter out rbd devices and not allow PV to be created using a rbd device. To fix add the types option to /etc/lvm/lvm.conf

    types = [ "rbd", 16 ]




