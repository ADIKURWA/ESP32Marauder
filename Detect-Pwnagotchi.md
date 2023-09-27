# Detect Pwnagotchi
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/pwnagotchi_22.bmp?raw=true" width="100">
</p>

### Menu Path
`WiFi`>`Sniffers`>`Detect Pwnagotchi`  

### Info
The ESP32 is able to filter captured WiFi traffic to display the information of any active [pwnagotchis](https://pwnagotchi.ai/) within range of this device.  

### Filtering Traffic
Once a packet is captured, it undergoes a series of checks and enumerations to extract the desired information.  

The packet must be a beacon frame. If the packet is a beacon frame, the source MAC must be `de:ad:be:ef:de:ad`.
```C++
    if ((snifferPacket->payload[0] == 0x80) && (display_obj.display_buffer->size() == 0))
    {
      char addr[] = "00:00:00:00:00:00";
      getMAC(addr, snifferPacket->payload, 10);
      src.concat(addr);
      if (src == "de:ad:be:ef:de:ad") {
```

Information about the active pwnagotchi is stored in the ESSID of the beacon it sends as a JSON object.  
The json must be decoded to extract the desired information.
```C++
        // Load json
        DynamicJsonBuffer jsonBuffer;
        JsonObject& json = jsonBuffer.parseObject(essid);
        if (!json.success()) {
          Serial.println("\nCould not parse Pwnagotchi json");
          display_string.concat(essid);
        }
        else {
          Serial.println("\nSuccessfully parsed json");
          String json_output;
          json.printTo(json_output);
          Serial.println(json_output);
          display_string.concat(json["name"].as<String>() + " pwnd: " + json["pwnd_tot"].as<String>());
        }
```

For each pwnagotchi packet captured, the following information is displayed on screen:  
- Pwnagotchi name
- Number of all networks Pwned

All pwnagotchi packets will be saved to an attached SD card in a PCAP file.

This function can be exited by touching the screen. Once exited, the user will be sent back to the menu.