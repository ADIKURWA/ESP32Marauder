# ESP32 Marauder Kit
The ESP32 Marauder Kit is a bundle of hardware components that allow a user to assemble a fully functional ESP32 Marauder. All that is required from the user is that they must provide their own [Adafruit Huzzah32](https://www.adafruit.com/product/3405) flashed with the ESP32 Marauder firmware, and a 3.7V LiPo battery compatible with the Huzzah32. 

### Installing Firmware
To build the ESP32 Marauder firmware from source and install it on the Adafruit Huzzah32, follow the instructions under [Installing Firmware](installing-firmware).

### Assembling Hardware
1. Solder the male header pins included with your Adafruit Huzzah32 to the Huzzah32 board
2. Connect the Huzzah32 to the ESP32 Marauder Kit PCB
3. Connect your 3.7V LiPo battery to the JST connector of the Huzzah32
    - Note: Ensure the power switch of the ESP32 Marauder Kit PCB is in the `off` position
4. Using some sort of adhesive such as double sided tape or glue, fix the 3.7V LiPo battery to the inside of the Marauder enclosure
5. Using the 4 included M2.5 x 5mm screws, screw the ESP32 Marauder PCB to the enclosure so that the TFT Touch screen faces outward
