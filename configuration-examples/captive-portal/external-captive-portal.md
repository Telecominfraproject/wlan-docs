---
description: OpenWiFi 2.1
---

# External Captive Portal

When an external access controller, such as a captive portal appliance or a Universal Access Method \(UAM\) redirector is required to handle subscriber login, OpenWiFi optionally supports builds that include use of CoovaChili. 

To configure a CoovaChilli service, OpenWiFi supports the `"third-party"` schema definition.  

Through the use of third-party, many configurations are possible, for external captive portal, third-party will process a services lookup of `"chilli"` applied to an interface. 

Within `"third-party"` will be the necessary CoovaChilli configuration parameters.

```text
"third-party": {
                "chilli": {
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

Associate to an interface:

```text
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
					"name": "chilli-redirect",
					"wifi-bands": [
						"2G", "5G"
					],
					"bss-mode": "ap"
				}
			]
		}
```

