# Run Ducky Script

### Menu Location
`BadUSB`>`Run Ducky Script`  

### Info
<b>The ESP32 Marauder must be connected to a target machine via USB</b>  
Allows the user to run ducky script keystroke injection attacks against a target machine with physical access.  
<b> This feature is only available on the ESP32 Marauder 7 </b>

### Writing Scripts
Once the menu option is selected, you will be presented with an on-screen keyboard and a text box. They keyboard can be used to type keystroke injection scripts written in [Ducky Script](https://docs.hak5.org/hc/en-us/articles/360049449314-Ducky-Script-Command-Reference#:~:text=Ducky%20Script%20is%20the%20payload,for%20all%20Hak5%20payload%20platforms.)

### Saving Scripts
Once a script is written, you will have the option to save the script to `/SCRIPTS` on the SD card.  
Upon selecting `Save As`, you will be presented with a new text box which will require you to enter the name of the file to save the script under.
<b>You must add the file extension if you wish it to have one</b>

### Loading Scripts
Ducky scripts are loaded from an SD card connected to the ESP32 Marauder.  
The scripts are stored on the SD card under `/SCRIPTS`.

Once `Load` is selected, you will be presented with a scrollable menu of scripts found on the SD card.

### Editing loaded Scripts
Once a script is loaded, you can edit it by using the on-screen keyboard. Hitting the `Save` button will save the current text box content under the currently loaded script.

### Executing Scripts
To execute the script shown in the text box, hit the check button on the button-right of the on-screen keyboard.