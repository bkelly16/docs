# 45 Drives - Video Analytics

Upcoming trend in video surveillance is not just mass recording to a storage server, but to have another server appliance analyse the data real time or afterwards.

In a traditional setup, to accomplish the goal of having 
    - IP cameras recording video
    - Storing a massive storage network
    - Analysing data real time, or afterwards

Could require up to three expensive hardware appliances;
 1.  NVR server
 2.  Actual data storage server
 3.  Analytic server

It is possible with high compute (single or dual CPU with high core #) to pack this all into one box. Either using software designed to run in linux or by using a hypervisor to manage multiple VMs

This would reduce costs incredibly.

The hardware would require lots of system resources (CPU and RAM), massive storage capabilities with support ofr both SSD and HDD in same chassis. 
I.e our current models with a SSD bank.

We would have to partner with a 3rd SW provider but we could offer a 3 in 1 (video capture, storage, and analytic) surveillance server.

Using technology like ovirt(KVM + UI) we could start with a single box and scale incredibly with gluster.

See this article discussing how this is done currently https://www.securityindustry.org/Pages/Technology/State-Video-Analytics.aspx

The Section titled Hybrid Analytics would be the most like the idea described here, however rather than separate servers for each layer (analytics, VMS, and Recording servers) it would just the Storinator with beefy components.



This could benefit a number of markets rather than just pure security recording. Anyone who requires large amounts of video recorded stored and analysed. 
For example

*  Manufacturing Quality Assurance

*  Machine Learning

*  Astronomy 

*  .... etc

See this article discussing how this is done currently and further detail into the relavant markets
https://www.securityindustry.org/Pages/Technology/State-Video-Analytics.aspx

Note the diagrams showing the massive racks set up with multiple servers. Our idea would reduce # of servers required, which would greatly reduce cost, maintenance and power bills.

POSSIBLE SOFTWARE:

*  intuVision SDK (open source vid analytics) - http://www.intuvisiontech.com/products/sdk.php

