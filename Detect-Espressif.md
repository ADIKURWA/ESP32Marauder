# Detect Espressif
The ESP32 is able to filter captured WiFi traffic to display the information of any active Espressif device in range.  

### Filtering Traffic
Once a packet is captured, the first 3 bytes of the source MAC is checked against a list of known Espressif vendor MACs.  
```C++
  for (int i = 0; i < (sizeof(espressif_macs) / sizeof(espressif_macs[0])); i++) {
    if (src_addr_string.startsWith(espressif_macs[i])) {
      match = true;
      break;
    }
  }
```

The referenced list contains the following Espressif vendor MACs
```C++
PROGMEM static String espressif_macs[] = {
  "fc:f5:c4",
  "f4:cf:a2",
  "f0:08:d1",
  "ec:fa:bc",
  "e0:98:06",
  "dc:4f:22",
  "d8:f1:5b",
  "d8:bf:c0",
  "d8:a0:1d",
  "cc:50:e3",
  "c8:2b:96",
  "c4:4f:33",
  "bc:dd:c2",
  "b8:f0:09",
  "b4:e6:2d",
  "ac:d0:74",
  "ac:67:b2",
  "a4:cf:12",
  "a4:7b:9d",
  "a0:20:a6",
  "98:f4:ab",
  "90:97:d5",
  "8c:aa:b5",
  "84:f3:eb",
  "84:cc:a8",
  "84:0d:8e",
  "80:7d:3a",
  "7c:df:a1",
  "7c:9e:bd",
  "70:03:9f",
  "68:c6:3a",
  "60:01:94",
  "5c:cf:7f",
  "54:5a:a6",
  "50:02:91",
  "4c:11:ae",
  "48:3f:da",
  "40:f5:20",
  "3c:71:bf",
  "30:ae:a4",
  "2c:f4:32",
  "2c:3a:e8",
  "24:b2:de",
  "24:6f:28",
  "24:62:ab",
  "24:0a:c4",
  "18:fe:34",
  "10:52:1c"
};
```

For each Espressif device frame captured, the following information is displayed on screen:  
- Channel
- Source MAC

All Espressif packets will be saved to an attached SD card in a PCAP file.

This function can be exited by touching the screen. Once exited, the user will be sent back to the menu.