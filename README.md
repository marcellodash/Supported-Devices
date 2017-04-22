# EEEmu SPI Supported Device Configurations

This repository contains configurations for all the currently supported EEPROM and Flash chips for the EEEmu SPI.

## How to use config files
Find your SPI flash chip device (you can use the search function to do this, or browse the repository directories). Download this file and rename to eeemu_spi.conf. Place the eeemu_spi.conf file on the EEEmu device (via the USB mass storage interface or directly to the SD card).

## My device isn't listed, is it supported?
This repository lists working configuration files for EEPROM and Flash devices for the 

## How do I make new configuration files to support a new device?
Check eeemu_spi.conf for the configuration file template. Details of each setting are commented in this file.

## How do I add a config file that I have created?
Clone the repository, add a config file to your local repository, then create a pull request for it to be merged back in. Alternatively you can create a new issue with the configuration file details.