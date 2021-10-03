---
description: TIP OpenWiFi 2.0
---

# Captive Portal

OpenWiFi supports multiple models for Captive Portal. A built-in captive portal is described below. With multiple overlay tunnel services such as GRE and L2TP in addition to VLAN features, OpenWiFi is also easily deployed with any number of Captive Portal appliance solutions in either in-band or out-of-band style deployments.

## Local Captive Portal

Creating a local captive portal involves associating the "captive" service with an interface. In the example below, "captive" is enabled on a downstream role interface. Any associated SSID on LAN side of this Access Point will be subject to configuration of the local captive portal. This would also apply to LAN interfaces if also associated with "captive".

```text
        {
            "name": "captive",
            "role": "downstream",
            "captive": {
                "max-clients": 32,
                "gateway-name": "Lobby Wi-Fi Welcome",
                "upload-rate": 10,
                "download-rate": 20,
                "upload-quota": 300,
                "download-quota": 300
            },
            "ipv4": {
                "addressing": "static",
                "subnet": "192.168.2.1/24",
                "dhcp": {
                    "lease-first": 10,
                    "lease-count": 100,
                    "lease-time": "6h"
                }
            },
            "ssids": [
                {
                    "name": "Office Lobby Wi-Fi",
                    "wifi-bands": [
                        "5G",
                        "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "none",
                        "ieee80211w": "optional"
                    },
                    "roaming": {
                        "message-exchange": "ds",
                        "generate-psk": true
                    }
                }
            ]
        }
    ],
```

Local captive portal will redirect to a default landing page and display the name as configured in "gateway-name". Per associated user bandwidth and usage quota limits and total association limits may all be defined.

