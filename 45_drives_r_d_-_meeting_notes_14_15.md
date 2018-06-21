# 45 Drives R&D - Meeting Notes 14_15

##  September 28, 2015

*  Attendees: Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Stephen McNeil, Christien Aucoin

*  Absent: Amy Keeping, Steve Lilley, Doug Milburn, Lloyd Brown

##### Marketing - Allison

*  KillDisk has gotten back to Steve re: the ask (most are doable) - need to schedule a follow-up call this week

*  Brett blog post about RockStor going live by end of day today, just need Doug's approval

*  Cam working on e-blast to announce Rockstor as an OS

*  Chris and Rob to work on a How-To video for Destroyinator customers

*  Linus - email reply, getting 250MB/s for both reads and writes (send another loaner pod?)

*  Next: Researching next best options for vertical markets (genomics and video production)

*  Web traffic for September so far: 8,541 (August total was 12,668)

#####  Sales - Steve

*  Week of Sept 21 - 25: $141,896 (week 1)

##### Supply Chain & Partners - Steve

*  Seagate:  (arranging a visit, they are very slow)

*  Western Digital/HGST- no update(have pricing on Hitachi as of friday, asking for permission to add to the page) no update

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. no update(followed up they are waiting ion us to specify our samples drives need to sit with brett)need it sit with Sandisk and select drives

*  have new X11 board need to test

##### Admin - Amy

*  FedEx - Received one quote back for packaging so far. I'm going to follow up with the other companies today to get comparables.
    * Accelerameters - Gavin to investigate acclerameters to test forces applied to boxes during shipping. 

##### Production - Amy and Mike

*  Inventory: 
    * Current $463,855K - Inventory levels are now measured as whats in the building, not after jobs have been allocated.
    * Rocket 750s: $219,600 (47.34%); LSI Cards: $11,900.85; Redundant PSU: $58,910; Standard PSU: $13,860
    * Motherboard count: 
       * Update on inventory: Qty 1 X9DRL, Qty 0 X9SRL
       * The X10 boards have arrived and we'll start shipping the X10SRL board this week.
       * We've asked Tong to release Qty 25 of the X9SCM board for the end of this month, October, November and Decemeber. We'll be carrying a high level of this board unless usage goes up.

*  Units Shipped
    * Week of Sept 21-25; 14 complete units were shipped (does not include reworks or component orders)
    * 1 other units were 100% complete but missed shipping deadline.

*  Production Hours
    * Estimated Assembly Time: (does not include rework, maintenance or inventory time)
       * Week of Sept 21-25 - 66.79 hrs 
       * Units not shipped but assembled - 4.5 hrs

#####  R&D - Brett

 1.  Rockstor - Suman has sent us the latest release with backup config. 

    * Current Bugs:
       * If there is any addon NICs in the system the MGMT IP will not be active until you run dhclient - REPORTED
 2.  Recovery Stick - 

    * Recovery/Cloning process documented on wiki -COMPLETE
    * Create recovery stick images - UNDERWAY Sept 28
    * Determine best way to host images to internet. Build our own FTP server? 
 3.  UNB Trip. -GAVIN AND BRETT visited last Thursday/fri 

    * Visted Ken & Aaron, rebuilt the enhanced storinator they had into Turbo
    * Ken had ideas for Engage grant - benchmarking different configurations. Aaron, his research assistant, will be doing most of this work over the next 6 months.  Ken to write the application.   
    * Ken would like to build a performance dashboard a as follow up project after Engage.  
 4.  Caringo - To do install this week

    * Initial install complete. Must use CentOS 6 for head server, R750 drivers do not work with the caringo software. LSI does
 5.  Video Production Use Case - Brett and Christien to meet with sales this week to determine what kind of questions Video customers ask them regularly 

##  September 21, 2015

*  Attendees: Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping, Steve Lilley, Doug Milburn, Stephen McNeil, Christien Aucoin

*  Absent: 

##### Marketing - Allison

*  KillDisk has gotten back to Steve re: the ask (most are doable) - need to schedule a follow-up call this week

*  Brett blog post about RockStor going live this week

*  Chris and Brett to work on a How-To video for Destroyinator customers

*  Next: Researching next best options for vertical markets (genomics and video production)

*  Web traffic for September so far: 5,890 (August total was 12,668)

#####  Sales - Steve

*  Week of Sept 6-19: $273,727 ($40 wk 1, $233 wk 2)

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

*  Hotness factor is now on each quote coming in - Starting to watch trends on the hotness level

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call. Another thunderbolt has been ordered for testing.(need update)

*  Seagate:  (arranging a visit, they are very slow)

*  Western Digital/HGST- no update(have pricing on Hitachi as of friday, asking for permission to add to the page)

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. no update(followed up they are waiting ion us to specify our samples drives need to sit with brett)

*  Found a Pegasuses fiber thunderbolt adapter.  hoping a customer purchases to test.

##### Admin - Amy

*  FedEx - we've gotten 1 report back from FedEx so far. They've failed our packaging and have reccomended 2 inch foam on all sides. We'll be looking into getting bigger boxes to accommodate this - may have to do custom box sizes.

##### Production - Amy and Mike

*  Inventory: 
    * Current $463,855K - Inventory levels are now measured as whats in the building, not after jobs have been allocated.
    * Rocket 750s: $219,600 (47.34%); LSI Cards: $11,900.85; Redundant PSU: $58,910; Standard PSU: $13,860
    * Motherboard count: 
       * Update on inventory: Qty 9 X9DRL, Qty 2 X9SRL
       * The X10 boards have arrived and we'll start switching over this week and next
       * We've asked Tong to release Qty 25 of the X9SCM board for the end of this month, October, November and Decemeber. We'll be carrying a high level of this board unless usage goes up.

*  Units Shipped
    * Week of Sept 7-18; 21 complete units were shipped (does not include reworks or component orders)
    * 4 other units were 75% complete and are waiting on components to arrive (should be here today or tomorrow).

*  Production Hours
    * Estimated Assembly Time: (does not include rework, maintenance or inventory time)
       * Week of Sept 7-18 - 126.64 hrs 
    * Paid hours: Week of Sept 7-18 - Should have this numbers this morning.

#####  R&D - Brett

 1.  Rockstor - Suman has sent us the latest release with backup config. 

    * Current Bugs:
       * If there is any addon NICs in the system the MGMT IP will not be active until you run dhclient - REPORTED
 2.  Creating Custom CentOS Install with our drivers (ISO) - Works, Images to be created, and process docu'd

    * We could provide our clonezilla files, and instruct the customer to live boot clonezilla to make their boot disks.
    * We create a recovery image that can boot from usb.
    * This allows (1) OS recovery & (2) Personal customer backup if anything goes wrong. 
 3.  Conference with Dr Kent discussed report. -GAVIN AND BRETT visting on Thursday/fri this week

    * Possibility for NSERC grant.
    * Available for contract. Were going to get our Turbo measured
      * His unit will need to be rebuilt to get the Turbo done, maybe a good excuse for Brett to head up to UNB to check out Dr. Kents setup.
 4.  Caringo - To do install this week

    * We are sending hardware to them so they can verify us as a vendor.
    * We have full access to their software & Docs and are scheduled to install our own cluster in the lab.
 5.  Video Production Use Case - No Update

    * Wrote benchmark script that gives reliable and repeatable numbers
      * This will be used for our benchmark tool from now one so to standardize numbers
      * Script utilizes Iozone and measures throughput based on user input: (1) number of threads to run through (2) record size (3) file size.
      * ATM only does sequential reads/writes, this is on purpose, as video production workload is typically large sequential files. Random r/w can be added pretty easily if needed in the future.
    * Local speeds on FreeNAS are great, not so much on Rockstor. (show graphs)
    * Network benchmarks. Using both a FreeNAS (44RAIDz2) and Rockstor (44 RAID6) system following benchmarks were run. (Powerpoint)
      * Host:FreeNAS Client:CentOS7 via nfs share. Results were poor
      * Host:FreeNAS Client:MacOSX via afp/tbt. Results were better but not great 

#####  IT

 1.  info@protocase.com and info@45drives.com go to the same people.  Need to figure out a way to direct these to only the people who need it.  

##  September 14, 2015

*  Attendees: Alan Hillier, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping

*  Absent: Gavin Andrews, Steve Lilley, Doug Milburn, Stephen McNeil

##### Marketing - Allison

*  Updates to Destroyinator hardware and software in the works

*  Destroyinator E-Scrap Follow-up E-Blast (131 emails): 57% open rate, 10.7% clicked to website, four replies to email 

*  Blog posts in the works: UNB Ken research (Brett) & New Lid (Steve)

*  Next: Determining 1-2 next new vertical markets

*  Web traffic for September so far: 3,777 (August total was 12,668)

#####  Sales - Steve

*  Week of Sept 7-11: $40,086

*  The Sales dashboard is in place for 45Drives - shows current quotes by hot level by sales manager.

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call. Another thunderbolt has been ordered for testing.

*  Switch provider - need to find supplier/partner.( no update yet cannot find a switch in a  good price range)

*  Seagate: Had a call with them yesterday. 

*  Western Digital/HGST- no update

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. no update   

##### Admin - Amy

*  Western Digital - Len had questions for Brett last week. No update other than that.

*  New lid - EVERYTHING IS THE NEW LID NOW!. 

*  FedEx has received our pods for packaging testing and design review - No update. 

##### Production - Amy and Mike

*  Inventory: 
    * Current $497,051K - Inventory levels are now measured as whats in the building, not after jobs have been allocated.
    * Rocket 750s: $225,600 (45.39%); LSI Cards: $11,900.85; Redundant PSU: $68,500; Standard PSU: $14,520
    * A new issue with inventory was discovered. The reorder trigger is now coming from the "on hand" column and needs to come from the "available" column. Spoke with Dan about this and it will be corrected. 
    *  Amy to check inventory to set a launch date. - When we do a design change. 
       * Update on inventory: Qty 14 X9DRL, Qty 14 X9SRL
       * The X9DRL and X9SRL have been marked as obsolete. Orders for the X10 of both models have been placed. We can do a soft launch as we run out of the X9's.
       * Tong is looking for qty releases pf the X9SCM for September, Oct, November

*  Units Shipped
    * Week of Sept 7-11; 7 complete units were shipped (does not include reworks or component orders)

#####  R&D - Brett

 1.  Thunderbolt - Ray J has updated his main editing station to OSX10.10 and thunderbolt performance has increased back to expected. CLOSED Sept 14  
 2.  LSU -      

    * Reviewed report. Ask him for testimonial on what he uses for it for. 
 3.  Rockstor - Suman has sent us the latest release with backup config. 

    * Current Bugs:
      * IPMI does not allow console sharing- THOUGHT occured, this may not be a bug, Rockstor may not install the proper ipmitools. Need to verify
      * If there is any addon NICs in the system the MGMT IP will not be active until you run dhclient - REPORTED
 4.  Creating Custom CentOS Install with our drivers (ISO) - Brett to start investigating

    * We could provide our clonezilla files, and instruct the customer to live boot clonezilla to make their boot disks.
    * This will work. We create a recovery image that can boot from usb.
    * This allows (1) OS recovery & (2) Personal customer backup if anything goes wrong. 
 5.  Conference with Dr Kent discussed report. -NO Update, Brett didn't talk to ken last week. TO BE DONE TODAY SEPT 14.

    * Possibility for NSERC grant.
    * Available for contract. Were going to get our Turbo measured
      * His unit will need to be rebuilt to get the Turbo done, maybe a good excuse for Brett to head up to UNB to check out Dr. Kents setup.
 6.  Caringo 

    * We are sending hardware to them so they can verify us as a vendor.
    * We have full access to their software & Docs and are scheduled to install our own cluster in the lab.
 7.  Video Production Use Case

    * Wrote benchmark script that gives reliable and repeatable numbers
      * This will be used for our benchmark tool from now one so to standardize numbers
      * Script utilizes Iozone and measures throughput based on user input: (1) number of threads to run through (2) record size (3) file size.
      * ATM only does sequential reads/writes, this is on purpose, as video production workload is typically large sequential files. Random r/w can be added pretty easily if needed in the future.
    * Local speeds on FreeNAS are great, not so much on Rockstor. (show graphs)
    * Network benchmarks. Using both a FreeNAS (44RAIDz2) and Rockstor (44 RAID6) system following benchmarks were run. (Powerpoint)
      * Host:FreeNAS Client:CentOS7 via nfs share. Results were poor
      * Host:FreeNAS Client:MacOSX via afp/tbt. Results were better but not great 

#####  IT

 1.  info@protocase.com and info@45drives.com go to the same people.  Need to figure out a way to direct these to only the people who need it.  


##  September 9, 2015

*  Attendees: Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping

*  Absent: Steve Lilley, Doug Milburn, Stephen McNeil

##### Marketing - Allison

*  Destroyinator update, post-Orlando

*  Follow up e-blast to E-Scrap connections

*  Blog: UNB Ken research

*  Next: Determining 1-2 next new vertical markets

*  Web traffic for September so far: 2,261 (August total was 12,668)

#####  Sales - Steve

*  Week of Aug 28 - Sept 2: $127,209

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

*  Hotness factor is now on each quote coming in - Starting to watch trends on the hotness level

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call. Another thunderbolt has been ordered for testing.

*  Switch provider - need to find supplier/partner.( no update yet cannot find a switch in a  good price range)

*  Seagate: Had a call with them yesterday. 

*  Western Digital/HGST- no update

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. no update   

##### Admin - Amy

*  Western Digital - Len had questions for Brett last week. No update other than that.

*  New lid - EVERYTHING IS THE NEW LID NOW!. 

*  FedEx has received our pods for packaging testing and design review - No update. 

##### Production - Amy and Mike

*  Inventory: 
    * Current $488,434K - Inventory levels are now measured as whats in the building, not after jobs have been allocated.
    * Rocket 750s: $227,400 (46.56%); LSI Cards: $14,647.20; Redundant PSU: $70,555; Standard PSU: $14,850
    * There is an issue with inventory when Princess was switched over. We noticed the problem late on Thursday and believe we know what happened. Dan and Adam have the issue fixed and Dan is going to confirm quantities today.
       * Inventory has been counted and confirmed. Princess is now accurate after the switch.
       * Quotes older than September 1 can not be promoted. This is to force the use of the new templates
    *  Amy to check inventory to set a launch date. - When we do a design change. 
       * Update on inventory: Qty 14 X9DRL, Qty 11 X9SRL
       * The X9DRL and X9SRL have been marked as obsolete. Orders for the X10 of both models have been placed. We can do a soft launch as we run out of the X9's.
       * Tong is looking for qty releases pf the X9SCM for September, Oct, November

*  Units Shipped
    * Week of Aug 28 - Sept 2; 17 complete units were shipped (does not include reworks or component orders)
    * 3 other units were 50% complete and should shipped on Tuesday morning.

*  Production Hours
    * Estimated Assembly Time: (does not include rework, maintenance or inventory time)
       * Week of Aug 24-Sept 4 - 147.59 hrs (for pods completed but not shipped)
    * Paid hours: Week of Aug 24-Sept 4: 122.85

#####  R&D - Brett

 1.  Thunderbolt - Ray J has updated his main editing station to OSX10.10 and thunderbolt performance has increased back to expected. CLOSED 

    * Ray J was seeing very poor read speeds but expected writes. Turns out problem was due to the version of OSX. The Macbook I tested it on was 10.10 while his main editing iMac is 10.9.
    * Does not want to update until he finishes his project, so he updated one of his macbook in the meantime and reported it successfully fixed the read issue.    
 2.  LSU -      

    * Reviewed report. Ask him for testimonial on what he uses for it for. 
 3.  Rockstor - Suman has sent us the latest release with backup config. 

    * NEXT: Add Images to burning server. (COMPLETE)
    * Add general how-to documentation to Wiki (i.e driver installation and basic FAQ. Point actual software issues to suman/forum) - Ongoing
      * Driver Install steps - COMPLETE
      * WebGUI Install steps - COMPLETE
      * No MGMT interface provided troubleshooting - COMPLETE
    * Current Bugs:
      * IPMI does not allow console sharing
      * If there is any addon NICs in the system the MGMT IP will not be active until you run dhclient
 4.  Creating Custom CentOS Install with our drivers (ISO) - Brett to start investigating

    * You can use a tool called kickstart to custom install packages/(maybe)drivers - NOT a simple process
    * Using dd to clone a drive should work for single boot drives but will not work with redundant booties
    * We could provide our clonezilla files, and instruct the customer to live boot clonezilla to make their boot disks. 
 5.  Conference with Dr Kent discussed report.

    * Possibility for NSERC grant.
    * Available for contract. Were going to get our Turbo measured
      * His unit will need to be rebuilt to get the Turbo done, maybe a good excuse for Brett to head up to UNB to check out Dr. Kents setup.
 6.  Video Production Use Case

    * Wrote benchmark script that gives reliable and repeatable numbers
      * This will be used for our benchmark tool from now one so to standardize numbers
      * Script utilizes Iozone and measures throughput based on user input: (1) number of threads to run through (2) record size (3) file size.
      * ATM only does sequential reads/writes, this is on purpose, as video production workload is typically large sequential files. Random r/w can be added pretty easily if needed in the future.
    * Local speeds on FreeNAS are great, not so much on Rockstor. (show graphs)
    * Network benchmarks. Using both a FreeNAS (44RAIDz2) and Rockstor (44 RAID6) system following benchmarks were run. (Powerpoint)
      * Host:FreeNAS Client:CentOS7 via nfs share. Results were poor
      * Host:FreeNAS Client:MacOSX via afp/tbt. Results were better but not great 

##  August 31, 2015

*  Attendees: Rob MacQueen, Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping, Steve Lilley, Doug Milburn

*  Absent: Stephen McNeil

##### Marketing - Allison

*  Destroyinator - Steve and Cam are in Orlando!

*  Blog: upcoming post on new lid (why we changed it, and how we designed it)

*  Next: Determining 1-2 next new vertical markets

*  Web traffic for August: 12,235 (July total was 14,886)

#####  Sales - Steve

*  Week of Aug 24-28: $75,899.57 

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

*  Hotness factor is now on each quote coming in. We need to start looking at a probability factor going forward. Conversion rates for a 1 should be high (approx 75%), while conversion rates for a 3 will be much lower (30-40%). 

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call. Another thunderbolt has been ordered for testing.

*  Switch provider - need to find supplier/partner.( no update yet cannot find a switch in a  good price range)

*  Seagate: Scheduling a visit in Sept, they want us to sell their drives.

*  Western Digital/HGST- no update

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. no update   

##### Admin - Amy

*  Western Digital - Pods are at WD for testing

*  New lid - XL60 still has old lid inventory. 
    * Qty 4 XL60
    * The Q30 with the new lid were processed on Friday (for shipping this week)

*  Quoting process - Gavin - started July 20th
     - Should be importing web quotes by August 24

*  FedEx has received our pods for packaging testing and design review. They are in the que and I spoke with Tammy Surwic at their design facility last week and they should be put through this week and we should have results in 4-6 business days.

##### Production - Amy and Mike

*  Inventory: 
    * Current $471,220K
    * Rocket 750s: $223,800 (47.49%); LSI Cards: $5,797.85; Redundant PSU: $62,335; Standard PSU: $13,530
    * There is an issue with inventory when Princess was switched over. We noticed the problem late on Thursday and believe we know what happened. Dan and Adam have the issue fixed and Dan is going to confirm quantities today.
    *  Amy to check inventory to set a launch date. - When we do a design change. 
       * Qty 8 X9DRL (10 on order), Qty 7 X9SRL
       * The X9DRL and X9SRL have been marked as obsolete. Orders for the X10 of both models have been placed. We can do a soft launch as we run out of the X9's.
       * Qty 40 X9SCM available with 115 on hold with ASI for us. July usage was over 40 but we're down in August. We should have enough boards until Oct/Nov based on current usage and hopefully the X11 will be released by then.

