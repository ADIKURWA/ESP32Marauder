# Deauthentication Attack workflow

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