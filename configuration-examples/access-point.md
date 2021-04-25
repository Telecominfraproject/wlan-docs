---
description: Device Profiles
---

# Access Point

### Access Point Profile 

TIP SDK will process a 1:1 \(one to one\) or 1:Many \(one to many \) association of Access Point Profile offering a number of possible configuration approaches. 

When configuring in a 1:1 approach, it is advised to name the Access Point Profile in a manner meaningful to the deployment, for example Profile Name including significant OUI information. 

When configuring in a 1:M approach, it is advised to name the Access Point Profile in a manner meaningful to the shared service, RF parameters or grouped function all Access Points of this Profile will inherit. 

![Access Point Profile ](../.gitbook/assets/screen-shot-2021-04-25-at-2.52.34-pm.png)

Within the Access Point Profile, RF configuration all device members will share is specified. 

![RF Profile Associated to Access Point Profile](../.gitbook/assets/screen-shot-2021-04-25-at-2.54.30-pm.png)

One or many SSID Profiles may be associated to the Access Point Profile.

![SSIDs Enabled on Access Point Profile](../.gitbook/assets/screen-shot-2021-04-25-at-2.55.26-pm.png)

### Access Point

Relationship of RF Profile and Access Point Profile is visible in the Network, Access Point device record. 

Example inherited Profiles to an Access Point device:

![Network - Access Point Device Record - Profile](../.gitbook/assets/screen-shot-2021-04-25-at-2.59.35-pm.png)



