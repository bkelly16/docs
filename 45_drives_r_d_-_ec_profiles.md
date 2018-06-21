# EC Profiles

#### Create EC Profile

    ceph osd erasure-code-profile set $PROFILE_NAME \
    plugin=$PLUGIN \
    k=$k m=$m \
    ruleset-failure-domain=$BUCKET_TYPE \

Where:


*  $PROFILE_NAME = User specified profile name

*  $PLUGIN = Use either **isa** or **jerasure**. ISA only works with intel processors, jerasure works with everything

*  $k $m = K is the # of data chunks, M is the # of parity chunks. **A RAID6 equivalent would be k=4,m=2**. For more detail on choice see here: [Erasure Coding](45_drives_r_d_-_erasure_coding)

*  $BUCKET_TYPE = Specify where you want object chunks stored. Default is host, meaning no chunk of data will ever live on the same host. You can also use "osd" but beware, you run the risk of a single point of failure. Full list of bucket types can be found here [Ceph Bucket Types](http://docs.ceph.com/docs/mimic/rados/operations/crush-map/#crush-structure)

### RAID6 Equivalent Example

Wants:

   * RAID 6 equivalent ( **k=4, m=2** )
   * Disk level failure domain ( **ruleset-failure-domain=osd** )
   * Intel Processors ( **plugin=isa** ) 

Therefore the command to create the desired profile is :
    ceph osd erasure-code-profile set RAID6 plugin=isa k=4 m=2 crush-failure-domain=osd crush-device-class=hdd

Verify with:
    ceph osd erasure-code-profile get RAID6

    crush-device-class=hdd
    crush-failure-domain=osd
    crush-root=default
    k=4
    m=2
    plugin=isa
    technique=reed_sol_van

#### Create Pool With new Rule

Create a EC pool using the new rule created:

    ceph osd pool create RAID6 1024 1024 erasure RAID6

Note the proper #number of PG is a function of replication level, #OSD and percentage of total data on cluster.

See this page for more details on choosing the right value: [PG Sizing](45_drives_r_d_-_placement_groups)

#### Verify Data Layout

Create a text file, move it onto the cluster, map out which OSD the chunks live on to verify data layout.


*  Create an object in the EC pool created

    echo "world" > hello.txt
    rados -p RAID6 put object1 hello.txt
    rados -p RAID6 ls


*  Map object with crush

    ceph osd map RAID6 object1
    
    osdmap e169 pool 'RAID6' (20) object 'object1' -> pg 20.bac5debc (20.3c) -> up ([3,11,0,2,9,5], p3) acting ([3,11,0,2,9,5], p3)


*  You can see the object is split into **6** chunks where 4 of them are data and two are parity. You can also see the OSDs that hold each chunk.
    
    Run "ceph osd tree" to see where each OSD is located in which chassis. 

    ID CLASS WEIGHT  TYPE NAME         STATUS REWEIGHT PRI-AFF 
 1. 1       0.58429 root default                              
 2. 3       0.19476     host cephosd1                           
    0   hdd 0.04869         osd.0         up  1.00000 1.00000 
    3   hdd 0.04869         osd.3         up  1.00000 1.00000 
    6   hdd 0.04869         osd.6         up  1.00000 1.00000 
    9   hdd 0.04869         osd.9         up  1.00000 1.00000 
 3. 5       0.19476     host cephosd2                         
    1   hdd 0.04869         osd.1         up  1.00000 1.00000 
    4   hdd 0.04869         osd.4         up  1.00000 1.00000 
    7   hdd 0.04869         osd.7         up  1.00000 1.00000 
    11   hdd 0.04869         osd.11        up  1.00000 1.00000 
 4. 7       0.19476     host cephosd3                         
    2   hdd 0.04869         osd.2         up  1.00000 1.00000 
    5   hdd 0.04869         osd.5         up  1.00000 1.00000 
    8   hdd 0.04869         osd.8         up  1.00000 1.00000 
    10   hdd 0.04869         osd.10        up  1.00000 1.00000 





    


