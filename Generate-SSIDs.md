# Generate SSIDs
<p align="left">
  <img alt="ESP32 WROOM-32U" src="https://github.com/justcallmekoko/ESP32Marauder/blob/master/pictures/icons/generate_22.bmp?raw=true" width="100">
</p>
The ESP32 Marauder maintains a list of ESSIDs to be used in a [Beacon Spam](beacon-spam-list) attack. The list is stored in memory and is cleared anytime the ESP32 Marauder is powered off or rebooted.  

Once this option is selected, the ESP32 Marauder generates 20 random ESSIDs and BSSIDs and adds them to the list of SSIDs.  

These SSIDs will appear in the list of SSIDs show when using [Add SSID](add-ssid).

Generated SSIDs can be cleared from the list using [Clear SSIDs](clear-ssids)