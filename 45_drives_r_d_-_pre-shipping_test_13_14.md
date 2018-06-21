# Continued Testing Procedure Prior to Shipping

   *   Customer boot drive(s) is swapped for the 4TB test drive.\\
   

   *   System is booted with 45 drives inside unit.\\

   *   Once logged on, click: **Applications** → **System Tools** → **Terminal**\\

   *   In Terminal, type: **su**
press: **Enter**\\
\\       

   *   The system will prompt you for the root password type: **password**\\  
    
   

   *   Next, type: **cd SMARTSCAN**
press: **enter**\\
This will take you to the directory where the scanner is located.

   *   Next, type: **./smartscript.rev1.sh**
press: **enter**\\

{{:snapshot1.png?600}}

This will initialize the smartscript scan. 

   *   Minimize the Terminal.

   *   Click: **Places** → **Home Folder**
 

   *   Click: **Places** → **TEST VOLUME**
It will prompt you for Admin password.
type: **password**\\
press: **ok**\\
{{:snapshot3.png?600}}

   *   In the **Home Folder**, drag and drop **TestFile** into the **TEST VOLUME** directory.

{{:snapshot4.png?600}}

   *   Allow the entire file to copy over. This should take about an hour.

   *   Once the file has completed the transfer, return to the **Terminal** that was minimized, and press **Ctrl** + **z** This stops the script.

   *   After stopping the script, open the **SMARTSCAN** folder inside the **Home Folder**; you will see 2 text files; open them up.
{{:snapshot5.png?600}} 

   *   Compare the UDMA_crc errors on each drive. If the error numbers are unchanged everything is working properly; If the numbers have changed we know we have an issue with the port that the error is on.
{{:222_2_.png?800}}\\
#### If an error DOES occur

   *   1. Swap drives from another location in the unit. 

   *   2. If the error persists in the same location, replace HBA Rocket 750 card. 

   *   3. If the error again remains, swap cable.
\\  
#### If an error DOES NOToccur=== 

   *   Before shutting down, remove the transferred **TestFile** from the **TEST VOLUME** and empty the trash.  This insures that the RAID is clean for the next test.
   

   *   Finally, system is shut down and test boot drive is swapped with customer boot drive(s) and one last boot is completed before unit is sent to packaging.
\\

