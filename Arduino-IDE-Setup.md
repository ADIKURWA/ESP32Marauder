# Arduino IDE Setup
1. Install and open the the latest release of [Arduino IDE](https://www.arduino.cc/en/main/software)
2. In the Arduino IDE, go to `File`>`Preferences`
3. Add the following URLs to Additional Boards Manager URLs:
    - https://dl.espressif.com/dl/package_esp32_index.json
    - https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json
4. Go to `Tools`>`Board`>`Boards Manager`, search for `esp32` and install `esp32 by Espressif Systems`
    - Make sure it is version `2.0.0-rc1`
5. Install the [CP210X Drivers](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
6. Install the [CH340X Drivers](https://github.com/justcallmekoko/ESP32Marauder/blob/master/Drivers/CH34x_Install_Windows_v3_4.EXE)

### These next steps only apply if you plan to build the full ESP32 Marauder firmware from source
### If you are following [these instructions](https://github.com/justcallmekoko/ESP32Marauder/wiki/esp32-marauder-kit#installing-firmware-over-the-air-ota-option-1easy), you do not need to do this
5. With any text editor, open `C:\Users\<USERNAME>\AppDate\Local\Arduino15\packages\esp32\hardware\esp32\2.0.0-rc1\platform.txt`
6. Add `-w` to the end of line `33` so it appears like so
    - `build.extra_flags.esp32=-DARDUINO_SERIAL_PORT=0 -w`
7. Add `-zmuldefs` to the end of line `27` (`compiler.c.elf.libs.esp32=`)