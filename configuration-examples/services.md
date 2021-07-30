---
description: OpenWiFi 2.0
---

# Services

OpenWiFi devices have global services that operate either independently system wide or as an association to a physical or logical interface. 

Within the "services" configuration block, define the operating mode for each service, then associate a service with an interface.

### SSH

Secure shell may be enabled on OpenWiFi devices, associated to specific interface\(s\), and support operator defined keys or password authentication.

```text
	"services": {
		"ssh": {
			"port": 22
		}
	}
```

#### Associate Service to Interface

```text
		{
			"name": "LAN",
			"role": "downstream",
			"services": [ "ssh" ],
			"ethernet": [
				{
					"select-ports": [
						"LAN*"
					]
				}
			],
```

### 

### NTP

Network time protocol for OpenWiFi devices may be configured to listen for time synchronization from  NTP sources and may also be configured to supply NTP source.

```text
	"services": {
		"ntp": {
			"servers": [
			"0.openwrt.pool.ntp.org",
			"1.openwrt.pool.ntp.org"
			]
		}
	}
```

#### Associate to an Interface 

```text
		{
			"name": "WAN",
			"role": "downstream",
			"services": [ "ntp" ],
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
```

### LLDP

Link Layer Discovery Protocol describes interfaces and capabilities between directly attached neighbors over Layer 2. 

```text
		"lldp": {
			"describe": "OpenWiFi",
			"location": "Stadium Level 2"
		},
```

Associate "lldp" as a services attribute to any interface.

### MDNS

To assist in device or service discovery over smaller networks,  multicast DNS \(mDNS\) protocol if often used. In an mDNS environment there is no local name server for resources to leverage.  mDNS zero-configuration service effectively behaves as unicast Domain Name Service \(DNS\).

```text
		"mdns": {
			"enable": true
		},
```

### Syslog 

Remote syslog systems may be configured to receive device logs in a central location. This content is standard device log and not related to telemetry for metrics and service information received by the OpenWiFi Gateway. 



### IGMP

When enabled the OpenWiFi device will process IGMP Proxy. 





