# Deauth Flood

### Menu Location
`WiFi`>`Attacks`>`Deauth Flood`  

### Info
The ESP32 is capable of transmitting specially crafted WiFi packets, but the ESP8266 is required in order to accomplish a deauthentication attack due to the limitations of the espressif idf. In a deauthentication attack, the attacker sends specially crafted packets which appear to come from a target network. These packets force clients to disconnect from the target network. Packets can be crafted to broadcast to all clients or target specific clients. Because these packets are unencrypted, the attack can be executed from outside the network. This attack is only available on versions of the ESP32 Marauder that come with an ESP8266. See [Marauder Versions](marauder-versions) for more information.

*Implementation coming soon*