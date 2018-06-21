#  45 Drives R&D Power Experiments 13 14


{{:20140606_103744.jpg?450}}{{:20140714_135030.jpg?450}}


## Power droop test

**July 23, 2014**\\
\\
Storinator 4.0 was loaded with 43 Seagate 4TB HDDs (-2 for the tap in power supply)\\
\\
#### Seagate spec.

   *   ±5% on 5 VDC = 4.75v - 5.25v\\
   *   ±10% on 12 VDC = 10.8v - 12.2v\\
\\
#### Test (read/write)

   *   2, 15 Drive Seagate 4TB  striped arrays were created.\\
   *   Random read/write tests, and benchmarks were performed on the array.\\
   *   Voltage readings were captured on oscilloscope.\\
   *   All voltage readings remained within HDD specifications during test.\\
   *   Voltage trigger was set up on scope for + or - 5% on the 5 volt, large file was copied to array overnight and scope did not pick up any extremes.
\\
#### Test (power on/off)

   *   The machine remained loaded with Seagate drives, including the arrays.\\
   *   Storinator was turned on and off repeatedly 20 times.\\
   *   There was no voltage drop occurring on drive initial spin-up during these tests.\\
\\
#### Test (bad HDD Toshiba dt01aca100)

   *   The machine remained loaded with Seagate drives, including the arrays.\\
   *   A known bad hard dive was hot swapped into the machine.\\
   *   Voltage once again, remained within specifications.\\

\\ 

*These experiments were repeated on different power harnesses, 24 and 20 pin, throughout the machine*\\
\\
\\

**July 22, 2014**\\
\\
Seagate spec.

±5% on 5 VDC = 4.75v - 5.25v\\
±10% on 12 VDC = 10.8v - 12.2v\\ 
\\
12VDC (read/write on single drive)\\
Highest Reading: 12.2v   
Lowest Reading:  11.7v\\ 
\\
5VDC (read/write on single drive)\\
Highest Reading: 5.11v   \\
Lowest Reading:  4.82v\\
\\

**July 21, 2014**\\
\\
\\
{{:droop_test_2.png|}}

## Triple Redundant Supply Model: M3W-6950P Specifications:

   *   DC Output: 950 Watts

   *   12 Volt Line Max Current: 60 Amps

   *   5 Volt Line Max Current: 56 Amps

   *   5 & 3.3 Volt Max Current Combined: 75 Amps

   *   Current Overload Protection: 110 - 160% of max current.

   *   Efficiency: 68% at max load. 


## Standard Supply  Model: PSL-6850P Specifications:

   *   DC Output: 850 Watts

   *   12 Volt Line Max Current: 60 Amps

   *   5 Volt Line Max Current: 45 Amps

   *   5 & 3.3 Volt Max Current Combined: 70 Amps

   *   Current Overload protection: 110 - 160% of max current.

   *   Efficiency: 71% at max load.

## Power Consumption on the 60 Hard Drive Machine:

   *   **The Standard Power Supply would not run more than 50 hard drives, the power needed for start-up was too large. The Triple Redundant Supply was needed to run all 60 Drives.**

#### Total Power to the 60 Hard Drive Machine:

   *   Start-up: 1530 Watts
   *   Steady-state: 407 Watts

####  Start-up Current on 60 Drives:

      *   12 Volt Line: 87.2 Amps 
      *   5 Volt Line:  21.8 Amps
    

   *   Start-up Current on 120 Volt AC receptacle: 13.2 Amps\\

#### Steady-state Current on 60 Drives:

      *   12 Volt Line: 14.2 Amps
      *   5 Volt Line:  14.3 Amps

   *   Steady-state Current on 120 Volt AC receptacle: 3.56 Amps\\

#### Current Draw for an Individual Hard Drive:

   *   **12 Volt Line:**\\
      *   Start-up: 1.46 Amps\\
      *   Steady-state: 0.18 Amps\\

   *   **5 Volt Line:**\\
      *   Start-up: 0.42 Amps\\
      *   Steady-state: 0.28 Amps\\

## Power Consumption for Major Hardware Components other than Hard Drives:

   *   Motherboard/Processor - Supermicro X9SCM-F/Intel Core i3-3240: **123 Watts** - 12, 5, 3.3, -5 Volt Lines.\\

   *   Motherboard Fan - Intel E97379: **7.2 Watts** - 12 Volt Line.\\

   *   Cooling Fans - Top Motor DF121225BH: 7.8 Watts - 12 Volt Line, we are using 6 fans for a total of **46.8 Watts.**\\

   *   Host Bus Adaptor - Rocket 750: 11 Watts - 12 Volt Line, we are using 2 Rocket 750's for a total of **22 Watts.**\\



### Back To:

[45drives_innovation_priorites ](45drives_innovation_priorites )\\
[45_drives](45_drives)
