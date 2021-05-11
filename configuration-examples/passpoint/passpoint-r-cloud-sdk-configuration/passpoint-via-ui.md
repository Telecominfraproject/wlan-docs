---
description: Passpoint® Configuration
---

# Passpoint® via UI

Cloud SDK user interface enables all Passpoint® configuration needed for live service. 

Passpoint® services will combine multiple Cloud SDK Profiles. 

* RADIUS
* Passpoint
* Passpoint ID Provider
* Passpoint Operator
* Passpoint Venue

### RADIUS Profile

Add a RADIUS Profile, specify the IP address and shared secret and port required for reachability and authentication and accounting with the defined server\(s\). 

![Profiles - RADIUS](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.35.43-pm.png)

### Operator Profile - Venue 

Each Operator of Wi-Fi services or Venue must be defined. 

![Passpoint Venue - Operator of Wi-Fi Services](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.42.28-pm.png)

### Passpoint Operator 

![Passpoint Operator - Profile](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.48.25-pm.png)

### Passpoint ID Provider

![Identity Provider Profile](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.52.04-pm.png)

Network Access Identifier \(NAI\) Realm implements all possible EAP methods for authentications. When adding EAP method, select the appropriate configuration to the deployment. 

![ID Provider NAI Configuration](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.54.38-pm.png)

![EAP Method](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.54.53-pm.png)

![EAP Method Authentication Mode](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.55.25-pm.png)

### Passpoint Profile

Passpoint profile aggregates the other Operator / Venue, Identity Provider together, once joined to an SSID will be combined with RADIUS in terms of the Access Point processing logic for UE association and authentication. 

Add Passpoint Profile

![Passpoint Profile with Venue Operator ID Provider SSID](../../../.gitbook/assets/screen-shot-2021-05-11-at-7.04.40-pm.png)

Associate to the SSIDs of network service:

![SSID to Passpoint Profile](../../../.gitbook/assets/screen-shot-2021-05-11-at-7.01.38-pm.png)

Advertise type of IP Connectivity

![IP Connectivity Advertisement](../../../.gitbook/assets/screen-shot-2021-05-11-at-6.59.32-pm.png)

Advanced settings support ANQP Domain ID, GAS Behaviors and DGAF operation

![Passpoint Profile Advanced](../../../.gitbook/assets/screen-shot-2021-05-11-at-7.00.11-pm.png)

