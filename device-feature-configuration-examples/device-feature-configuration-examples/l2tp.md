---
description: TIP OpenWiFi 2.0
---

# L2TP

Layer 2 Tunneling Protocol may be associated to any interface using the "tunnel" configuration option.

This makes it possible to configure L2TP for multiple types of deployments as any interface may be encapsulated by the "tunnel" parameter.

For example, to send all content of a specific SSID over an L2TP tunnel, the following configuration would apply.

```
        {
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh" ],
            "ethernet": [
                {
                    "select-ports": [
                        "LAN*"
                    ]
                }
            ],
            "ipv4": {
                "addressing": "static",
                "subnet": "192.168.1.1/24",
                "dhcp": {
                    "lease-first": 10,
                    "lease-count": 100,
                    "lease-time": "6h"
                }
            }
        },
        {
            "name": "L2TP",
            "role": "downstream",
            "tunnel": {
                "proto": "l2tp",
                "server": " far end IP address ",
                "user-name": "secret-l2tp-username",
                "password": "secrectPassword"
            },
            "ipv4": {
                "addressing": "static",
                "subnet": "192.168.10.1/24",
                "dhcp": {
                    "lease-first": 10,
                    "lease-count": 100,
                    "lease-time": "6h"
                }
            },
            "ssids": [
                {
                    "name": "Tunneled SSID",
                    "wifi-bands": [
                        "5G", "2G"
                    ],
                    "bss-mode": "ap"
                }
            ]
        }
    ],
```
