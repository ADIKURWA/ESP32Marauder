# update
Performs and firmware update of the ESP32 using either an OTA web interface or a connected SD card. In order to use the latter option, you must have an SD card connected to the ESP32 SPI interface and be using a version of the firmware which expects an SD card. For more information on the firmware update process, see [Update Firmware Menu](update-firmware-menu).

## Usage
```update -s/-w```

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-s/-w` | Required | Specify whether to use SD Card (`-s`) or web OTA (`-w`) |