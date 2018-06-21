As per suman regarding Streamvision ticket. Problem with high IO and lots of files.

perf tuning recommendations: (1) add actimeo=60 (experiment with even higher value) mount option on clients. (2) increase MTU on server and clients, to a max of 9000.

TL;DR

Thanks for confirming the mount options from the clients. It confirms the tuning recommended(async, larger rsize and wsize) back in october, which is good.

I looked at 3 potential bottlenecks in the write pipeline, broadly speaking. TCP -> NFS -> Disk-IO

`netstat -t` on the server shows clients writing as expected. If there was a bottleneck at the TCP layer, I'd expect the *Recv-Q

* to have consistent high values. But the queue is being emptied really fast as expected. The kernel is able to drop packets to the application layer optimally. So the TCP layer is not the bottleneck.

`iostat` shows that the CPUs are idling 86% of the time. I do see an iowait of 5-10% which is attributable to the RAID5/6 write performance overhead. So at this time I would not qualify the Disk-IO layer to be creating significant congestion.

This leaves us with investigating NFS. The obvious redflag to me is the large percentage of getattr calls. 31% of all nfs calls are getattr and if we tune to reduce them, you should see a performance boost. Currently, the defaults are in effect which refresh file-attr cache every 3 seconds and dir-attr cache every 30 seconds. I am speculating that for your workload, file and dir attributes don't change that often, if at all. So go ahead and add actimeo=60 and see how much that will reduce the % of get/set-attr calls in nfsstat. You can even try setting it higher, but at some point you'll reach diminishing results.

Increase MTU size on server and perhaps on the clients as well depending on your router settings. Try increasing them up to 8K in 2K increments to see how much that helps. You can set it to 9000, which is the theoretical optimal value and usually recommended by RHEL folks.

Hope this will be sufficient tuning. I also encourage reading perf tuning guides from RHEL and NFS docs.
