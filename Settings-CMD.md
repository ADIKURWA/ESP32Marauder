# Settings
Display and manage settings for the ESP32 Marauder firmware.

## Usage
```settings [-s <setting> enable/disable]/[-r]```

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-s <setting> enable/disable` | Optional | Enable or disable a specific setting |
| `-r` | Optional | Restore settings to default |

#### Examples
`select`: Displays settings available for management  
`select -s ForcePMKID enable`: Enables deauthentication packets while sniffing for PMKID  
`select -r`: Restores all settings to their default values