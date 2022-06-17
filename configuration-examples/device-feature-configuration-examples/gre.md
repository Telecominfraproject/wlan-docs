---
description: TIP OpenWiFi 2.0
---

# GRE

OpenWiFi 2.0 supports Generic Routing Encapsulation as an available "tunnel" protocol type.

This makes it possible to configure GRE for multiple types of deployments as any interface may be encapsulated by the "tunnel" parameter.

For example, to send all content of a specific SSID over an GRE tunnel, the following configuration would apply.

```
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
            }
        },
        {
            "name": "GRE",
            "role": "upstream",
            "vlan": {
                "id": 20
            },
            "tunnel": {
                "proto": "gre",
                "peer-address": "far end IP address",
            },
            "ssids": [
                {
                    "name": "Tunneled SSID via GRE from VLAN 20 Interface",
                    "wifi-bands": [
                        "2G", "5G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "none",
                        "ieee80211w": "optional"
                    },
                    "rate-limit": {
                        "ingress-rate": 100,
                        "egress-rate": 100
                    },                    
                    "roaming": {
                        "message-exchange": "ds",
                        "generate-psk": true
                    }
                }
            ]
        },
```

In the above example, the WAN untagged port will request DHCP in addition to present a VLAN interface with id 20 that both initiates the GRE tunnel as well as passes SSID traffic over that tunnel. Optionally the GRE tunnel itself may also carry a VLAN encapsulated payload. In the above example a WAN presentation of VLAN interface 20 has GRE tunnel. Within the GRE tunnel on WAN interface of VLAN 20 is a GRE payload with VLAN 30 in the payload header.&#x20;
