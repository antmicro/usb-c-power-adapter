# USB-C Power Delivery Adapter

Copyright (c) 2024 [Antmicro](https://www.antmicro.com)

![](img/USB-C-power-adapter_top_iso_paper_black.png)

## Overview

The USB-C Power Delivery Adapter is a compact device providing **12V 55W** continous power output from a single [**USB-C PD**](https://www.usb.org/usb-charger-pd) power supply. The output power is expandable up to **75 Watts** by using an active colling sollution.

The board was designed to enable standalone GPU operation with the [Antmicro's Thunderbolt to GPU Adapter](https://openhardware.antmicro.com/boards/thunderbolt-gpu-adapter/?tab=features).

The project was created using [KiCad 7.x](https://www.kicad.org/).

## Key features
* **12V 55W** continous power output
* Vishay [SIC477](https://www.vishay.com/docs/77113/sic47x.pdf) high efficiency volatge buck regulator
* STMicroelectronics [STUSB4500](https://www.mouser.com/datasheet/2/389/dm00489312-1799262.pdf) USB Power Delivery sink controller
* Additional **+5V** and **+3.3V** DC/DC converters delivering up to 500mA of continous output current
* [QWIIC](https://www.sparkfun.com/qwiic) connector for programmable PD profile selector
* [Nano-Fit](https://www.molex.com/en-us/products/connectors/wire-to-board-connectors/nano-fit-connectors) output connector


## Configuration
To operate properly, the STUSB4500 PD sink controller must be programmed first. It features an onboard [QWIIC](https://www.sparkfun.com/qwiic) connector dedicated to this task. The power delivery profile should be set to 20V for the default operation. Users have the option to bypass the SIC477 (enabling direct power output from the PD source) if 75 watts is excessive and select an alternative power delivery profile, with a maximum voltage of 12V.

Programming instructions and tools can be found on the [manufacturer's website](https://www.st.com/en/interfaces-and-transceivers/stusb4500.html#overview).


## Operation
The USB-C Power Delivery Adapter must be powered from PD power supply capable of delivering **20V** power input. Make sure that used wall power supply is compatible with programmed profile. 

Used components provide onboard **overtemperature and overvoltage protections**. The device works stably at 55 Watts load with passive cooling. At 60 Watts power load, the device will turn itself off after 3 minutes.


## Project structure
The main directory contains the KiCad project files, the licence and this readme file.
Remaining files are stored in following directories:
* `img`- contains Blender renders used in this readme
* `doc`- contains schematic in PDF format


## License
The project is included under the [Apache 2.0](/LICENSE) license.
