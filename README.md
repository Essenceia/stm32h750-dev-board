# 10 year Anniversary developpement board

Minimal custom arm m7 devloppement board designed as a 10 year anniversary present. 

Selected MCU : STM32H750VBT6TR 

MCU package :  LQFP-100 

Requirements :

- SWD debug connected with pinout compatible with native 20 pin J-Link probe

- Route all remaining mcu pins to female connectors 

## Schematics

Schematic : [schematics](/doc/schematic.pdf)

## PCB

Resulting pcb, front : 

![fount!](/doc/front.png)

back :

![back!](/doc/back.png)

## SWD - J-Link

SWD Connector Pinout:
![connector!](/doc/swd_jlink.svg)

The following table lists the J-Link / J-Trace SWD pinout.
|Pin|Signal|Type|Description|
|---|------|----|-----------|
|1|VTref|Input|This is the target reference voltage. It is used to check if the target has power, to create the logic-level reference for the input comparators and to control the output logic levels to the target. It is normally fed from Vdd of the target board and must not have a series resistor.|
|2|Vsupply|NC|This pin is not connected in J-Link. It is reserved for compatibility with other equipment. Connect to Vdd or leave open in target system.|
|3|Not used|NC|This pin is not used by J-Link. If the device may also be accessed via JTAG, this pin may be connected to nTRST, otherwise leave open.|
|5|Not used|NC|This pin is not used by J-Link. If the device may also be accessed via JTAG, this pin may be connected to TDI, otherwise leave open.|
|7|SWDIO|I/O|Single bi-directional data pin.|
|9|SWCLK|Output|Clock signal to target CPU. It is recommended that this pin is pulled to a defined state of the target board. Typically connected to TCK of target CPU.|
|11|Not used|NC|This pin is not used by J-Link. This pin is not used by J-Link when operating in SWD mode. If the device may also be accessed via JTAG, this pin may be connected to RTCK, otherwise leave open.|
|13|SWO|Input|Serial Wire Output trace port. (Optional, not required for SWD communication.)|
|15|nRESET|I/O|Target CPU reset signal. Typically connected to the RESET pin of the target CPU, which is typically called "nRST", "nRESET" or "RESET". This signal is an active low signal.|
|17|Not used|NC|This pin is not connected in J-Link.|
|19|5V-Supply|Output|This pin is used to supply power to some eval boards.|

Pins 4, 6, 8, 10, 12, 14, 16, 18, 20 are GND pins connected to GND in J-Link. They should also be connected to GND in the target system.


## Future improvements ideas

- After adding support for USB 3.0 and up switch usb b mini for thunderbolt
