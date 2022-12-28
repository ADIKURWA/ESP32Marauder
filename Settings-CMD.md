# Settings
Display and manage settings for the ESP32 Marauder firmware. For more information on the available settings, see [Marauder Settings](marauder-settings).

## Usage
```settings [-s <setting> enable/disable]/[-r]```

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-s <setting> enable/disable` | Optional | Enable or disable a specific setting |
| `-r` | Optional | Restore settings to default |

#### Examples
`settings`: Displays settings available for management  
`settings -s ForcePMKID enable`: Enables deauthentication packets while sniffing for PMKID  
`settings -r`: Restores all settings to their default values