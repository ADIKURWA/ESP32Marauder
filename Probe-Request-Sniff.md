# Probe Request Sniff
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/probe_sniff_22.bmp?raw=true" width="100">
</p>

### Menu Location
`WiFi`>`Sniffers`>`Probe Request Sniff`  

### Info
The ESP32 is able to filter captured WiFi traffic to display and harvest probe request sent from surrounding WiFi clients against any network.  
Once a packet is captured, it is checked for the identifying probe request byte.  
```C++
if ((snifferPacket->payload[0] == 0x40) && (display_obj.display_buffer->size() == 0))
```

For each probe request captured, the following information is displayed on the screen:  
- Source MAC
- Destination ESSID

All probe requests will be saved to an attached SD card in a PCAP file.

This function can be exited by touching the screen. Once exited, the user will be sent back to the menu.