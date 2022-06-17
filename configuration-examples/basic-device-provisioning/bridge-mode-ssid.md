---
description: OpenWiFi 2.0
---

# Bridge Mode SSID

Creating logical bridges may be done through association to named "interfaces".\
To associate a logical SSID interface directly to the WAN, place SSID configuration within the interface have a "role" of upstream.

{% tabs %}
{% tab title="SSID to WAN" %}
```
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
            },
            "ssids": [
                {
                    "name": "OpenWifi",
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
```
{% endtab %}

{% tab title="Dual SSID to WAN" %}
```
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
            },
            "ssids": [
                {
                    "name": "OpenWifi_2GHz",
                    "wifi-bands": [
                        "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    }
                },
                {
                    "name": "OpenWifi_5GHz",
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
```
{% endtab %}

{% tab title="Dual SSID Bridge Rate-Limit to WAN" %}
```
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
            },
            "ssids": [
                {
                    "name": "OpenWifi_2GHz",
                    "wifi-bands": [
                        "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    },
                    "rate-limit": {
                        "ingress-rate": 100,
                        "egress-rate": 100
                    }
                },
                {
                    "name": "OpenWifi_5GHz",
                    "wifi-bands": [
                        "5G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWifi",
                        "ieee80211w": "optional"
                    },
                    "rate-limit": {
                        "ingress-rate": 250,
                        "egress-rate": 250
                    }
                }
            ]
```
{% endtab %}
{% endtabs %}
