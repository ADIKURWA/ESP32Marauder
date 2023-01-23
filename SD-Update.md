# SD Update
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/sd_update_22.bmp?raw=true" width="100">
</p>

*Using a Samsung MicroSD card will cause Marauder not to boot*
1. Download the [latest release](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) of the Marauder firmware

| Hardware | Binary Version |
| -------- | -------------- |
| v4 (OG) | `_old_hardware.bin` |
| v6 | `_new_hardware.bin` |
| Kit | `_kit.bin` |
| Mini | `_mini.bin` |
| Flipper Zero | `_flipper.bin` |
| MutliBoard S3 | `_multiboardS3.bin` |
| Dev Board Pro | `_marauder_dev_board_pro.bin` |

2. Copy the bin file you downloaded to the root of an SD card
3. Rename the bin file on the SD card to `update.bin`
4. With Marauder powered off, insert the SD card into Marauder
5. Power Marauder on and navigate to `Device`>`Update Firmware`>`SD Update`
    - `update -s` if you are using CLI
6. Click `Yes` to confirm the update
    - Marauder will automatically reboot once the update has been applied