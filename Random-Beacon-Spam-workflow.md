# Random Beacon Spam workflow
Random Beacons Spam describes an attack where the user broadcasts beacon frames with random SSIDs. There are two ways to accomplish this attack with Marauder.  
The following describes the order of operations necessary to properly execute this attack.

### Beacon Spam Random List
This method will generate a list of random SSIDs. During the Beacon Spam, the SSIDs broadcasted will only be from the list of SSIDs randomly generated in the first steps.
1. Generate a random list of 50 SSIDs
    - `ssid -a -g 50`
2. Display the list of SSIDs to confirm they have been added to your list
    - `list -s`
3. Execute a beacon list attack
    - `attack -t beacon -l`

### Beacon Spam Random Auto
This method will generate a new random SSID every time a beacon frame is built and sent. There is no requirement to generate a list of SSIDs
1. Execute a random beacon spam attack
    - `attack -t beacon -r`