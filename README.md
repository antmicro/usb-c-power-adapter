# Antmicro's USB-C Power Adapter

Copyright (c) 2023 [Antmicro](https://www.antmicro.com)

![](img/USB-C-power-adapter_top_iso_paper_black.png)

## Overview

The project includes open-source design files of a USB-C power adapter, engineered to utilize the **USB-C power delivery** protocol for delivering up to **75 watts** of power from a single power unit. The design features a **Nano-Fit** output connector, enabling support for a diverse array of devices while prioritizing maximum space efficiency.

The board was designed to enable standalone GPU operation with the [Antmicro's Thunderbolt to GPU Adapter](https://openhardware.antmicro.com/boards/thunderbolt-gpu-adapter/?tab=features).

The project was created using [KiCad 7.0](https://www.kicad.org/).

## Key features
* STMicroelectronics **STUSB4500** USB Power Delivery sink controller with I2C programmable PD profile selecting
* Viashy SIC477 high efficiency volatge buck regulator
* Nano-Fit output connector for maximum compability
* Additional +5V and +3.3V DC/DC converters delivering up to 500mA of continous output current

## Block diagram


## Project strcture
The main directory contains the KiCad project files, the licence and this readme file.
Remaining files are stored in following directories:
* `img`- contains Blender renders used in this readme
* `doc`- contains schematic in PDF format


## License
The project is included under the [Apache 2.0](/LICENSE) license.
