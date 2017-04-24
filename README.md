# EEEmu SPI Supported Device Configurations

This repository contains configurations for all the currently supported EEPROM and Flash chips for the EEEmu SPI.

## How to use config files
Find your SPI flash chip device (you can use the search function to do this, or browse the repository directories). Download this file and rename to eeemu_spi.conf. Place the eeemu_spi.conf file on the EEEmu device (via the USB mass storage interface or directly to the SD card).

## My device isn't listed, is it supported?
This repository lists working configuration files for EEPROM and Flash devices for the EEEmu. This doesn't mean that your device isn't supported, it's just that a verified working configuration hasn't been uploaded yet. Most EEPROM and Flash follow a standard protocol set, so the eeemu_spi.conf might be suitable for your particular application. If you find it doesn't work, you will need to check out the datasheet for your specific chip and change some parameters like the clock phase/polarity and the command set. If you are having trouble interpreting a specific datasheet to do this, don't hesitate to raise an issue on GitHub with your chip's model number and we will try to create a new configuration for you that you can test and verify.

## How do I make new configuration files to support a new device?
Check eeemu_spi.conf for the configuration file template. Details of each setting are commented in this file.

## How do I add a config file that I have created?
Clone the repository, add a config file to your local repository, then create a pull request for it to be merged back in. Alternatively you can create a new issue with the configuration file details and we will get it merged for you.

## What is the SPI mode, clock phase and polarity?
| SPI Mode | Clock Polarity (CPOL/CKP) | Clock Phase (CPHA) | Clock Edge (CKE/NCPHA) |
|----------|---------------------------|--------------------|------------------------|
|0|0|0|1|
|1|0|1|0|
|2|1|0|1|
|3|1|1|0|

Setting SPI mode is optional and will override the clock polarity and clock phase parameters. Clock edge isn't required. For more details wee the wikipedia article - https://en.wikipedia.org/wiki/Serial_Peripheral_Interface_Bus

## What if I don't set a config line?
If a config line isn't set, then it will take up a default configuration (the defaults are the same as what's in the eeemu_spi.conf in the root of this repository).

## How do I know if my config is loaded correctly?
If there are syntax errors in the config file, then the EEEmu will flash out the line number of the offending error. If there are no flashes, then the configuration has loaded correctly. If there are missing parameters, then defaults will be applied for that parameter, so if things aren't working correctly, make sure that you have applied all the appropriate parameters.