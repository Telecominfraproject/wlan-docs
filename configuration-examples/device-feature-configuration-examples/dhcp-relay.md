---
description: TIP OpenWiFi 2.0
---

# DHCP Relay

When operators of enterprise or service provider networks seek to influence or control the allocation of dynamically assigned IP address, typically the network edge has been provisioned to encode information in DHCP Relay packets that help identify the access device through which a subscriber is attached, the logical sub-interface of that network edge or the subscriber directly.

TIP OpenWiFi supports DHCP Relay with encoding of client Circuit-Id information containing any of:

* Interface
* VLAN-Id
* SSID
* Encryption Mode
* Device Name
* Device Model
* Device Location
* Access Point MAC Address
* Access Point MAC in Hex
* Client MAC Address
* Client MAC Address in Hex

TIP OpenWiFi Relay-Agent remote-id may be configured to contain any of the following:

* VLAN-Id
* SSID
* AP-MAC
* AP-MAC-Hex
* Client MAC
* Client MAC Hex

The remote-id originates from a configured IPv4 interface address.

```
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
					"relay-server" : "192.168.100.20",
					"circuit-id-format": "{Interface}:{SSID}:{AP-MAC}:{Location}",
					"remote-id-format": "{AP-MAC}:{SSID}"
				}
			}
		}
	]
```

In the above example, when the IPv4 downstream interface 192.168.1.1 has DHCP enabled for `relay-server` a DHCP relay process associates to the IP interface of the subnet. When DHCP DISCOVER packets arrive as broadcasts, they will be copied to a unicast packet from the `192.168.1.1` interface as the `relay-id` source address and unicast forwarded to the defined `relay-server` address. Additional parameters are encoded for inspection at the DHCP server as present in `circuit-id`-format and `remote-id`-format options.&#x20;
