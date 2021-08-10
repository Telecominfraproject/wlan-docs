---
description: OpenWiFi 2.0
---

# Multi-VLAN SSID

The most common use case for VLANs and Wi-Fi is likely the service provider, venue, enterprise where Wi-Fi traffic is not subject to address translation. This is the example that will be shown, however it is entirely possible to create multiple downstream VLANs with SSIDs as well. Simply replace the logic of upstream to downstream where desired.

{% tabs %}
{% tab title="Single SSID VLAN" %}
```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "lldp", "dhcp-snooping" ],
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
                "name": "WAN100",
                "role": "upstream",
                "vlan": {
                    "id": 100
                },
                "ethernet": [
                    {
                        "select-ports": [
                            "WAN*"
                        ]
                    }
                ],         
            "ssids": [
                {
                    "name": "VLAN 100 Wi-Fi",
                    "wifi-bands": [
                        "2G", "5G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    }
                }
            ]
        },
```
{% endtab %}

{% tab title="Dual SSID - Dual VLAN" %}
```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "lldp", "dhcp-snooping" ],
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
                "name": "WAN100",
                "role": "upstream",
                "vlan": {
                    "id": 100
                },
                "ethernet": [
                    {
                        "select-ports": [
                            "WAN*"
                        ]
                    }
                ],         
            "ssids": [
                {
                    "name": "VLAN 100 Wi-Fi",
                    "wifi-bands": [
                        "2G", "5G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    }
                }
            ]
        },
            {
                "name": "WAN200",
                "role": "upstream",
                "vlan": {
                    "id": 200
                },
                "ethernet": [
                    {
                        "select-ports": [
                            "WAN*"
                        ]
                    }
                ],         
            "ssids": [
                {
                    "name": "VLAN 200 Wi-Fi",
                    "wifi-bands": [
                        "5G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    }
                }
            ]
        },
```
{% endtab %}
{% endtabs %}

In all cases the WAN port without VLAN id is using DHCP to obtain a management IP address.  
Each additional "upstream" role interface with an SSID associated have no IP configuration.

