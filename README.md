[![MCHP](images/microchip.png)](https://www.microchip.com)

# I2C Host Read/Write Data Using Interrupts

## Objective
This repository contains an example of bare metal source code for I2C as described in [Fix this link](https://www.microchip.com/wwwappnotes/appnotes.aspx?appnote=en1003077) document from Microchip.

The PIC18F47Q10 configured in I2C Host Mode using the MSSP1 peripheral and performing read operations. This example will use the client [MCP3221](https://ww1.microchip.com/downloads/en/devicedoc/20001732e.pdf), a 12-bit ADC, addressed in 7-bit mode.

## Related Documentation
- [TB3281 - Getting Started with I2C Using MSSP on PIC18](https://www.microchip.com/wwwappnotes/appnotes.aspx?appnote=en1003077)
- [PIC18-Q10 Product Family Page](https://www.microchip.com/design-centers/8-bit/pic-mcus/device-selection/pic18f-q10-product-family)
- [PIC18F47Q10 Data Sheet](http://ww1.microchip.com/downloads/en/DeviceDoc/40002043D.pdf)
- [MCP3221 - Low-Power 12-Bit A/D Converter](https://ww1.microchip.com/downloads/en/devicedoc/20001732e.pdf)
- [PIC18F47Q10 Code Examples on GitHub](https://github.com/microchip-pic-avr-examples?q=pic18f47q10-cnano&type=&language=)

## Software Used
- MPLAB® X IDE 5.50 or newer [(microchip.com/mplab/mplab-x-ide)](http://www.microchip.com/mplab/mplab-x-ide)
- MPLAB® XC8 2.31 or newer [(microchip.com/mplab/compilers)](http://www.microchip.com/mplab/compilers)
- MPLAB® Code Configurator (MCC) 4.1.0 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- MPLAB® Code Configurator (MCC) Device Libraries PIC10 / PIC12 / PIC16 / PIC18 MCUs 1.81.7 or newer [(microchip.com/mplab/mplab-code-configurator)](https://www.microchip.com/mplab/mplab-code-configurator)
- Microchip PIC18F-Q Series Device Support 1.3.89 (Check if this version is correct) or newer [(packs.download.microchip.com/)](https://packs.download.microchip.com/)

## Hardware Used

- Curiosity Nano Base for Click Boards™ [(AC164162)](https://www.microchip.com/Developmenttools/ProductDetails/AC164162)
- PIC18F47Q10 Curiosity Nano [(DM182029)](https://www.microchip.com/Developmenttools/ProductDetails/DM182029)
- PICkit™ Serial I2C™ Demo Board [(PKSERIAL-I2C1)](https://www.microchip.com/DevelopmentTools/ProductDetails/PKSERIAL-I2C1)

## Setup
The PIC18F47Q10 Curiosity Nano Development Board is used as the test platform.

<br><img src="images/PIC18F47Q10_CNANO.png" width="600">

The following configurations must be made for this project:
- Clock
	- Oscillator Select: HFINTOSC
	- HF Internal Clock: 4 MHz
	- Clock Divider: 1
- MSSP1
	  - Serial Protocol: I2C
    - Mode: Host
    - I2C Clock Frequency: 100000
- Watchdog Timer: disabled
- Low-voltage Programming: disabled

|Pin           | Configuration      |
| :----------: | :----------------: |
|RB1 (SCL1)    | With Pull Up  & Open Drain     |
|RB2 (SDA1)    | With Pull Up  & Open Drain     |

## Operation
1. Connect the board to the PC.

2. Open the *pic18f47q10-cnano-i2c-read-write-int-bare.X* project in MPLAB® X IDE.

3. Configure the project properties:
    - Right click on the project and click *Properties*
    - Select the device pack in the *Packs* tab
    - Select the *PIC18F47Q10 Curiosity Nano* (click on the SN) in the *Hardware Tool* tab
    - Select the compiler version in the *Compiler Toolchain* tab
    - Click *OK* to save the changes
    
<br><img src="images/properties.png" width="600">

4. Program the project to the board: right click on the project and click *Make and Program Device*

Demo:

</br><img src="images/rw-int.gif" width="600px" alt="Hardware Setup"/>

## Summary
This project is an illustration for a basic use case based around MSSP1.