*  Units Shipped
    * Week of Aug 24-28; 6 complete units were shipped (does not include reworks or component orders)
    * 5 other units were sitting at shipping Friday afternoon but did not leave and 2 others were 75% complete and should ship at 11am this morning.

*  Production Hours
    * Estimated Assembly Time: (does not include rework, maintenance or inventory time)
       * Week of Aug 24-28 - 37.73 hrs, 37.425 hrs (for pods completed but not shipped)
    * Paid hours: Week of Aug 10-21: 160.98

#####  R&D - Brett

 1.  Western Digital Red Drives dropping out - 3 customers are now reporting drives dropping out.  Ongoing 

    * The issue turned out being a combo of the 6TB WD Red + R750. A certain number of these drives are spinning up slower than as expected and the R750 incorrectly fails the drives.
    * Determined that since it was fine in the LSI + MOBO that HiPoint only needed to extend there window before declaring a disk failed.
    * As of Aug 21. May has reported that can they recreate the problem and plan to have a beta driver to us by early next week.
    * Len of WD has provided a tool that changes the spin up rate of the drive, which seems to of fixed the issue as well. however come at the tradeoff of more power during start-up. 85% increase.
    * All customers have been notified of the process throughout, the only one really promptly responds is quite happy with resolution and plans on buying more pods.
    * Highpoint Driver has been verified to fix the issue. Customers now have and I am waiting to hear results. (ALMOST)CLOSED  
 2.  Thunderbolt - Ray J is happy with speeds once updated, once he updates his main editing station this can be CLOSED to R&D

    * Ray J was seeing very poor read speeds but expected writes. Turns out problem was due to the version of OSX. The Macbook I tested it on was 10.10 while his main editing iMac is 10.9.
    * Does not want to update until he finishes his project, so he updated one of his macbook in the meantime and reported it successfully fixed the read issue.    
 3.  LSU -      

    * Reviewed report. Ask him for testimonial on what he uses for it for. 
 4.  Rockstor - Suman has sent us the latest release with backup config. 

    * Config back up - CLOSED
    * Successfully set-up redundant boot drives - CLOSED
    * NEXT: Add Images to burning server.
    * Add general how-to documentation to Wiki (i.e driver installation and basic FAQ. Point actual software issues to suman/forum) - Ongoing.
 5.  Creating Custom CentOS Install with our drivers (ISO) - Brett to start investigating
 6.  Conference with Dr Kent discussed report.

    * Gave great material Brett to summarize for marketing/sales.
    * Possibility for NSERC grant.
    * Available for contract. Were going to get our Turbo measured    


##  August 24, 2015

*  Attendees:  Rob MacQueen, Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping, Stephen McNeil, Steve Lilley, Doug Milburn

*  Absent: 

##### Marketing - Allison

*  Data Destruction:
    * Destroyinator webpage and tweaked navigation are live!
    * SERI contacts now in Princess - ready for sales cold-calling
    * Tradeshow banner in
    * Next steps: getting spec sheet printed, and sending booth items to tradeshow location

*  Networking blog - Part 2: 3,580 pageviews so far

*  Video: Replacing failed redundant boot drives without turning off machine coming soon

*  Web traffic for August so far: 8,988 (July total was 14,886)

#####  Sales - Steve

*  Week of Aug 17-21: $109,282.54 (above moving average)

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

*  hotness factor to define sale funnel.

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call.  Need to order 2 more for engineering.

*  Switch provider - need to find supplier/partner.( no update yet cannot find a switch in a  good price range)

*  Seagate: Scheduling a visit in Sept, they want us to sell their drives.

*  Western Digital/HGST- Merger is happening now(SEPT) we do not know the consequences of the merger yet I have been assured we will benefit. 

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. Chantal is our contact Steve to try again, but their price too high.  Steve to try to get some enterprise class SSD's for Brett's tiering experiment.    

##### Admin - Amy

*  Western Digital - Pods are at WD for testing

*  New lid - XL60 still has old lid inventory. 
    * Qty 4 XL60
    * The Q30 with the new lid were processed on Friday (for shipping this week)

*  Quoting process - Gavin - started July 20th
     - Should be importing web quotes by August 24

##### Production - Amy and Mike

*  Inventory: 
    * Current $465,525K
    * Rocket 750s: $230,400 (49.49%); LSI Cards: $5,797.85; Redundant PSU: $71,925; Standard PSU: $14,520

*  Units Shipped
    * Week of Aug 17-24; 9 complete units were shipped (does not include reworks or component orders)

*  Production Hours
    * Estimated Assembly Time: (does not include rework, maintenance or inventory time)
       * Week of Aug 10-14: 134.47 hrs 
       * Week of Aug 17-21: 53.29
    * Paid hours: Week of July 27-Aug 7: 180.96. Will have paid hrs for Aug 8-22 this morning

#####  R&D - Brett

 1.  Western Digital Red Drives dropping out - 3 customers are now reporting drives dropping out.  Ongoing 

    * The issue turned out being a combo of the 6TB WD Red + R750. A certain number of these drives are spinning up slower than as expected and the R750 incorrectly fails the drives.
    * Determined that since it was fine in the LSI + MOBO that HiPoint only needed to extend there window before declaring a disk failed.
    * As of Aug 21. May has reported that can they recreate the problem and plan to have a beta driver to us by early next week.
    * Len of WD has provided a tool that changes the spin up rate of the drive, which seems to of fixed the issue as well. however come at the tradeoff of more power during start-up. 85% increase.
    * All customers have been notified of the process throughout, the only one really promptly responds is quite happy with resolution and plans on buying more pods.
    * Once new HiPoint driver is verified. This will be CLOSED.  
 2.  The Destroyer - Rob

    * **ENTRY DATE:** July 14 2015
    * **EXPECTED CLOSE DATE:** August 5 2015
    * Documented the wipe times for marketing purposes - Have 1, 3 and 6 TB drives done. NEXT: will investigate secure wipe in Linux, will contact Killdisc - Rob.
    * SSD and SAS wiping -  get SAS drives and test wiping SAS drives. - Arrived, untested
      * Expected Close Date: August 31, 2015
 3.  Motherboard Replacement Testing - (Rob) 

    * **ENTRY DATE:** EONS AGO
    * **UPDATE EXPECTED:** MONDAY August 5
    * SRL board - tech to add 1 standoff pem would fix aesthetics. ongoing Rob to follow up with Dean and Christa
    * NEXT: Amy to check inventory to set a launch date. - When we do a design change. 
       * Qty 8 X9DRL (10 on order), Qty 7 X9SRL
       * Updates for these boards can be ordered now. If we are going ahead ASAP then I will make the change in princess so none of the existing boards are ordered again
       * Qty 40 X9SCM available with 115 on hold with ASI for us. July usage was over 40 but we're down in August. We should have enough boards until Oct/Nov based on current usage and hopefully the X11 will be released by then.
 4.  Thunderbolt - Ray J is happy with speeds once updated, once he updates his main editing station this can be CLOSED to R&D

    * Ray J was seeing very poor read speeds but expected writes. Turns out problem was due to the version of OSX. The Macbook I tested it on was 10.10 while his main editing iMac is 10.9.
    * Does not want to update until he finishes his project, so he updated one of his macbook in the meantime and reported it successfully fixed the read issue.    
 5.  LSU - Steve spoke to Tim, all his machines are running.     

    * Steve got a report from Tim today, but haven't looked at it.  Will review and send to R&D. 
 6.  Rockstor - Suman has sent us the latest release with backup config. 

    * Config back up - CLOSED
    * Successfully set-up redundant boot drives
    * Re-adding failed however, not sure if error in procedure or we set up redundant boot drive incorrect. 
    * Add general how-to documentation to Wiki (i.e driver installation and basic FAQ. Point actual software issues to suman/forum)
 7.  Creating Custom CentOS Install with our drivers (ISO) - Brett to start investigating
 8.  IPMI Tool - Brett to send link to everyone 
 9.  New PSU - still not here, Make sure the PWM bus is included with this PSU. -Steve
 10.  
    

##  August 17, 2015

*  Attendees:  Rob MacQueen, Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping, Stephen McNeil

*  Absent: Steve Lilley, Doug Milburn

##### Marketing - Alison

*  Data Destruction:
    * Final touches on Destroyinator website + web navigation being completed this week
    * Have reached out to KillDisk twice - no response re: cross-marketing opportunities
    * SERI contacts for cold-calling being inputted by Wednesday
    * Tradeshow banner ordered
    * Next steps: signage for tradeshow booth, Destroyinator spec sheet, detailed pictures of Destroyinator pod

*  Networking blog - Part 2: Inputting changes from Doug, will publish tomorrow

*  Video: Replacing failed redundant boot drives without turning off machine

*  Web traffic for August so far: 6,498 (July total was 14,886)

#####  Sales - Steve

*  Week of Aug 10-14: $109,282.54 (above moving average)

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

*  hotness factor to define sale funnel.

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call.  Need to order 2 more for engineering.

*  Switch provider - need to find supplier/partner.( no update yet cannot find a switch in a  good price range)

*  Seagate: Scheduling a visit in Sept, they want us to sell their drives.

*  Western Digital/HGST- Merger is happening now(SEPT) we do not know the consequences of the merger yet I have been assured we will benefit. 

*  Sandisk will teach us on consumer/enterprise SSDs - Steve. Chantal is our contact Steve to try again, but their price too high.  Steve to try to get some enterprise class SSD's for Brett's tiering experiment.    

##### Admin - Amy

*  Western Digital - Pods are at WD for testing

*  New lid - XL60 still has old lid inventory. 
    * Qty 2 XL60
    * The Q30 with the new lid were processed on Friday (for shipping this week)

*  Quoting process - Gavin - started July 20th
     - Should be importing web quotes by August 24

##### Production - Amy and Mike

*  Inventory: 
    * Current $502,231K
    * Rocket 750s: $231,300 (50.40%); LSI Cards: $6,713.30; Redundant PSU: $76,035; Standard PSU: $14,520

*  Units Shipped
    * Week of Aug 10-18; 22 complete units were shipped (does not include reworks or component orders)

*  Production Hours
    * Estimated Assembly Time: Week of Aug 10-14: 126.69 hrs (does not include rework, maintenance or inventory time)
    * Paid hours: Week of July 13 - 24: 160.90. Will have paid hrs for July 27 - Aug 7 this morning

