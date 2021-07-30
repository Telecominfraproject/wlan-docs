---
description: OpenWiFi 2.0
---

# Multi-PSK \( MDU Multiple Shared Key \)

Multiple Pre Shared Key is a popular configuration option in Multi Dwelling Unit, dormitory or similar environment where it is costly to implement complex 802.1x security however that same level of per-client security is highly desired. 

A SSID when configured for multi-psk can have multiple PSK/VID mappings. Each one of them can be bound to a specific MAC or be a wildcard.

```text
			"ssids": [
				{
					"name": "MDU Wi-Fi",
					"wifi-bands": [
						"5G",
						"2G"
					],
					"bss-mode": "ap",
					"encryption": {
						"proto": "psk2",
						"ieee80211w": "optional",
						"key": "OpenWifi"
					},
					"multi-psk": [
						{
							"key": "akey",
							"vlan-id": 100
						},
						{
							"key": "bkey"
						}
					],
					"roaming": {
						"message-exchange": "ds",
						"generate-psk": true
					}
				}
			]
```

