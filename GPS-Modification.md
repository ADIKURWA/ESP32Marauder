# GPS Modification
As of ESP32 Marauder firmware version 0.11.0, users can modify their Marauder hardware to use external GPS modules. These GPS modules provide location data used for wardriving(planned). The following GPS modules was used during testing and proven to function properly.

<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/b52b881b-5dd3-4900-8f88-d09e3fe66d9a" width="400">  

*Teyleten Robot ATGM336H NEO-6M*

<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/f24cf723-8423-4b60-9f5e-faaa591844ba" width="400">

*DWEII GY-NEO6MV2*

## Connections
Connect your GPS module VCC and GND to corresponding VCC and GND on your Marauder. Use the following table as a reference to make the UART connection between your Marauder and GPS module:

| Marauder Hardware | GPS TX | GPS RX |
| ----------------- | ------ | ------ |
| OG Marauder | IO04 | IO13 |
| Marauder v6 | IO04 | IO13 |
| Marauder Kit | IO04 | IO13 |
| Flipper Zero WiFi Dev Board | IO09 | IO21 |
| WiFi Dev Board Pro | IO21 | IO17 |

Use a piece of strong double sided tape like from 3M to adhere the GPS module and antenna to a spot on the Marauder PCB/Enclosure.  
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/26a104dc-784e-497f-ac4d-549ee1f2a831" width="400"> 


## Verifying Successful Installation
You will know if you've successfully installed the GPS module if you see a "GPS" menu item on the main menu of Marauder. You will also see a red or green satellite icon on the far left side of your status bar. If you have not properly installed the GPS module or you used an incompatible GPS module, you will **not** see these two items.
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/6823c140-407e-4a21-a16d-903a882f20d7" width="400"> 

## Antenna
The following options are available when attaching an antenna to your GPS module. Since most GPS modules feature an IPX socket, you can use ceramic antennae or SMA antennae with a pigtail adapter. Your options are not limited to this list but these are good examples and have undergone successful testing:

#### Ceramic
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/3e73b34d-430e-42b7-9b7c-4174236a87ba" height="400">
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/e8d033f9-7593-4c06-828a-abf5c3c7a3e8" height="400">


#### SMA
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/d4dbf61b-8e7c-4a92-be1e-bf9df7af094b" height="400">
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/c7da3237-2ead-4f69-a87a-2afb1eded3ba" height="400">
<img src="https://github.com/justcallmekoko/ESP32Marauder/assets/25190487/6f177101-0fb9-4ea7-b853-17da9233cddf" height="400">  

The [following enclosures](https://github.com/justcallmekoko/ESP32Marauder/tree/master/mechanical/V6) can be used for the Marauder v6 when mounting your GPS antenna. If you select a model that requires brass inserts, use [these](https://www.mcmaster.com/94180A331/).


## Usage Information
For usage information, see [GPS](gps).