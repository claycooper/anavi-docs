# ANAVI Info uHAT

**An open source hardware Raspberry Pi add-on board with mini OLED display, buttons and slots for sensors**

---

# DISCLAIMER

Raspberry Pi and the Raspberry Pi logo are registered trademarks of the Raspberry Pi Foundation. ANAVI, the ANAVI logo and combinations thereof, are registered trademarks of Leon Anavi. Other product names may be trademarks of others and the rights belong to their respective owners.

The information in this document is provided in connection with Anavi products. No license, express or implied or otherwise, to any intellectual property right is granted by this document or in connection with the sale of Anavi products.

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://www.creativecommons.org/licenses/by-sa/3.0/.

ANAVI Info uHAT hardware design is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.

The software examples are released under MIT and the rest of the software is available under GPLv3.

It is possible that the pictures in this manual differ from the latest revision of the board.

The product described in this document is subject to continuous development and improvements. All particulars of the product and its use contained in this document are given by Anavi in good faith. However all warranties implied or expressed including but not limited to implied warranties of merchantability or fitness for purpose are excluded. This document is intended only to assist the reader in the use of the product. Anavi shall not be liable for any loss or damage arising from the use of any information in this document or any error or omission in such information or any incorrect use of the product.

This evaluation board/kit is intended for use for engineering development, demonstration, or evaluation purposes only and is not considered by Anavi to be a finished end-product fit for general consumer use. People handling the product must have electronics training and observe good engineering practice standards. As such, the goods being provided are not intended to be complete in terms of required design-, marketing-, and/or manufacturing-related protective considerations, including product safety and environmental measures typically found in end products that incorporate such semiconductor components or circuit boards.

There is no warranty for the design materials and the components used to create ANAVI Info uHAT. They are considered suitable only for ANAVI Info uHAT.

---

# Overview

## Introduction

ANAVI Info uHAT is a low-cost, open source Raspberry Pi add-on board with mini OLED display, 3 buttons, red and green indication LEDs as well as slots for various sensors. Each kit includes 0.96" yellow-blue I²C OLED display with resolution of 128x64 individual white OLED pixels. This is a low power consumption display that makes its own light abd therefore no additional backlight is required. Additional slots allows attaching various I²C sensors for temperature, humidity, light and barometric pressure as well as a UART pins for easy serial communication. ANAVI Info uHAT follows the official Raspberry Pi uHAT mechanical specification with a valid ID EEPROM.

ANAVI Info uHAT supports multiple sensors for temperature, humidity, barometric pressure, and light. Getting started is easy: just plug it into a Raspberry Pi with your bare hands and follow the instructions in the user manual. No soldering is necessary, and no tools are required.

## Features

ANAVI Info uHAT Raspberry Pi HAT includes:

* Replaceable 0.96" yellow-blue I²C OLED display
* Slots for up to 3 plug-and-play I²C sensors
* UART pins for serial communication
* Green and red indication LEDs
* 3 buttons
* Follows uHAT mechanical specification with a valid ID EEPROM
* Excellent software support, documentation, and open source examples

## Supported Raspberry Pi Versions and Models

ANAVI Info uHAT is compatible with the following Raspberry Pi versions and models:

