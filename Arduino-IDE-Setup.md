# Arduino IDE Setup
1. Install and open the [Arduino IDE](https://www.arduino.cc/en/main/software)
2. In the Arduino IDE, go to `File`>`Preferences`
3. Add the following URLs to Additional Boards Manager URLs:
    - https://dl.espressif.com/dl/package_esp32_index.json
    - https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_dev_index.json
4. Go to `Tools`>`Board`>`Boards Manager`, search for `esp32` and install `esp32 by Espressif Systems`
    - Make sure it is version `2.0.0-rc1`
5. With any text editor, open `C:\Users\<USERNAME>\AppDate\Local\Arduino15\packages\esp32\hardware\esp32\2.0.0-rc1\platform.txt`
6. Add `-w` to the end of line `33` so it appears like so
    - `build.extra_flags.esp32=-DARDUINO_SERIAL_PORT=0 -w`
7. Add `-zmuldefs` to the end of line `27` (`compiler.c.elf.libs.esp32=`)