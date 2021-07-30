---
description: OpenWiFi 2.0
---

# Mesh

OpenWiFi Mesh has been designed to eliminate configuration complexity while also remaining capable of advanced topology designs including Multi-Gateway, Multi-SSID, VLAN, and Zero Touch Mesh onboarding. 

The physical wired interface\(s\) to participate in the mesh topology egress are defined with the protocol "mesh".

The logical wireless interface\(s\) to participate in mesh topology are defined by their bss-mode set to "mesh".

{% tabs %}
{% tab title="Basic Mesh" %}
```text
	"interfaces": [
		{
			"name": "WAN",
			"role": "upstream",
            "tunnel": {
				"proto": "mesh"
			},           
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
					"name": "transit",
					"wifi-bands": [
						"5G"
					],
					"bss-mode": "mesh",
					"encryption": {
						"proto": "psk2",
						"key": "meshpassword",
						"ieee80211w": "optional"
					}
				},
                {
					"name": "2GHz Clients",
					"wifi-bands": [
						"2G"
					],
					"bss-mode": "ap",
					"encryption": {
						"proto": "psk2",
                        "key": "OpenWiFi",
						"ieee80211w": "optional"
					}
				},                  
					{
						"name": "5GHz Clients",
						"wifi-bands": [
							"5G"
						],
						"bss-mode": "ap",
						"encryption": {
							"proto": "psk2",
							"key": "OpenWiFi",
							"ieee80211w": "optional"
						}					

					}
			]
		},
```
{% endtab %}
{% endtabs %}

In this basic mesh, dual SSIDs are configured for clients while an SSID for mesh transit is configured for IEEE802.11s client associations. Additional mesh clients simply use the same approach, no other configuration is required for the client to participate in this mesh. 

Advanced examples with VLANs and roaming are all possible by adding additional configuration steps. 

