# AP Clone spam workflow
An AP Clone Spam attack will broadcast beacon frames with the SSIDs of other access points in range with spaces appended to their names. This will give the appearance of multiple access points with the same name to anyone looking at available WiFi networks.  
The following describes the order of operations necessary to properly execute this attack.

1. Scan for access points in range
    - `scanap`
2. Display list of access points from your scan
    - `list -a`
3. Select the access points you want to clone and spam (Selecting APs 0, 1, 2 for example)
    - `select -a 0,1,2`
4. Confirm the access points have been selected
    - `list -a`
5. Execute the AP Clone Spam attack
    - `attack -t beacon -a`


### References
- [scanap](scanap)
- [list](list)
- [select](select)
- [attack](attack)