# Battery
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/battery_16.bmp?raw=true" width="100">
</p>
The ESP32 Marauder may be used with an external LiPo battery for portability. A battery is intended to be positioned between the back of the main PCB and the enclosure. You will notice a pair of vertical bars in the enclosure running parallel to one another. These are designed to contain the battery.  

The battery is to be fixed to the inside of the enclosure using double sided scotch tape.
The battery must have the following dimensions. 
- 5mm thick
- 40mm Wide

The JST socket on the ESP32 Marauder accepts a female 2mm pitch 2-pin JST PH series connector.

I have chosen a 1500mah 504050 LiPo found [here](https://www.aliexpress.com/snapshot/0.html?orderId=8127618493544303)
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://ae04.alicdn.com/kf/U4251afb912f240bcba1093149fa568b8a.jpg" width="300">
</p>

### Charging and Output
Battery charging, output, and boost is accomplished using an INJOINIC IP5306 I2C.  
Notable features:  
- Output over current, over voltage, short circuit protection
- Input overvoltage, overcharge, overdischarge, overcurrent discharge protection
- Standby power consumption is less than 100 µA
- Boost efficiency up to 92%
- Customizable I2C interface
- Output voltage 5V

The datasheet for the IP5306 can be found [here](https://datasheet.lcsc.com/lcsc/1809201029_INJOINIC-IP5306_C181692.pdf).  
For additional information on the implementation of the IP5306 I2C in the Marauder hardware, check [IC Connections](ic-connections).