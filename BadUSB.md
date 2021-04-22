# BadUSB
<b>This feature is only available on the ESP32 Marauder 7</b>  
The ESP32 Marauder 7 features an on-board ATmega32u4. The ESP32 communicates with it in order to perform keystroke injection attacks.  
Keystroke injection scripts are written by the user, relayed to the ATmega32u4 by the ESP32, and executed against the target machine over USB.  

This capability is made possible by the [Arduino Keyboard Library](https://github.com/arduino-libraries/Keyboard)

- [Test BadUSB](test-badusb)
- [Run Ducky Script](run-ducky-script)