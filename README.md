# SDIO-driver

SDIO block device driver. 

This is not officially supported driver.

## License & Contributions 

The software is provided under [Apache-2.0 license](LICENSE). Contributions to this project are accepted under the same license. Please see [contributing.md](CONTRIBUTING.md) for more info.

This is an implementation for a blockdevice to use SDHC cards via SDIO interface.

## Supported Hardware
- STM32F1
- STM32F4
- STM32F7
- STM32L4
- STM32H7

Note: For MCUs with multiple SDMMC instances, only SDMMC1 is supported.

## Tested Hardware
- AliOS Things STM32L496VG Developer Kit
- Boring-Tech STM32L431RC Core Board
- QIMINGXINXIN STM32F407ZG V5.1 Board
- FANKE STM32H7B0VB Core Board
- PUZHONG STM32F103ZE Z100 Board
  
## Driver Description
This SDIOBlockdevice inherits from Blockdevice. The implementation uses an intermediate layer for the target specific code. This version uses the STM HAL 
for the SD card communication, an approach that is not fully mBed compliant. So this driver is not part of the mbed-os, a cleaner solution maybe supplied in the future. Anyway, this driver passes the same tests as for a SDBlockdevice with SPI interface.

## Usage
The driver is used like other blockdevices, a good starting point is https://github.com/ARMmbed/mbed-os-example-filesystem
