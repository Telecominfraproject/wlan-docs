# RADIUS MAC-Auth

When deploying headless devices such as IoT services, MAC based authentication dedicated to a unique SSID may be required. TIP OpenWiFi supports MAC-Auth for any SSID when configured with RADIUS parameters set to "mac-filter" true.



Example&#x20;

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
                    "name": "OpenWiFi Headless",
                    "wifi-bands": [
                        "5G", "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "none",
                        "ieee80211w": "optional"
                    },
                    "radius": {
                        "authentication": {
                            "host": "192.168.178.192",
                            "port": 1812,
                            "secret": "secret",
                            "mac-filter": true
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



