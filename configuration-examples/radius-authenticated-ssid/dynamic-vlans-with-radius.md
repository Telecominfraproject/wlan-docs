---
description: TIP OpenWiFi 2.0
---

# Dynamic VLANs with RADIUS

In many deployment scenarios, user authentication is centralized with RADIUS systems. In addition, users may have association to their own networks or private networks. A common approach for this is to dynamically assign VLANs to Wi-Fi subscribers as they join the OpenWiFi network.

To configure Dynamic VLANs with RADIUS, associate an SSID with RADIUS authentication, and associate the interface to "upstream" role as dynamic VLANs are most likely to be applicable across the service provider, venue, enterprise network.

```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "ethernet": [
                {
                    "select-ports": [
                        "WAN*"
                    ]
                }
            ],
            "ipv4": {
                "addressing": "dynamic"
            },
            "ssids": [
                {
                    "name": "OpenWifi",
                    "wifi-bands": [
                        "5G", "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "wpa2",
                        "ieee80211w": "optional"
                    },
                    "radius": {
                        "authentication": {
                            "host": "192.168.178.192",
                            "port": 1812,
                            "secret": "secret"
                        },
                        "accounting": {
                            "host": "192.168.178.192",
                            "port": 1813,
                            "secret": "secret"
                        }
                    }
                }
            ]
        },
```

## RADIUS Access-Accept

OpenWiFi devices will determine a VLAN is associated to the authentication of a subscriber when the access-accept message returns the following attribute value pairs:

* Tunnel-Type = 13
* Tunnel-Medium-Type = 6
* Tunnel-Private-Group-Id = VLAN Id Number

Upon return of an access-accept from RADIUS, based on any method chosen for security, OpenWiFi will dynamically create a VLAN Id as described in Tunnel-Private-Group-Id, associated to the interface role, in this example upstream.

