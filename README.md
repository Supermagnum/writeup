# writeup
just a list of components for K3NG rotor controller.

Controller box inside shack:
1X Arduino Leonardo

1X LCD2004A ,LCD 20*4 Characters for Arduino, with  HD44780 I2C bus. 

1x SparkFun Differential I2C Breakout - PCA9615 ( 5V power is sent by the 16 feet long ethernet cable )

1X DC bias insertion pcb, mounted in aluminium box, ferrites on DC cables.

--------------------------------------------

Remote:
 ABS plastic box. Rotates in azimuth.

Contents:
1x GY-291 ADXL345 Triple Axis Accelerometer, in a small aluminium box, mounted to the elevation axis gearbox shaft.

1x LSM303DLHC digital compass and accelerometer,in a small aluminium box.
Mounted close to the top. Non magnetic fasteners.
It's located ~ 121 mm above the steppers and the gearboxes.
I hope that it's enough to not be affected by the magnetic field from the steppers and worm gears.

1x SparkFun GPS Breakout - NEO-M9N, Chip Antenna,I2C adress 0x42.
Mounted in top of the remote box.

1x PCF8575 or PCA9555 I2C 16-Bit Digital Input Output Expander IC2 adress 0x3E, controlls :
2X Dual BTS7960 H Bridge stepper motor controllers ( uses 6 pins for control each + 2 pins for 5V and gnd )  Mounted in a aluminium box. Non magnetic fasteners.

2X NEMA 23 steppers 1.8° steps with 60:1 ( 0.03 ° output steps ) worm gear boxes for azimuth and elevation in this for mechanical strength:
https://github.com/Supermagnum/Nemabox/blob/main/README.md
Ferrite core on the motor cables.

DC bias extractor in a aluminium box, ferrite on the DC cables.

Note:
24 V DC power for the motors by coax cable ( Up to 10A 60 Vdc, 1.8 MHz to  470 MHz ): https://github.com/Supermagnum/Mjollnir.

Ferrites should be mix 51 or 61 ( European 4C65 ).
Those should also perhaps be used on the I2C bus cables, or shielded cable used.