#####  R&D - Gavin

 1.  Western Digital Red Drives dropping out - 3 customers are now reporting drives dropping out.  Ongoing 

     * Quality issue with the drives possible
     * In contact with may at Highpoint and len at WD
     * Successfully recreated problem with customers HDD, currently investigating what happens with different cards and OS'. As it stands it appears to be faulty drive whenever used with an HBA card but works fine in MOBO or other PC.
 2.  The Destroyer - Rob

    * **ENTRY DATE:** July 14 2015
    * **EXPECTED CLOSE DATE:** August 5 2015
    * Document the wipe times for marketing purposes - Have 1 TB and 6 TB drives done. will investigate secure wipe in linux - Rob.
    * Will give certificate to steve and allison.
    * SSD and SAS wiping -  get SAS drives and test wiping SAS drives. - ordered.
 3.  Motherboard Replacement Testing - (Rob) 

    * **ENTRY DATE:** EONS AGO
    * **UPDATE EXPECTED:** MONDAY August 5
    * SRL board - tech to add 1 standoff pem would fix aesthetics. ongoing Rob
    * NEXT: Amy to check inventory to set a launch date. - When we do a design change.  
 4.  Thunderbolt - Steve to call Ray J, Ray J sent a video to Brett.

    * Spoke to RAYJ there is an issue with the thunderbolt. Saw a video and not transferring very fast. what can we do to fix this? (https://youtu.be/mCOjh0GKySs) 
    * Communicate with Ray J, going to go out and take a look at the problem. Initial suspicion is network set up and not a fault of the hardware, however will know more after visit - Brett
    * **UPDATE:** August 5 
 5.  LSU - Steve spoke to Tim, all his machines are running.  Writing report, but wants to do more testing before final.   

    * **REPORT EXPECTED:** August 7
    * Nothing yet from tim Working on it.
 6.  Rockstor - Suman has sent us the latest release with auto backup config. 

    * Sucessfully failed and replaced a boot drive. Communicated with Suman 
    * NEXT: set up auto backup just like FreeNAS.
    * Add documentation to Wiki
    * Need to investigate memory usage compared to freenas

##  August 10, 2015

*  Attendees:  Rob MacQueen, Alan Hillier, Gavin Andrews, Mike Hagen, Allison MacDonald, Brett Kelly, Amy Keeping

*  Absent: Steve Lilley, Doug Milburn, Stephen McNeil

##### Marketing - Alison

*  Data Destruction:
    * Final touches on Destroyinator website + web navigation being completed this week
    * Photos of Destroyinator pod today
    * Quoted our first unit!
    * Have reached out to KillDisk twice - no response re: cross-marketing opportunities
    * Next steps: SERI contacts for cold-calling, designing/ordering tradeshow items and promotional unit to PowerHouse Recycling

*  Networking blog - Part 2: Waiting for draft from Rob

*  Upcoming project: Getting postcard created to ship in each order that provides contact info for tech support etc

#####  Sales - Steve

*  Week of July 26 - Aug 8, 2015: $180,068.84

*  Territory - set.  The territories are ready to go - an entry has been made on the wiki outlining the territories for each.

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call.  Getting good pricing for large orders.  They want to talk to Brett and Rob about limitations.  Allison, make a thunderbolt page and start co-marketing.  Steve to get more sonnet devices.  One D.C. customer is asking a lot about thunderbolt.    

*  Rockstor service packages - how will Suman and team be able to reach out to 45 Drives customers? Will communicate with us. 
    * Limited incidents - term used for marketing only, not enforcing it. 
    * Steve is happy with it now.  

*  Switch provider - need to find supplier/partner.  

##### Admin - Amy

*  Western Digital - chassis are being built. sending them down for full chassis evaluation. 
    *COMPLETE - The pods are in the que for testing. 
    *XL60 shipped July 31
    *S45 shipped July 29
    *Q30 shipped July 31

*  New lid - XL60 and Q30 still have old lid inventory. 
    * Qty 6 XL60
    * Qty 2 Q30
    * Qty 1 S45
     - XL60s with new lid are in assembly, waiting to use old inventory before shipping

*  Quoting process - Gavin - started July 20th
     - Should be importing web quotes by July 31, 2015

##### Production - Amy and Mike

*  Inventory: 
    * Current $502,231K
    * Rocket 750s: $238,800 (47.55%); LSI Cards: $-1,220.60; Redundant PSU: $85,625; Standard PSU: $14,520
    * 12 LSI cards are in a custom job for Orions Systems - Target ship date is Aug 20th. LSI cards were ordered on Aug 5

*  Units Shipped
    * Week of July 27 - Aug 7; 16 complete units were shipped (does not include reworks or component orders)

*  Production Hours
    * Estimated Assembly Time: Week of July 27 - Aug 7: 93.74 hrs (does not include rework, maintenance or inventory time)
    * Paid hours: Week of July 13 - 24: 160.90. Will have paid hrs for July 27 - Aug 7 this morning

#####  R&D - Gavin

 1.  Western Digitial Red Drives dropping out - 3 customers are now reporting drives dropping out.  We now have 6 drives, but cannot replicate the problem.  All CentOS, highpoint, and Western Digital 6TB drives.  Brett contacted all custBomers.  Waiting to see if LSI cards fix the problem, then will contact Highpoint by the end of today.  Brett to check 4TB drive problem with customer.        
 2.  The Destroyer - Rob

    * **ENTRY DATE:** July 14 2015
    * **EXPECTED CLOSE DATE:** August 5 2015
    * Document the wipe times for marketing purposes - ROB 
    * SSD and SAS wiping -  get SAS drives and test wiping SAS drives.  
 3.  Drive mounting "Wedgie" (Brett)

    * **ENTRY DATE:** EONS AGO
    * **EXPECTED UPDATE:** JULY 27 2015
    * Install in unit, test with HDD, various rubbers. Send update to Alan at AGL.   
 4.  Tiering - Rockstor **LONG TERM RESEARCH**

    * NEXT: try tiering with BTRFS and CentOS - Brett No UPDATE 
    * Sandisk will teach us on consumer/enterprise SSDs - Steve. Chantal is our contact Steve to try again, but their price too high.  Steve to try to get some enterprise class SSD's for Brett's tiering experiment.   
 5.  20gig Project - (Rob)

    * Part 2 will gioven to marketing by end of day tomorrow 
 6.  Motherboard Replacement Testing - (Rob) 

    * **ENTRY DATE:** EONS AGO
    * **UPDATE EXPECTED:** MONDAY August 5
    * SRL board - tech to add 1 standoff pem would fix aesthetics. Rob
    * DRL board - READY TO SHIP
    * NEXT: Amy to check inventory to set a launch date.     
 7.  Thunderbolt - Steve to call Ray J, Ray J sent a video to Brett.

    * NEED TO CALL RAY J TODAY  
    * **UPDATE:** August 5 
 8.  LSU - Steve spoke to Tim, all his machines are running.  Writing report, but wants to do more testing before final.   

    * **REPORT EXPECTED:** August 7
 9.  Higher efficiency PSU - Rob

    * **ENTRY DATE:**July 20, 2015 
    * **UPDATE EXPECTED** August 5, 2015
    * $675 per Unit - William is willing to talk volume pricing (Steve). Ordered one in for testing.
    * NEXT: 6-7 weeks lead time. To test as soon it comes in.
    * **FINISH DATE:** September 30, 2015
 10.  Rockstor - Suman has sent us the latest release with auto backup config. 

    * Got it going and running.  Config backup is in the GUI, and saves in the Rockstor box.  Does not save appliance settings and cosmetic settings, but he will add that at a later date.  Rob still has some more testing for failing boot drive to do.  
    * NEXT: set up auto backup just like FreeNAS. Rob/Brett to communicate  

##  August 4, 2015

*  Attendees: Doug Milburn, Rob MacQueen, Alan Hillier, Gavin Andrews, Mike Hagen,  Darrell Cormier, Allison MacDonald, Stephen MacNeil, Brett Kelly

*  Absent: Steve Lilley, Amy Keeping

##### Marketing - Alison

*  Data Destruction (CentOS only)
    * Destroyinator webpage/navigation being worked on by Jason currently - Need Amy/Sales to confirm pricing and product specs
    * Test print of Destroyinator front panel - Complete and Approved by Doug
    * Signed up for E-Scrap conference
    * Next steps: SERI contacts for cold-calling, final website work, circling back with KillDisk and designing/ordering tradeshow items

*  Networking blog - Part 2: Waiting for draft from Rob

*  Front panel graphic design: Updated website Storinator order form to be more clear to customers re: the two choices they have (temporary solution - 1-2 months, make graphic standard/default)

*  E-blast went out last Thursday - 29% open rate (list avg. is 27%) and 5.8% CTR (list avg. is 7.8%)

*  Postcard to tech support in the box.

#####  Sales - Steve

*  Quoting Numbering Process - (Andrew)

*  Week of July 12 - 25: $215,006.23

*  Projected sales - Amy (with Steve/Allan)

*  Territory - set.  Will start on Monday, Aug 9.

*  Need to start putting notes on account page for Cutomer's usage requirements, industry.  

*  Need sale cycle information/graph, closure rates.

##### Supply Chain & Partners - Steve

*  Sonnet (Thunderbolt) Steve had conference call.  Getting good pricing for large orders.  They want to talk to Brett and Rob about limitations.  Allison, make a thunderbolt page and start co-marketing.  Steve to get more sonnet devices.  One D.C. customer is asking a lot about thunderbolt.    

*  Rockstor service packages - how will Suman and team be able to reach out to 45 Drives customers? Will communicate with us. 
    * Limited incidents - term used for marketing only, not enforcing it. 
    * Steve is happy with it now.  

*  Switch provider - need to find supplier/partner.  

##### Admin - Amy

*  Western Digital - chassis are being built. sending them down for full chassis evaluation. 
    * **EXPECTED FINISH DATE:** Aug 7, 2015

*  Need number on the amount of shipping damaged units so far - Amy/Steve
    * **EXPECTED FINISH DATE:** July 27, 2015

*  Need to file damage claims with Fedex - Tanya/Shirley - Complete by July 21st

*  30 Drive units - Extended front panel. Becoming standard (desktop panels) Replace template with extended faceplate - COMPLETE

*  New lid - XL60 and Q30 still have old lid inventory. 
     - XL60s with new lid are in assembly, waiting to use old inventory before shipping

*  Quoting process - Gavin - started July 20th
     - Should be importing web quotes by July 31, 2015

##### Production - Amy and Mike

*  Inventory: 
    * Current $444,441K 
    * Rocket 750s: $243,600 (54.81%); LSI Cards: $7,933.90; Redundant PSU: $9,590; Standard PSU: $14,520

*  Units Shipped
    * Week of July 13 - 24; 17 complete units were shipped, 2 retro fit kits (does not include reworks or component orders)

*  Production Hours
    * Estimated Assembly Time: Week of July 13 - 24: 100.91 hrs (does not include rework, maintenance or inventory time)
    * Paid hours: Week of July 13: paid time is received every other week. Week of June 28 - July 11: 95.38 hrs

#####  R&D - Gavin

 1.  Western Digitial Red Drives dropping out - 3 customers are now reporting drives dropping out.  We now have 6 drives, and Rob set them up and they are running fine.  All CentOS, highpoint, and Western Digital.  Brett to contact all parties, and customers.     
 2.  The Destroyer - Rob

    * **ENTRY DATE:** July 14 2015
    * **EXPECTED CLOSE DATE:** August 5 2015
    * Drive Wipe time - Depends on the largest capacity drive that is being wiped. Not the number of drives. For a 3x pass of 0's (a standard wiping mode) with 6TB drives it takes 20 hours to complete.
    * SSD and SAS wiping - will need LSI cards for SSD drives. Can put one LSI card to wipe the front row.  
      * NEXT: get SAS drives and test wiping SAS drives.  
 3.  Drive mounting "Wedgie" (Brett)

    * **ENTRY DATE:** EONS AGO
    * **EXPECTED UPDATE:** JULY 27 2015
    * In CNC queue.  Brett to check in with Christa about assembly.   
 4.  Tiering - Rockstor **LONG TERM RESEARCH**

    * NEXT: try tiering with BTRFS and CentOS - Brett ENTRY DATE: July 
    * Sandisk will teach us on consumer/enterprise SSDs - Steve. Chantal is our contact Steve to try again, but their price too high.  Steve to try to get some enterprise class SSD's for Brett's tiering experiment.   
 5.  20gig Project - (Rob)

    * Part 2 is delayed. Only Seeing 10Gigabit when writing to the server from clients with round-robin policy. Trying to find a way to increase this. Investigating another bonding mode with updelay , and managed switches. 
 6.  Motherboard Replacement Testing - (Rob) 

    * **ENTRY DATE:** EONS AGO
    * **UPDATE EXPECTED:** MONDAY August 5
    * SRL board - One of the screw holes doesn't line up however does not affect structure. - 1 standoff pem would fix aesthetics. Discuss With Tech. Rob
    * DRL board - working great, currently under test as a client in our 20gig experiment.
    * NEXT: Amy to check inventory to set a launch date.     
 7.  Thunderbolt - Steve to call Ray J, Ray J sent a video to Brett.  

    * **UPDATE:** August 5 
 8.  LSU - Steve spoke to Tim, all his machines are running.  Writing report, but wants to do more testing before final.   

    * **REPORT EXPECTED:** August 7
 9.  Higher efficiency PSU - Rob

    * **ENTRY DATE:**July 20, 2015 
    * **UPDATE EXPECTED** August 5, 2015
    * $675 per Unit - William is willing to talk volume pricing. Ordered one in for testing.
    * **FINISH DATE:** September 30, 2015
 10.  Rockstor - Suman has sent us the latest release with auto backup config. 

    * Got it going and running.  Config backup is in the GUI, and saves in the Rockstor box.  Does not save appliance settings and cosmetic settings, but he will add that at a later date.  Rob still has some more testing for failing boot drive to do.  
    * NEXT: Once he is out of beta, then we will be comfortable with selling this.  

##  July 27, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alan Hillier, Gavin Andrews, Amy Keeping, Brett Kelly, Mike Hagen,  Darrell Cormier, Allison MacDonald

*  Absent: Doug Milburn, Steve Lilley

##### Marketing - Alison

*  Data Destruction
    * Destroyinator webpage/navigation being worked on by Jason currently - Need Amy/Sales to confirm pricing and product specs
    * Test print of Destroyinator front panel in production - need ASAP (by Friday)
    * Signing up for E-scrap Conference this week

*  "This week in Enterprise Tech" - Brett completed video podcast on Friday. Great feedback from followers.

*  Networking blog - Part 2 is being written, Wednesday deadline

*  Front panel graphic design:
     - 10 Printed front panels have been ordered for inventory so they can be added to a job at anytime now.
     - Live on website (pics + updated order form) 
     - With Design/Without Design - internal paperwork (take offline)

*  E-blast going out this week to 45 Drives customers (Now Offering WD HDDs, Networking Blog Post, New Front Panel and Failed Redundant Boot Drives)

*  Video podcast - list to be featured on 

*  Wiki - List has been started of upcoming articles. Allison will finish by end of week

#####  Sales - Steve

*  Week of July 12 - 25: $215,006.23

*  Projected sales - Amy (with Steve/Allan)

*  Feedback on the new lid from customers who are receiving them.

*  Territory discussions underway - Shirley received a report from Matt, to determine the territories.. ETA August 1st

##### Supply Chain & Partners - Steve

*  Reach out to Sonnet (Thunderbolt) Steve to have a conference call.  This week. conference call thursday

*  Rockstor service packages need to be figured out - how will Suman and team be able to reach out to 45 Drives customers? ONGOING talk to Suman this week - Steve last question about limited incidents on basic package answer by friday.

*  Killdisc- arrange call by thursday

*  find new switch provider

##### Admin - Amy

*  Western Digital - chassis are being built. sending them down for full chassis evaluation. 
    * **EXPECTED FINISH DATE:** Aug 7, 2015

*  Need number on the amount of shipping damaged units so far - Amy/Steve
    * **EXPECTED FINISH DATE:** July 27, 2015

*  Need to file damage claims with Fedex - Tanya/Shirley - Complete by July 21st

*  30 Drive units - Extended front panel. Becoming standard (desktop panels) Replace template with extended faceplate - COMPLETE

*  New lid - XL60 and Q30 still have old lid inventory. 
     - XL60s with new lid are in assembly, waiting to use old inventory before shipping

*  Quoting process - Gavin - started July 20th
     - Should be importing web quotes by July 31, 2015

##### Production - Amy and Mike

*  Inventory: 
    * Current $444,441K 
    * Rocket 750s: $243,600 (54.81%); LSI Cards: $7,933.90; Redundant PSU: $9,590; Standard PSU: $14,520

*  Units Shipped
    * Week of July 13 - 24; 17 complete units were shipped, 2 retro fit kits (does not include reworks or component orders)

*  Production Hours
    * Estimated Assembly Time: Week of July 13 - 24: 100.91 hrs (does not include rework, maintenance or inventory time)
    * Paid hours: Week of July 13: paid time is received every other week. Week of June 28 - July 11: 95.38 hrs

#####  R&D - GavinHAPPY BIRTHDAY ROBERT

 1.  The Destroyer - Rob

    * **ENTRY DATE:** July 14 2015
    * **EXPECTED CLOSE DATE:** July 31 2015
    * Test Once Made, record time for full secure erase. 
 2.  Drive mounting "Wedgie" (Brett) - 

    * **ENTRY DATE:** EONS AGO
    * **EXPECTED UPDATE:** JULY 27 2015
    * Proto Parts are with tech, to follow up with Dean before 29th 
 3.  LCD on front panel - (Brett) - 

    * Mid September until we receive samples (10 of them, code and hardware). 10 weeks for full production once we approve samples (Mid Nov). TO DO ask for 15 screens for sample.
    * We will design the front plate before September 15th.  
    * **ENTRY DATE:** JULY 1, 2015
    * **EXPECTED FINISH DATE:** November 30, 2015
 4.  Tiering - Rockstor **LONG TERM RESEARCH**

    * NEXT: try tiering with BTRFS and CentOS - Brett ENTRY DATE: July 
    * UPDATE - Btier works with btrfs but performance is not great, this is due to the kernel version however. But at kernels where btrfs performance is on par with xfs, btier does not work yet. (4.1.2). This needs to be fixed by the author of btier, I have informed him(&the btier mailing list) of the error.
    * Sandisk will teach us on consumer/enterprise SSDs - Steve .. Chantal is our contact Steve to try again.
    * QuickTier - In house RAID/tier creator/destroyer + benchmarking. Useful tool for increased work efficiency  
 5.  20gig Project - (Rob)

    * Part 2 is on schedule. As of friday we successfully saturated a 20gbe (5 pod clients, 1 host) link by transferring large back ups of chris pod with a samba share. (500-600MB/s per client). Once we added the 6th it transferred at a reduced speed (350MB/s) and all other transfers decreased a little as well. 
 6.  Rockstor - (Darrell) - Rockstor Export Config

    * Spoke with Suman on Friday ( July 24 ) - No update as yet. Still working on the config. 
 7.  Motherboard Replacement Testing - (Rob) 

    * **ENTRY DATE:** EONS AGO
    * **UPDATE EXPECTED:** MONDAY August 4
    * SRL board was DOA, ordered new one, TBD send for RMA. One of the screw holes doesnt line up however does not affect structure.
    * DRL board is working great, currently under test as a client in our 20gig experiment   
 8.  Thunderbolt - Steve to call Ray J

    * **UPDATE:** August 4 
 9.  LSU 

    * **REPORT EXPECTED:** August 4th
 10.  Higher efficiency PSU - Rob

    * **ENTRY DATE:**July 20, 2015 
    * **UPDATE EXPECTED** July 27, 2015
    * Communicated with Zippy, possible suitable PSU (12V - 100A, 5V - 50A, 2N redundant, 80% Full Load). All 2N redundant PSUs have the same eff rating. William Li to follow up with price. To order a PSU.
    * **FINISH DATE:** September 30, 2015
    

##  July 20, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alan Hillier, Gavin Andrews, Amy Keeping, Brett Kelly, Mike Hagen, Doug Milburn, Steve Lilley, Darrell Cormier

*  Absent: Allison MacDonald

##### R&D

 1.  Linus (Brett) - Closed- He will keep us posted. 

    * **ENTRY DATE: JUNE 29 2015**
    * **CLOSED DATE: July 20 2015**
 2.  The Destroyer - In Production, will be at assembly on Wednesday at the latest. images complete. Chassis will hit assembly tomorrow. TO DO: Save images onto burning server 

    * **ENTRY DATE: July 14 2015**
    * **EXPECTED R&D CLOSE DATE: July 24 2015**
 3.  Drive mounting "Wedgie" (Brett) - No update from Alan. Brett to call today. They have an idea they want to share. 

    * **ENTRY DATE: EONS AGO**
    * **EXPECTED UPDATE: JULY 27 2015**
 4.  LCD on front panel - (Brett) - PO sent... 8 Weeks until we receive samples (10 of them, code and hardware). 10 weeks for full production once we approve samples. We will design the front plate.

    * **ENTRY DATE:**
    * We have to design the front plate to house LCD. highpoint has provided mech drawings of the keypad and screen. **EXPECTED UPDATE: BEFORE WE GET THE SAMPLES**  
 5.  Thunderbolt - Steve to call Ray J. 

    * **CLOSED FOR R&D: July 21 2015**
 6.  Tiering - Rockstor **LONG TERM RESEARCH**

    * NEXT: try tiering with BTRFS and CentOS - Brett ENTRY DATE: July UPDATE EXPECTED MONDAY JULY 27
    * Sandisk will teach us on consumer/enterprise SSDs - DATE??
    * Btier will install on ElRepo kernel (which we can call the rockstor kernel) however the btier source code will not compile on kernels >3.19. This is an error in Btier and the author has been contacted with my findings in hopes of a patch.
    * QuickTier 2 allows quick (full) setup of a tier. Current version is perfect for in-house btier devel. Script also works as a bare metal and file system benchmark. Each part (i.e tier build, raid build fs creation ....) is built as a module so they can be run within quicktier or as a standalone. **AS OF JULY 21** 
 7.  20gig Project - (Rob) - Blog published. Part 2? real file transfers across our 20gbe network.
 8.  Rockstor - (Darrell) - Rockstor Export Config - about 70% done as of last Thursday - Backup part is done, the restore function is almost done. Expected the end of this week.
 9.  Motherboard Replacement - (Rob) X10 Boards are in testing to be done this week-- **UPDATE EXPECTED MONDAY JULY 27**   
 10.  LSU - Steve spoke to Tim; mobo failed Steve sent replacement. Report expected end of the week.
 11.  Higher efficiency PSU needed eff => 80%, Need at least 40 Amps on the 5v line. 12V line should be around 90-100A. **ENTRY DATE:**July 20, 2015 

##### Marketing

*  Data Destruction
    * Destroyinator logo and webpage being worked on by Jason, Allison working w/ him to figure out website navigation. Ongoing, to be complete mid week.
    * Prototype pod going into production - in production expected tues/weds
    * Tradeshow booth hasn't been booked yet, but lots of spots available- To be booked this week. Shows in September.

*  Strategy sessions - marketing doing follow-up research on video surveillance. Strategic meeting same time same place this week.

*  Geek Beat - Chris heard back from Kien, GB plans to do a small segment about Storinator so far, and an episode about making the switch to 4K and how the Storinator has played a major role.
    * Looking into other video folks. 
    * create wiki page of video folks

*  "This week in Enterprise Tech" - Test run to be completed on Monday afternoon. chris will prep with Brett for video podcast, which takes place on Friday, July 24.

*  Networking blog - HUGE SUCCESS, discuss part 2? collect questions from customers - Team

*  Hot swapping video - reshoot video ready for Doug's approval. - Chris

*  Front panel graphic design - Done by end of week - V5 version of website's pod pics have been updated, Jason is working on revised order form next. - Allison.
     - Amy/Shirley build sheets by Wednesday
     - Full launch Friday 

*  Wiki - List has been started of upcoming articles. - Allison

##### Admin

*  Serial #'s  

*  Western Digital - chassis are being built. sending them down for full chassis evaluation. 

*  Put dates for each item - Gavin

*  New Seaside Internet Connection - Darrell. - First link is building one is up - everything is moved to the new connection. Waiting on Seaside for the B2 link - should be this week.

*  Sales forecasting needs to be upgraded to make it easier to track. Inquiries/quotes with estimates. Needs to be dumped into a spreadsheet. - Shirley/Amy

*  Sales To Do Today Reminders - Shirley/Amy

#####  Sales

*  Sales: Week of june 28 - July 11: $237,362

*  Projected sales - We've been in an upswing the last few weeks so the numbers are skewed downward when we look at 3 and 6 month averages. We've used a 6 week average to project the next two months.- Amy (with Steve/Allan)

*  "what they are using the pod for?" - Amy and Alison Adam ---results to be analyzed 

*  Sales is going to solicit feedback on the new lid from customers who are receiving them.
    - Begin collection of Lid feedback

*  Follow ups/Stale customer list - ongoing... hearing good feedback 

*  Quoting process - manual process of copying and pasting (15-20 min). Programming for pricing, copying line items, etc being added to the list. (Training will be required after programming work complete). meeting today (1:30) to discuss the technicalities of a updated quoting process

*  Territory discussions underway - Shirley received a report from Matt, to determine the territories.. ETA August 1st

##### Supply Chain & Partners

 * Reach out to Sonnet (Thunderbolt) re: working with them - Steve -talked to VP of sales at Sonnet. Steve to have a conference call.  This week.

*  Netgear re: a tier-2 agreement - Giving steve static, we want OEM partner. Steve - Ongoing 

*  Rockstor service packages need to be figured out - how will Suman and team be able to reach out to 45 Drives customers? ONGOING talk to suman this week - Steve

##### Production

*  Inventory: 
    * Current 450K - motherboards, processors and other items were received. 
    * Rocket 750s: $252,000 (55.92%); LSI Cards: $9,459; Redundant PSU: $13,700; Standard PSU: $17,490

*  Units Shipped
    * Week of July 13 - 7 complete units were shipped, 2 retro fit kits (does not include reworks or component orders)

*  Production Hours
    * Estimated Assembly Time: Week of July 13: 49.68 hrs (does not include rework time)
    * Paid hours: Week of July 13: paid time is received every other week. Week of June 28 - July 11: 95.38 hrs

*  New lid - 
    * XL60 and Q30 still have old lid inventory. The XL60s are coming through production with the new lid but we have to use current stock first. The Q30 units have not hit a reorder level yet.

*  30 Drive units - Extended front panel. Becoming standard (desktop panels) Replace template with extended faceplate - Amy To be done by July 27th 

*  Shipping damage - 2 lower corners of the extended front panel were getting damaged during shipping. Have shipped units with a third board on the bottom. Waiting to hear from customers to see if the units arrived in good condition. - Mike 

*  Need number on the amount of damaged units so far - Amy - Collected numbers

*  Need to file damage claims with Fedex - Tanya/Shirley - Complete by July 21st
    

##  July 13, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alison MacDonald, Alan Hillier, Gavin Andrews, Amy Keeping, Brett Kelly, Mike Hagen, Doug Milburn, Steve Lilley, Darrell Cormier

*  Absent: 
#####  Sales

*  Tableau Chart - still being worked on. Amy/Shirley
    * Inquiries
    * Quotes  
    * Sales  

*  Projected sales - need to do a formal projection completed every week. Needs to go on one long-term inventory. Check on the status of report (has it ever been done?) - Amy (with Steve/Allan)

*  LCD Screen Survey - Steve spoke to nine customers about the appeal of having an LCD screen. All said they would like that feature, but asked about OS integration. If price included the LCD screen, one customer said it wouldn't stop him from buying (though he wouldn't choose to pay $200 extra for it). Need to inquire about OS integration, and what that means. - Steve

*  LCD Screen - $38/unit, with a $10,000 engineering charge. (Would be paid off in 64 units).

*  "what they are using the pod for?" - Amy and Alison

*  Sales now have projections. Inventory/production numbers haven't changed much since the last week. 

*  Sales is going to solicit feedback on the new lid from customers who are receiving them.

*  Follow ups/Stale customer list - Inquiries are down, but it gives the team time to contact stale customers. 

*  Quoting process - manual process of copying and pasting (15-20 min). Programming for pricing, copying line items, etc being added to the list. (Training will be required after programming work complete).

*  Territory discussions underway - Shirley

*  Reach out to Sonnet (Thunderbolt) re: working with them - Steve

*  Steve has reached out to Netgear re: a tier-2 agreement

*  Rockstor service packages need to be figured out - how will Suman and team be able to reach out to 45 Drives customers? - Steve

