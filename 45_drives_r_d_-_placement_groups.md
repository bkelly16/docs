# Placement Groups

### PG Sizing

Sizing PG very important. You can always increase pg size later but never decrease.

Keep in mind increasing # of PGs will cause all data to begin a migration. this will put a strain on your cluster performance until it is complete.

It is best to follow:

 1. Size correctly off the bat with pg_calculator.https://ceph.com/pgcalc/
 2. If unsure what to choose for the correct # of PG, start with 64 PG per pool. And increase the PG count at a later date. Ideally before you put data on the pool

Off hand rule of thumb is as follows:

    Less than 5 OSDs set pg_num to 128
    Between 5 and 10 OSDs set pg_num to 512
    Between 10 and 50 OSDs set pg_num to 1024
    If you have more than 50 OSDs, you need to understand the tradeoffs and how to calculate the pg_num value by yourself
    For calculating pg_num value by yourself please take help of pgcalc tool

If using multiple device classes (ssd,hdd,nvme), treat each device class as if it was a separate cluster when it comes to PG calcs. i.e if the pool is going to live on the ssd device class the # of OSDs would eqaul only the number of ssds in the cluster and the percentage of data would be 100%


