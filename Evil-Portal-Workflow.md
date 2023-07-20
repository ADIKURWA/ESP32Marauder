# Evil Portal Workflow
The following documentation describes the process for configuring and executing Evil Portal. Logged usernames and passwords will be stored in `evil_portal_x.log` on the root of your SD card. For more usage and requirement information, see [evilportal](evilportal).

1. [Prepare Your HTML](#prepare-your-sd-card)
2. [Prepare Your AP Configuration](#prepare-your-ap-configuration)
    - [Using SSID List](#using-ssid-list)
    - [Using Access Point List](#using-access-point-list)
    - [Using Configuration File](#using-configuration-file)

## Important Note
As of v0.11.0 of the Marauder firmware, this attack will require an SD card to be attached directly to your ESP32. This may change in later versions, but for now you will be required to follow [these instructions](https://github.com/justcallmekoko/ESP32Marauder/wiki/flipper-zero#sd-card-modification) to ensure you have this capability.

## Prepare Your HTML
1. Select an html file from [this page](https://github.com/bigbrodude6119/flipper-zero-evil-portal/tree/main/portals)
2. Rename the file to `index.html`
3. Place the file on the root of your ESP32 SD card

## Prepare Your AP Configuration
Select one of the following options to proceed. Keep in mind, Marauder's default AP name selection priority is as follows: 
1. SSID list
2. Selected AP list
3. `/ap.config.txt` from SD card

### Using SSID List
1. Use the [ssid](ssid) command to add one SSID to your list of SSIDs
    - `ssid -a -n FreeWiFi`
2. Check your [list](list) of SSIDs to ensure the SSID has been properly added
    - `list -s`
3. Execute the [evilportal](evilportal) command and pay attention to the on-screen output
    - `evilportal -c start`

### Using Access Point List
1. Scan for surrounding access points in your area using [scanap](scanap)
    - `scanap`
2. Stop the AP scan with [stopscan](stopscan)
    - `stopscan`
3. List the scanned access points using [list](list)
    - `list -a`
4. Select the desired access point from the list using [select](select)
    - `select -a <index>`
5. List the access points again to ensure the AP you selected shows "selected"
    - `list -a`
6. Execute the [evilportal](evilportal) command and pay attention to the on-screen output
    - `evilportal -c start`

### Using Configuration File
1. Create a file named `ap.config.txt`
2. Place the desired name of your access point
3. Re-insert the SD card into the ESP32 connected SD card slot
4. Execute the [evilportal](evilportal) command and pay attention to the on-screen output
    - `evilportal -c start`