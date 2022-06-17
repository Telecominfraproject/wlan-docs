---
description: TIP OpenWiFi 2.0
---

# RADIUS Authenticated SSID

When authenticating clients with back office RADIUS systems, the configuration of OpenWiFi permits this on a per SSID basis.

{% tabs %}
{% tab title="Simple RADIUS" %}
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
            },
            "ssids": [
                {
                    "name": "OpenWifi",
                    "wifi-bands": [
                        "5G"
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
{% endtab %}

{% tab title="EAP-Local SSID" %}
```
            "ssids": [
                {
                    "name": "OpenWifi",
                    "wifi-bands": [
                        "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "wpa2",
                        "ieee80211w": "optional"
                    },
                    "certificates": {
                        "ca-certificate": "/etc/ucentral/cas.pem",
                        "certificate": "/etc/ucentral/cert.pem",
                        "private-key": "/etc/ucentral/key.pem"
                    },
                    "radius": {
                        "local": {
                            "server-identity": "OpenWiFi-Local-EAP",
                            "users": [
                                {
                                    "user-name": "open",
                                    "password": "wifi"
                                }
                            ]
                        }
                    }
                }
            ]
        },
```
{% endtab %}
{% endtabs %}

Many parameters are possible with RADIUS authentications given the many methods in use worldwide. Many of the EAP methods have configuration options described below.

| RADIUS Attribute   | Description                                                                                                                                                                                                                                                                                                                                                                                                          |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| nas-identifier     | Unique NAS Id used with RADIUS server                                                                                                                                                                                                                                                                                                                                                                                |
| chargeable-user-id | Chargeable User Entity per RFC4372                                                                                                                                                                                                                                                                                                                                                                                   |
| local              | <p>Local RADIUS within AP device</p><ul><li><p>server-identity</p><ul><li>users - Local EAP users based on username, PreShared Key and VLAN id</li></ul></li></ul>                                                                                                                                                                                                                                                   |
| authentication     | <p>RADIUS server</p><ul><li>host IP address</li><li>port ( example 1812)</li><li>secret ( Shared secret with RADIUS server )</li></ul><p>Additional methods within Access-Request</p><ul><li><p>request-attribute ( id of RADIUS server )</p><ul><li>id ( numeric value of RADIUS server )</li><li><p>value</p><p>Any sub-value defined as integer RADIUS attribute value</p></li></ul></li></ul>                    |
| accounting         | <p>RADIUS server</p><ul><li>host IP address</li><li>port ( example 1813)</li><li>secret ( Shared secret with RADIUS server )</li></ul><p>Additional methods within Access-Request sent in Accounting</p><ul><li><p>request-attribute ( id of RADIUS server )</p><ul><li>id ( numeric value of RADIUS server )</li><li><p>value</p><p>Any sub-value defined as integer RADIUS attribute value</p></li></ul></li></ul> |
| accounting         | interval ( Interim accounting interval defined in seconds )                                                                                                                                                                                                                                                                                                                                                          |
