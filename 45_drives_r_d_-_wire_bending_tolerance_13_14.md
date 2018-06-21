# Ideas Limited Cable Test

\\
11 July 2014\\
\\

   *   Three Cables were taken out of the unit and tested to see if they were operating normally (12 Connectors)
   *   Initially when cables were connected to 12 Hitachi 3TB Hard Drives everything operated normally; the 12 drives showed up on the HighPoint web GUI and in CentOS Disk utility even with repeated re scanning.
   *   A sample read/write was done and everything was ok.
   *   Next the cables were moderately stressed at the connector, (Bent cables back and forth 180 degrees to the left and right about 10 times.
   *   All 12 drives were detected and operated normally even under read/write. 
   *   Finally maximum stress was applied to the cables at the connector ( Spun clockwise and counter clockwise about 15-20 times ) - The Shielding was completly off in the spot that was stressed.
   *   10 out of the 12 drives failed at this point - only 2 of them were displayed on the web GUI & Disk Utility
   *   None of the drives failed until the wire was completly bared of its shielding, even when moderate stress was applied the cables performed to spec. 

{{:20140711_155746.jpg?500}}   {{:20140711_155837.jpg?500}}

## 22 AWG Aluminum Stranded Un-Shielded Wire

**The following bending tolerance was found from multiple sources on the web.**

The minimum bend radius for 22 AWG Aluminum Stranded un-shielded wire is 4 times the overall diameter of the cable, if the cable diameter is less than 0.125" - this is our case.

   *   Diameter of our power cables: 0.0253"\\
   *   Multiplier: 4x

**Calculation:**

0.0253" * 4 = 0.1012" - This is the minimum bend radius for our power cables.\\

0.1012" * 2 = 0.2024" - This is the minimum diameter in which you can bend the wire without kinking or causing whiteness on the cable.\\

Breaking Force of 22 AWG Aluminum Stranded Wire: 18 LBS\\

Source: The Okonite Company - Installation Practices

## 30 AWG Aluminium Shielded SAS Wire

The minimum bend radius for 30 AWG Aluminum shielded wire is 10 times the overall diameter of the cable, if the cable diameter is less than 0.75" - this is our case.

   *   Diameter of our SAS cables: 0.0100"\\
   *   Multiplier: 10x

**Calculation:**

0.0100" * 10 = 0.1000" - This is the minimum bend radius for our power cables.\\

0.1000" * 2 = 0.2000" - This is the minimum diameter in which you can bend the wire without kinking or causing whiteness on the cable.\\


Source: The Okonite Company - Installation Practices









