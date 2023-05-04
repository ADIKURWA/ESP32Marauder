# Targeted Active PMKID Sniff workflow
The following documentation describes a method of traffic sniffing where WPA handshakes are provoked from client and AP by means of deauthentication attack. Unlike the a general active PMKID sniff, this workflow utilizes a pre-scanned list of access points to ensure only the target devices are disrupted.

1. Build list of target access points
  - `scanap`  
![image](https://user-images.githubusercontent.com/25190487/236300558-fa38c9b7-7c75-4cf0-853c-43543586ace3.png)

2. Display list of available access points
  - `list -a`  
![image](https://user-images.githubusercontent.com/25190487/236300601-a2e6b79b-6acd-453e-8525-71dcf1321ea7.png)

3. Select a target access points from the list. Multiple access points may be specified
  - `select -a 0,1`  
4. Verify access points 0 and 1 have been selected with list
  - `list -a`  
![image](https://user-images.githubusercontent.com/25190487/236300655-a9e5494e-b1a0-4d80-9467-c4e0c5634889.png)

5. Execute a targeted active PMKID sniff
  - `sniffpmkid -d -l`

You will see notification text indicating when a beacon from a target access point is received and that a deauthentication attack is being executed.