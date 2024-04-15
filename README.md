# Antmicro's USB-C Power Delivery Adapter

Copyright (c) 2024 [Antmicro](https://www.antmicro.com)

![](img/USB-C-power-adapter_top_iso_paper_black.png)

## Overview

The project includes open-source design files of a USB-C power adapter, engineered to utilize the [**USB-C power delivery**](https://www.usb.org/usb-charger-pd) protocol for delivering up to **75 watts** of power from a single power unit. The design features a **Nano-Fit** output connector, enabling support for a diverse array of devices while prioritizing maximum space efficiency.

The board was designed to enable standalone GPU operation with the [Antmicro's Thunderbolt to GPU Adapter](https://openhardware.antmicro.com/boards/thunderbolt-gpu-adapter/?tab=features).

The project was created using [KiCad 7.x](https://www.kicad.org/).

## Key features
* STMicroelectronics **STUSB4500** USB Power Delivery sink controller
* **QWIIC** connector for programmable PD profile selector
* Vishay **SIC477** high efficiency volatge buck regulator
* **Nano-Fit** output connector for maximum compability
* Additional **+5V** and **+3.3V** DC/DC converters delivering up to 500mA of continous output current

## Operation
To operate properly, the STUSB4500 PD sink controller must be programmed first. It features an onboard QWIIC connector dedicated to this task. The power delivery profile should be set to 20V for the default operation. Users have the option to bypass the SIC477 (enabling direct power output from the PD source) if 75 watts is excessive and select an alternative power delivery profile, with a maximum voltage of 12V.

## Project strcture
The main directory contains the KiCad project files, the licence and this readme file.
Remaining files are stored in following directories:
* `img`- contains Blender renders used in this readme
* `doc`- contains schematic in PDF format


## License
The project is included under the [Apache 2.0](/LICENSE) license.
