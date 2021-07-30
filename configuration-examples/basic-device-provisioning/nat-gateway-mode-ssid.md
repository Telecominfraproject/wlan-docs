---
description: OpenWiFi 2.0
---

# NAT Gateway Mode SSID

Creating a NAT Gateway is easily done via association to an interface having a role of "downstream".

{% tabs %}
{% tab title="Dual SSID NAT" %}
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
					"name": "OpenWifi_2GHz",
                    "role": "downstream",
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
                    "role": "downstream",
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

		}
```
{% endtab %}
{% endtabs %}

Based on the above Dual SSID NAT configuration, a unique 2GHz and 5GHz SSID are created and logically bound to the same NAT LAN side network. 

The NAT service is inherited by the downstream role with DHCP addressing defined according to the range set within the downstream "ipv4" configuration. 

