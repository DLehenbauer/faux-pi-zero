# Faux Pi Zero

Open RP2040 dev board in a Raspberry Pi Zero compatible form factor.

**STATUS:** Untested.  Preparing to order first boards from JLCPCB.

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

The Faux Pi pinout is partially compatible with the Raspberry Pi.  I've tried to expose pins with similar functionality at the same locations on the 40 pin header:

* UART on pins 8 and 10
* SPI [controller](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) or [peripheral](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) on pins 19, 21, 23, and 24
  * Configure [controller](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) or [peripheral](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) using solder jumper on back
* SPI [controller](https://www.oshwa.org/a-resolution-to-redefine-spi-signal-names/) on pins 12, 35, 38, 40 (shared with micro SD)
  * Note: Shared with SD card
* I2C on pins 27 and 28
* I2C on pins 3 and 5 (optionally shared with DVI)
  * Close solder jumper to use DVI.
  * Danger: Closing solder jumpers enables 5V pullups
* GCLK via PWM on pins 7, 29, and 31

See schematic for more details.

[![](docs/assets/pinout.drawio.svg)](docs/assets/pinout.drawio.svg)

## Schematic

(Click image to view PDF)

[![](docs/assets/schematic.png)](docs/assets/schematic.pdf)
