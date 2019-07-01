---
layout: post
author: redle
title: Recover Arduino Leonardo with Raspberry PI
---

# Recover bootloader with Raspberry

This process was used to recover bootload on Arduino Leonardo Pro Micro and BadUsb Arduino.

Both was with bootloader bricked!


## Download Raspbian PI with Desktop
https://downloads.raspberrypi.org/raspbian_latest

```
# unzip XXXX-XX-XX-raspbian-XXXXX.zip
# dd if=XXXX-XX-XX-raspbian-XXXXX.zip of=/dev/sdX bs=1M
```

## Download last Arduino ARM Version
https://www.arduino.cc/download_handler.php

tar xf ~pi/Downloads/arduino-X.X.X-linuxaarch64.tar.xz -C /opt/


## Configure Arduino IDE

Add following lines on /opt/arduino-X.X.X/hardware/tools/avr/etc/avrdude.conf

```
programmer
  id    = "gpio";
  desc  = "Use sysfs interface to bitbang GPIO lines";
  type  = "linuxgpio";
  reset = 8;
  sck   = 11;
  mosi  = 10;
  miso  = 9;
;
```

Add following lines on /opt/arduino-1.8.9/hardware/arduino/avr/programmers.txt:
```
gpio.name=Raspberry Pi GPIO
gpio.protocol=gpio
gpio.program.tool=avrdude

```

Now a programmer Raspberry Pi GPIO available:
> Tools > Programmer > Raspberry Pi GPIO
Select correct board:
> Tools > Board 
Burn the Bootloader
Tools > Burn Bootloader


# Conecting Raspberry PI And Arduino:
```
RPI: 24 (SPI0 CS0) <-> Arduino: RST
RPI: 19 (SPI0 MOSI) <-> Arduino: MOSI
RPI: 21 (SPI0 MISO) <-> Arduino: MISO
RPI: 23 (SPI0 SCLK) <-> Arduino: SCLK
```

## Pinout boards

### Arduino
![alt text](https://simba-os.readthedocs.io/en/latest/_images/arduino-pro-micro-pinout.png "Pinout Arduino Pro Micro")

### Raspberry PI 3
![alt text](https://camo.githubusercontent.com/3af697a8467ed5288e78a473e873625fa2b9811c/68747470733a2f2f6d6172636f6d696e657276612e626c6f622e636f72652e77696e646f77732e6e65742f70686f746f732f5261737062657272795069325f50696e6f75742e706e67 "Pinout Raspberry PI 3")

## References:
> https://github.com/gojimmypi/arduino
> https://www.instructables.com/id/Fixing-Bootloader-on-Arduino-Leonardo-ProMicro-Wit/
> https://learn.sparkfun.com/tutorials/installing-an-arduino-bootloader
> https://learn.sparkfun.com/tutorials/pro-micro--fio-v3-hookup-guide/troubleshooting-and-faq