##### R&D

 1.  Linus (Brett) - Contacted, He's seeing max 1GB/s which is saturation of a 10gig line. Trying to SMB multi-channeling (which does not work in Linux). He was also having an issue with network drives dropping out (need to determine if it's a Windows issue). Brett sent him some fixes, will follow-up today.    
 2.  Drive mounting "Wedgie" (Brett) - Alan & AGL are trying our a few ideas. Emailed Alan thanks for the consult help and shared with him all we've done so far. Alan is going to mock something up and get back to us - he wants to do a drive-by-drive basis. 
 3.  Thunderbolt - Akito adpater does work in OSX however all our NIC cards are non-supported. The Sonnet adapter works great. Using AFP(apple) share we see read/writes = 800/900 MB/s. NFS is slower..read/write = 350/350 MB/s (Ray J is happy with this). Ray J set up with Sonnet adapter and is loving it so far. Big fan of the fact it works alongside his current setup, no need to replace. Can connect through 1 gig line or thunderbolt. Q: Can you have multiple slots (for multiple editors/workstations)? Best for Mac (it's inconsistent in terms of read/write in Windows). Might be a Sonnet issue. 
 4.  20gig Project - (Rob) - Blog has been passed to marketing; making final changes, will work with cam to properly display images.
 5.  Rockstor - (Darrell) - Redundant boot drives now possible ( non-elegant but working ).  Config backup almost complete (Suman estimates by end of this week, or early next week). Suman is also working out his support packages currently. Need to figure out our level of support with Rockstor - supporting the setup of Rockstor is crucial. After that, we will support if it's a hardware issue. 
 6.  Motherboard Replacement - (Rob) Ordered. - Awaiting Arrival for testing.     
 7.  Tiering - Is awesome, Brett has initial numbers. Nice speeds with SSDs, etc, but it shines in iopps and small files, is ridiculously fast. (Brett) Brett to write up a quick review of his tests. Btier & Rockstor... Requires a full kernel source to install. Need to talk to Suman about this (would give Rockstor an edge). - Darrell
 8.  NEXT: try tiering with BTRFS and CentOS - Brett (Steve to reach out to Sandisk with some Qs)
 9.  LCD on front panel - (Brett) Need to get tech to design a frontplate to house the LCD module. Highpoint has provided correct dimensions and drawings. Need to give Steve Chang an official go-ahead - Brett   
 10.  LSU - A few reachouts have gone unanswered. Need to reach out to Adam, to see if he can make contact - Steve

##### Production

*  Last pay period: 140 paid hours / 80 assembly hours. Note: needs to be updated!!! 

*  Need to figure out the accurate amount of man hours to build/test - reporting doesn't seem to match currently. - Steve MacKay (with Amy)

*  Stay with Production for a couple hours to watch the Pod - Amy

*  Inventory: 
    * Current 435K, usage last week 10K. Note: needs to be updated!!! 

*  Single Non redundant chassis in production and should be ready this week. - Steve (with Christa) 

*  New lid - 
    * S45 units have shipped with new lids. Production team now has remove/attach instruction sheet to include in shipment. (XL60 and Q30 still have old lid inventory)

*  30 Drive units - Extended front panel. Becoming standard (desktop panels) - 

*  Shipping damage - 2 lower corners of the extended front panel were getting damaged during shipping. Have shipped units with a third board on the bottom. Waiting to hear from customers to see if the units arrived in good condition. - Mike 

*  Need number on the amount of damaged units so far - Amy

*  Need to file damage claims with Fedex - Tanya/Shirley 
    
##### Marketing

*  E-Recycling Data Destruction Critical Path - Need to loop Brett in - Allison

*  Ray J - vidoes - ON HOLD

*  strategy session - Part 2 complete, need to review remaining two vertical markets: video surveillance and law enforcement. Add Genomics research - Allison

*  Geek Beat - chris is going to contact  
    * Looking into other video folks. 

*  "This week in Enterprise Tech" - emailed tech to schedule test run for this Thurs. 

*  Networking blog - ready for Doug's approval.

*  Hot swapping video - ready for Doug's approval.

*  Front panel graphic design - Getting it added as the standard option. Have to coordinate with Amy, get new photos for website, change order form. Need to have dates - Allison. 

*  New lid is now shipping for S45 (postcards/video complete) - still waiting for inventory for Q30 and XL60 to be cleared

*  Wiki - Will make a list on our internal wiki, and will review at the next meeting. - Allison

*  30 Drive units - Extended front panel. Becoming standard (desktop panels) - need website order form updated. Allison

##### Admin

*  Serial #'s - bought printer, but need to take back becasue it's not network compatible.  - Amy

*  Western Digital

*  New Seaside Internet Connection - Darrell. - Order is in. Installation in within the next week or so.  New routers orders.

*  Sales forecasting needs to be upgraded to make it easier to track. Inquiries/quotes with estimates. Needs to be dumped into a spreadsheet. - Shirley/Amy

*  Sales To Do Today Reminders - Shirley/Amy



##  July 6, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alison MacDonald, Alan Hillier, Gavin Andrews, Amy Keeping, Brett Kelly, Mike Hagen

*  Absent: Doug Milburn, Steve Lilley, Darrell Cormier
#####  Sales

*  Tableau Chart - 220K in sales last week.  Almost a record.  Steve forecasts that we will see an upswing in sales in the next couple of months because alot of projects are starting up.

*  Follow ups - need to schedule a follow up schedule.  

*  LCD Screen - Steve sent out some emails asking about LCD screens and haven't heard anything back.  

*  Stale customer lists - calling a list of customers to see why they didn't buy, or what they think about their pod when they did buy.  Getting poor reviews from the backplane model.    

*  Marketing wants sales to talk to customers to see "what they are using the pod for?" - Amy and Alison 

*  Inquiries are way down, but lots of quotes are out that we are waiting on.  

##### R&D

 1.  Linus (Brett) - Haven't figured out his speed issues.  His numbers seem normal.  Network mapping troubles too with his video editing software.    
 2.  Drive mounting "Wedgie" (Brett) - no update.   
 3.  Thunderbolt - Adapters are working in windows. Odd performance numbers. It is not working for a Mac.  Will continue working on it this week and will talk with the manufactuer if we can't get it working.  
 4.  20gig Project - (Rob) First draft of blog is done, but need to make a couple edits then sending it to Alison and Cameron.  
 5.  Rockstor - (Darrell)  Darrell not here, he added the ability to RAID boot drives.  
 6.  DocMaster (Darrell/UIT program) Project - Phased.io. Adam and Darrell have been talking to them but they don't really need much data.  They wouldn't really need one of our pods.  -CLOSED   
 7.  Motherboard Replacement - (Rob) Ordered all the parts last week (XRL, DRL, processors and DDR4 RAM).  Amy checking on prices, and we could upgrade for about $20cost increase).       
 8.  Tiering - (Brett) Btier works and makes it better/faster in Linux. What do we want to do with this?  Need to apply to a particular solution, and test in a particular setting.  Brett to write up a quick review of his tests. 
 9.  LCD on front panel - (Brett) Contacted Highpoint, but haven't heard back.   
 10.  LSU - (Steve) Email Tim last week and haven't heard back.  Steve to call this week. 

##### Production

*  Waiting for chassis and some LSI cards for some pods.  

*  Last pay peroid: 140 paid hours / 80 assmebly hours.  We need to track our hours when we are not assemblying pods (maintenance, NRC, burning boot drives, etc.)

*  Inventory: current 435K, usage last week 10K.  
    * Needed to take out hard drives from the numbers because they were being treated as negatives. 

*  Single Non redundant chassis in production and should be ready this week.  

*  45 unit new lid that goes through needs photos 
    * Marketing needs to know when we will ship out the new lids.  Mike to call Alison.

*  30 Drive units - they only come through with the short front, but some customers want the extended front panel. The website shows both the extended and short front panel.  

*  Shipping damage - 2 lower corners of the extended front panel are getting damaged during shipping. - Mike 
    
##### Marketing

*  NAS Appliance - live, but haven't promoted - CLOSED 

*  Wiki - It is all updated.  We need need to keep it up to date as we go. We need a master list of needed material. Alison will make a list on our internal wiki, and will review at the next meeting.   

*  Ray J - vidoes are ready and Doug need to review, but on hold for overall strategy session

*  strategy session - on going, meeting last week, having another meeting this week after getting some customer data.  

*  Spiceworks - live. No update. -CLOSED  

*  Geek Beat - chris is going to reach out to John P to see how they are getting along with their storinator. 
    * Looking into other video folks. 

*  "This week in Enterprise Tech" - worried about bandwidth.   

*  Networking blog - waiting for first draft.

*  Hot swapping video - Chris and Brett to work on this week.

*  Front panel graphic design - the red looked too orange than red, but they ran it on 600 rather than 800. - Alison to follow up with Jenn to get a rework in.   

##### Admin

*  Serial #'s - bought printer, but need to take back becasue it's not network compatible.  - Amy

*  Western Digital is here on Wednesday morning so we need to clean up assembly area and lab.   

*  Need another internet connection for our building - Darrell. Seaside can set up a wireless connection for us, waiting for quote.  SHould be this week.
     

##  June 29, 2015

*  Attendees: Doug Milburn, Stephen MacNeil, Steve Lilley, Rob MacQueen, Alison MacDonald, Alan Hillier, Gavin Andrews, Amy Keeping, Darrell Cormier, Brett Kelly, Harold MacNeil 

*  Absent: Mike Hagen
 
#####  Sales

*  Tableau Chart

*  LCD Screen - customer survey. No update.

*  Sales Projections - Allan and Steve to discuss. 

