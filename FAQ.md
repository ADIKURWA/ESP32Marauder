# Frequently Asked Questions

- [I bought a Marauder and the screen is just black when I turn it on](#i-bought-a-marauder-and-the-screen-is-just-black-when-i-turn-it-on)
- [class TFT_eSPI has no member named setTouch or getTouch](#class-tft_espi-has-no-member-named-settouch-or-gettouch)
- [How do I attach the screen to the ESP32](#how-do-i-attach-the-screen-to-the-esp32)
- [How do I attach the SD card reader to the ESP32](#how-do-i-attach-the-screen-to-the-esp32)
- [Does the Marauder firmware work on other ESP32 devices](#does-the-marauder-firmware-work-on-other-esp32-devices)
- [I updated the Marauder and now the touch screen does not work](#i-updated-the-marauder-and-now-the-touch-screen-does-not-work)
- [My SD card is not detected by the Marauder](#my-sd-card-is-not-detected-by-the-marauder)

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
If the screen does not work after updating the firmware, it is possible you used the incorrect firmware update file. If you marauder looks like [this](https://github.com/justcallmekoko/ESP32Marauder/raw/master/pictures/esp32marauder_thumbnail.jpg), then you must use the `old_hardware` update file. If your marauder looks like [this](https://github.com/justcallmekoko/ESP32Marauder/raw/master/pictures/IMG_0426.JPG?raw=true), then you must use the `new_hardware` update file. You can still update your marauder like normal, but thouch coordinates of your marauder are inverted. Imagine the marauder screen being upside down while your try to navigate it. Once you update with the proper firmware, it will return to normal.

## My SD card is not detected by the Marauder
Ensure the size of the SD card you are using is less than or equal to 32GB. If this is the case, try using an SD card by Sandisk. Some other brands of SD card such as Samsung cause the Marauder not to boot properly or not initialize the SD card.