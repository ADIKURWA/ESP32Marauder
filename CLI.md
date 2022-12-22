# Marauder Command Line Interface
This feature is actively being developed for firmware v0.9.6. The goal is to produce command line interface which can be used over hardware serial and/or bluetooth serial. In theory this will allow anyone with an ESP32 and a TX/RX or phone with bluetooth to make and use their own Marauder.

For full usage on how to establish a connection to the Marauder command line interface, see [Usage](cli-usage)

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