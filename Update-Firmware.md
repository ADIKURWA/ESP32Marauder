# Update Firmware

## Flipper Zero WiFi Dev Board, ESP32 Wemos D1 Mini Adapter
You can use any of the following options to update your Flipper Zero WiFi Dev Board Marauder firmware:
  - [CLI Update](https://github.com/justcallmekoko/ESP32Marauder/wiki/update) **(recommended)**
  - [FZ Marauder Flasher](https://github.com/UberGuidoZ/Flipper/tree/main/Wifi_DevBoard/FZ_Marauder_Flasher)
  - [FZEasyMarauderFlash](https://github.com/SkeletonMan03/FZEasyMarauderFlash)
  - [Marauder OTA](https://github.com/justcallmekoko/ESP32Marauder/wiki/installing-firmware-via-ota) (buggy)
  - [Spacehuhn Web Updater](#using-spacehuhn-web-updater)

## ESP32 Marauder v4, v6, Kit, Mini, WiFi Dev Board Pro:
You can use any of the following options to update your ESP32 Marauder v4:
  - [CLI Update](https://github.com/justcallmekoko/ESP32Marauder/wiki/update)
  - [Update Firmware Menu](update-firmware-menu) **(recommended)**
  - [Marauder OTA](https://github.com/justcallmekoko/ESP32Marauder/wiki/installing-firmware-via-ota) (buggy)
  - [Spacehuhn Web Updater](#using-spacehuhn-web-updater)

## Using Spacehuhn Web Updater
You can use the web updater made by Spacehuhn to install/update the Marauder firmware on your device. To do so, you will need to provide the Marauder firmware file, partition file, and bootloader file to the installer. Please use the instructions and table below to update your device.

1. Go to the [Web Updater](https://esp.huhn.me/)
2. With your device plugged in, click connect
3. Use the following table to select the appropriate files and place them at the corresponding address
    - Enter the address shown as the blue text in the appropriate space and add the file linked to that blue text  

|            | ESP32 Marauder v4, v6, Kit, Mini | Flipper Zero WiFi Dev Board | Flipper Zero Multi Board S3 | WiFi Dev Board Pro/LDDB/NodeMCU-32S/ESP32 Wemos D1 Mini |
| ---------- | -------------------------------- | --------------------------- | --------------------------- | ------------------ |
| Bootloader | [0x1000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.bootloader.bin) | [0x1000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroDevBoard/esp32_marauder.ino.bootloader.bin) | [0x0](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/esp32_marauder.ino.bootloader.bin) | [0x1000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.bootloader.bin) | 
| Partitions | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.partitions.bin) | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroDevBoard/esp32_marauder.ino.partitions.bin) | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/esp32_marauder.ino.partitions.bin) | [0x8000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/MarauderV4/esp32_marauder.ino.partitions.bin) |
| Boot App   | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) | [0xE000](https://github.com/justcallmekoko/ESP32Marauder/raw/master/FlashFiles/FlipperZeroMultiBoardS3/boot_app0.bin) |
| Firmware   | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) | [0x10000](https://github.com/justcallmekoko/ESP32Marauder/releases/latest) |

  - Use the following table to select the proper Marauder binary for your hardware. Please refer to version marking on your Marauder hardware is present.  

| Hardware | Binary Version |
| -------- | -------------- |
| v4 (OG) | `_old_hardware.bin` |
| v6 | `_new_hardware.bin`/`_v6.bin` |
| v6.1 | `_v6_1.bin` |
| Kit | `_kit.bin` |
| Mini | `_mini.bin` |
| Flipper Zero | `_flipper.bin` |
| MutliBoard S3 | `_multiboardS3.bin` |
| LDDB/NodeMCU/Wemos | `_lddb.bin` |
| Dev Board Pro | `_marauder_dev_board_pro.bin` |

4. Click program and wait. Once it says "To run the new firmware please reset your device", either hit the reset button or just flick the power switch off and back on