##### R&D

 1.  Linus - He feels he should be seeing faster speeds than he is getting.  He is using Samba 3, and we think that might be it.  Brett and Darrell to call him.  
 2.  Queen Mary University of London - proposal is due on Friday.   
 3.  Drive mounting (Lid and Wedgie) - Lid is CLOSED. Wedgie - vibration results show it works just as good as the old hoods.  Going to do more testings to get numerical results.  
 4.  Video 

    * Thunderbolt - Testing Sonnet and Akati thunderbolt adapters. Both work, but we are seeing funny read/write results (160MBs read/800MB/s writes. Need to do more testing
 5.  20gig Project - Rob. Blog post: "How to get 20 gig inexpensively" - Rob will have first draft today and will share with Brett and Alison.
 6.  Rockstor - (Darrell) Back up configurations (users, shared folders) is under development by Suman.  Suman feels like he is ready for launch.   
 7.  DocMaster (Darrell/UIT program) Project - No update.  Adam P is in talks with Phased.io about this project.  All is still in planning phase.  
 8.  Motherboard Replacement - Rpb. X10 SRL will work but needs an expensive processor, Amy to order for testing.  X10 DRL is an extended ATX motherboard, Rob going to investigate X11 and other motherboards. X11 SCM is our replacement for the X9 but we need to confirm the prices of DDR4 RAM.    
 9.  Tiering - Brett, Using Btier with Thunderbolt. Seeing improvements with tiering, need to write blog to get conversation started. Talk to IRA about SSD partnership.    
 10.  LCD on front panel - Brett has a scheduled call today. 
 11.  LSU - (Steve) Tim is working on it, but will contact again. 

##### Production

*  Inventory  
    * Current: $429K
    * Last week usage: 25K

*  Production Hours 
    * NCRs have a big impact on Production hours per pod.  

*  Lids - new lids should be arriving this week.  Alison needs to see those as they go through.  Non redundant lid order is being placed today. 

##### Marketing

*  Appliance - NAS appliance is launched.  Haven't promoted it yet. 

*  Wiki - Adam and Rob.  We are caught up, and finished everything on Steve's list. Need new silkscreen for 45 Drives lite.
    * NEXT: Adam P to build a guild to the wiki.  

*  "Cannot use redundant boot drives while using FreeNAS" is warned when someone adds FreeNAS on the website.   

*  Ray J - Chris has finished a shorter video of the "best of Ray J"

*  Thursday is a strategy session with Doug to release verticle markets. 

*  Darrell wrote a blog post regarding Rockstor. 

*  Spiceworks - we are in their network to interact with IT professionals, community account.  They provide IT management tools.  Just setting it up now.  

*  Geek Beat - Alison will coordinate with Chris about next step. 

*  "This week in Enterprise Tech" - reached out to us, and Brett will be on the show July 24th to talk about power draw.  

##### Admin

*  Serial #'s and model numbers - Amy bought a simple label printer, production can type in the model and job number, but need to get everything out of Princess.  Amy to talk to Steve Mackay about proceduralize this step and will talk to Paul and Supervisors. 

*  Need another internet connection for our building - Darrell to get together a proposal this week.
     

##  June 22, 2015

*  Attendees: Rob MacQueen, Alison MacDonald, Alan Hillier, Gavin Andrews, Amy Keeping, Darrell Cormier, Stephen MacNeil, Doug Milburn 

*  Absent: Steve Lilley
 
##### Priorities

 1.  Drive mounting   

    * New lid design - Tech still processing. The knobs for the lid are on backorder.  Should be shipping the new lid next week for 45's.  
      * Brett to let Adam P know when he has the first prototype.  
    * Locking mechanisms - "The Wedgie" - No Update. Need to work on tolerance. Alan and Dave from AGL are good to come over to look at mechanical design - Brett.  
      * NEXT: Vibration Testing - Brett.  Order new parts for testing.  To be done this week.    
 2.  Video Application 

    * Ray J - NEXT: Add Highpoint Web GUI when he is available.  
    * Ataki - 3 thunderbolt adapters arrived. 1 for Ray J, 2 for our testing.  Need a MacBook for testing (Jeff S or Ray J).  Will try connecting 2 pods together with two thunderbolt adapters - Brett   
      * NEXT: Order Sonnet brand thrunderbolt adapters - AMY to contact. 
 3.  Appliance - NAS appliance is launched on the website, haven't pushed. 

    * FreeNAS - Public wiki updated.  
      * Might need to add "Cannot use redundant boot drives while using FreeNAS" with the solution to saving your config files to a separate USB drive.  Need to ship 2 files. - Alison to update website.   
      * "Whats in the box" ready to order. 
      * Add FreeNAS appliance section to Wiki - Its live, and ongoing - CLOSED 
    * Rockstor - technically improving.  Ability to Re-import your volumes - done and working. Back up configurations (users, shared folders) is under development and should be complete soon. This should bring Rockstor's disaster recovery close to FreeNAS.  This is the last major feature that was missing.    
      * DocMaster (UIT program) Adam and Darrell to set up Rockstor machine for cloud storage - meeting was rescheduled to today.   
      * Nic bonding will be the next development 
 4.  Tiering - Brett, Using Btier with Thunderbolt.  
 5.  20gig Project - Rob.  We can do 20gig with two cards (used intel, and Chesio cards and they both work, Need to test SuperMicro cards).      

    * Rob and Brett to started a blog post for this - "How to get 20 gig inexpensively"
 6.  Motherboard Replacement - Steve has a list, and will share with team. Steve to share today.   

#####  Notes

*  Documentation (external wiki) - Rob and Adam (marketing).  At the end of this week everything should be up to date.  

*  Serial #'s and model numbers - AMY 

*  LCD on front panel - Brett to schedule a call to discuss next steps.  
    * Brett to order a few LCD screens in 
    * Steve to emailed a few customers - no response      

*  UNB Project 
    * They now have all the hardware we sent and put the machine together. Gavin to send Aaron's email to brett.  
      * NEXT: Steve to email him a list of common customer requests. To do.   

*  LSU - Steve and Brett sent questions. Haven't heard anything.  Steve to contact. 

*  2N PSU 1500W redundant option - 5V draw is a bit too high for the PSU with enterprise drives, so we are going to cancel the order. Brett to contact Nippy to see if they can adapt this PSU for our use.  - Brett

*  Develop HDD compatibility matrix - add startup surge - Brett to build and pass to marketing for website/wiki. -ONGOING



##  June 15, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alison MacDonald, Alan Hillier, Gavin Andrews, Amy Keeping, Darrell Cormier, Doug Milburn, Steve Lilley

*  Absent: 
 
##### Priorities

 1.  Drive mounting   

    * New lid design - Still need 30 Drive. The knobs for the lid are on backorder.  Should be shipping the new lid on Monday.  
      * Postcard is ready to be printed.  Brett and marketing will work on a video this week.   
    * Locking mechanisms - "The Wedgie" - Need to work on tolerance. Brett to talk to Doug Steve and Dean about moulded plastic.
      * Vibration Testing - Brett to test new design.   
 2.  Video Application 

    * Ray J - Visited on Friday and gave him hard drives, and he seems more educated and confident.
      * Need to add Highpoint web gui (this week), and have it report back to us.
      * He feels like we need to offer a preconfigured machine with drives.  We don't know if this is possible.      
    * Chris did some initial videos, but it should be time to go back and do a follow up.   
 3.  Appliance   

    * FreeNAS - Public wiki - Appliance Documentation. ONGOING
         * "Whats in the box" doc made into a customer card to show Doug.
         * Add FreeNAS appliance section to Wiki - Brett
    * Rockstor - Adam and Darrell to meet with DocMaster (UIT program) to set up a cloud service machine for anyone to use for testing. Suman is excited, and will assist if required.   
 4.  2N PSU 1500W redundant option - Design Change - Brett  

    * Delayed because we just got a new order of the old PSU.  
 5.  Caching/UNB Project 

    * UNB -More useful benchmarking tool - no update. Gavin to contact 
      * NEXT: Steve to email him a list of common customer requests      
 6.  Tiering - Brett to revisit tiering. Btier in particular    
 7.  20gig Project -    

    * Max 14g through switch.  Put two cards in each machine and got 28gig.  Brett to ask Ken regarding this.  Rob and Brett to start with a blog post for this.  
    * Steve to talk to Jim D. 
 8.  Develop HDD compatibility matrix - add startup surge - Brett to build and pass to marketing for website/wiki. -ONGOING
 9.  Need to investigate replacement motherboard (ours is EOL) and therefore new CPU as well - Steve has a list, and will share with team.  

#####  Notes

*  Documentation (external wiki) - Talked to Doug and he feels Suzanne Townsend is probably not the best resource.  He would like Brett and Adam (marketing) to team up to review all outdated information and update/delete.  Time frame? - Brett and Adam P. 

*  Documentation Procedure - Need procedure to approve documentation that will be released to customers.  

*  Name Plate with serial #'s and model numbers. Amy and Paul meet and decided on printer. Still need to talk to Adam. - AMY 

*  Discuss LCD for drive location. Highpoint is working on it. Brett gave him a template of the front panel.  Brett to order a few LCD screens in. Steve to talk to some customers to see if they would pay a little more for LCD screen.       

*  LSU - Steve and Brett to generate questions for Tim.

*  Ataki - 3 thunderbolt adapters shipped on Friday. 1 for Ray J, 2 for our testing.   
    * NEXT: Order sonnet brand thrunderbolt adapters. 

##  June 9, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alison MacDonald, Alan Hillier, Gavin Andrews, Amy Keeping, Darrell Cormier, 

*  Absent: Doug Milburn, Steve Lilley
 
##### Priorities

 1.  Drive mounting   

    * New lid design - Engineering complete, Ready for launch. Burning out old inventory.
      * NEXT: Customer Communications, Once current stock is run out we can start shipping new design
    * Locking mechanisms - "The Wedgie" - New prototype, need to work on tolerance, find new rubber. 
 2.  Video Application 

    * Ray J - Ray J wants to expand. Setup up back up for him to increase his confidence levels.
 3.  Appliance   

    * FreeNAS - Brett working on documentation.Folder on public wiki called Appliance Documentation. ONGOING
         * "Whats in the box" doc made into a customer card to show Doug. NO update
         *  Add FreeNAS appliance section to Wiki.
    * Rockstor - We have the new 4.0 drivers from Highpoint.NEXT: build a rockstor NAS and get people to read/write. Slam it it with datatest script.
 4.  2N PSU 1500W redundant option - Steve wants to replace the current PSU with this one due to the Gold Efficiency. Design Change needed Brett to talk to tech.  
 5.  Caching/UNB Project 

    * UNB - Gavin, Brett, Steve and Doug talked to Ken last week.  He is going to look into making a more useful benchmarking tool for our application. Steve to email him a list of common customer requests      
 6.  Evolve Machine - Our Storinator is roughly twice as fast as the Evovle machine.  Results are on the wiki. - CLOSED    
 7.  Tiering - Brett to revisit tiering. Btier in particular    
 8.  20gig Project -   

    * There are multiple modes to investigate different settings.
      * Round Robin gives 14Gbit. Round robin is designed for fault tolerance     
    * Stephen to investigate getting a compatible switch. Talk to IOSwitch about new product         
    * FTP transfer are giving 650MB/s. 
 9.  Develop HDD compatibility matrix - Brett ONGOING
 10.  Need to investigate replacement MOBO (ours is EOL) and therefore new CPU as well. 

#####  Notes

*  Stephen to make a list of items that we are missing (or out of date) documentation.  

*  Documentation Procedure - Need procedure to approve documentation that will be released to customers. - AMY GAVIN DARREL 

*  Name Plate with serial #'s and model numbers - meeting last week: we are going to start printing stickers to put on the pods.Amy to talk with Adam regarding new serial number procedure . - AMY 

*  Discuss LCD for drive location. LCD screen given to Highpoint, they are working onto it - Brett Expect update next week     

*  LSU - Talked last week.  Tim to start writing reports. Steve and Brett to generate questions for Tim. TO BE DONE TODAY

*  Western Digital - They are sending us 240 Enterprise 6tb drives for testing. Received 60 of WD Ae+.    

*  Ataki - Ordered as of Friday. 3 of them. two for us and one for Ray J. Not in yet 

##  June 1st, 2015

*  Attendees: Stephen MacNeil, Rob MacQueen, Alison MacDonald, Steve Lilley, Alan Hillier

*  Absent:  Gavin Andrews, Amy Keeping, Darrell Cormier(sick), Doug Milburn
 
##### Priorities

 1.  Drive mounting   

    * New lid design - Templates are complete.
      * NEXT: Customer Communications, Once curretn stock is run out we can start shipping new design
    * Locking mechanisms - "The Wedgie" - No update. 
 2.  Video Application 

    * Ray J - Darrell tried to call Ray J, but didn't get him regarding lost data.  Will try again.
    * Chris has first draft of Ray video    
 3.  Appliance   

    * FreeNAS - Brett working on documentation.Folder on public wiki called Appliance Documentation
         * "Whats in the box" doc made into a customer card to show Doug.
    * Rockstor - We have the new 4.0 drivers from Highpoint. They install and work fine, but are now testing. Still haven't done some serious reads and writes. Darrell to talk to Suman.    
 4.  2N PSU 1500W redundant option - Expected in this week. NEXT Rob to verify when it comes in. 
 5.  Caching/UNB Project 

    * UNB - Gavin and Brett talked to Ken last week.  He is going to investigate further caching techniques focusing on DM cache.  He is also looking at creating a better more useful benchmarking tool.    
     * NEXT: Conference call with Ken wednesday 2:30.    
 6.  Evolve Machine - Our Storinator is roughly twice as fast as the Evovle machine.  Results are on the wiki.    

    * We are seeing a lot of chatter on the storinator machine.  Not sure why, but don't think it's not the CPU.  LSI cards still have chatter.   
 7.  20gig Project - got a 10 gig network working, and got the ports to bind on Centos 7.  We binded two machines without a switch and have about 12-13gig in the pipe.  We are not sure why we are not getting 20 gig.  

    * There are multiple modes to investigate different settings.
      * Round Robin gives 14Gbit. Round robin is designed for fault tolerance
      * IEEE gives 10 all times. 
    * Stephen to investigate getting a compatible switch.    
      * NEXT: Rob to contact Netgear for information.    
    * Why do write speeds are so slow (400MB/s) -Brett/Rob
 8.  Develop HDD compatibility matrix - Brett
#####  Notes

*  Stephen to make a list of items that we are missing (or out of date) documentation.  

*  Documentation Procedure - Need procedure to approve documentation that will be released to customers. - AMY  

*  Name Plate with serial #'s and model numbers - meeting last week: we are going to start printing stickers to put on the pods.  Paul will look for the printer. - AMY 

*  Discuss LCD for drive location. LCD screen given to Highpoint, they are working ont= it. Expect update in 2 weeks - Brett      

*  LSU - Talked last week.  Tim to start writing reports. Steve and Brett to generate questions for Tim.

*  Western Digital - They are sending us 240 Enterprise 6tb drives for testing. Shipped today from Cali.     

*  Ataki - Ordered as of Friday. 3 of them. two for us and one for Ray J.  

##  May 25, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Amy Keeping, Rob MacQueen, Alison MacDonald, Darrell Cormier, Doug Milburn, Steve Lilley

*  Absent:  Brett Kelly (sick)
 
##### Priorities

 1.  Drive mounting   

    * New lid design - ECR is waiting for the 30 and 60 design to be complete.  60 Drive Lid and Chassis changes were designed and put in production last Wednesday.
      * NEXT: follow up with tech to design 30, and finish ECR
    * Locking mechanisms - "The Wedgie" - No update. 
 2.  Video Application 

    * Ray J - Darrell tried to call Ray J, but didn't get him regarding lost data.  Will try again.
    * Chris has first draft of Ray video    
 3.  Appliance   

    * FreeNAS - Brett working on documentation.  He sent them to Jason, and Jason will distribute.  It's been developed into a customer card to show Doug.  Brett made a wiki page with the same information, and put a link on the desktop.    
    * Rockstor - We have the new 4.0 drivers from Highpoint.  They install and work fine, but are now testing.  Still haven't done some serious reads and writes.  Darrell to talk to Suman.    
 4.  2N PSU 1500W redundant option - Not in yet.  
 5.  Caching/UNB Project 

    * UNB - Gavin and Brett talked to Ken last week.  He is going to investigate further caching techniques focusing on DM cache.  He is also looking at creating a better more useful benchmarking tool.   
      * NEXT: We will send him more hardware (SSD's, upgraded motherboard, processor, RAM) to test caching on a similar machine that Brett is using.  
      * NEXT: Gavin to set up a conference call with Ken for when Doug gets back.    
 6.  Evolve Machine - Our Storinator is roughly twice as fast as the Evovle machine.  Results are on the wiki.    

    * We are seeing a lot of chatter on the storinator machine.  Not sure why, but don't think it's not the CPU.  LSI cards still have chatter. NEXT: try a faster CPU.  
    * Tested Evolve machine against our old Tera-store machine but had a hardware error.      
 7.  20gig Project - got a 10 gig network working, and got the ports to bind on Centos 7.  We binded two machines without a switch and have about 12-13gig in the pipe.  We are not sure why we are not getting 20 gig.  There are multiple modes to investigate different settings.  

    * We were running through a switch, but it has to be compatible for binded ports (dynamic post aggregation).  Stephen to investigate getting a compatible switch.    
      * NEXT: Rob to contact Netgear for information.    

##### Notes

*  Why do write speeds are so slow (400MB/s)?  Protocols? Gavin to arrange a call with Ken (UNB)  

*  Stephen to make a list of items that we are missing (or out of date) documentation.  

*  Documentation Procedure - Need procedure to approve documentation that will be released to customers. - AMY  

*  Highpoint driver for 512k bug - passed.  Brett to sum up the results and send to marketing.    

*  Name Plate with serial #'s and model numbers - meeting last week: we are going to start printing stickers to put on the pods.  Paul will look for the printer. - AMY 

*  Discuss LCD for drive location - we have a preferred options.  - Brett      

*  LSU - Talked last week.  Seagate wants documentation before going forward.  Tim to start writing reports. 

*  Western Digital - They are sending us 240 Enterprise 6tb drives for testing.     

*  Ataki - Steve asked for a quote for a thunderbolt to 10Gig adapter.  


##  May 18, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Amy Keeping, Brett Kelly, Rob MacQueen

*  Absent:  Doug Milburn (Travel), Steve Lilley (travel), Alison MacDonald (travel), Darrell Cormier  (IT)
 
##### Priorities

 1.  Drive mounting   

    * New lid design - ECR is waiting for the 30 and 60 design to be complete.  They were supposed to be done on Friday and Brett to talk to Dean after this meeting.  
    * Locking mechanisms - "The Wedgie" - No update. 
 2.  Video Application 

    * Ray J - commented to Gavin that he lost some data.  He had the directory trees, but no files in some of them.  Darrell to contact.  
      * Chris is working on the video, and has a first draft to show. 
 3.  Appliance   

    * FreeNAS - Brett wrote up documentation and gave to Marketing.  It's been developed into a customer card to show Doug.  Brett made a wiki page with the same information.    
      * Preconfigured SSD hybird pool for customers - Connected with Ken from UNB with specific questions, see below.   
    * Rockstor - they are waiting on 4.0 drivers from Highpoint, we should be getting them next week.  
 4.  2N PSU 1500W redundant option - They sent it, but we haven't received it yet.  
 5.  UNB Project - Brett sent updates and questions to Ken.  He confirmed some of our results for caching.  Brett will copy the Protocase Database over to a FreeNAS machine to build a dummy data set to test caching techniques.  

    * Ken has found a student for a small 30 hour project to start right away, and hoping to build a larger NSERC project.
 6.  Caching Project - Brett to look into other caching methods (Advanced IO, dm cach, etc) now we have more knowledge of how caching works.          
 7.  Backpanel PCI opening - design complete, and starting the ECR this week.  Rob to work with Amy. Waiting for nomenclature meeting.  
 8.  Evolve Machine - Benchmarked this week. Our Storinator is roughly twice as fast as the Evovle machine.  Results will be put on the wiki.  We are seeing a lot of chatter on the storinator machine.  Not sure why.

    * NEXT: test Evolve machine against our old Tera-store machine.      

*  20gig Project - got a 10 gig network working, and got the ports to bind on Centos 7.  Not seeing 20 gig, only 10gig.  We are running through a switch, so we will try running straight from one machine to machine.  Then will try different modes to try to achieve 20gig speeds.  

##### Notes

*  Documentation Procedure - Need procedure to approve documentation that will be released to customers.  

*  Highpoint driver for 512k bug - passed.  Brett to sum up the results and send to marketing.     

*  Name Plate with serial #'s and model numbers - meeting last week: we are going to start printing stickers to put on the pods.  Paul will look for the printer.  

*  Discuss LCD for drive location - brett looked at different options.  Highpoint has asked some questions and we need to response.  Brett and Stephen to go through today.      

*  LSU - Stephen to ask for a formal document of their results.  

*  Windows Server - NEXT: Stephen will investigate and get a copy to test. Will see at the show.  

*  Western Digital - They are sending us 180 Enterprise 6tb drives.    

*  Ataki - Steve asked for a quote for a thunderbolt to 10Gig adapter.  

##  May 11, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Amy Keeping, Brett Kelly, Darrell Cormier, Rob MacQueen, Alison MacDonald

*  Absent:  Doug Milburn
 
##### Priorities

 1.  Drive mounting -    

    * New lid design - ECR is waiting for the 30 and 60 design to be complete. 
      * 30 & 60 drawing changes have not been completed. Brett to check with Dean. 
    * Locking mechanisms - "The Wedgie" - No update  
 2.  Video Application 

    * Ray J - commented to Gavin that he lost some data.  He had the directory trees, but no files in some of them.  Darrell to contact.  
      * Chris is working on the video, and should have the first draft completed this week. 
 3.  Appliance   

    * FreeNAS 
      * To finish ECR: need to write up documentation to give to customer to tell them what they are getting. Brett has started.  Once he is complete, he will give to Alison to make a postcard to go with the SSD's.  
      * Preconfigured hybird pool for customers - Brett is working on, but having a hard time testing because it needs past history to optimize caching.  NEXT: connect with Ken from UNB with specific questions.   
    * Rockstor - nothing new, still in development.  Waiting for drivers for the 4 kernel.  Suman is testing. 
 4.  2N PSU 1500W redundant option - Rob received the shell, and they will send the PSU today.   
 5.  UNB Project - Brett to contact today.     
 6.  Backpanel PCI opening - design complete, and starting the ECR this week.  Rob to work with Amy.   
 7.  Highpoint driver with kernel 4.0 support - Darrell will follow up to get teh 4.0 driver. 
 8.  Evolve Machine - Rob built a 45 drive array and will benchmark against ours.  

*  20gig Project - got the ports to bind on Centos 7, but still need to do speed testing. 

##### Notes

*  highpoint driver - Brett is testing new driver.   

*  Name Plate with serial #'s and model numbers - Amy talked to Paul, but need to set up a meeting with Adam Darrel and Paul.

*  new rails (AMY) no update    

*  Discuss LCD for drive location - brett looked at different options.  We can use smaller fans (90mm). they range from $20 to $50.  The more expensive screens have multiple colors.  Brett to investigate more LCD screens and smaller fans.     

*  Highpoint - Been reporting bugs with 4k drives (not self reporting as 4K), but they are aware and will fix in next driver (may 8th).   
    * request for freebsd 9.3 4kn driver. 

*  LSU - Using new highpoint 4k drivers and working.  The SMR 512 Drives are much slower than SMR 4k drives. We will send a 60 drive machine and try out Western Digital.  Stephen to ask for a formal document of their results.  

*  Windows Server - NEXT: Stephen will investigate and get a copy to test. Will see at the show.  

*  Western Digital - Stephen and Amy to follow up. Nothing yet.

*  Ataki - Steve asked for a quote for a thunderbolt to 10Gig adapter.  

##  May 4, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Amy Keeping, Brett Kelly, Darrell Cormier, Rob MacQueen, Doug Milburn

*  Absent: Alison MacDonald, 
 
##### Priorities

 1.  CentOS 7 upgrade - complete and CLOSED.
 2.  Video Application 

    * Ray J - Is going to buy 10gig to thunderbolt adapter -Stephen sent a quote to thunder bolt adapters, but haven't received anything yet. Will get some in as soon as possible. 
      * Chris is working on the video, but got side tracked last week.  He has all the clips, but needs to edit.      
 3.  Appliance   

    * FreeNAS -  
      * Auto-config works
      * To finish ECR: need to write up documentation to give to customer to tell them what they are getting. 
      * Preconfigured hybird pool for customers - Brett is working on, but having a hard time testing because it needs past history to optimize caching.  NEXT: connect with Ken from UNB. 
    * Rockstor - 
      * drivers will not install 3.18; on the new kernel 3.19 is does. Suman fixing this. - Darrell
      * Ongoing - come back from a boot drive failure. Suman
 4.  Drive mounting - All Designs were put in a week ago to production.   

    * New lid design - final iteration of lid complete. ECR underway, still waiting on tech for 30 & 60 drawing changes. Doug talked to Dean today. -Brett
    * Locking mechanisms - "The Wedgie" - Tested, dimensions off but concept works. Brett to sit with Dean to nail down correct dimensions. No update.  
 5.  Investigate 2N PSU redunant option. Need minimum 1500W - Rob found one at Zippy and ordered.  
 6.  UNB Project - haven't heard from Ken lately, so Gavin and Brett will contact this week.  
 7.  Backpanel PCI opening - prototype in production on Friday and should be done today- Rob
 8.  Contact Highpoint for driver with kernel 4.0 support, once they finish the 4k fix then they release the driver - Darrell

#####  Notes

*  Name Plate with serial #'s and model numbers - Amy talked to Paul, but need to set up a meeting with Adam Darrel and Paul.

*  new rails (AMY) no update    

*  Discuss LCD for drive location - brett looked at different options.  We can use smaller fans (90mm). they range from $20 to $50.  The more expensive screens have multiple colors.  Brett to investigate more LCD screens and smaller fans.     

*  Highpoint - Been reporting bugs with 4k drives (not self reporting as 4K), but they are aware and will fix in next driver (may 8th).   
    * request for freebsd 9.3 4kn driver. 

*  LSU - Using new highpoint 4k drivers and working.  The SMR 512 Drives are much slower than SMR 4k drives. We will send a 60 drive machine and try out Western Digital.  Stephen to ask for a formal document of their results.  

*  Windows Server - NEXT: Stephen will investigate and get a copy to test. Will see at the show.  

*  Western Digital - Stephen and Amy to follow up. Nothing yet.

*  Ataki - Steve asked for a quote for a thunderbolt to 10Gig adapter.  

*  20gig Project - Rob will start this week. 

##  April 27, 2015

*  Attendees: Stephen MacNeil, Alison MacDonald, Amy Keeping, Brett Kelly, Arnie MacLean, Darrell Cormier, Rob MacQueen,

*  Absent:  Doug Milburn, Gavin Andrews
 
##### Priorities

 1.  CentOS 7 upgrade

    * ECR regarding rails - Investigate new rails (AMY) no update        
 2.  SAS Machine for Protocase - Darrell.  In place - CLOSED  
 3.  Video Application 

    * Ray J - Is going to buy 10gig to thunderbolt adapter -Stephen
      * Chris is working on the video. no update     
 4.  Appliance   

    * FreeNAS - 
      * NEXT: auto-config works, ECR to follow, to be done by next monday. BRETT
      * Preconfigured hybird pool for customers - Brett no update, NEXT: show real network speeds.
     

    * Rockstor - drivers will not install 3.18; on the new kernel 3.19 is does. Suman fixing this. - Darrell
      * Ongoing - come back from a boot drive failure. Suman
      * Need Beta customers (LSU? Tim G at Santa Clara?) Stephen to build a possible list of customers. 
 5.  Drive mounting - All Designs were put in a week ago to production.   

    * New lid design - final iteration of lid complete. ECR underway, waiting on tech for 30 & 60 drawing changes -Brett
    * Locking mechanisms - "The Wedgie" - Tested, dimensions off but concept works. Brett to sit with Dean to nail down correct dimensions 
 6.  Name Plate with serial #'s and model numbers - Amy 
 7.  Investigate 2N PSU option. Need minimum 1500W - Rob
 8.  UNB Project - is open to more collaboration. Brett/Gavin -No update
 9.  Backpanel PCI opening - Check to see if production - Rob
 10.  COntact Highpoint for driver with kernel 4.0 support -Darrell
#####  Notes

*  Discuss LCD for drive location  

*  Highpoint   
    * request for freebsd 9.3 4kn driver. 

*  LSU - Using new highpoint 4k drivers and working.  The SMR 512 Drives are much slower than SMR 4k drives. We will send a 60 drive machine and try out Western Digital.  Stephen to ask for a formal document of their results.  

*  Windows Server - NEXT: Stephen will investigate and get a copy to test. Will see at the show.  

*  Western Digital - Stephen and Amy to follow up. Nothing yet.

##  April 20, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Brett Kelly, Arnie MacLean, Darrell Cormier, Rob MacQueen,

*  Absent:  Steve Lilley,Gavin Andrews
 
##### Priorities

 1.  CentOS 7 upgrade - CLOSED

    * ECR for adding 10G nic, add SSDs - CLOSED
    * ECR regarding rails - Investiugate new rails (AMY)        
 2.  SAS Machine for Protocase - Darrell.  In place - CLOSED  
 3.  Video Application 

    * Ray J - Is going to buy 10gig to thunderbolt adapter
      * Chris is working on the video. no update     
 4.  Appliance   

    * FreeNAS - 
      * NEXT: Auto - config concept realized. Need to verify images will work on new pod. Brett
      * Preconfigured hybird pool for customers - Brett
     

    * Rockstor - drivers will not install 3.18; on the new kernel 3.19 is does. Suman fixing this. - Darrell
      * Ongoing - come back from a boot drive failure. Suman
      * Need Beta customers (LSU? Tim G at Santa Clara?) Stephen to build a possible list of customers. 
 5.  Drive mounting - All Designs were put in a week ago to production.   

    * New lid design - final iteration of lid complete. ECR schedule to be figured -Brett
    * Locking mechanisms - "The Wedgie" - Design is in Tech; has not made it to production yet. -Brett 
 6.  New 1500W 2N Power Supply - Source 1500W from zippy for customers who want 2N.
 7.  UNB Project - is open to more collaboration. Brett/Gavin
 8.  Backpanel PCI opening - video card support - Rob
#####  Notes

*  New Highpoint driver for 4k drives - testing Windows. Brett to ask for Window's version of 4K driver.  
    * Stephen to talk to May about notifications of new drivers. 

*  Highpoint - request for freebsd 9.3 4k driver. 

*  LSU - Using new highpoint 4k drivers and working.  The SMR 512 Drives are much slower than SMR 4k drives. We will send a 60 drive machine and try out Western Digital.  Stephen to ask for a formal document of their results.  

*  Windows Server - NEXT: Stephen will investigate and get a copy to test. Will see at the show.  

*  Western Digital - Stephen and Amy to follow up. Nothing yet.

##  March 30, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Darrell Cormier, Rob MacQueen, Brett Kelly, Arnie MacLean, Doug Milburn

*  Absent: Steve Lilley
 
##### Priorities

 1.  CentOS 7 upgrade - already on wiki for CentOS 7 mate upgrade, but no communication as a engineering change. 

    * ECR (add 10G nic, add SSDs, change to Centos 7) - change has been written up, but not signed off yet. This week.    
    * Images - made. CLOSED     
    * Testing Intel video card - (nVidia) Works, but the VGA input is too high on chassis.  We need to change the panel anyways, so Brett and Dean will change this (ECR) when they change it for the new power supply.        
 2.  SAS Machine - We need to build a SAS machine in our server room - Darrell. 
 3.  Video Application 

    * Ray J - Darrell talking to Ray J, he is happy with it.  He is going to buy the thunderbolt adapter. 
      * Chris is working on the video.     
 4.  Appliance   

    * FreeNAS - Test and write down procedures for failed USB - DONE and on external wiki.
      * NEXT: Look at automating saving config file  
      * Kien from Geekbeat has had some issues with FreeNAS - back up and running, he had some bad cables.  FreeNAS's update caused an old driver to install.  Darrell working with Steve Change (Highpoint) about getting a new driver, he had a problem seeing the problem.  Hihpoint is working on a permenant solution. 
    * Rockstor - still in development.  Darrell will have a conference call this week. 
      * Testing stability in the newer kernels.  Pulling drives out of the RAID working well.  
      * Still to finish - come back from a boot drive failure. 
        * We cannot mirror the boot drives
      * Driver Problem - we cannot install our drivers on a default install - Darrell working with Rockstor to get a prebuilt package for us with our drivers. He will remote in to determine the problem.       
 5.  Drive mounting  

    * New lid design - 2 new prototype to built this week, testing for perfect feel. 
    * Locking mechanisms - The first "The Wedgie" getting built this week.  
 6.  45 Lite - New Cables - Designed. China long is producing them, and sample will be here this week. 
 7.  New 1200W Power Supply - We need to make design check for new power supply.  It can ship with our custom power harness. Will cost less than current configurations.    
 8.  UNB Project - Ken writting up a final report for this project, but wants to continue next FY.  Will write a proposal for the next step.

    * Concluded that we have get great bandwidth in and out, but poor computational power.    

#####  Notes

*  Highpoint sent a new driver for 4k drives - testing. We are compatible with Linux, and Brett to ask about Windows. 
    * Brett to contact Highpoint to get notifications of new drivers.

*  Windows Server - NEXT: Stephen will investigate and get a copy to test.  

*  Western Digital - Stephen and Amy to follow up. 


##  March 23, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Darrell Cormier, Rob MacQueen, Brett Kelly, Arnie MacLean, 

*  Absent: Steve Lilley, Doug Milburn
 
##### Priorities

 1.  CentOS 7 upgrade - 

    * ECR (add 10G nic, add SSDs, change to Centos 7) - haven't made the change yet. Amy to talk to Steve MacKay.  
    * Images - still working on Images (time consuming and distractions). Will finish this week.     
    * Graphics cards - Steve to reach out to Femrice for a video card - no card avaliable.  They have a 10G copper card available soon, and the fibre card works.  
    * Testing Intel video card - (nVidia) They are in the lab, but we need a testing machine with a SRL board.  Testing to start today.     
 2.  Video Application 

    * Ray J - everything working.  Chris has been working with him.     
 3.  Appliance   

    * FreeNAS - ready to go. 
      * NEXT: Test and write down procedures for failed USB - Brett    
    * Rockstor - still in development.      
    * NAS for Free - no update.
    * TrueNas - for IX systems machines only. Cannot download, so cannot test. - CLOSED 
 4.  Drive mounting  

    * New lid design - new lid is made, the lid now point in.  Will test to make sure it's ok. 
    * Locking mechanisms - "The Wedgie" is designed, but needs to be built. This week.       
 5.  45 Lite - Design New Cables - Designed. Samples on the way from China Long. No quote from Nippon.   
 6.  UNB Project - no update from Ken. Brett to get in touch this week. 

##### Notes

*  FreeNAS - Kien from Geekbeat has had some issues with FreeNAS.  Darrell working with Steve Change (Highpoint) about getting a new driver.  He had to do a fresh install and it's working. Highpoint is working on a permenant solution. 

*  Rockstor - we cannot install our drivers on a default install - Rockstor problem. Darrell working with Rockstor to get a prebuilt package for us with our drivers.  Does he need Highpoint to agree?  Darrell will work with both to work through this.    

*  CBU - Steve talking to Ben Pickles who runs the server at CBU.  Needs a low cost SAN for research data storage.  He is coming for a tour.  

*  Unified Web server - Steve in talks with a software development company.  Steve shared the whitepapers with everyone - lacking details.


##  March 16, 2015

*  No meeting due to winter storm, notes by Brett
 
##### Priorities

 1.  CentOS 7 upgrade - Nailed down proper imaging for C7, make all the varieties(single,redundant,ssd,etc) of Images this week.     

    * Graphics cards - Steve to reach out to Femrice for a video card - no response yet.  
 2.  Video Application 

    * Ray J -  
      * Wiki post for setting up a network connection and using editing software - CLOSED
        * http://www.45drives.com/wiki/index.php/Using_a_45Drives_NAS_in_an_Apple_Environment_%26_Final_Cut_ProX  
 3.  Appliance -  

    * FreeNAS - ready to go
      * NEXT: Test and write down procedures for failed USB - Brett, no update    
    * Rockstor - Darrell to talk to Suman about USB OS recovery.  We are testing back and forth. Not ready for release - still working on recovery process.     
    * NAS for Free - Web GUI
 4.  Drive mounting  

    * New lid design - **Done its in the lab, were waiting on caps for the standoffs to come in either today or tomorrow then we can get everyones opinion and then its ready to go**
    * Locking mechanisms - Bought force sensor, and mocked up a experiment piece.  Will design in Solidworks, and get it milled.  
 5.  45 Lite - Design New Cables - Will send drawings to China Long and Nippon. **China Loong order has been placed,, still waiting on Nippon for a quote**  
 6.  UNB Project - Gavin and Brett meet with Dr. Kenneth Kent on Friday.  He agreed to take a loaned Storinator back to his lab for testing.** Hes doing good, from his email ".We are in the process now of trying to think how to populate the machine with a database and then start to perform some queries to see how it performs."  **

##### Notes

##  March 9, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Darrell Cormier, Rob MacQueen, Brett Kelly, Arnie MacLean, Steve Lilley, Doug Milburn

*  Absent: 
 
##### Priorities

 1.  CentOS 7 upgrade - Making images, need signiatures for ECR. **Nailed down proper imaging for C7, make all the varieties(single,redundant,ssd,etc) of Images this week. ECR to finalized by the end of the week.**      

    * Graphics cards - Steve to reach out to Femrice for a video card - no response yet.  
    * Testing Intel video card -     
 2.  Video Application 

    * Ray J -  
      * Wiki post for setting up a network connection and using editing software - minor change to do. **DONE**http://www.45drives.com/wiki/index.php/Using_a_45Drives_NAS_in_an_Apple_Environment_%26_Final_Cut_ProX  
 3.  Appliance -  

    * FreeNAS - ready to go
      * NEXT: Test and write down procedures for failed USB - Brett ** havent done this yet**    
    * Rockstor - Darrell to talk to Suman about USB OS recovery.  We are testing back and forth. Not ready for release - still working on recovery process.     
    * NAS for Free - Web GUI
 4.  Drive mounting  

    * New lid design - **Done its in the lab, were waiting on caps for the standoffs to come in either today or tomorrow then we can get everyones opinion and then its ready to go**
    * Locking mechanisms - Bought force sensor, and mocked up a experiment piece.  Will design in Solidworks, and get it milled.  
 5.  45 Lite - Design New Cables - Will send drawings to China Long and Nippon. **China Loong order has been placed,, still waiting on Nippon for a quote**  
 6.  UNB Project - Gavin and Brett meet with Dr. Kenneth Kent on Friday.  He agreed to take a loaned Storinator back to his lab for testing.** Hes doing good, from his email ".We are in the process now of trying to think how to populate the machine with a database and then start to perform some queries to see how it performs."  **

##### Notes

 

##  March 2, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Darrell Cormier, Rob MacQueen, Brett Kelly, Arnie MacLean

*  Absent: Steve Lilley, Doug Milburn
 
##### Priorities

 1.  CentOS 7 upgrade - Ready to go. Switching to CentOS 7-Mate as our default. Verified that Mate works.  Released note to wiki. Brett to do ECR    

    * Graphics cards - Steve to reach out to Femrice for a video card - no response yet.  
    * Any intel video card - Rob bought 2 (0.5 GB and 1GB cards)  Around $40.     
 2.  Video Application - Editing straight on the machine. 

    * Thunderbolt - Cards are now working in Windows.  Cards will not work in Linux because there is no drivers for our chip sets (Falcon Ridge). HP may make some cards that work. 
    * Ray J - Uploading 110,000 videos. 
      * Wiki post for setting up a network connection and using editing software - minor change to do.   
 3.  Appliance -  

    * FreeNAS - ready to go
      * In case of failed USB, would we be able to put in a new USB and rebuild your share? Yes, but it's much easier if you backup your config file.   
      * NEXT: Test and write down procedures for failed USB - Brett    
    * Rockstor - Darrell to talk to Suman about USB OS recovery.  We are testing back and forth. Not ready for release - still working on recovery process.     
    * NAS for Free - We got the driver to install, but not the web GUI.  Will work on that today. 
 4.  Drive mounting  

    * New lid design - newest prototype is working well.  Still trying to find new PEMs for the sides that do not stick out as much. 
    * Locking mechanisms - Bought force sensor, and mocked up a experiment piece.  Will design in Solidworks, and get it milled.  
 5.  45 Lite - Design New Cables - Will send drawings to China Long and Nippon.  

##### Notes

*  UNB Contact - Gavin and Brett to have introduction call with Kenneth Kent, a CS professor at UNB, this afternoon. http://www.cs.unb.ca/~ken/

*  Processor - I3 processor is going end-of-life, so we need to plan a new processor (E3?)  
    * NEXT: Amy to look into new motherboard/processor for our base level.  
    * SuperMicro for a new motherboard or plan - they suggested a new motherboard, but it's really expensive and not fit for purpose.

*  Power Supplies - found two (redundant and non redundant) new Zippy power supplies that are cheaper than current PS, and have more Watts.  
    * NEXT: Buy one of each for testing.  
 

##  February 23, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Darrell Cormier, Rob MacQueen, Brett Kelly, Doug Milburn

*  Absent: Steve Lilley, Arnie MacLean
 
##### Priorities

 1.  CentOS 7 upgrade - tested different enviroments (MATE - good, XFCE - not good).  MATE is a reduced GUI of CentOS 7 that works well.   

    * Need to document on website with a how to install.  Brett to send Alison info. 
    * Graphics cards - Steve to reach out to Femrice for a video card.  Any intel video card - Rob to buy 2 or 3 to test.     
 2.  Video Application - Editing straight on the machine. 

    * Thunderbolt - found a solution, a 10 gig thunderbolt adapter ($599) but they are a straight competitor. 
      * Thunderbolt over IP is very slow (100MB/s); it's only good for localized storage.      
    * Ray J - Darrell saw him last week.  He will upgrade to a 10gig network. 
      * Final cut pro X will not work on Apple software (AFS), so he set up a NFS share and it worked right away.  
      * Ray J will clear his pod, and try to do it again to learn how it works.      
      * Wiki post for setting up a network connection and using editing software - needs only minor additions.   
 3.  Appliance -  Gavin and Brett created a check list for NAS appliances.

    * FreeNAS - ready to ship.  Should ship an extra USB for disaster recovery. 
      * In case of failed USB, would we be able to put in a new USB and rebuild your share? 
      * NEXT: Test and write down procedures for failed USB - Brett    
    * Rockstor - still in development, but should be close. Darrell to talk to Suman about USB OS recovery.  
    * NAS for Free - looks very similar to FreeNAS, but our HBA driver doesn't work on it.  
      * NEXT: Reach out to NAS for Free regarding our driver - ROB 
    * Open Filer - doesn't go on a USB and drivers are not working. 
 4.  Drive mounting  

    * New lid design - waiting for custom PEM, Brett will follow up. 
    * Locking mechanisms - measuring the force displacement for rubber to size the wedge mechanism.  Buying force sensor.  
 5.  45 Lite - Design New Cables - design finished, Brett to send to Nippon and China Long 

##### Notes

*  New Power supply - Need to test (1250W dual high efficiency redundant) $450. 

*  Processor - I3 processor is going end-of-life, so we need to plan a new processor (E3?)  
    * NEXT: Amy to look into new motherboard/processor for our base level.  
    * NEXT: Stephen to reach out to SuperMicro for a new motherboard or plan. 
 

##  February 17, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Amy Keeping, Darrell Cormier, Rob MacQueen, Brett Kelly, Doug Milburn

*  Absent: Steve Lilley, Arnie 
 
##### Priorities

 1.  CentOS 7 upgrade

    * Need to offer CentOS 7, with low graphics intensity GUI option with explanation for base/small model.  
    * Need to document on website. 
    * Graphics cards - Darrell to look into card compatibility. Amy to look into pricing.  
 2.  Video Application - running editing software on server 

    * Thunderbolt - only 3m limit to cords.  Need 10gb/thunderbolt adapter (Sonnet).  Brett hasn't heard back from SuperMicro about 3.17.  
    * Ray J - Only writing 100mb/s because of his 1gb network.  Darrell to visit this week to work on his file system and other issues.   
      * To Do: Wiki post for setting up a network connection and using editing software.  Brett drafted and is done, but will send it out once back.   
 3.  Appliance - Rob to test new USB that has printable logo.  Tested 4 other USB drives, and they all worked. 

    * FreeNAS - Gavin and Brett to go through this week.  
 4.  Drive mounting  

    * New lid design - Newest prototype was missing pems.  Will get installed this week.
    * Cam locking for drives - no update.  Still designing.  
 5.  45 Lite - Design New Cables - Brett

    * Steve to send Brett current design so Brett can make new design. 
    * Made new folder to save all design 

#####  Wants

*  60 Drive 
    * Brett to look into mini power connectors and a possible bus host for 15 drive banks - no update
    * Larger power supply
      * Seagate 6TB drives - Brett testing - working but write speeds slower.     

*  SSD Caching & Tier - no update. 
    * PCI Card - testing this week. 
    * NEXT: try using B tier and B cache on Chris' 30 drive machine
    * Femrice - 10 Gb cards 

*  Appliance - Rob to investigate one. 
    * Openfiler - need to reach out - Stephen to contact about co marketing. 
    * NAS for Free - need to investigate but not priority.  
    * Rockstor - big improvements lately.  Disaster recovery has been added.  Still cannot software RAID boot drives because of BTRFS.  Darrell to contact this week.  

*  LSU - call last week. Their 5TB crawford machine is working really well.  Overall impressed. Looking into LVN tier caching program to speed up preformance.  Waiting on Seagate to respond about highpoint cards. 

*  Redundancy of HBA cards - Currently no redundancy for a HBA card and cable failure.  Only works for SAS cards, but we need to start selling SAS machines to determine demand.  

##  February 9, 2015

*  Attendees: Gavin Andrews, Stephen MacNeil, Alison MacDonald, Brett Kelly, Doug Milburn, Amy Keeping

*  Absent: Darrell Cormier, Rob MacQueen, Chris McGean, Steve Lilley
 
##### Priorities

 1.  Video Application - running editing software on server 

    * Thunderbolt - No update. More testing to do.  Brett hasn't heard back from SuperMicro about 3.17.  
    * Ray J - Brett and Darrell visited last week. It is set up to his "Mac-final cut pro" network - problem was the port was set to static and he plug into the wrong port.  He was very impressed.  Multitasking and doing things in parallel was a great feature (streaming to Youtube, backing up failed hard drives, video editing).      
      * To Do: Wiki post for setting up a network connection and using editing software.  Brett just finishing the write up and will send out for review.  
    * Geek beat video conference - talked to Ken (FreeNAS). He is happy with the Storinator.  Everything is run off the box and stored there; 5-6 users.  No major speeds up, or down.  They will be doing an episode - Chris.  
 2.  Appliance 

    * FreeNAS - set up is pretty comprehensive, but Brett is working on it.  
    * Rockstor - BTRFS is still in active development and not ready. Back burner.
    * NAS for Free - need to investigate but not priority.  
    * Openfiler - no knowledge.  Need to investigate but not priority. 
 3.  Drive mounting  

    * New lid design - one desing worked, but wasn't ideal.  Dean made a design, and it works great.  Redesigning the front panel to add one/two tool-less screws. 
    * Cam locking for drives - Still designing up a experimental piece to adjust for rubber feel.  
 4.  45 Lite - Design New Cables - Brett

    * Steve to send Brett current design so Brett can make new design. 
    * Made new folder to save all designs  

#####  Wants

*  CentOS 7 upgrade
    * NEXT: Stephen to call CentOS to discuss  
    * To Do: Give customers an option for CentOS 6.6 or 7, with cautionary note for graphics intensity. NEXT: Brett to follow up.   

*  60 Drive 
    * Brett to look into mini power connectors and a possible bus host for 15 drive banks - no update
    * Larger power supply
      * Seagate 6TB drives - Brett to do power measurements this week.  

*  SSD Caching & Tier - no update. 
    * PCI Card - testing this week. 
    * NEXT: try using B tier and B cache on Chris' 30 drive machine
    * Femrice - 10 Gb cards 


##  February 2, 2015

*  Attendees: Gavin Andrews,  Darrell Cormier, Stephen MacNeil, Chris McGean, Alison MacDonald, Brett Kelly, Rob MacQueen, Doug Milburn, Cameron MacDonald, Steve Lilley, Amy Keeping

*  Absent: 
 
##### Priorities

 1.  60 Drive 

    * Staggered Spin Up - Brett finished a public wiki post to discuss staggered spin up.  
    * Brett to look into mini power connectors and a possible bus host for 15 drive banks - no update
    * Larger power supply
      * Seagate 6TB drives - Brett to wait until we have all large HD to do measurements.  Amy to check with hard drives. 
 2.  Video Application - running editing software on server 

    * Thunderbolt - cables are here.  Isn't working very well with Linux.  More testing to do.  Brett to go back to SuperMicro about 3.17.  
    * Ray J - wants to plug into his network.  Darrell to go over this week to set up.  
      * To Do: Wiki post for setting up a network connection and using editing software.  
    * Chris to talk to Geek beat, talked to Ken, but wants to do a video conference Wed/Thursday - Chris 
      * Need to determine how they set up their system and see if it's working or not.       
 3.  Drive mounting  

    * New lid design - received first chassis but missing some PEMS - Brett to follow up. Second unit finish production today   
    * Sketched up a design for Cam locking for drives.  Need to design up a experimental piece to adjust for rubber feel.  
 4.  SSD Caching & Tier - no update. 

    * New highpoint cards (2720's) is working very well with SSDs - only hardware RAID. 
    * PCI Card - testing this week. 
    * 10 Gb networking blog posts - Brett 
    * NEXT: try using B tier and B cache on Chris' 30 drive machine
    * Femrice - 10 Gb cards - to test this week.  

#####  Wants

*  CentOS 7 upgrade 
    * SuperMicro - our current boards are not good for 7.  They have more boards (X10), but are very expensive with processor and RAM (DDR4) to match.
      * NEXT: Stephen to call CentOS to discuss. 
    * Darrell to look for a spin off version of CentOS 7 that is less graphic intensive to work with our current machine.
      * No "official" spin off versions.
    * To Do: Give customers an option for CentOS 6.6 or 7, with cautionary note for graphics intensity - WHO? 

*  Three Base Configurations (Storage only, normal, high speed) Meeting last week. End of week will have configurations finished - Amy   

*  External Wiki - Brett to work with marketing to update. 

*  Canadian Tire Video Project - wants the better motherboard and CPU.  CPU was maxed out.      

*  Walmart project - (CEPH, 8TB SMR) 

*  Special Projects:
    * University of Santa Cruz - get 60 drive unit ready for shipment.  - Stephen     
    * Seagate/LSU project - no update.  

*  Removal SSD back for caching. 

*  NAS for Free - need to investigate.  

##  January 26, 2015

*  Attendees: Gavin Andrews,  Darrell Cormier, Stephen MacNeil, Chris McGean, Alison MacDonald, Brett Kelly, Rob MacQueen, Doug Milburn, Cameron MacDonald, Steve Lilley, Amy Keeping

*  Absent: 
 
##### Priorities

 1.  60 Drive 

    * Staggered Spin Up - Made list of drives that support staggered spin up (Western Digital - currently compiling list, Toshiba - all drives, Seagate - nothing yet).  Brett to write a public wiki post to discuss staggered spin up. 
    * Brett to look into mini power connectors and a possible bus host for 15 drive banks. 
    * Larger power supply?  Need to measure power draw for large hard drives (4TB, 6TB, etc)
      * Seagate 6TB drives - Brett to do power measurements
 2.  Video Application - running editing software on server 

    * Thunderbolt - cable not here yet. 
    * Ray J - has a technical bug with his editor software.  Was impressed with speed for the short time it was working.  
    * Chris to talk to Geek beat about their project.  No update.      
 3.  Drive mounting - 

    * New lid design - just went to production today.  
    * Sketched up a design for Cam locking for drives - will sit with Doug today to discuss. 
 4.  SSD Caching & Tier - no update. 

    * PCI Card - testing this week. 
    * 10 Gb networking blog posts - Brett 
    * NEXT: try using B tier and B cache on Chris' 30 drive machine
    * Femrice - 10 Gb cards - to test this week.  

#####  Wants

*  CentOS 7 - graphics intensive, and slows transfer speeds. Should we and when should we upgrade? 
    * Darrell found some workstation board that might work, but nothing much in the server world.  
    * Darrell to look for a spin off version of CentOS 7 that is less graphic intensive to work with our current machine.
    * To Do: Give customers an option for CentOS 6.6 or 7, with cautionary note for graphics intensity - WHO? 
    * NEXT: Stephen to contact SuperMicro to see their thoughts. No update.  

*  External Wiki - Brett to work with marketing to update. 

*  Canadian Tire Video Project - Testing continues, and working.    

*  Walmart project - (CEPH) Conference call last friday. Looking at 8TB SMRs. 

*  Rack Ears - 
    * Design solid front plate - Copmplete, and in production for pictures and testing  
    * Communication - video - Alison 
    * Packing material - Complete  

*  Special Projects:
    * University of Santa Cruz - get 60 drive unit ready for shipment.  - Stephen     
    * Seagate/LSU project - no update.  

*  Serial Numbers - each pod needs to have a unique number - Paul looking into it.  

##  January 19, 2015

*  Attendees: Gavin Andrews,  Darrell Cormier, Stephen MacNeil, Chris McGean, Alison MacDonald, Brett Kelly, Rob MacQueen, Doug Milburn

*  Absent:  Cameron MacDonald, Steve Lilley
##### Priorities

 1.  60 Drive 

    * Staggered Spin Up - Making list of drives that support staggered spin up (Western Digital - currently compiling list, Toshiba - all drives, Seagate - nothing yet)
    * NEXT: Brett to ask Highpoint about how they stagger spin up (pin 11).    
    * Larger power supply?  Need to measure power draw for large hard drives (4TB, 6TB, etc)
 2.  Video Application - running editing software on server 

    * Thunderbolt - Brett to do a wiki page.  The cable isn't here yet.  [45drives_hardware_testing](45drives_hardware_testing)  
    * Ray J - has a 30 drive up and running.  He is setting up his editing software (Final cut pro) last weekend.  He was very impressed with the speed.
    * Chris to talk to Geek beat about their project.       
 3.  Drive mounting - 

    * Two new lid design is in.  New ball bearing screws are in.  
    * To do: Brett to talk to Alex regarding Cam locking for drives.
    * NEXT: drive locking design - Brett 
 4.  SSD Caching & Tier 

    * B Tier - new release is out, but is not working.  Reporting errors back.  
    * PCI caching card - not a big improvements over putting SSD's on a HBA card. 
      * Interesting when we switched 4x and 8x slots.  Highpoint cards went to 4x, and not much change in speed.  The SSD's on 8x were a lot faster.  To investigate further.  
    * NEXT: try using B tier and B cache on Chris' 30 drive machine

#####  Wants

*  CentOS 7 - graphics intensive, and slows transfer speeds. Should we and when should we upgrade?  To contact SuperMicro to discuss our problem with the current motherboard.  
    * NEXT: Stephen to contact SuperMicro to see their thoughts.  
    * NEXT: send out communication on CentOS 7.  

*  Canadian Tire Video Project - Upgraded motherboards and CPU's.  Testing continues, but no new updates.    

*  Walmart project - (CEPH) shipped remaining pods.  

*  Rack Ears - calling 3 customer and they want the solid front plate and do not really like the ears.  
    * NEXT: Design solid front plate, and make one for pictures and testing - Brett.  
    * To do: Communication - video 
    * To do: Check packing material - Brett 
    * To do: Brett to talk to Paul regarding 'design change' in Princess  

*  Special Projects:
    * University of Santa Cruz - looking for a 60 drive pod.    
    * Seagate/LSU project - Seagate wants to set up a webinar for enterprise drives. Phone conference on Friday. 5TB SMR drives are working well, but no staggered spin up.  Pod is working well.  

*  Serial Numbers - each pod needs to have a unique number - Amy K. 
   

##  January 12, 2015

*  Attendees: Gavin Andrews,  Darrell Cormier, Julie Murray, Stephen MacNeil, Chris McGean, Steve Lilley, Alison MacDonald, Brett Kelly, Rob MacQueen, Cameron MacDonald, Doug Milburn

*  Apology:  
##### Priorities

 1.  60 Drive 

    * Staggered Spin Up - Neither Seagate or LSI have reported back. Rob to send a message to both. 
    * NEXT: look into a larger power supply. 
 2.  30-drives & Quite Model 

    * New power harness (China Long) - tested and works.  Made some changes to plug, and will order for production.     
    * Chris continue testing - inside the editing suite we didn't see a speed change from SSD and mechanical hard drive (CPU at 100%).  We saw the upload was faster than the download from the server.    
 3.  Video Application 

    * Thunderbolt - test motherboard is in.  Processors and RAM (DDR) are in.  We are waiting for thrunderbolt cord.  We are seeing very fast speeds (700MB/s) over a 10G network. Brett to do a wiki page.     
 4.  Drive mounting - parts for incline tooth design expected today.  

    * New lid design should go in today, and ordered new ball bearing screws.
    * Brett to talk to Alex regarding Cam locking for drives.
 5.  SSD Caching & Tier - no update 

    * B Teir: Numbers seem slower than expected (70-400 MB/s internally). 

#####  Wants

*  CentOS 7 - graphics intensive, and slows transfer speeds. Should we and when should we upgrade?  To contact SuperMicro to discuss our problem with the current motherboard.  Darrell looking at different board options. 

*  Canadian Tire Video Project - having some problems getting all the cameras to download with the standard processors (CPU is at 100%).  No update.  

*  Walmart project - (CEPH) shipping this week. 

*  Rack Ears - Julie - organize calling customer to question regarding rack ears offering. Playing phone tag, and waiting for responses.   

*  Special Projects:
    * University of Santa Cruz    
    * Seagate/LSU project - conference was missed last week (cannot detect and RAID). Steve to contact everyone this week. Seagate wants to set up a webinar for enterprise drives.  



##  January 5, 2015

*  Attendees: Gavin Andrews,  Darrell Cormier, Julie Murray, Stephen MacNeil, Chris McGean, Steve Lilley, Alison MacDonald, Brett Kelly, Rob MacQueen

*  Apology:  Doug Milburn, 
##### Priorities

 1.  60 Drive 

    * Staggered Spin Up - emailed Seagate to determine what hard drives support staggered spin up.  Will compile a list of compatible drives. Contacted LSI to to ask about stagged spin up.  Going on the public wiki. 
 2.  30-drives & Quite Model 

    * New power harness (China Long) to be tested for size and function     
    * Chris continue testing - did SSD testing, but Rob is putting mechanical drive in as boot drive to determine speed change - Rob  
 3.  Video Application 

    * Thunderbolt - test motherboard is in.  Processors and RAM (DDR) are not in yet.     
    * BTRFS - Rockstor video conference a couple weeks ago. Seems stable, the only problems are fringe applications. Development active. 
      * Machine to Rockstor for testing/development - shipping today.  
    * FreeNAS on USB drive - done.  Need to stock USBs now.  
 4.  Drive mounting - had brain storming meeting last week, and created many new ideas. 

    * Expanding on "inclinded tooth" design, and looking into new cam design.  Brett to talk to Alex. 
    * Changing cover design (spring loaded locking mechanism). Brett to get new cover design into tech today.  
 5.  SSD Caching & Tier - working on b cache, working now with upgraded kernels.  Have not bench marked yet. 

    * B Teir: Numbers seem slower than expected (70-400 MB/s internally). 
      * NEXT: determine conditions when we got 1GB/s to determine what could be bottle necking our results.  Test internal transfer speeds within one machine. Make two identical tiered banks (10 drives).  

#####  Wants

*  CentOS 7 - graphics intensive, and slows transfer speeds. Should we and when should we upgrade?  To contact SuperMicro to discuss our problem with the current motherboard. 

*  Canadian Tire Video Project - having some problems getting all the cameras to download with the standard processors (CPU is at 100%).   

*  Walmart project - (CEPH) currently building units

*  Rack Ears - Julie - organize calling customer to question regarding rack ears offering.   

*  Special Projects:
    * University of Santa Cruz    
    * Seagate for LSU project - conference this week on SMR hard drives (cannot detect and RAID) 


##  2014 December 22

*  Attendees: Gavin Andrews,  Darrell Cormier, Rob MacQueen, Julie Murray, Stephen MacNeil, Doug Milburn, Chris McGean, Steve Lilley, Alison MacDonald

*  Apology: Brett Kelly (vacation) 
##### Priorities

 1.  30-drives & Quite Model 

    * Chris continue testing.  No difference between loading off server than off laptop for 8G project file.  
      * Goal: achieve the same speed as a local drive, but still be able to run off a server for storage.  
      * NEXT: What if we switch the SSD drive to a mechanical hard drive. What kind of speed change do we see?   
    * Power harness - production model arrived from Nippon.  Will install and tested.  Quote from China Long in and order placed.         
 2.  Video Application

    * Thunderbolt - requires a new motherboard, processor (expensive). NEXT: Order for a test motherboard in order to test Thunderbolt - Brett to update.    
    * BTRFS - Rockstor video conference last week. Seems stable, the only problems are fringe applications. Development active. 
      * NEXT: sending a machine to Rockstor for testing/development.  Assembly tomorrow.        
 3.  Drive mounting - The first prototype looked good and functioned well, but was only 6-7 drives long.  Second prototype built (full 15-drives) and installed. Still need to make changes.   
 4.  SSD Caching & Tier

    * [45_drives_r_d_-_tiering_14_15](45_drives_r_d_-_tiering_14_15)  - numbers seem slower than expected (70-400 MB/s). 
      * NEXT: determine conditions when we got 1GB/s to determine what could be bottle necking our results.  Test internal transfer speeds within one machine. Make two identical tiered banks (10 drives).  
    * BTier  
      * NEXT: Brett to talk to Rockstor regarding Btier.
    * DM cache not working well. Need to investigate further and try different configurations. 
    * NEXT: Try B cache.

#####  Wants

*  FreeNAS on USB drive - required for appliance application (Ray J)

*  Staggered Spin up - more people are saying that 6 TB hard drives require staggered spin up.  Need to update wiki.  

*  Redhat certification - Brett   

*  Canadian Tire Video Project - up and running. Testing and everything is working fine.  

*  Walmart Project - Testing CEPH (object store).  Testing with 10 machines, and will report results when done.  

*  Rack Ears - Julie - organize calling customer to question regarding rack ears offering.   

*  Special Projects:
    * University of Santa Cruz - sending a machine with more RAM, upgrade to motherboard, 60 drive.  Need to ask him what he would like.    
    * Seagate for LSU project: Scheduled a meeting with next week.  To discuss testing and drivers.  They received cables and cards late last week.  They are going to simulate drives and cards and run experiments.  


##  2014 December 15

*  Attendees: Gavin Andrews,  Darrell Cormier, Rob MacQueen, Brett Kelly, Julie Murray, Stephen MacNeil, Doug Milburn, Chris McGean, Steve Lilley 

*  Apology: Alison MacDonald
##### Priorities

 1.  Highpoint driver - no problems. Final version received.  - CLOSED 
 2.  30-drives & Quite Model 

    * Chris continue testing.  Need to record process.  NFS seems slow (60 MB/s on 1 G connection) but this might be a config problem.    
    * Power harness - production model should be here from Nippon today.  Waiting on quote from China Long.         
 3.  Video Application

    * Thunderbolt - this week. Plug and play. 
    * Chris testing (FreeNAS, 30 drive) - continues.  
        * NEXT: Document, and measure exact results.  Then show Ray J. 
    * BTRFS - Rockstor video conference this wednesday at 1pm.     
 4.  Drive mounting - Prototype pieces received, but need to put together and test/iterate today.  

##### Wants

*  SSD Caching & Tier - Brett  
    * BTier works and is stable.  Simple. 40 drive raid with 5 SSD's striped together - 400 MB/s.  Looking very promising.  Should be able to get a theoretical 500,000 IOPS, but haven't seen this yet.  Continue testing, and contact expertise (Mr. Btier). 
      * [45_drives_r_d_-_caching_14_15](45_drives_r_d_-_caching_14_15)
      * Can we mix SSD brands? Sizes? NEXT: need to order new SSD's. 
      * NEXT: Brett to talk to Rockstor regarding Btier. 
    * DM cache not working well. Need to investigate further and try different configurations. 
    * NEXT: Try B cache.        
    * PCI fast caching cards - still haven't received.  
    * How many and how do we connect SSD's to motherboard?  Direct?    

*  Staggered Spin up - more people are saying that 6 TB hard drives require staggered spin up.  Need to update wiki.  

*  Redhat certification - Brett started investigating. Highpoint drivers may not be supported, but will look into this.  

*  Canadian Tire Video Project - 30 drives unit arrived.  They upgraded. They are installing and Stephen MacNeil to talk to Nolan this week.  

*  Rack Ears - Should we change the design to lock into a rack.  We can either add rack ears, or widen the face plate.  We need to ask customers which they prefer.  Julie - organize customer questionnaire and decision making before next meeting.  

*  Special Projects:
    * University of Santa Cruz - sending a machine.  
    * LSU - The Highpoint cards and cables were held up at customs.  Meeting with them this Friday.  To discuss testing and drivers.  

*  List of applications - 
    * Multiple Virtual Machines - how many machines? what hardware do we need? What is the load? How does our storage come into play?
      * All depends on what we are trying to do.  If they need more, we can add processor or RAM. 
      * NEXT: set up a virtual machine on a 45 drives unit.  Record results on wiki if it works or doesn't.      

##  2014 December 8

*  Attendees: Gavin Andrews,  Darrell Cormier, Rob MacQueen, Brett Kelly, Julie Murray, Stephen MacNeil, Doug Milburn, Chris McGean, Alison MacDonald, Steve Lilley 

##### Priorities

 1.  Highpoint driver  

    * Done, tested, and good to go. They need to send a final "non-beta" version.  
    * Geek Beat Q&A regarding driver issue - Doug, Darrell, and Brett to do a Q&A tomorrow.   
 2.  30-drives & Quite Model  

    * Power harness - Prototype built and got a quote from Nippon Labs. Asked for quote from China Long - first came back without SAS, but next batch will have SAS.            
    * Noise measurements - finished, and video complete.     
 3.  Video Application

    * To Do: Thunderbolt - need to find documentation, and start plugging in.  This week. 
    * Chris testing (FreeNAS, 30 drive) - very happy with results. Very smooth. Very little lagging. 1-2 Gb files. Reaching 350 Mb/s. Noise is not a problem. 
        * NEXT: Document, and measure exact results.  Then show Ray J. 
    * BTRFS - Rockstor will do a video conference with us on BTRFS.   
 4.  Drive mounting - Design is in Tech.  Brett to check if its in production.  

##### Wants

*  SSD Caching & Tier - Brett  
    * PCI fast caching cards will be in this week - integral SSD storing caching card. 
    * Tiering - benchmarkings - 4 SSDS, two tier, RAID 10. Result: 24,000 IOPS. More testing to do with files larger than the SSD tier. Also testing with striped RAID. Test with DM caching too.    

*  Earth quake ears to secure machine to rack - design complete, video complete. -COMPLETE    

*  Redhat certification - Brett started investigating. Highpoint drivers may not be supported, but will look into this.  

*  Canadian Tire Video Project - shipped 30 drive units. Will communicate this week. 

*  Special Projects:
    * University of Santa Cruz- get into conversation to determine what should be our "high performance" machine 
    * LSU - meeting with Seagate and LSU. Seagate hard drives causing troubles. Sending them Highpoint cards.

*  List of applications - 
    * Multiple Virtual Machines - how many machines? what hardware do we need? What is the load? How does our storage come into play? 


##  2014 December 8

*  Attendees: Gavin Andrews,  Darrell Cormier, Rob MacQueen, Brett Kelly, Julie Murray, Stephen MacNeil, Doug Milburn, Chris McGean, Alison MacDonald, Steve Lilley 

##### Priorities

 1.  Highpoint driver - have a full version of the driver.  Will complete testing this week with kernel 3.17.  

    * **Geek Beat Q&A - Chris** 
 2.  30-drives & Quite Model  

    * Power harness - Prototype built and got a quote from Nippon Labs. NEXT: get a quote from China Long.           
    * Noise measurements    
      * Industry standards for noise  
 3.  Video Application - meeting with Ray J regarding making machine for Video application.  

    * Want something that will work "out-of-the-box" easy. 
      * BTRFS - new file system we need to investigate (Rockstor).   
    * Thunderbolt - received a new thunderbolt card. Used for transferring data between 2 machines (2 Gb/sec). 
      * Ray J wants thunderbolt for video editing. 
      * Darrell and Brett to test with our machines.
 4.  Drive mounting - Brett designing prototype. Communicating with tech this afternoon to build prototype. 
 5.  Backblaze Machines - not here yet.  

    * They will be testing periodically over the next couple months with new cables. They were asked to report on progress.
    * To Do: Doug to talk to Tim.  Fix remaining Backblaze machines when they get here.

##### Wants

*  Rockstor - they don't have a hardware partner. Potential for co-development.   
    * Darrell has communicating with Rockstor. They are working on their software (Disaster recovery), and we will send him one machine to test.  
    * Doug talked to owner regarding next steps.  
    * NEXT: video conference with Rockstor to discuss road map, and BTRFS

*  New Cables - seeing some failures. Communicating with manufacture.
    * Expected cables from China Long this week.  Will test when they arrive (SAS compatible).    
    * Design seems good, but we are still seeing high error rate. Steven MacNeil will liaison with manufacturer. 

*  SSD Caching & Tier - Brett    

*  Earth quack ears to secure machine to rack. - Brett  

*  Redhat certification - Brett  

*  Canadian Tire Video Project 

*  Special Projects:
    * Geek Beat - need to communicate with ken to get project moving.  
    * University of Santa Cruz- on hold 


##  2014 December 1

*  Attendees: Gavin Andrews,  Darrell Cormier, Rob MacQueen, Brett Kelly, Julie Murray, Stephen MacNeil, Doug Milburn, Chris McGean, Alison MacDonald, Steve Lilley 

##### Priorities

 1.  Video Application - meeting with Ray J regarding making machine for Video application.  

    * Want something that will work "out-of-the-box" easy. 
      * BTRFS - new file system we need to investigate (Rockstor).   
    * Thunderbolt - received a new thunderbolt card. Used for transferring data between 2 machines (2 Gb/sec). 
      * Ray J wants thunderbolt for video editing. 
      * Darrell and Brett to test with our machines. 
 2.  Backblaze Machines - not here yet.  

    * They will be testing periodically over the next couple months with new cables. They were asked to report on progress.
    * To Do: Doug to talk to Tim.  Fix remaining Backblaze machines when they get here.
 3.  Rockstor - they don't have a hardware partner. Potential for co-development.   

    * Darrell has communicating with Rockstor. They are working on their software (Disaster recovery), and we will send him one machine to test.  
    * Doug talked to owner regarding next steps.  
    * NEXT: video conference with Rockstor to discuss road map, and BTRFS
 4.  New Cables - seeing some failures. Communicating with manufacture.

    * Expected cables from China Long this week.  Will test when they arrive (SAS compatible).    
    * Design seems good, but we are still seeing high error rate. Steven MacNeil will liaison with manufacturer. 
 5.  Highpoint driver - have a full version of the driver.  Will complete testing this week with kernel 3.17.  
 6.  Drive mounting - Brett designing prototype. Communicating with tech this afternoon to build prototype. 
 7.  30-drives & Quite Model  

    * Power harness - Prototype built and got a quote from Nippon Labs. NEXT: get a quote from China Long.           
    * Noise measurements - Measured 5 db.  Our original machine is about 20 db. Completed a video.   
      * [45_drives_r_d_-_noise_measurements_14_15](45_drives_r_d_-_noise_measurements_14_15)
      * Industry standards for noise and measuring noise - mostly used for safety standards.  Will continue investigating. 

##### Wants

*  SSD Caching & Tier - Brett    

*  60 Drive Unit

*  Earth quack ears to secure machine to rack. - Brett  

*  Redhat certification - Brett  

*  Canadian Tire Video Project 

*  More Hard Drives - Received, have lots now. - CLOSED      

*  Special Projects:
    * Geek Beat - need to communicate with ken to get project moving.  
    * University of Santa Cruz- on hold 




##  2014 November 24

*  Attendees: Gavin Andrews, Doug Milburn, Darrell Cormier, Rob MacQueen, Brett Kelly, Stephen MacNeil, Chris McGean, Steve Lilley

*  Absent: Julie Murray

##### Priorities

 1.  Backblaze Trip - all but 3 machines were complete (the demo, PCI bus card, power harness) These machines are coming back. 

    * Warming up to Highpoint cards
    * They will be testing periodically over the next couple months. They were asked to report on progress.
    * To Do: Doug to talk to Tim.  Fix remaining Backblaze machines when they get here.
 2.  Rockstor - Darrell and Brett met with Rockstor in San Francisco

    * Still small and developing, but open to working with us.  All API calls, very modular.
    * Could be useful for some of our vertical applications. 
    * No disaster recovery - should be ready for next release. 
    * Doug to talk to owner regarding next steps.     
 3.  New Cables - working    

    * Tested SAS capability with new cables and LSI cards and it works good. 
    * Design seems good, but we are still seeing high error rate. Steven MacNeil will liaison with manufacturer. 
    * Expected cables from China Long this week.  Will test when they arrive.   
 4.  Highpoint driver - have released a full version of the driver.  Will test this week.  
 5.  Drive mounting - Brett designing prototype
 6.  30-drives & Quite Model  

    * Power harness - Prototype built and will sent to Nippon Labs, not production ready.          
    * Noise measurements - Measured 5 db.  Our original machine is about 20 db.   
      * NEXT: Look for industry standards for noise and measuring noise.
      * NEXT: Will test again, and video.

##### Wants

*  SSD Caching - Brett adding to wiki page, testing with DM cache.  B cache on hold because it won't work.   

*  60 Drive Unit 

*  Canadian Tire Video Project 

*  More Hard Drives    

*  Special Projects:
    * Geek Beat, Ray J, University of Santa Cruz- on hold 

##  2014 November 10

*  Attendees: Gavin Andrews, Doug Milburn, Darrell Cormier, Rob MacQueen, Brett Kelly, Julie Murray, Stephen MacNeil 

*  Absent: Chris McGean, Steve Lilley

##### Priorities

 1.  Testing Driver - Driver is working. Finished.

    * BackBlaze Testing - All done, and work well.  
      * Steve MacNeil to talk to BackBlaze to test the new driver. Darrell and Brett going to BackBlaze next week.     
    * Highpoint Tests
      * Cannot boot if two cables are cut, only in Debian.  Works now - CLOSED 
      * Darrell to talk to Highpoint about removing the "Beta" from the driver. 
      * Highpoint is sending another driver that supplies staggered spin up,working. 
      * Tested a full 45 RAID array with CentOS 7.  Everything working with kernel up to 3.12.  
    * LSU Command Line Error - Once they remove web GUI then the machine will not boot up. Cannot replicate but asking for more information.  Steve to communicate with LSU. Why do 5 TB SMR drives do not work in RAID.   
    * NEXT: FreeNAS - serial numbers were not displaying correctly.  Steve MacNeil to talk to FreeNASs to solve this problem.  
 2.  NAS applications - Rockstor, FreeNAS, Openfiler.  Need to understand and document. Benchmark including SSD caching.
 3.  Rob's IOPS Project - Vertical applications: Video (GeekBeat, Chris, Ray J) vs. basic storage.  
 4.  Drive mounting - Brett designing prototype
 5.  New Cables - Test, and build BackBlaze sub assemblies. Make transition plan from old cables to new cables. 

    * Test SAS capability with new cables and LSI cards - Brett    
 6.  30-drives & Quite Model  

    * Power harness - Prototype built and will sent to Nippon Labs, not production ready.          
    * Noise measurements - Measured 5 db.  Our original machine is about 20 db.   
      * NEXT: Look for industry standards for noise and measuring noise.
      * NEXT: Will test again, and video.
    * No Redundant power supply right now - not sure if this will be an issue with customers.   

##### Wants

*  SSD Caching - Brett adding to wiki page, testing with DM cache.  B cache on hold because it won't work.   

*  60 Drive Unit 

*  Canadian Tire Video Project 

*  More Hard Drives    

*  Special Projects:
    * Geek Beat, Ray J, University of Santa Cruz- on hold 


##  2014 November 4 - Priorities Meeting

*  Attendees: Gavin Andrews, Doug Milburn, Darrell Cormier, Rob MacQueen, Brett Kelly, Chris McGean, Julie Murray, Stephen MacNeil, Steve Lilley  
 1.  Finish Highpoint Driver Testing - duel processor boards test.  Test after Highpoint fixes Debian-2 bad cable error.  
 2.  NAS Appliance - Rockstor (still in development), FreeNAS (associated with hardware sponsor), Openfiler 
 3.  SSD Caching - need to figure it out 
 4.  Vertical Application - video 
 5.  30 Drive Unit - need redundant and nonredundant versions.  
 6.  Drive Mounting - Brett and Doug to discuss.  
 7.  New Cables - SAS capability with LSI cards.   
    


##  2014 November 3

*  Attendees: Gavin Andrews, Doug Milburn, Darrell Cormier, Rob MacQueen, Brett Kelly, Steve Lilley, Chris McGean, Julie Murray

*  Absent: Stephen MacNeil 
##### Priorities

 1.  Testing Driver - Driver is working well so far. 

    * BackBlaze Testing - All done, and work well.  Works with Debian, 1 highpoint card with 5 drives directly into motherboard.  Driver works as expected. 
      * Steve MacNeil to talk to BackBlaze to test the new driver.  Waiting for new cables before going to BackBlaze.    
    * Highpoint Tests
      * Queue depth is defaulted to 1 on Highpoint cards - determined to be insignificant to throughput.  Most hard drives set to 32.  - CLOSED
        * Throughput experiments show no difference in performance, only max latency doubles in some random examples.  - CLOSED
        * Talk to LSU and Seagate regarding queue depth. 
      * Only problem - Cannot boot if two cables are cut, only in Debian.  Brett to replicate and then contact Highpoint.  
      * Test speed on old driver vs new - no speed difference between drivers. - CLOSED 
      * NEXT: Need to test a full 45 RAID array with CentOS 7.  Waiting for Hard Drives.  
      * NEXT: Highpoint is sending another driver that supplies staggered spin up, Need to test once we have it. 
    * LSI - Queue depth is set via drive. - CLOSED
    * LSU Command Line Error - cannot replicate but asking for more information. 
 2.  Next Step: NAS applications - Rockstor, FreeNAS, Openfiler.  Need to understand and document. Benchmark including SSD caching.
 3.  Rob's IOPS Project - Vertical applications: Video (GeekBeat, Chris, Ray J) vs. basic storage.  
 4.  30-drives & Quite Model  

    * Power harness - Prototype built and will sent to Nippon Labs, not production ready.          
    * NEXT: Noise measurements, need to find a standard or methodology to measure noise - Rob  
    * No Redundant power supply right now - not sure if this will be an issue with customers.   
 5.  Drive mounting - Brett 
 6.  New Cables - Test, and build BackBlaze sub assemblies. Make transition plan from old cables to new cables.  How many old cables do we have?   


##### Wants

*  Caching - Brett doing initial investigation - no update.

*  HBA Card- moving to an LSI 9201-16i alternative, and possibly designing our own HBA card - on hold. 
    * Mother board X9DRL-3f not booting with 3 LSI Cards - Steve to contact both board manufacturer and LSI. 

*  60 Drive Unit - on hold.

*  Canadian Tire Video Project - on hold   

*  Queue Depth - Steven and Brett investigating. Brett to collect references/materials and circulate to team.  
    * After investigation, we will contact Seagate and LSI to discuss optimization.   

*  Need 6TB Drives - Asked Seagate for special pricing, but slow to respond.  

*  Advanced Designs - Nippon Cables due Nov 8 (3 week lead time), SAS compatible.  NEED to test once cables get here.    

*  Special Projects:
    * Geek Beat, Ray J, University of Santa Cruz- on hold 


##  2014 October 27

*  Attendees: Gavin Andrews, Doug Milburn, Darrell Cormier, Rob MacQueen, Stephen MacNeil, Brett Kelly, Steve Lilley 

*  Apology: Chris McGean, Julie Murray
##### Priorities

 1.  Testing Procedure in Bad Machine - slight hang up (2min) but the machine isn't crashing.  Driver is working well so far. 

    * New driver working well with our default settings.   
    * BackBlaze Testing - need to test for Backblaze configuration to check if it works, and then pass onto backblaze to test.  
      * Highpoint Tests
        * Determine queue depth for old drivers (before change to QD = 1)
        * Test speed on old driver (between single drives, between decent sized raid arrays file large enough beyond caching or shut cache off)
        * Test Speeds, same as above, for new highpoint driver with QD=1
        * NEW DRIVER SET QD=4, then QD=32 does it crash, and what is speed???
        * Talk to highpoint
      * LSI 
        * Determine QD on a new install
        * Test speed symmetric to highpoint tests
    * Testing at LSU now - saying that if the web GUI is not installed (command line only) then their machine will not boot up.  Darrell to try to replicate problem, and will send all logs to Doug to send to Highpoint.  
 2.  HBA Card- moving to an LSI 9201-16i alternative, and possibly designing our own HBA card. 

    * Mother board X9DRL-3f not booting with 3 LSI Cards - Steve to contact both board manufacturer and LSI. 
 3.  30-drives & Quite Model  

    * Power harness - Prototype built and will send to Nip On Labs once finished, need to switch to different pins, Brett.       
    * To do: Noise measurements, need to find a standard or methodology to measure noise.   
    * Thermal measurements - Measurements and documentation complete
 4.  Rob's IOPS Project - Project starts today.  Rob is now a CBU employee working on site.  Will report to Sarah for hours, and Blair for project.      
 5.  60 Drive Unit - no update, on hold.
 6.  Power - - On hold    
 7.  Canadian Tire Video Project - on hold until HBA card decision.    
 8.  Drive mounting - on hold.   

##### Wants

*  Caching - Brett doing initial investigation.  

*  Queue Depth - Steven and Brett investigating. Brett to collect references/materials and circulate to team.  
    * After investigation, we will contact Seagate and LSI to discuss optimization.   

*  Need 6TB Drives - Asked Seagate for special pricing, but slow to respond.  

*  Advanced Designs - Nip On Cables due Nov 8 (3 week lead time), SAS compatible.  LSI is SAS compatible, but Highpoint is not.  Could be a marketing differentiator to push LSI once we have the new cables.  NEED to test once cables get here.    

*  Process Development 

*  Special Projects:
    * Geek Beat, LSU, Ray J, University of Santa Cruz- on hold 


##  2014 October 20

*  Attendees: Gavin Andrews, Julie Murray, Doug Milburn, Darrell Cormier, Rob MacQueen, Stephen MacNeil, Chris McGean 

*  Apology: Brett Kelly 
##### Priorities

 1.  HBA Card- moving to an LSI 9201-16i alternative, and possibly designing our own HBA card. 

    * Highpoint releasing new driver today, Darrell to test this week. 
    * Darrell is testing different RAID arrays and increasing by one drive to find where the driver fails.
    * Bad Machine Testing Machine - Brett to collect bad parts to make a testing machine to reproduce problems we are seeing in the field.  
      * Rob to test 4 drive RAID six, and add drives until it dies.  
 2.  30-drives & Quite Model  

    * Power harness - Prototype built and will send to Nip On Labs once finished, need to switch to different pins, Brett.       
    * To do: Noise measurements, need to find a standard or methodology to measure noise.   
    * Thermal measurements - Measurements and documentation complete
 3.  Rob's IOPS Project - We have a proposal, budget, and supervisor.  Sarah to send contract to Gavin and Rob will start on Monday.  Gavin, Rob, Sarah and Blair will set up a meeting to discuss project.     
 4.  60 Drive Unit - no update, on hold.
 5.  Power - Power measurements complete on 30, 45 and 60 drive units complete. - On hold    
 6.  Canadian Tire Video Project - on hold until HBA card decision.    
 7.  Drive mounting - on hold.   

##### Wants

*  Caching - Brett doing intitial investigation.  

*  Need 6TB Drives - Asked Seagate for special pricing, but slow to respond.  

*  Linux Learning 

*  Advanced Designs 
    * Testing Procedure is not picking up problems.  Darrell to develop new testing method with smaller RAID arrays for quicker test. Currently using 1 array with min data size.  


*  Process Development 

*  Special Projects:
    * Geek Beat, LSU, Ray J, University of Santa Cruz- on hold 

*  Vibration - To do: 10,000 rpm drive

*  Application - What kind of applications can we run on these machines? Virtual machines, MySQL, etc.

##  2014 October 15

*  Attendees: Gavin Andrews, Julie Murray, Brett Kelly, Doug Milburn, Darrell Cormier, Rob MacQueen, Stephen MacNeil, Chris McGean 

##### Priorities

 1.  HBA Card- moving to an LSI 9201-16i alternative, and possibly designing our own HBA card. 

    * Highpoint is trying to repair their divers still.  Better communication this week. 
 2.  60 Drive Unit - no update
 3.  Power - Power measurements complete on 30, 45 and 60 drive units.  Putting into a document and conclusions.  To be complete this week.    
 4.  Canadian Tire Video Project - on hold until HBA card decision.    
 5.  30-drives & Quite Model  

    * Power harness - Prototype built (waiting on connectors) and will send to Nip On Labs once finished.       
    * To do: Noise measurements, need to find a standard or methodology to measure noise. This week.   
    * NEXT: Thermal measurements - Measurements complete, documentation needs small edits 
 6.  Drive mounting - The test grating is complete.  

     * Experimentation with different sizes of grating, ongoing 
 7.  Rob's IOPS Project - We have a proposal, budget, and supervisor.  NEXT: Need to formalize work plan and submit - Gavin     

##### Wants

*  Caching - Brett to investigate
     *starting using benchmarking software fio, works well filesystem level caching

*  Need 6TB Drives - Asked Seagate for special pricing, but slow to respond.  

*  Linux Learning Project - David suggested Edx for training.  Free. [https://www.edx.org/course/linuxfoundationx/linuxfoundationx-lfs101x-introduction-1621#.VD18WvldXNu](https///www.edx.org/course/linuxfoundationx/linuxfoundationx-lfs101x-introduction-1621#.VD18WvldXNu)

*  Advanced Designs 

*  Process Development 
    * Auto Screw Gun - assembly complete, need to make some changes. In progress   

*  Special Projects:
    * Geek Beat - Chris went last week.    
    * LSU - communicating, but they are having some problems with RAID 5, 6TB drives.  Steve McNeil to talk to them this week.   
    * Ray J - on hold 
    * University of Santa Cruz - will do a project with a 60 drive unit. On hold until we fix our driver problem. 

*  Vibration - To do: 10,000 rpm drive

*  Application - What kind of applications can we run on these machines? Virtual machines, MySQL, etc.




##  2014 October 6

*  Attendees: Gavin Andrews, Julie Murray, Brett Kelly, Doug Milburn, Darrell Cormier, Rob MacQueen, Stephen MacNeil 

*  Apologies: Chris McGean (work trip) 
##### Priorties

 1.  Vibration - Papers have been reviews and changes made.  Just need approval and release. - MOVE TO MARKETING AND CLOSED 
 2.  60 Drive Unit 

    * Thermal completed - Results summed up. In rob's user file. - MOVE TO MARKETING AND CLOSE 
    * RAID 5 and 6 diver issues still a problem.  RAID 0 and under 40 HD's do not seem to be a problem.  The Highpoint driver is still buggy but they are indicating they will not support our product anymore. Calls to be done today. - Darrell to visit backblaze this week.  
 3.  Power - Power measurements complete on 30, 45 and 60 drive units.  Putting into a document and conclusions.  To be complete this week.      
 4.  Canadian Tire Video Project - no update  
 5.  30-drives & Quite Model  

    * Power harness - Prototype built and will send to Nip On Labs        
    * To do: Noise measurements, need to find a standard or methodology to measure noise. This week.   
    * NEXT: Thermal measurements - To do this week.  Need to wait for HD.  Julie to investigate getting more HD's.   
 6.  Drive mounting - need to redesigned the grid for a testing piece.  NEXT: Test piece will be complete today or tomorrow, then experimentation with different sizes of grating.     
 7.  Rob's Project - Sarah (CBU) is looking for a project supervisor. Blair MacNeil said he would take on the project if no one else does.  

##### Wants

*  Caching - In progress now that we have a stable driver.  Lead developer from CentOS will dial into one of our machines this week.  - Brett

*  Need 6TB Drives - Asked Seagate for special pricing, but slow to respond.  

*  Set Up White Paper - Complete - MOVE TO MARKETING AND CLOSED 

*  Linux Learning Project - David suggested Edx for training.  Free. [https://www.edx.org/course/linuxfoundationx/linuxfoundationx-lfs101x-introduction-1621#.VD18WvldXNu](https///www.edx.org/course/linuxfoundationx/linuxfoundationx-lfs101x-introduction-1621#.VD18WvldXNu)

*  Advanced Designs - top cover, front display, cables.

*  Process Development 
    * Auto Screw Gun - assembly complete   

*  Special Projects:
    * Geek Beat - Doug and Chris are going to Geek Beat this week.  
    * LSU - no update, Stephen will email.  
    * Ray J 
    * University of Santa Cruz - will do a project with a 60 drive unit. 

*  Vibration - To do: 10,000 rpm drive

*  Application - What kind of applications can we run on these machines? Virtual machines, MySQL, ect.
