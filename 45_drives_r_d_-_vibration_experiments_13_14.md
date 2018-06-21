# 45 Drives R&D - Vibration Experiments 13 14


Accelerometer Specification Sheet:\\
{{:adxl327.pdf|}}


Operational Amplifier Specification Sheet:\\
{{:lm358p.pdf|}}


## Cooling fan Vibration

#### In Air


{{:20140806_125814.jpg?500}}

X-axis: 0.26gs\\
Y-axis: 0.26gs\\
Z-axis: 0.26gs\\

Frequency: 48Hz

{{:20140806_125736.jpg?500}}

{{:20140806_125806.jpg?500}}


#### Inside Storinator



{{:20140811_142258.jpg?500}}

X-axis: 0.02gs\\
Y-axis: 0.12gs\\
Z-axis: 0.04gs\\

Frequency: 44Hz

{{:20140811_142429.jpg?500}}

{{:20140811_142529.jpg?500}}

## Procedure for Characterizing Vibration Measurements

   *   In order to accurately determine how much our storage server is vibrating, we must determine a range of measurements in which our storage server will fall within.\\

   *   To receive the largest magnitude of acceleration, the hard disk drive (HDD) under test was suspended from the ceiling using twine with a high elasticity. That way the HDD can move freely. (There is nothing obstructing its movement.)\\

   *   From here, the suspended HDD is written to using various benchmarks and large files.\\

   *   Next, the hard disk drive under test is mounted to a 100 pound slab of granite. This will give the HDD a large moment of inertia, thus preventing the drive to move freely. We expect the lowest magnitude of acceleration to come from this set of measurements.\\

   *   Now that the range has been established, acceleration readings are taken inside the storage server; on various drives with the cover on and off, and while performing read/write tasks.\\

   *   It is our expectation that the readings taken inside our storage server will be within the range of measurements taken while the drive was suspended in air and rigidly mounted to the slab of granite.\\

## To Date Summary

   *   As expected, the largest acceleration readings were observed while the Hard Drive was suspended in air. The lowest while mounted to a rigid steel plate that is 10 times the mass of the hard drive itself.
   *   Our range of measurements so far is between 0.01g's - 0.16g's. This includes read/write. - We expect the measurements taken inside the Storinator to be within this range.
   *   The Largest Reading inside the Storinator is 0.07 g's along the z-axis just above a running fan. - **July 10**

{{:20140710_145122.jpg?600}}

## Experiment Setup

{{:20140529_140734.jpg?500}}          {{:20140725_095944.jpg?500}}


   *   The HDD under test is suspended from the ceiling for the first part of the test. - This is expected to give the largest magnitude of acceleration.
   *   Next the hard drive under test is mounted to a thick piece of steel plate. - The is expected to give us the smallest magnitude of acceleration. 
   *   An ADXL327 accelerometer is mounted to the face of the HDD.
   *   The X & Y axis of the accelerometer are measuring lateral acceleration (The plane in which the platter and head move).
   *   The X, Y & Z inputs are ran through a non-inverting amplifier (LM358P) with a gain of 18 in order to view the signal more clearly.
   *   Platter and random head movements are captured by a Tektronix Oscilloscope and results are given below.
   *   For all measurements taken from oscilloscope the axis' are defined as follows:
      *      X-Axis: Blue Signal
      *      Y-Axis: Yellow Signal
      *      Z-Axis: Purple Signal
                                                                          

**Amplification Schematic:** 

{{:wiring_schematic.png?600}}


## Tested Hard Drive Models


   *   [Toshiba 1 TB HDD - DT01ACA100](Toshiba 1 TB HDD - DT01ACA100)\\

   *   [Hitachi 3 TB HDD - 0F12460](Hitachi 3 TB HDD - 0F12460)\\

   *   [Seagate 4 TB HDD - ST4000DM000](Seagate 4 TB HDD - ST4000DM000)\\

   *   [Western Digital 320 GB HDD - WD3200AAKX](Western Digital 320 GB HDD - WD3200AAKX)















## Obstacles

   *   Amplification Circut is working to some degree, however the Gain calculation does not match the actual gain of the signal - **June 25**\\
        * Calculated Gain: 18\\
        * Actual Gain: 5 - This was found by compairing unamplified signal with amplified signal under exact same conditions.
        * Various sized capacitors were tried on the input to the opamp to make sure we were not filtering out a portion of the signal.
        * Stephen ordered new opamps and capacitors today.



   *   The ADXL327 has a spec resonant frequency at 5.5kHz, however our scope is showing 60-80kHz which is unusually high.\\
   *   The accelerometer we have is showing a consistent reading vibrating at 900Hz-1.2KHz but I believe that is much too high. Samsung 500 GB SATA HDD's have a tight range of operating vibration:

- 0.25gs - 0.5gs @ 22-350Hz\\

The above frequencies are much lower than the readings we are getting on the scope.

   *   The accelerometer has a sensitivity of 400mV/g but noise levels spike into the 200mV range. We need to control the noise.\\
##### Noise

   *   The majority of our noise is being caused by the switching power supply. We are currently grounded to the bus bar in the milling-machine room in building 2 - We have confirmed that this is our best place for ground.\\
   *   There are noise spikes caused by the current switching on and off. We wrapped The output leads from our power supply around a large steel nail to create more of an inductive circuit. - The goal here is to oppose those unwanted current spikes when the power supply switches.\\
   *   We are getting a much cleaner signal after completing the above enhancements.

## Measurements of an Isolated Hard Disk - Unamplified

The next set of images show the lateral vibration about the Z-axis of a spinning Hard Drive with the accelerometer mounted to the rail. - **May 2014**

   *   The Hard Drive under test is the Western Digital WD3200AAKX 320GB @ 7200 RPM

{{:z-axis_rail_mount.jpg?600}}

{{:fft_vibrating.jpg?600}}

   *   The first image shows a pk-pk amplitude of about 24mV which corresponds to 0.06g

   *   The Power Spectrum shows a frequency of 120Hz.//

Next we mounted the accelerometer on the face and measured the lateral vibration (About the x-Axis) to be 18mV. This is slightly less than the 24mV; this maybe because the workbench was absorbing a portion of the vibration. We will suspend the hard drive from the ceiling and reattempt this measurement.

{{:face_mount_damped.jpg?600}}

#### Suspended Hard Drive Measurements


{{:20140529_140734.jpg?600}}

Now that the hard drive is suspended from the ceiling the measurements are slightly smaller than when the hard drive was measured on the desk.

**Face Mount:**                      For axis reference, see diagram above.
   *   x-axis amplitude: 16mV\\
   *   y-axis amplitude: 16mV\\
   *   z-axis amplitude: 14mV\\

**Rail Mount:**
   *   x-axis amplitude: 12mV\\
   *   y-axis amplitude: 16mV\\
   *   z-axis amplitude: 16mV\\

**Face Mount x-axis(Lateral Vibration):**\\

{{:20140529_100550.jpg?600}}\\

**Rail Mount Z-Axis (Lateral Vibration):**\\

{{:20140529_103625.jpg?600}}\\





# Back To:

[45drives_innovation_priorites ](45drives_innovation_priorites )\\
[45_drives](45_drives)
