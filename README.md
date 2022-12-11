# Faux Pi Zero

Open RP2040 dev board in a Raspberry Pi Zero compatible form factor.

[![](docs/assets/render.jpg)](docs/assets/render.jpg)

## Description

Due to the shortage of Pi Zeros in 2022, I designed this board to aid with migrating a project from the Pi Zero to the RP2040.  The compatible footprint and partially compatible pinout help migrate existing designs and retain the option of moving back to the Pi Zero in the future.
## Features

* Compatible footprint and I/O:
  * Mini HDMI (via [bitbanged DVI](https://github.com/Wren6991/PicoDVI))
  * Micro SD (via SPI mode.  Cards must be <2TB)
  * Micro USB
  * Power (via Micro USB)
* Partially compatible pinout (see [pinout](#pinout))
* 16MB Flash
* Green status LED on GP25 (same as Pico)
* Red SD activity LED on GP9
* BOOTSEL and RESET buttons
* SWD Header
## Pinout

The Faux Pi pinout is partially compatible with the Raspberry Pi.  I've done my best to expose RP2040 pins with similar functionality on the 40 pin header:

* UART on pins 8 and 10
* SPI [controller](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) or [peripheral](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) on pins 19, 21, 23, and 24
* SPI [controller](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) on pins 12, 35, 38, 40 (shared with micro SD)
* I2C on pins 27 and 28
* I2C on pins 3 and 5 (optionally shared with DVI)
* GCLK via PWM on pins 7, 29, and 31

[![](docs/assets/pinout.svg)](docs/assets/pinout.svg)
## TODO

* Use 50k pulls on SD card?
* Use 300 ohm termination (C25102)

## Notes

* [SPI and SD cards](https://electronics.stackexchange.com/questions/602105/how-can-i-initialize-use-sd-cards-with-spi)
* [A guide to debouncing](https://my.eng.utah.edu/~cs5780/debouncing.pdf)
