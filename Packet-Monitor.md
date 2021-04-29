# Packet Monitor
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/monitor_22.bmp?raw=true" width="100">
</p>
The ESP32 is able to filter captured WiFi traffic to display and harvest general 802.11 management frames on a graphical user interface.

<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/IMG_1853.JPG?raw=true" width="500">
</p>

### Filtering Traffic
Scan iterations occur once every 1/10th of a second.  
Once a packet is captured, is check for 3 different identifying bytes:  

#### Beacon
```C++
if ((snifferPacket->payload[0] == 0x80) && (display_obj.display_buffer->size() == 0))
```

#### Probe Request
```C++
if ((snifferPacket->payload[0] == 0x40) && (display_obj.display_buffer->size() == 0))
```

#### Deauthentication/Disassociation
```C++
if ((snifferPacket->payload[0] == 0xA0 || snifferPacket->payload[0] == 0xC0 ) && (display_obj.display_buffer->size() == 0))
```

### Displaying Metrics
Traffic density of displayed on a landscape oriented line graph. Beacon, Probe Request, and Deauthentication frames are displayed as Green, Blue, and Red lines respectively.  
Once the line graph reaches the end of the screen, the graph begins refreshing and overwriting starting at the beginning of the graph.

### Input Buttons
The X and Y axis both feature `+` and `-` buttons which adjust the zoom level of the line data displayed on the graph.  
The current sniffing channel can be adjusted by hitting the `+` or `-` buttons associated with the channel configuration at the top of the screen.  

This function can be exited by hitting the red X button at the top of the screen.

All captured traffic will be saved to an attached SD card in a PCAP file.