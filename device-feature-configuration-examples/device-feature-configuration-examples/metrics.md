---
description: TIP OpenWiFi 2.0
---

# Metrics

## Metrics

Several metrics are reported during intervals to the OpenWiFi Gateway. In general metrics contain traffic counters, neighbor tables, discovered clients.

Each OpenWiFi device is capable of sending statistics on SSID, LLDP, and associated Clients learned by the device.

Additionally, OpenWiFi devices expose all 802.11 management data within wifi-frames and to assist network troubleshooting and client fingerprinting solutions OpenWiFi provides dhcp-snooping for all possible client exchanges over DHCP and DHCPv6.

```
    "metrics": {
        "statistics": {
            "interval": 60,
            "types": [ "ssids", "lldp", "clients" ]
        },
        "health": {
            "interval": 300
        },
        "wifi-frames": {
            "filters": [ "probe",
                "auth",
                "assoc",
                "disassoc",
                "deauth",
                "local-deauth",
                "inactive-deauth",
                "key-mismatch",
                "beacon-report",
                "radar-detected"]
        },
        "dhcp-snooping": {
            "filters": [ "ack", 
                                "discover", 
                                "offer", 
                                "request", 
                                "solicit", 
                                "reply", 
                                "renew" ]
        }
```

The metrics data is sent to OpenWiFi Gateway at the intervals set where configurable.

Metrics must be associated with the interfaces they are to report on. For example, to send DHCP data from LAN to OpenWiFi Gateway, the following configuration would apply.

```
        {
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh", "lldp", "dhcp-snooping" ],
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
        }
    ],
```
