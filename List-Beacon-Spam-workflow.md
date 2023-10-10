# List Beacon Spam workflow
List Beacon Spam is a method of beacon spam where beacon frames are constructed from a list of SSIDs provided by the user then broadcasted to all stations in range.  
The following describes the order of operations necessary to properly execute this attack.

1. Create a list of SSIDs (use any of these options)
    - `ssid -a -g 3` (generates 3 random SSIDs)
    - `ssid -a -n chiken` (adds a single SSID named "chicken")
2. Display your list of SSIDs to confirm they have been added
    - `list -s`
3. Execute a beacon list spam attack
    - `attack -t beacon -l`

### References
- [ssid](ssid)
- [list](list)
- [attack](attack)