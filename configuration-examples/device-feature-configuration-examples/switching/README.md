---
description: TIP OpenWiFi 2.0
---

# Switching

TIP OpenWiFi use of the OpenWrt operating system combined with new virtual data plane present in all images for 2.0 major release and the uCentral data model make it possible to include PoE access switching as a cloud managed component of the OpenWiFi stack.

Nightly builds include supported switch platforms. 

Currently the list of features for switching include:

* IEEE 802.1Q VLAN
  * Port based Untagged
  * Tagged trunk
* IEEE 802.1ad Q-inQ
* VxLAN 
* PoE Auto Power 
* Port Mirroring / Monitor
* Link Aggregation
* Link Layer Discovery Protocol 
* Port Speed Control 

### Configuring a Switch

All ports needs to be specified for link negotiation to occur. In the below example, the "ethernet" section defines the physical port. The "interfaces" configuration will cause the physical port to negotiate. Effectively removal of a "select-ports" for a physical port in any or all "interfaces" is the equivalent of an interface in shutdown state. 

```text
    "ethernet": [
        {
            "select-ports": [
                    "WAN1"
            ],
            "speed": 1000,
            "duplex": "full"
        },
        {
            "select-ports": [
                    "WAN2"
            ],
            "speed": 1000,
            "duplex": "full"
        },
        {
            "select-ports": [
                    "WAN3"
            ],
            "speed": 1000,
            "duplex": "full"
        },
        {
            "select-ports": [
                    "WAN4"
            ],
            "speed": 1000,
            "duplex": "full"
        },
        {
            "select-ports": [
                    "WAN5"
            ],
            "speed": 1000,
            "duplex": "full"
        },       
        {
            "select-ports": [
                    "WAN6"
            ],
            "speed": 1000,
            "duplex": "full"
        },
        {
            "select-ports": [
                    "WAN7"
            ],
            "speed": 1000,
            "duplex": "full",
            "vlan-tag": "auto"
        },       
        {
            "select-ports": [
                    "WAN8"
            ],
            "speed": 1000,
            "duplex": "full",
            "vlan-tag": "auto"
        },       
        {
            "select-ports": [
                    "WAN9"
            ],
            "speed": 1000,
            "duplex": "full"
        },       
        {
            "select-ports": [
                    "WAN10"
            ],
            "speed": 1000,
            "duplex": "full"
        },       
        {
            "select-ports": [
                    "WAN11"
            ],
            "speed": 1000,
            "duplex": "full"
        },       
        {
            "select-ports": [
                    "WAN12"
            ],
            "speed": 1000,
            "duplex": "full"
        }                       
    ],
```

Without any "interfaces" defined, the ifconfig on the switch will return eth0, lan1, lo as an output. When adding "interfaces" additional ports become active and also visible. 

```text
   "interfaces": [
		{
        {
			"name": "VLAN-30-Ports",
			"role": "upstream",
			"services": [ "lldp" ],
            "vlan": {
                "id": 30,
                "proto": "802.1q"
            },
			"ethernet": [
				{
					"select-ports": [
						"WAN7", "WAN8"
					]
				}
			]
     }
```

Vlan-Id 30 has been assigned to interfaces 7 and 8 on the switch. 

#### Ifconfig output example

```text
# ifconfig
eth0      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C0  
          inet6 addr: fe80::923c:b3ff:fe39:c0c0/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1504  Metric:1
          RX packets:24115 errors:0 dropped:0 overruns:0 frame:0
          TX packets:4807 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:3322522 (3.1 MiB)  TX bytes:865658 (845.3 KiB)
          Interrupt:24 Memory:c000000-bb00a3ff 

lan1      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:20544 errors:0 dropped:68 overruns:0 frame:0
          TX packets:3061 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:2194380 (2.0 MiB)  TX bytes:540139 (527.4 KiB)

lan7      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C7  
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:1772 errors:0 dropped:0 overruns:0 frame:0
          TX packets:360 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:343681 (335.6 KiB)  TX bytes:72656 (70.9 KiB)

lan8      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C8  
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:948 errors:0 dropped:0 overruns:0 frame:0
          TX packets:355 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:161130 (157.3 KiB)  TX bytes:71641 (69.9 KiB)

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:742 errors:0 dropped:0 overruns:0 frame:0
          TX packets:742 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:59470 (58.0 KiB)  TX bytes:59470 (58.0 KiB)

up        Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:20024 errors:0 dropped:0 overruns:0 frame:0
          TX packets:2090 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:2254588 (2.1 MiB)  TX bytes:325852 (318.2 KiB)

up0v0     Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet addr:10.75.0.154  Bcast:10.75.0.255  Mask:255.255.255.0
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:16032 errors:0 dropped:0 overruns:0 frame:0
          TX packets:1615 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:1713250 (1.6 MiB)  TX bytes:266686 (260.4 KiB)

up1v30    Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:1096 errors:0 dropped:0 overruns:0 frame:0
          TX packets:8 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:233477 (228.0 KiB)  TX bytes:816 (816.0 B)
```

#### Bridge Vlan Table Output

```text
# bridge vlan
port              vlan-id  
lan1              4090 PVID Egress Untagged
lan7              30
lan8              30
up                30
                  4090
# 
```







