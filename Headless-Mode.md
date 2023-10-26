# Headless Mode
Headless Mode is a capability provided by Marauder hardware variations that feature a screen. If you which to just use the Marauder CLI and don't plan to use the screen (like if you are tethered to a mobile phone for example), you can disable the screen and touch features to conserve the device battery.

## How to enabled Headless Mode
Headless Mode can be enabled on startup while the Marauder logo is on screen. Simple hold the predefined button at the time the screen transitions from the logo to the startup debug messages screen. If you performed this action correct, the screen will transition from the logo to black and the screen will no longer display an image and touch functions will no longer work. Do not hold the predefined button while powering on the device as some of the devices' predefined buttons are its boot button. Only start holding the button when the logo appears.

### Predefined Buttons
| Hardware | Button |
| -------- | ------ |
| Marauder v4(Coming) | GPIO0 (Boot button on front of PCB) |
| Marauder v6 | GPIO0 (Boot button on back of PCB) |
| Marauder v6.1 | GPIO0 (Boot button on back of PCB) |

## How to exit Headless Mode
Reboot the Marauder device