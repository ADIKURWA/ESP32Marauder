# evilportal
The evilportal command spawns an access point and hosts a webserver. The webserver serves a web page with username and password forms. Once a client connects to the access points and attempts to access any web page, they will be redirected to the web page served by Marauder. Any credentials they enter in the username and password fields will be displayed in Serial, Screen, and logs. Evilportal can be stopped with [stopscan](stopscan) (tapping the screen on TFT models).

## Requirements
In order to run evilportal, the user will be required to provide two configurations.  
| Access Point Name | index.html |
| ----------------- | ---------- |
| Can be provided by [SSID](ssid) list, [AP](scanap) list, or SD file | Can only be provided by SD file |

### Access Point Name
The access point name can be set by the following priority list:  
1. The first SSID in the list of [SSIDs](ssid)
2. The first instance of a "selected" AP in the list of [APs](scanap)  
3. From `/ap.config.txt` in the SD card attached to your ESP32

##### Using SSIDs
You can create a list of SSIDs using [ssid](ssid), [Add SSID](add-ssid), or [Generate SSIDs](generate-ssids)

##### Using APs from scanap
You can get a list of access points using [scanap](scanap) or [Scan APs](scan-aps). This option will essentially clone a pre-scanned access point and use it for EvilPortal.

##### Using `ap.config.txt`
You only need to put the desired name of your access point in the file like so...  
`FreeWifi`

### index.html
For the time being, `index.html` can only be provided via `/index.html` on the root of your ESP32-attached SD card.  
You can find many different HTML files [here](https://github.com/bigbrodude6119/flipper-zero-evil-portal/tree/main/portals) in [bigbrodude6119](https://github.com/bigbrodude6119)'s EvilPortal repo. Once you have chosen your HTML file, rename it to `index.html` and place it in the root of your ESP32 SD card. If you wish to store multiple HTML files on your SD card, you can use the `sethtml` subcommand of `evilportal` to select a specific HTML file before starting the attack or when starting the attack.

## Usage
`evilportal [-c start [-w <html.html>]/sethtml <html.html>]`

# Arguments
| Arguments | Required/Optional | Description |
| --------- | ----------------- | ----------- |
| `-c` | Optional | Execute a command against the evil portal module <`start`/`sethtml`> |
| `-w` | Optional | Specify an HTML file to use. Only used when using `-c start` |


### Examples
- `evilportal -c start`: Start evil portal with default `index.html` file as the HTML
- `evilportal -c sethtml apple.html`: Set the active HTML as `apple.html`
- `evilportal -c start -w CoxWifi.html`: Start evil portal with `CoxWifi.html` as the HTML