# Flashing

## QMK Toolbox

### Requirements

* avr-gcc version up to 8.x.
* qmk_firmware in ~/qmk_firmware (you can use one in this folder as a backup)


```
qmk setup
```

This clones the main qmk repo to $HOME.

```
qmk info
```

Should show something like

```
Keyboard Name: Dactyl Manuform 5x6
Manufacturer: tshort
Website:
Maintainer: QMK Community
Keyboard Folder: handwired/dactyl_manuform/5x6
Layouts: LAYOUT_5x6
Processor: atmega32u4
Bootloader: caterina
```

If so, you can proceed with

```
qmk flash gnapiorkowski.json
```

# Flashing a hex

1. Get info for `avrdude`
    boards.txt:
    ```
    micro.build.mcu=atmega32u4
    micro.upload.protocol=avr109
    micro.upload.speed=57600
    ```
2. Flash with avrdude
```
avrdude -v -patmega32u4 -cavr109 -P/dev/ttyUSB0 -b57600 -Uflash:w:"handwired_dactyl_manuform_5x6_bla.hex":i
```
