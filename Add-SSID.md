# Add SSID
The ESP32 Marauder maintains a list of ESSIDs to be used in a [Beacon Spam](beacon-spam-list) attack. The list is stored in memory and is cleared anytime the ESP32 Marauder is powered off or rebooted.  

Once this option is selected, the user will be presented with a large, scrollable text box and an on-screen keyboard. The keyboard is used to add ESSIDs to the large text box. Enter the ESSID and hit the check button on the bottom right of the keyboard to add it to the list. Hit the X button on the button left to exit the keyboard and return to the menu.  

SSIDs added by using [Generate SSIDs](generate-ssids) will appear in the text box containing the list of SSIDs.  
SSIDs can be cleared from the list by using [Clear SSIDs](clear-ssids)