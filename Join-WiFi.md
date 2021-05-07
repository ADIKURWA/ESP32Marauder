# Join WiFi
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/join_wifi_22.bmp?raw=true" width="100">
</p>

### Menu Location
`WiFi`>`General`>`Join WiFi`  

### Info
The ESP32 Marauder is capable of joining a WiFi network. Once this option is selected, the user will be presented with two text boxes and an on-screen keyboard. The user must enter a valid ESSID and password to join a network.  

Once a network is joined, several things will be true:  
- The WiFi interface will be constantly active
- Your device will be visible on the network
- Running any WiFi sniffers or attacks will cause you to leave the network

You can leave the network by using one of the following methods:  
- [Shutdown WiFi](shutdown-wifi)
- Start a WiFi sniffer or WiFi Attack
- Shutdown the ESP32 Marauder
- [Reboot](reboot)