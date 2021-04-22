# Clear SSIDs
The ESP32 Marauder maintains a list of ESSIDs to be used in a [Beacon Spam](beacon-spam-list) attack. The list is stored in memory and is cleared anytime the ESP32 Marauder is powered off or rebooted.  

Once this option is selected, the ESP32 Marauder will clear any SSIDs added to the list by [Generate SSIDs](generate-ssids) and [Add SSID](add-ssid).