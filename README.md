# writeup
just a list of components for K3NG rotor controller.

Controller box inside shack:
1X Arduino Mega 2560

2x SPDT on-off-on momentary switches for manual up,down,CW and CCW rotation.

1X LCD2004A ,LCD 20*4 Characters for Arduino, with  HD44780 I2C bus. 

1x SparkFun Differential I2C Breakout - PCA9615 ( 3,3V DC and 5VDC power is sent by the 16 feet long ethernet cable, details in notes )

1X DC bias insertion pcb, mounted in aluminium box, ferrites on DC cables.


--------------------------------------------


Remote:
ABS plastic box. Rotates in azimuth.

Contents:

1x SparkFun Differential I2C Breakout - PCA9615 ( 3,3V DC and 5VDC power is received by the 16 feet long ethernet cable, details in notes )

1x GY-291 ADXL345 Triple Axis Accelerometer, in a small aluminium box, mounted to the elevation axis gearbox shaft.

1x LSM303DLHC digital compass and accelerometer,in a small aluminium box.
Mounted close to the top. Non magnetic fasteners.
It's located ~ 121 mm above the steppers and the gearboxes.
I hope that it's enough to not be affected by the magnetic field from the steppers and worm gears.

1x SparkFun GPS Breakout - NEO-M9N, Chip Antenna,I2C adress 0x42.
Mounted in top of the remote box.

1x PCF8575 or PCA9555 I2C 16-Bit Digital Input Output Expander IC2 adress 0x3E, controlls:
1X TB6600 H Bridge stepper motor controllers per stepper motor.  
Mounted in a aluminium box. These stepper controllers requires 5VDC for the electronics to work.
Please read notes.


2X NEMA 23 steppers 1.8° steps with 60:1 ( gives 0.03 ° output steps ) worm gear boxes for azimuth and elevation in this for mechanical strength:
https://github.com/Supermagnum/Nemabox/blob/main/README.md
Ferrite cores on the motor cables. 12V or 24 V drive, PWM.

DC bias extractor in a aluminium box, ferrite on the DC cables.

---------------------------------------------------

Notes:
5VDC and 3.3VDC is supplied by Ethernet cable.
Reference: https://learn.sparkfun.com/tutorials/qwiic-differential-i2c-bus-extender-pca9615-hookup-guide?_ga=2.13469055.99411050.1603366417-1824621102.1602464067
VDD A-B jumper trace has been cut.
Separate power supply (3.0-5.5V) is supplied to VDD_B, while VDD_A remains at 3.3V.
VDD_B voltage is connected to a twisted pair of the Ethernet cable and sent to the slave nodes.

The IO expanders is currently not supported in the K3NG rotor controller code.
Feature request: https://github.com/k3ng/k3ng_rotator_controller/issues/82

12V or 24 V DC power for the motors by coax cable ( Up to 10A 60 Vdc, 1.8 MHz to  470 MHz ): 
https://github.com/Supermagnum/Mjollnir.

Ferrites should be mix 51 or 61 ( European 4C65 ).
Those should also perhaps be used on the I2C bus cables, or shielded cable used.

All aluminium boxes and grounds must be tied together.

Option:

2X Omron E6B2-CWZ6C 2000P incremental rotary encoders 
could possibly be used in combination with the mentioned sensors.
They give 2000 pulses per 360° of rotation, 
that's around 5.5 steps per degree, 0.18° resolution.

The ideal whould be a resolution of 0.03 °, but that involves sensors with 10,000 steps per 360 turn.
This one is capable of that, but it's very expensive and overkill for this application.
https://www.digikey.com/en/products/detail/sensata-bei-sensors/01005-1066/6244934





