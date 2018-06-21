## Faulty Western Digital Red WD30EFRX Test

*July 24, 2014

   *   A known faulty Western Digital 3TB Red Drive was placed in running storage server running CentOS 6.5 with Rocket 750 HBA Cards. The HighPoint Web GUI and CentOS Disk Utility fails to pick up the faulty drive.
   *   When server is rebooted the login screen fails to come up, the machine hangs on an error screen.
{{:20140724_121616.jpg?600}}

   *   Rocket 750 HBA cards were then swapped for LSI-9201 HBA Cards, the system turned on and booted up with the bad drive connected but still did not pick up on the CentOS disk utility.


## Faulty Toshiba DT01ACA100 Test

### Rocket 750

**July 23, 2014**

*  A known bad 1 TB Toshiba (dt01aca100) Disk Drive was placed in Storinator 4.0\\
*  The bad drive was placed within a unit with 44 known, working, and even raided drives.\\
*  The other Drives were Seagate 4TB (st4000md000).\\

#### TEST hot plugged bad HDD on Rocket 750

*  The Storinator was booted up without the bad Toshiba.
*  Toshiba was then hot swapped in the unit.
*  CentOS Disk utility, nor the Highpoint web GUI detected the bad HDD.

#### TEST cold plugged bad HDD on Rocket 750

*  Attemped to boot Storinator with bad HDD
*  The system does not boot, hangs on this error message below. *Left hang for over 2 hours*
{{:highpointbaddriveerror.jpg?900|}}


*Both rocket cards were switched with brand new ones, and the location of the bad HDD was changed... Same result occurred*

### LSI

**July 23, 2014**

*  A known bad 1 TB Toshiba (dt01aca100) Disk Drive was placed in Storinator 4.0\\
*  The bad drive, was placed within a unit with 44 known, working, and even raided drives.\\
*  The other Drives were Seagate 4TB (st4000md000).\\

#### TEST hot plugged bad HDD on LSI

*  The Storinator was booted up without the bad Toshiba.
*  Toshiba was then hot swapped in the unit.
*  CentOS Disk Utility detected Bad hard drive.
{{:badharddrivelsi.jpg?900|}}

#### TEST cold plugged bad HDD on LSI

*  Attemped to boot Storinator with bad HDD.
*  The system takes longer than usual to boot.
*  System boots, and detects which sectors are faulty on HDD.
{{:lsitest.jpg?900|}}





