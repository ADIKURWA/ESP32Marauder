# led
This command is responsible for manipulating the color of the onboard RGB LED (on supported hardware). You can specify a hex color code or a pre-programmed pattern.

### Usage
`led -s <#hexcode>/-p <pattern>`

### Arguments
| Argument | Required/Optional | Description |
| -------- | ----------------- | ----------- |
| `-s`     | Optional          | Specify a color hex code |
| `-p`     | Optional          | Specify a pre-programmed pattern |

### Examples
Set the LED color to hex code `8F00FF`: `led -s #8F00FF`  
Set the LED pattern to rainbow: `led -p rainbow`

### Resources:
Color codes can be found [here](https://htmlcolorcodes.com/)