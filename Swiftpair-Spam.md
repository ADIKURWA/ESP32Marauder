# Swiftpair Spam
Swiftpair spam creates BLE Swiftpair traffic sourcing from randomly generated MAC addresses. This causes repeated notifications for BLE device pair on Swiftpair enabled devices, such as Windows PCs. The vulnerability research and attack development was conducted by [@Spooks4576](https://github.com/Spooks4576). In addition to this capability development, he has assisted in its integration into Marauder's suite of tools. Additional information about this attack can be found [here](https://www.mobile-hacker.com/2023/10/17/spam-ios-android-and-windows-with-bluetooth-pairing-messages-using-flipper-zero-or-android-smartphone/). To exit the attack, press anywhere on the screen and you will be returned to the Marauder menu.

## Menu Path
`Bluetooth`>`Bluetooth Attacks`>`Swiftpair Spam`

## CLI
This function is available for use via the [Marauder CLI](https://github.com/justcallmekoko/ESP32Marauder/wiki/cli). The following documentation describes command usage. The Swiftpair Spam function can be stopped with [stopscan](https://github.com/justcallmekoko/ESP32Marauder/wiki/stopscan).

### Usage
`swiftpair`