---
description: OpenWiFi 2.0
---

# WDS

Wireless Distribution System \(WDS\) supports an Access Point, Station and Repeater mode of operation. OpenWiFi 2.0 supports all three.

In the below example, the LAN side of the Access Point at the top of the topology will be wirelessly bridged to the LAN side of the Access Point Station at the bottom of the topology.

{% tabs %}
{% tab title="WDS-AP" %}
```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "lldp" ],
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
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh", "lldp" ],
            "ethernet": [
                {
                    "select-ports": [
                        "LAN*"
                    ]
                }
            ],
            "ssids": [
                {
                    "name": "OpenWifi_WDS_AP",
                    "wifi-bands": [
                        "5G"
                    ],
                    "bss-mode": "wds-ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    },
                    "roaming": {
                        "message-exchange": "ds",
                        "generate-psk": true
                    }
                }
            ],            
            "ipv4": {
                "addressing": "static",
                "subnet": "192.168.10.1/24",
                "dhcp": {
                    "lease-first": 10,
                    "lease-count": 100,
                    "lease-time": "6h"
                }
            }
        }
    ],
```
{% endtab %}

{% tab title="WDS-STA" %}
```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "lldp" ],
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
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh", "lldp" ],
            "ethernet": [
                {
                    "select-ports": [
                        "LAN*"
                    ]
                }
            ],
            "ssids": [
                {
                    "name": "OpenWifi_WDS_AP",
                    "wifi-bands": [
                        "5G"
                    ],
                    "bss-mode": "wds-sta",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    },
                    "roaming": {
                        "message-exchange": "ds",
                        "generate-psk": true
                    }
                }
            ],
    }
```
{% endtab %}
{% endtabs %}

In this configuration, LAN clients of the WDS Station AP receive IP addresses from the WDS Access Point AP from its LAN side DHCP service, via WDS link at 5GHz.

