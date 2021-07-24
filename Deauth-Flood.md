# Deauth Flood

### Menu Location
`WiFi`>`Attacks`>`Deauth Flood`  

### Info
The ESP32 is capable of transmitting specially crafted WiFi packets.
Before executing deauth flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [Scan APs](scan-aps) and [Select APs](select-aps) for more details on how to build a target list.

Once a proper target list has been built, an deauth flood can be executed by simply selecting the menu option. The packet transmission rate will be displayed on screen. The attack can be ended by touching the screen.

**NOTE: The more target networks selected, the less effective the attack will be. More networks means more time must be taken to send packets to each access point.**

The deauthentication packet is defined in [WiFiScan.h](https://github.com/justcallmekoko/ESP32Marauder/blob/master/esp32_marauder/WiFiScan.h) as the following:  
```C++
    uint8_t deauth_frame_default[26] = {
                              0xc0, 0x00, 0x3a, 0x01,
                              0xff, 0xff, 0xff, 0xff, 0xff, 0xff,
                              0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
                              0x00, 0x00, 0x00, 0x00, 0x00, 0x00,
                              0xf0, 0xff, 0x02, 0x00
                          };
```

As the marauder iterates through the list of access points, the probe request packet is populated with the information of each "active" access point.