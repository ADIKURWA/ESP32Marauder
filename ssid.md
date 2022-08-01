# ssid
Generate or remove SSIDs for beacon spam attacks. Generated SSIDs can be viewed with [`list`](list)

## Usage
`ssid [-a [-g <count>]|[-n <name>]]|[-r <index>]`

#### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-a/-r <index>` | Required | Specify whether to add(`-a`) or remove(`-r`) |
| `-g <count>` | Optional | Specify after option `-a` how many SSIDs to generate |
| `-n <name>` | Optional | Specify after option `-a` the name of the SSID to be added |

#### Examples
`ssid -a -g 3`: Generates 3 random SSIDs and adds them to the SSID list  
`ssid -a -n chicken`: Generates an SSID named "chicken" and adds it to the list  
`ssid -r 3`: Removes SSID at index 3 from the list of SSIDs