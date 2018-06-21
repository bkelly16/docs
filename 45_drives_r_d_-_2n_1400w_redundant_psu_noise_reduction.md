# 2N 1400W PSU Noise Reduction

## Procedure
 1.  Record ambient room noise level
 2.  Place decibel meter 12 inches from PSU with **non-reduced** modules.
 3.  Plug in both modules to AC power.
 4.  Start server and wait 1 minute to hit steady state.
 5.  Record Noise level
 6.  Replace modules with **reduced RPM** modules.
 7.  Repeat steps 2 through 5

## Results

*  Ambient noise in test environment **55dB**

*  PSU without reduced RPM **72.5dB**

*  PSU with reduced RPM **67.5dB**

*  Measured 12 inches form PSU

## Analysis


*  Fan control circuit with altered resistor:{{:mtw-fan_speed_control_circuit.pdf|}}

*  Zippy reduced the resistance of R102 from 620ohms to 100ohms. From the circuit diagram above it can be seen that by reducing R102 the Gate voltage seen by transistor Q21 is also reduced. This reduced voltage will change the biasing of the transistor resulting in a reduced operating fan speed.

*  This reduced RPM is what allows for the noise reduction.However all this means is the PSU is pushing less of the heat generated out of the module, while the rest of the PSU is still generating the same amount of power.

*  Efficiency shouldn't change, however it is possible the increased module heat could result in higher failure rates.

*  Further thermal testing of the new PSU is required to ensure the module temps with the reduced RPMs are within allowed levels   

## Recommended Followup


*  Run similarly loaded units with and without reduced RPM modules and monitor modules temperatures for 24 hours.

*  Monitor power in and out as well to ensure that PSU efficiency has not changed.

