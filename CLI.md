# Marauder Command Line Interface
Every Marauder has the ability to offer a commandline interface. Official Marauder hardware or any ESP32 development board with a USB port can simply be interfaced via USB cable. The Marauder CLI allows for complete control of the firmware and will provide the user with the full capabilities of Marauder.

For full usage on how to establish a connection to the Marauder command line interface, see [Access CLI](#access-cli) below.
If you would like to see examples of how these commands are used in a workflow, check out [workflow examples](workflow-examples).

Here are the currently supported commands:
- General admin commands
  - [reboot](reboot-cmd)
- WiFi Scanning/Sniffing
  - [scanap](scanap)
  - [scansta](scansta)
  - [sniffbeacon](sniffbeacon)
  - [sniffdeauth](sniffdeauth)
  - [sniffpmkid](sniffpmkid)
  - [stopscan](stopscan)
- WiFi Attacks
  - [attack](attack)
- WiFi Aux commands
  - [channel](channel)
  - [clearap](clearap)
  - [listap](listap)
  - [select](select)

## Access CLI
The ESP32 Marauder firmware allows the user to interface with the device via its commandline interface over UART(TX, RX). If your device has a USB port, the physical connection is as simple as connecting the device to a PC or Android phone via USB cable. If your device does not have a USB port or your device is a Flipper Zero WiFi Dev Board, you will need to get a little more creative with how you interface with your device.

**Note: To find out which serial port your device uses when plugged into your PC, use Device Manager**

#### Standard USB
1. Connect your Marauder device to a PC or Android phone
2. Open your Serial terminal software
    - If you are using a PC, make sure you have [Putty]() installed
    - If you are using an Android device, install a Serial terminal from the app store
3. In your Serial terminal software, make sure the following is set
    - Baud: 115200
    - Port: Whatever serial port your device occupies when plugged in i.e. `COMX`
4. Click whatever button starts the connection
    - Putty: `Open`
    - Android: `Figure it out I guess`
5. Verify the connection was successful by typing `help` and hitting enter
    - You should see a list of available commands show up

#### Flipper Zero WiFi Dev Board
1. Connect your Dev Board to the Flipper Zero
2. Plug your flipper zero into your PC or Android phone
3. On your flipper, start the USB/UART bridge app under GPIO
4. Make sure the following settings are set
    - USB Channel: 0
    - Baudrate: 115200
5. Open your Serial terminal software
    - If you are using a PC, make sure you have [Putty]() installed
    - If you are using an Android device, install a Serial terminal from the app store
6. In your Serial terminal software, make sure the following is set
    - Baud: 115200
    - Port: Whatever serial port your device occupies when plugged in i.e. `COMX`
7. Click whatever button starts the connection
    - Putty: `Open`
    - Android: `Figure it out I guess`
8. Verify the connection was successful by hitting the reset button on the dev board
    - You should see the Marauder title screen appear