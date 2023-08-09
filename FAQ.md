# Frequently Asked Questions

- [What is Marauder](#what-is-marauder)
- [Can I build my own Marauder](#can-i-build-my-own-marauder)
- [I bought a Marauder and the screen is just black when I turn it on](#i-bought-a-marauder-and-the-screen-is-just-black-when-i-turn-it-on)
- [class TFT_eSPI has no member named setTouch or getTouch](#class-tft_espi-has-no-member-named-settouch-or-gettouch)
- [How do I attach the screen to the ESP32](#how-do-i-attach-the-screen-to-the-esp32)
- [How do I attach the SD card reader to the ESP32](#how-do-i-attach-the-screen-to-the-esp32)
- [Does the Marauder firmware work on other ESP32 devices](#does-the-marauder-firmware-work-on-other-esp32-devices)
- [I updated the Marauder and now the touch screen does not work](#i-updated-the-marauder-and-now-the-touch-screen-does-not-work)
- [My SD card is not detected by the Marauder](#my-sd-card-is-not-detected-by-the-marauder)
- [Multiple Definition of `ieee80211_raw_frame_sanity_check`](#multiple-definition-of-ieee80211_raw_frame_sanity_check)
- [I tried to compile the firmware and it complained about LVGL](#i-tried-to-compile-the-firmware-and-it-complained-about-lvgl)
- [I can't connect to MarauderOTA when doing the MarauderOTA installation method](#i-cant-connect-to-marauderota-when-doing-the-marauderota-installation-method)
- [My Flipper dev board reverts back to MarauderOTA after I disconnect it from power](#my-flipper-dev-board-reverts-back-to-marauderota-after-i-disconnect-it-from-power)
- [How do I use different attacks and scans on commandline](#how-do-i-use-different-attacks-and-scans-on-commandline)
- [My PCAPs aren't saving](#my-pcaps-arent-saving)

## What is Marauder
The ESP32 Marauder is a WiFi and Bluetooth analysis tool. It hosts a suite of capabilities for frame capture, device enumeration, and frame transmission. It is intended to serve as a portable device to stand in for physically larger traffic capturing tools and to provide captured data for post-op analysis.

## Can I build my own Marauder
Yes, you can build your own Marauder. All you need is an ESP32 development board and a 2.8" ILI9341 TFT touch screen.

## I bought a Marauder and the screen is just black when I turn it on
There have been some rare cases where the Marauder firmware was wiped from flash during transit through USPS. I am not sure what is causing this but the solution is to compile the firmware from source and upload using the Arduino IDE. Follow the instructions under [Installing Firmware](installing-firmware).

## class TFT_eSPI has no member named setTouch or getTouch
If you are building the project from source, ensure you are following the steps properly under [Installing Firmware](installing-firmware). If you are receiving this error, it is because you have not configured your `User_Setup.h`. Make sure you copy my `User_Setup.h` file into your `TFT_eSPI` library folder in your Arduino libraries.

## How do I attach the screen to the ESP32
Refer to the wiring documentation shown in [IC Connections](https://github.com/justcallmekoko/ESP32Marauder/wiki/ic-connections#ili9341-tft-touch-screen)

## How do I attach the SD card reader to the ESP32
Refer to the wiring documentation shown in [IC Connections](https://github.com/justcallmekoko/ESP32Marauder/wiki/ic-connections#ili9341-tft-touch-screen)

## Does the Marauder firmware work on other ESP32 devices
It is possible to get the Marauder firmware to work on many other ESP32 development boards some type of display. If you want to know if your display will work, check the original TFT_eSPI library. I will not be making changes to the Marauder source to make it function for any other specific displays. If you would like to create your own functionality, you may create a pull request.

## I updated the Marauder and now the touch screen does not work
If the screen does not work after updating the firmware, it is possible you used the incorrect firmware update file. If you marauder looks like [this](https://github.com/justcallmekoko/ESP32Marauder/raw/master/pictures/esp32marauder_thumbnail.jpg), then you must use the `old_hardware` update file. If your marauder looks like [this](https://github.com/justcallmekoko/ESP32Marauder/raw/master/pictures/IMG_0426.JPG?raw=true), then you must use the `new_hardware` update file. You can still update your marauder like normal, but thouch coordinates of your marauder are inverted. Imagine the marauder screen being upside down while your try to navigate it. Once you update with the proper firmware, it will return to normal. Following the instructions for [Update Firmware](update-firmware)

## My SD card is not detected by the Marauder
Ensure the size of the SD card you are using is less than or equal to 32GB. If this is the case, try using an SD card by Sandisk. Some other brands of SD card such as Samsung cause the Marauder not to boot properly or not initialize the SD card. You will also want to make sure the SD card is initialized in Fat32. If you are running any version of Marauder earlier than v0.9.15, update to the latest firmware.

## Multiple Definition of `ieee80211_raw_frame_sanity_check`
Make sure you followed [these steps](https://github.com/justcallmekoko/ESP32Marauder/wiki/arduino-ide-setup#these-next-steps-only-apply-if-you-plan-to-build-the-full-esp32-marauder-firmware-from-source) when setting up your Arduino IDE

## I tried to compile the firmware and it complained about LVGL
Make sure you have installed [`lv-arduino`](https://github.com/lvgl/lv_arduino) and not [`lvgl`](https://github.com/lvgl/lvgl) in your Arduino IDE

## I can't connect to MarauderOTA when doing the MarauderOTA installation method
Before you upload the MarauderOTA firmware to your ESP32, try changing the SSID and Password in the code to something different. Once you change it, upload the code and try the OTA update method again. Also make sure you refresh the page immediately after coming to the MarauderOTA update screen.

## My Flipper dev board reverts back to MarauderOTA after I disconnect it from power
Ensure you follow the MarauderOTA instructions exactly as they are written. Take great care to follow steps 5, 13, and 16. If that doesn't work, consider using one of the other [firmware install options](https://github.com/justcallmekoko/ESP32Marauder/wiki/flipper-zero#firmware-install-options)

## How do I use different attacks and scans on commandline
Check out some of the workflow examples [here](https://github.com/justcallmekoko/ESP32Marauder/wiki/workflow-examples)

## My PCAPs aren't saving
Make sure you have followed [these instructions](https://github.com/justcallmekoko/ESP32Marauder/wiki/flipper-zero#sd-card-modification) for installing the SD card modification on your flipper zero wifi dev board. PCAPs cannot save to the SD card connected to the actual Flipper Zero unless these three conditions are met:

- You are using the `flipper_sd_serial.bin`
- You are using a WiFi Dev Board that has an ESP32-S2 with supported connections
- You have enabled the SD Serial option in the Marauder companion app on your Flipper Zero

If these conditions have not been met, it is assumed you are using an SD card modification on your Dev Board or it came with an SD card slot.  
If you have already followed those instructions and you are certain you have followed them correctly, make sure you have the `SavePCAP` settings enabled. More information for settings can be found [here](marauder-settings). If that settings is enabled, try running [`settings -r`](https://github.com/justcallmekoko/ESP32Marauder/wiki/settings-cmd) to reset your settings.