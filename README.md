# MicroBot

## Control Board
![Thumbnail](https://github.com/user-attachments/assets/09b98205-f68b-45e7-a73e-55534b9a6e08)

The Control Board interfaces the microcontroller (a XIAO or QT PY board) with a radio transceiver (nRF24L01 module) to act as the base of a compact, remote control robotics platform.
  The nRF24L01 board is wired to the standard SPI pins on the microcontroller with the CE and CSN pins wired to D6 and D7 respectively. For a compatible remote check out https://github.com/JoshuaStanleyRobotics/Robot-Remote
	
Breakout servo headers are included wired to pins D0-D5 to allow for controlling up to 6 servo motors at once. 
	On the bottom side of the board, there are solder pads to select the supply voltage (VCC) for the servo headers and motor driver.
		Solder the corresponding outer pad to the center pad to select either the voltage supplied to the board (VIN) or the regulated voltage (5V).
	Space for an optional bus capacitor is included to help smooth the VCC voltage. 

A second set of breakout pins include power and I2C connections for expansions boards.
  Note: I2C uses pins D4 and D5 so these will not be usable through the servo header while an I2C device is in use.

An optional double H-bridge driver chip is included for driving up to two brushed DC motors. 
  The direction pins for motor 1 are wired to pins D0 and D1 with the enable pin wired to pin D4. 
  The direction pins for motor 2 are wired to pins D2 and D3 with the enable pin wired to pin D5.

An optional voltage regulator (L7805) can be used if the supply voltage is outside of the microcontrollers input voltage range (> 6 volts).
  To bypass this voltage regulator, solder all three voltage select solder pads together on the underside of the board. 
  This will directly connect the input power to the 5V pin on the microcontroller.
