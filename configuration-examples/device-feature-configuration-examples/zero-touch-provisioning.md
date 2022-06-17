---
description: OpenWiFi 2.0
---

# Zero Touch Provisioning

OpenWiFi supports Zero Touch Provisioning in a number of ways.&#x20;

* Zero Touch Mesh
* Zero Touch WDS
* Zero Touch Provisioning ( Provisioning Services in upcoming 2.5/2.6 Release )

### Onboarding&#x20;

OpenWiFi makes use of TIP device certificates present on every access point as a secure identity from which to automate a number of Zero Touch operations.&#x20;

Onboarding is a local EAP-TLS based authentication service available on any OpenWiFi device that works together with default OpenWiFi _firstboot_ behavior to scan for `"OpenWifi-onboarding"` SSID, associate to that SSID, when challenged supply TIP root signed device certificate.&#x20;

#### Onboarding Steps

1. Provision an Access Point for onboarding role as an SSID config\
   `{` \
   &#x20;  `"purpose": "onboarding-ap",` \
   &#x20;  `"bss-mode": "ap",` \
   &#x20;  `"encryption": { "proto": "wpa2", "ieee80211w": "required" },`    \
   &#x20;  `"certificates": { "use_local_certificates": true },` \
   &#x20;  `"radius": { "local":` \
   &#x20;            `{ "server-identity": "uCentral-EAP" }` \
   &#x20;            `},` \
   &#x20;   `"name": "OpenWifi-onboarding",` \
   &#x20;   `"wifi-bands": [ "2G" ]` \
   `}`
2. Ensure the SSID for onboarding use provides network connectivity for clients
   * Any topology such as NAT, Bridge, VLAN may be used
   * Any radio(s) may be used
3. Firstboot devices with no WAN wired port detected will
   * Enable all radios
   * Scan for SSID "OpenWifi-onboarding"
   * Associate and when challenged use TIP certificate as identity
   * Obtain IP connection using DHCP over wireless interface association to onboarding AP
   * Connect to SDK, obtain provisioning from OpenWiFi Gateway service
   * Reload configuration&#x20;

### Zero Touch Mesh

Deployment of Mesh may have multiple Mesh Client access points with no wired connectivity. These devices use IEEE802.11s Mesh participating interface(s) as transit for WAN / LAN connections.&#x20;

In a Zero Touch Mesh deployment, the Gateway Access Point, sometimes termed the Root node, advertises mesh participating interfaces when `"bss-mode": "mesh"` is applied to an SSID. Please see [mesh.md](mesh.md "mention") for further details on initial setup.

Mesh Client Access Points needing to associate wirelessly for initial provisioning to join the mesh network, may be served using the onboarding feature of OpenWiFi. &#x20;

Adding an SSID to the Mesh Gateway Access Point configuration to advertise `"OpenWifi-onboarding"` enables initial boot of any OpenWiFi Access Point to reach the OpenWiFi Gateway.&#x20;

Upon connection to Onboarding, the Access Point obtains management network access from the upstream Access Point providing `"onboarding-ap"` service.&#x20;

With management network access, reachability for the Mesh Client Access Point to the OpenWiFi Gateway should be possible, device provisioning stage will initiate with the production configuration being loaded to the client device.&#x20;

Once processed, client Access Point will have receive provisioning to join the Mesh network as a Mesh Client Access Point.&#x20;

### Zero Touch WDS&#x20;

Deployment of WDS links may have multiple WDS client devices with no wired WAN connectivity. WDS Access Points use the 4-tuple frame header with participating WDS Clients. Therefore WDS Clients must first receive provisioning from the OpenWiFi Gateway for their production state as a WDS link participant.&#x20;

WDS Client Access Points needing to associate wirelessly for initial provisioning to join the WDS network, may be served using the onboarding feature of OpenWiFi from the WDS Root Access Point at the top of the topology with a `"bss-mode": "ap"` SSID for onboarding. &#x20;

Adding an SSID to the WDS Root Access Point configuration to advertise `"OpenWifi-onboarding"` enables initial boot of any OpenWiFi Access Point to reach the OpenWiFi Gateway.&#x20;

Upon connection to Onboarding, the WDS Client Access Point obtains management network access from the upstream WDS Root Access Point providing `"onboarding-ap"` service.&#x20;

With management network access, reachability for the WDS Client Access Point to the OpenWiFi Gateway should be possible, device provisioning stage will initiate with the production configuration being loaded to the client device. For more information on WDS configuration please consult [WDS](wds-topologies.md).

Once processed, WDS Client Access Point will have receive provisioning to join the WDS link as a Client WDS node.&#x20;

###
