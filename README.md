# USB-C Power Delivery Adapter

Copyright (c) 2024 [Antmicro](https://www.antmicro.com)

![](img/USB-C-power-adapter_top_iso_paper_black.png)

## Overview

The USB-C Power Delivery Adapter is a module providing **12V 55W** continuous power output from a single [**USB-C PD**](https://www.usb.org/usb-charger-pd) power supply. 
The board was designed as a power option for [Antmicro's Thunderbolt to GPU Adapter](https://openhardware.antmicro.com/boards/thunderbolt-gpu-adapter/?tab=features) in stand-alone operation.

The design files were prepared in [KiCad 7.x](https://www.kicad.org/).

## Key features
* **12V 55W** output 
* Up to **75 Watts** achievable with active cooling
* Vishay [SIC477](https://www.vishay.com/docs/77113/sic47x.pdf) voltage buck regulator, operating at 94% efficiency
* STMicroelectronics [STUSB4500](https://www.mouser.com/datasheet/2/389/dm00489312-1799262.pdf) USB Power Delivery sink controller
* Additional **+5V** and **+3.3V** DC/DC converters delivering up to 500mA of continuous output current
* [QWIIC](https://www.sparkfun.com/qwiic) connector for programming the Power Delivery profile
* [Nano-Fit](https://www.molex.com/en-us/products/connectors/wire-to-board-connectors/nano-fit-connectors) output connector
* Overload and overtemperature protection

## Configuration
To operate properly, the PD sink controller must be first programmed.\
The [QWIIC](https://www.sparkfun.com/qwiic) connector is dedicated for I2C connection with STUSB4500.\
Programming instructions and tools can be found on the [manufacturer's website](https://www.st.com/en/interfaces-and-transceivers/stusb4500.html#overview).

Below, you can find the recommended profile for the PD sink:
```console
PDO1: 5V (+15%/-5%), 1.5A
PDO2: 20.0V (+10%/-20%), 3.0A
PDO3: 20.0V (+10%/-20%), 4.5A
PDO Number: 3
Flex Current: 2.0
External Power: False
USB Communication Capable: False
Configuration OK GPIO: 2
GPIO Control: 1
Enable Power Only Above 5V: False
Request Source Current: False
Factory Default: False
```

## Operation
The USB-C Power Delivery Adapter must be powered from a USB PD power supply with the following features:
  * capable of delivering **20 V** 
  * power rating exceeding the required load ( >60 W PD supply recommended)
  * supporting at least one of the programmed PD profiles

## Project structure
* `/.` -  contains the KiCad project files, the license and this README file
* `/img`- contains Blender renders used in this README
* `/doc`- contains schematics in PDF format


## License
The project is published under the [Apache 2.0](/LICENSE) license.
