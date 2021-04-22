# Beacon Spam List
The ESP32 is capable of transmitting specially crafted WiFi packets.  
In a beacon spam list attack, the ESP32 broadcasts beacon frames for each SSID contained within its list of SSIDs.  
SSIDs can be added to the list by using [Generate SSIDs](generate-ssids) and [Add SSID](add-ssid).  

SSIDs can be cleared from the list by [Reboot](reboot) or [Clear SSIDs](clear-ssids).

### Transmitting
The base data required for all beacon frame to transmit successfully is hardcoded in the Marauder firmware.  
```C++
// barebones packet
    uint8_t packet[128] = { 0x80, 0x00, 0x00, 0x00, //Frame Control, Duration
                    /*4*/   0xff, 0xff, 0xff, 0xff, 0xff, 0xff, //Destination address 
                    /*10*/  0x01, 0x02, 0x03, 0x04, 0x05, 0x06, //Source address - overwritten later
                    /*16*/  0x01, 0x02, 0x03, 0x04, 0x05, 0x06, //BSSID - overwritten to the same as the source address
                    /*22*/  0xc0, 0x6c, //Seq-ctl
                    /*24*/  0x83, 0x51, 0xf7, 0x8f, 0x0f, 0x00, 0x00, 0x00, //timestamp - the number of microseconds the AP has been active
                    /*32*/  0x64, 0x00, //Beacon interval
                    /*34*/  0x01, 0x04, //Capability info
                    /* SSID */
                    /*36*/  0x00
                    };
```

The `/* SSID */` tag is replaced by the ESSID of the current iteration in the list of SSIDs as well as the size of the ESSID.  
The bytes placeholder for the `BSSID` are replaced corresponding BSSID for the list.  

As the list of SSIDs cycles, each SSID beacon is broadcast transmitted 3 times.

### Monitoring Requests
As SSIDs are transmitted, the ESP32 Marauder monitors requests to join the transmitted networks by checking for probe requests with the destination set as one of the SSIDs from the list.
```C++
if ((snifferPacket->payload[0] == 0x40) && (display_obj.display_buffer->size() == 0))
    {

      for (uint8_t i = 0; i < snifferPacket->payload[25]; i++)
      {
        essid.concat((char)snifferPacket->payload[26 + i]);
      }

      for (int i = 0; i < ssids->size(); i++) {
        if (ssids->get(i).essid == essid) {
          Serial.println("Found a sheep");
          found = true;
          break;
        }
      }
```

The following information will be displayed on screen for each connection request:  
- RSSI
- Channel
- Source MAC
- Destination ESSID

All connection requests against of the SSIDs in the list will be saved to an attached SD card in a PCAP file.