* [Raspberry Pi 400](https://www.raspberrypi.com/products/raspberry-pi-400/)
* [Raspberry Pi 4 Model B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)
* [Raspberry Pi 3 Model B](https://www.raspberrypi.com/products/raspberry-pi-3-model-b/)
* [Raspberry Pi 2 Model B](https://www.raspberrypi.com/products/raspberry-pi-2-model-b/)
* [Raspberry Pi Zero](https://www.raspberrypi.com/products/raspberry-pi-zero-w/)
* [Raspberry Pi Zero W](https://www.raspberrypi.com/products/raspberry-pi-zero-w/)
* [Raspberry Pi Zero 2 W](https://www.raspberrypi.com/products/raspberry-pi-zero-2-w/)
* [Raspberry Pi Model B+](https://www.raspberrypi.com/products/model-b-plus/)
* [Raspberry Pi Model A+](https://www.raspberrypi.com/products/model-a-plus/)

ANAVI Info uHAT is **NOT** compatible with the earlier 26-pin models of Raspberry Pi 1 Model B & A's.

## Target Market

ANAVI Info uHAT is a Raspberry Pi HAT suitable for existing Raspberry Pi customers interested in home automation, software development and Internet of Things. The board is appropriate for embedded programming enthusiasts, GNU/Linux gadget fans, students as well as web and/or mobile app developers.

## Board Version

Revision 1.1 of ANAVI Info uHAT was used while writing this document. It is possible that it is outdated so it is always recommended to check the latest sources from the GitHub page of the board.

# Safety Guide

## Warnings

* This product shall only be connected to a compatible Raspberry Pi.

## Instructions for safe use

* Do not expose this product to water or moisture, and do not place it on a conductive surface whilst in operation.
* Do not expose this product to heat from any source; it is designed for reliable operation at normal room temperatures.
* Take care while handling this product to avoid mechanical or electrical damage to the printed circuit board and connectors.
* Avoid handling this product while it is powered. Only handle by the edges to minimize the risk of electrostatic discharge damage.

## Electrostatic Warning

ANAVI Info uHAT is shipped in a protective bag. The HAT as well as the Raspberry Pi must **NOT** be exposed to high electrostatic potentials. A grounding strap or similar protective device should be worn when handling the board. Avoid touching the component pins or any other metallic element.

# Getting Started

## Requirements

In order to setup ANAVI Info uHAT the following items are required:

* Compatible Raspberry Pi
* microSD card with compatible image
* USB power supply

Additionally you may attach USB mouse, keyboard, HDMI monitor or addition peripheral devices to your Raspberry Pi. It is recommended to use 2.5A (2500mA) power supply.

## Supported Peripherals

ANAVI Info uHAT Raspberry Pi HAT has an MCP3002 analog-to-digital converter (ADC) and two connectors for capacitive soil moisture sensors. Up to 2 I2C sensors can be also easily attached to the pHAT.

### Sensors

The officially supported I2C sensor modules by ANAVI Info uHAT are:

* Temperature and barometric pressure (BMP180)
* Temperature and humidity (HTU21)
* Light (BH1750)

You may also attach any other I2C sensors but you will have to take care of their software integration.

#### Temperature Sensor

BMP180 is I2C sensor capable of measuring both temperature and barometric pressure.

Using 4 Dupont jumper wires connect BMP180 to one of the 3 I2C slots on ANAVI Info uHAT as follows:

| BMP180   | ANAVI Info uHAT |
| -------- |:--------------- |
| VIN      | 3.3V            |
| GND      | GND             |
| SCL      | SCL             |
| SDA      | SDA             |

#### Humidity Sensor

HTU21 (SHT21) is I2C sensor capable of measuring both humidity and temperature.

Using 4 Dupont jumper wires connect HTU21 to one of the 3 I2C slots on ANAVI Info uHAT as follows:

| HTU21    | ANAVI Info uHAT |
| -------- |:--------------- |
| VIN      | 3.3V            |
| GND      | GND             |
| SCL      | SCL             |
| SDA      | SDA             |

#### Light Sensor

BH1750 is a light sensor.

Using 4 Dupont jumper wires connect BH1750 to one of the 3 I2C slots on ANAVI Info uHAT as follows:

| BH1750   | ANAVI Info uHAT |
| -------- |:--------------- |
| VCC      | 3.3V            |
| GND      | GND             |
| SCL      | SCL             |
| SDA      | SDA             |

## Assembly

You can assemble ANAVI Info uHAT and mount it on your Raspberry Pi with your bare hands following the steps below:

* Ensure that you Raspberry Pi is compatible with ANAVI Info uHAT.
* Power off your Raspberry Pi.
* Gently mount ANAVI Info uHAT on the 40 pin header of your Raspberry Pi.
* Add sensors to your ANAVI Info uHAT.
* Optionally, you may also mount two or four brass M2.5 standoffs to keep your Pi HAT snug on your Raspberry Pi while also keeping the two boards separated.
* That's all, now you are ready to go!

## Powering ANAVI Info uHAT

ANAVI Info uHAT is Raspberry Pi HAT therefore it is powered through Raspberry Pi. It is recommended to use the [official Raspberry Pi Power Supply](https://www.raspberrypi.org/products/universal-power-supply/) or another 2.5A USB power supply from reputable retailer.

---

# Software

## Installation

In order to work correctly, ANAVI Info uHAT requires an up-to-date kernel, I2C to be enabled, and a few libraries to get started. After booting microSD card with **Raspberry Pi OS** (previously known as Raspbian), open a terminal and follow the steps below:

* Ensure your APT package list is up-to-date:

```
sudo apt update
```

* Install additional applications, libraries and other tools needed by ANAVI Info uHAT

```
sudo apt install -y git i2c-tools vim python-dev python3-pip libfreetype6-dev libjpeg9-dev libsdl1.2-dev
```

* Install Python 3 libraries needed for controlling the mini I2C OLED display:

```
pip install --upgrade luma.oled
```

### Enable I2C

Follow the steps below to enable I2C which is required by the sensors for ANAVI Info uHAT.

* Open a terminal or login remotely via SSH to your Raspberry Pi and type in the following command:

```
sudo raspi-config
```

* Select **Interfacing Options > I2C** and enable it.

* Reboot the board.

### Serial Debugging

Follow the steps below to enable serial debugging through USB to serial cable:

* Open a terminal or login remotely via SSH to your Raspberry Pi and type in the following command:

```
sudo raspi-config
```

* Select **Interfacing Options > Serial** and enable it.

* Reboot the board.

* Plug the USB to serial cable and connect your Raspberry Pi to your PC. The **RX** line of the cable should go to **TX** line of **UART** on ANAVI Info uHAT. The **TX** line of the cable should go to the **RX** line of **UART** on ANAVI Info uHAT. The **GND** wire should go to the **GND** line of **UART** on ANAVI Info uHAT.

* Type in the following command on your computer if you are using GNU/Linux distribution to access ANAVI Info uHAT. Alternatively if your OS is Microsoft Windows use [putty](http://www.chiark.greenend.org.uk/~sgtatham/putty/download.html).

The recommended USB to UART serial modules for ANAVI Info uHAT are any with CP2102 or [Olimex USB-Serial-Cable-F](https://www.olimex.com/Products/Components/Cables/USB-Serial-Cable/USB-Serial-Cable-F/). All developer kits include CP2102 which out of the box on GNU/Linux distributions. Drivers for MS Windows and Mac OS X are [available at silabs.com](https://www.silabs.com/products/development-tools/software/usb-to-uart-bridge-vcp-drivers).

## Examples

Sample applications written in Python and the C programming language are provided for ANAVI Info uHAT under MIT license in GitHub. All examples have been tested on **Raspberry Pi OS** (previously known as Raspbian).

Open a terminal and execute the follow the steps by step instructions to install all dependencies and to get the source code:

* Install dependencies:

```
sudo apt update
sudo apt install -y git vim libi2c-dev python3 i2c-tools
```

* Download the examples for ANAVI Info uHAT

```
cd ~
git clone https://github.com/AnaviTechnology/anavi-examples.git
cd anavi-examples
```

### Sensors

It is mandatory to enable **I2C** to use all of the sensors supported by ANAVI Info uHAT.

#### Temperature Sensor (BMP180)

##### Python

Follow the steps below to use the BMP180 I2C temperature and barometric pressure sensor with ANAVI Info uHAT:

* Connect BMP180 to any of the I2C slots on ANAVI Info uHAT using male to female Duport jumper wire.

* Type in the following command and verify that the address of the sensor is listed:

```
sudo i2cdetect -y 1
```

The address of BMP180 I2C sensor is 77, for example:

```
pi@raspberrypi:~ $ sudo i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- 77
```

* Run the Python3 script and verify that the output is similar to (the exact values depend on the atmospheric condition):

```
cd ~/anavi-examples/sensors/BMP180/python/
python3 BMP180.py
```

For example:
```
pi@raspberrypi:~ $ cd ~/anavi-examples/sensors/BMP180/python/
pi@raspberrypi:~/anavi-examples/sensors/BMP180/python $ python3 BMP180.py
Temperature: 21.99C
Pressure: 1002hPa
```

#### Humidity Sensor (HTU21D)

Follow the steps below to use the HTU21D I2C temperature and humidity sensor with ANAVI Info uHAT:

* Connect HTU21D to any of the I2C slots on ANAVI Info uHAT using male to female Duport jumper wire.

* Type in the following command and verify that the address of the sensor is listed:

```
sudo i2cdetect -y 1
```

The address of HTU21D I2C sensor is 40, for example:

```
pi@raspberrypi:~ $ sudo i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: 40 -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --
```

##### C

* Type in the following commands to build and run the sample application that display temperature and humidity:

```
cd ~/anavi-examples/sensors/HTU21D/c/
make
./HTU21D
```

* Verify that the output is similar to (the exact values depend on the atmospheric condition):

```
pi@raspberrypi:~/anavi-examples/sensors/HTU21D/c $ ./HTU21D
HTU21D Sensor Module
22.90C
62.89%rh
```

##### Python

* Run the Python3 script and verify that the output is similar to (the exact values depend on the atmospheric condition):

```
cd ~/anavi-examples/sensors/HTU21D/python/
python3 htu21d.py
```

For example:

```
pi@raspberrypi:~ $ cd ~/anavi-examples/sensors/HTU21D/python/
pi@raspberrypi:~/anavi-examples/sensors/HTU21D/python $ python3 htu21d.py
Temperature: 22.77C
Humidity: 63.0%
```

#### BH1750 Light Sensor Module

Follow the steps below to use the BH1750 I2C light sensor with ANAVI Info uHAT:

* Connect BH1750 to any of the I2C slots on ANAVI Info uHAT using male to female Dupont jumper wires.

* Type in the following command and verify that the address of the sensor is listed:

```
sudo i2cdetect -y 1
```


The address of BH1750 I2C sensor is 23, for example:

```
pi@raspberrypi:~ $ sudo i2cdetect -y 1
     0  1  2  3  4  5  6  7  8  9  a  b  c  d  e  f
00:                         -- -- -- -- -- -- -- --
10: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
20: -- -- -- 23 -- -- -- -- -- -- -- -- -- -- -- --
30: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
40: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
50: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
60: -- -- -- -- -- -- -- -- -- -- -- -- -- -- -- --
70: -- -- -- -- -- -- -- --
```

##### C

* Type in the following commands to build and run the sample application that display luminous emittance:

```
cd ~/anavi-examples/sensors/BH1750/c/
make
./BH1750
```

* Verify that the output is similar to (the exact values depend on the atmospheric condition):

```
pi@raspberrypi:~/anavi-examples/sensors/BH1750/c $ ./BH1750
BH1750 Sensor Module
Light: 392 Lux
```

##### Python

* Run the Python3 script and verify that the output is similar to (the exact values depend on the atmospheric condition):

```
cd ~/anavi-examples/sensors/BH1750/python/
python3 bh1750.py
```

For example:

```
pi@raspberrypi:~ $ cd ~/anavi-examples/sensors/BH1750/python/
pi@raspberrypi:~/anavi-examples/sensors/BH1750/python $ python3 bh1750.py
Light: 399 Lux
```

## Device Tree Overlays

Device Tree (DT) in Linux is a description of the hardware in a system. The DT overlay adds a number of optional elements.

The EEPROM of ANAVI Info uHAT contains DT overlay with description of the peripheral devices on the HAT. After adding Anavi to your Raspberry Pi and booting it you  should have some new filesystem nodes at */proc/device-tree/hat*:

```
pi@raspberrypi:~ $ ls -l /proc/device-tree/hat/
total 0
-r--r--r-- 1 root root  4 Feb 15 00:27 name
-r--r--r-- 1 root root 20 Feb 15 00:27 product
-r--r--r-- 1 root root  7 Feb 15 00:27 product_id
-r--r--r-- 1 root root  7 Feb 15 00:27 product_ver
-r--r--r-- 1 root root 37 Feb 15 00:27 uuid
-r--r--r-- 1 root root  6 Feb 15 00:27 vendor
```

The information provided in these filesystem nodes helps you to identify ANAVI Info uHAT vendor, version, product name, etc. For example:

```
pi@raspberrypi:~ $ cat /proc/device-tree/hat/product
ANAVI Info uHAT

pi@raspberrypi:~ $ cat /proc/device-tree/hat/vendor
ANAVI
```

More information about device trees, overlays and parameters are available at [the official Raspberry Pi documentation](https://www.raspberrypi.org/documentation/configuration/device-tree.md).

---

# Schematics

## Pinout

The components of ANAVI Info uHAT utilize the following pins on Raspberry Pi:

| Component    | Pins                            |
| ------------ |:------------------------------- |
| I2C          | 3, 5                            |
| EEPROM       | 27, 28                          |
| UART         | 1, 8, 9, 10                     |
| LED D1       | 29                              |
| LED D2       | 31                              |
| Button SW1   | 15                              |
| Button SW2   | 13                              |
| Button SW3   | 11                              |

## I2C

The sensors that can be connected to ANAVI Info uHAT communicate with a host microcontroller via a communications standard called **I2C** (Inter-Integrated-Circut). I2C uses two wires, labelled SDA (Serial Data) and SCL (Serial Clock). To function properly, I2C requires a pullup resistor on each of those lines therefore ANAVI Info uHAT includes two 4.7kohm resistors labelled as R4 and R5. If for one reason or another you need to disable the I2C pullup resistors remove R4 and R5.

---

# Frequently Asked Questions (FAQ)

#### May I use ANAVI Info uHAT with other operating systems?

Yes, you can use ANAVI Info uHAT with other GNU/Linux distributions and even other operating systems but some porting efforts might be required.

#### May I use other I2C sensors with ANAVI Info uHAT?

Yes, you can use other I2C sensors with ANAVI Info uHAT but you should take care for their drivers and software support.

#### Can I remotely control ANAVI Info uHAT from a web browser on my smartphone, tablet, or laptop?

Yes, you may install popular open source software for home automation on your Raspberry Pi such as [Home Assistant](https://home-assistant.io/) or [OpenHAB 2](https://www.openhab.org/) and integrate ANAVI Info uHAT.

#### Is ANAVI Info uHAT software free and open source?

Yes, the official ANAVI Info uHAT software is free and open source. The examples are available under MIT license and the rest is available under GPLv3. Please contact us if you are working on a commercial product and you would like to use the software under alternative commercial license.

---

# Revision History

## Document Revision

| Date              | Changes                     | Modified pages  | Author          |
| ----------------- |:---------------------------:| :---------------| :---------------|
| 08 May 2022       | Initial manual release      | All             | Leon Anavi      |

## ANAVI Info uHAT Revision

| Revision| Notable changes                                              |
| ------- |:-------------------------------------------------------------|
| 1.0     | First version                                                |
| 1.1     | Added D1 and D2 LEDs                                         |

## See Also

For more information please visit [anavi.technology](http://anavi.technology/) and our [GitHub repositories](https://github.com/AnaviTechnology). If you have any questions or enquiries please contact us through [Facebook](https://www.facebook.com/AnaviTechnology/), [Twitter](https://twitter.com/AnaviTechnology) or [email](mailto:info@anavi.technology).

---
