# Settings (*to-do*)
The settings page allows the user to configure different aspects of the ESP32 Marauder. For more information on the available settings, see [Marauder Settings](marauder-settings).

## Available Settings

| Setting | Type | Options | Info |
| ------- | ---- | ------- | ---- |
| Channel | `int` | `1-14` |The channel the ESP32 is set to. Once the setting is saved, it is immediately applied. The setting will also be applied at boot. |
| Channel Hop Delay | `int` | `>=0` | How many seconds between channel hops when performing WiFi scans |
| Force PMKID | `bool` | `true, false` | Force WiFi handshakes by sending deauthentication frames |
| Save PCAP | `bool` | `true, false` | Determines whether or not to save PCAP files when performing WiFi scans |