# EAPOL PMKID Scan
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/eapol_22.bmp?raw=true" width="100">
</p>

### Menu Path
`WiFi`>`Sniffers`>`EAPOL/PMKID Scan`  

### Info
The ESP32 is able to filter captured WiFi traffic to display and harvest EAPOL PMKID packets on a graphical user interface. PMKID packets are saved to an attached SD card in PCAP files long with the necessary WiFi traffic in order for the user to carry out PMKID cracking on a 3rd party device.

### Filtering Traffic
Once a packet is captured, it undergoes a series of check to ensure the desired information is present.  
#### Packet length is checked
```C++
if (len == 173) {
    Serial.println("Maybe the PMKID");
    //sd_obj.addPacket(snifferPacket->payload, len);
  }
```
#### Check for identifying bytes
```C++
if (( (snifferPacket->payload[30] == 0x88 && snifferPacket->payload[31] == 0x8e)|| ( snifferPacket->payload[32] == 0x88 && snifferPacket->payload[33] == 0x8e) )){
    Serial.println("EAPOL!!");
    //sd_obj.addPacket(snifferPacket->payload, len);
    num_eapol++;
  }
```

### Displaying Metrics
The number of captured EAPOL/PMKID packets is displayed on a landscape oriented line graph. The number of packets itself is represented by a blue line.  
Once the line graph reaches the end of the screen, the graph begins refreshing and overwriting starting at the beginning of the graph.  

### Input Buttons
The X and Y axis both feature `+` and `-` buttons which adjust the zoom level of the line data displayed on the graph.
The current sniffing channel can be adjusted by hitting the `+` or `-` buttons associated with the channel configuration at the top of the screen.

This function can be exited by hitting the red X button at the top of the screen.
