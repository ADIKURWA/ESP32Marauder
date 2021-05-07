# Scan APs
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/beacon_sniff_22.bmp?raw=true" width="100">
</p>

### Menu Location
`WiFi`>`Sniffers`>`Scan APs`  

### Info
The ESP32 is able to filter captured WiFi traffic to display and harvest AP beacons sent from surrounding WiFi Access Points.  

Once a packet is captured, it is checked for the identifying beacon byte. This application functions the same as [Beacon Sniff](beacon-sniff) however access points with unique BSSIDs are added to the list of access points needed for WiFi attacks.

```C++
if ((snifferPacket->payload[0] == 0x80) && (display_obj.display_buffer->size() == 0))
```

For each beacon captured, the following information will be displayed on screen:  

- Source MAC
- Source ESSID  

All beacons will be saved to an attached SD card in a PCAP file.

This function can be exited by touching the screen. Once exited, the user will be sent back to the menu.

The list of captured access points can be viewed with [Select APs](select-aps).