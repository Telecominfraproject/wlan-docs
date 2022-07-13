---
description: TIP OpenWiFi 2.0
---

# External Captive Portal

When an external access controller, such as a captive portal appliance or a Universal Access Method (UAM) redirector is required to handle subscriber login, OpenWiFi optionally supports builds that include use of CoovaChili. This would be found in build profile chilli-redirect.yml.

To configure a CoovaChilli service, OpenWiFi supports the `"third-party"` schema definition.

Through the use of third-party, many configurations are possible, for external captive portal, third-party will process a services lookup of `"chilli-redirect"` applied to an interface.

Within `"third-party"` will be the necessary CoovaChilli configuration parameters.

```
"third-party": {
                "chilli-redirect": {
                        "uamport": 3990,
                        "radiusauthport": 1812,
                        "radiusacctport": 1813,
                        "radiusserver1": "radiusServerIP",
                        "radiusserver2": "radiusServerIP",
                        "radiusnasid": "nasID",
                        "uamallowed": "allowed.example.com,10.0.0.1,192.168.10.1",
                        "uamdomain": "exampleUAMdomain.com,otherExampleUAMdomain.com",
                        "defidletimeout": 900,
                        "definteriminterval": 600,
                        "acctupdate": 1,
                        "uamserver": "https://portal.example.com/portal/default/index.php?n=NAME&c=3&l=181",
                        "radiussecret": "radiusSecret",
                        "nasmac": "00:01:02:03:04:AA"
                }
        }
```

## NAT Mode

Associate to an interface:

```
{
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh", "chilli-redirect" ],
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
            },
            "ssids": [
                {
                    "name": "Hotspot SSID Name",
                    "wifi-bands": [
                        "2G", "5G"
                    ],
                    "bss-mode": "ap"
                }
            ]
        }
```

## Bridge Mode

In the above example, captive portal redirection occurs via a NAT interface on LAN side or `"downstream"` role.

When a direct to WAN presentation, or bridge mode operation is desired, associate the service to the `"upstream"` interface.

Associate to an interface:

```
"interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "chilli-redirect" ],
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
                    "name": "Hotspot SSID Name",
                    "wifi-bands": [
                        "2G", "5G"
                    ],
                    "bss-mode": "ap"
                }
            ]
        },
```
