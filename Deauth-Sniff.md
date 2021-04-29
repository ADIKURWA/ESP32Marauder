# Deauth Sniff
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://raw.githubusercontent.com/justcallmekoko/ESP32Marauder/master/pictures/icons/deauth_sniff_22.bmp" width="100">
</p>
The ESP32 is able to filter captured WiFi traffic to display and harvest deauths and disassociations sent from surrounding WiFi clients and APs against any network or client.  

Once a packet is captured, it is checked for the identifying deauth or disassociation byte.
```C++
if ((snifferPacket->payload[0] == 0xA0 || snifferPacket->payload[0] == 0xC0 ) && (display_obj.display_buffer->size() == 0))
```

For each deauthentication or disassociation packet captured, the following information is displayed on screen:  
- Source MAC
- Destination MAC

All deauthentications and disassociations will be saved to an attached SD card in a PCAP file.

This function can be exited by touching the screen. Once exited, the user will be sent back to the menu.