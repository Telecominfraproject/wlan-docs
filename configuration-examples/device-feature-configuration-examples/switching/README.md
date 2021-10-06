---
description: TIP OpenWiFi 2.0
---

# Switching

{% hint style="info" %}
Switching Features Remain Under Test
{% endhint %}

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
			"role": "downstream",
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

Vlan-Id 30 has been assigned to interfaces 7 and 8 on the switch. Traffic is isolated among participating ports.  

#### Ifconfig output example

```text
# ifconfig
down1v30  Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:79 errors:0 dropped:0 overruns:0 frame:0
          TX packets:10 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:22135 (21.6 KiB)  TX bytes:1036 (1.0 KiB)

eth0      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C0  
          inet6 addr: fe80::923c:b3ff:fe39:c0c0/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1504  Metric:1
          RX packets:31617 errors:0 dropped:0 overruns:0 frame:0
          TX packets:7479 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:4293282 (4.0 MiB)  TX bytes:1228185 (1.1 MiB)
          Interrupt:24 Memory:c000000-bb00a3ff 

lan1      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:27321 errors:0 dropped:69 overruns:0 frame:0
          TX packets:5445 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:2893034 (2.7 MiB)  TX bytes:825702 (806.3 KiB)

lan7      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C7  
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:2204 errors:0 dropped:0 overruns:0 frame:0
          TX packets:507 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:421385 (411.5 KiB)  TX bytes:100251 (97.9 KiB)

lan8      Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C8  
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:1241 errors:0 dropped:0 overruns:0 frame:0
          TX packets:496 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:220496 (215.3 KiB)  TX bytes:98164 (95.8 KiB)

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:958 errors:0 dropped:0 overruns:0 frame:0
          TX packets:958 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:76410 (74.6 KiB)  TX bytes:76410 (74.6 KiB)

up        Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:27027 errors:0 dropped:0 overruns:0 frame:0
          TX packets:4368 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:3008700 (2.8 MiB)  TX bytes:587431 (573.6 KiB)

up0v0     Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet addr:10.75.0.154  Bcast:10.75.0.255  Mask:255.255.255.0
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:22673 errors:0 dropped:0 overruns:0 frame:0
          TX packets:3865 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:2390361 (2.2 MiB)  TX bytes:525377 (513.0 KiB)
```

#### Bridge Vlan Table Output

```text
# bridge vlan
port              vlan-id  
lan1              4090 PVID Egress Untagged
lan7              30 PVID Egress Untagged
lan8              30 PVID Egress Untagged
up                30
                  4090
#
```

### Assigning VLANs to Ports

To define additional VLAN memberships to any port, create additional "interfaces" configuration.

```text
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
        },
        {
			"name": "VLAN-40-Ports",
			"role": "upstream",
			"services": [ "lldp" ],
            "vlan": {
                "id": 40,
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

#### Ifconfig and Bridge Results

```text
up1v30    Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:1178 errors:0 dropped:0 overruns:0 frame:0
          TX packets:8 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:245923 (240.1 KiB)  TX bytes:816 (816.0 B)

up2v40    Link encap:Ethernet  HWaddr 90:3C:B3:39:C0:C1  
          inet6 addr: fe80::923c:b3ff:fe39:c0c1/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:106 errors:0 dropped:0 overruns:0 frame:0
          TX packets:8 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:34638 (33.8 KiB)  TX bytes:816 (816.0 B)


# bridge vlan
port              vlan-id  
lan1              4090 PVID Egress Untagged
lan7              30
                  40
lan8              30
                  40
up                30
                  40
                  4090
```









