---
description: OpenWiFi 2.0 Device Configuration
---

# Creating a Configuration

To introduce the Community to the uCentral data model structure, the below illustrates a basic Access Point configuration that assumes a typical enterprise Wi-Fi scenario of a ceiling mount or wall mount device presenting a single WAN interface with a private management network and separate Wi-Fi network on a virtual local area network.

## Start with Location and Radios

We will set the unit location and timezone, then proceed to configure radios.

```
{
    "uuid": 2,
    "unit": {
        "location": "TIP Lab Network",
        "timezone": "EST+5EDT,M3.2.0/2,M11.1.0/2"
    },
    "radios": [
        {
            "band": "5G",
            "country": "CA",
            "channel": "auto",
            "channel-mode": "HE",
            "channel-width": 80,
            "require-mode": "HT",
            "rates": {
                "beacon": 6000,
                "multicast": 24000
            }
        },
        {
            "band": "2G",
            "country": "CA",
            "channel": 11,
            "channel-mode": "HE",
            "channel-width": 80,
            "require-mode": "HT",
            "rates": {
                "beacon": 6000,
                "multicast": 24000
            }
        }
    ],
```

In this example, a two radio device that indicates it is Wi-Fi 6 as the channel-mode values for both radios is "HE" which defines 802.11ax operation. Valid values are "HT" -High Throughput 802.11n mode, "VHT" - Very High Throughput 802.11ac mode, "HE" - High Efficiency 802.11ax mode.

Channel defines the specific channel number the radio shall operate on as an integer from 1 - 171 and may also be set to a string for "auto" mode. Channel width permits configuring the amount of RF channel the radio will operator over from 20-40-80-160 including 8080 mode (also known as 80+80) .

OpenWiFi radios may be set to require UE clients to associate to a minimum standard such as excluding any 802.11b associations depicted above with "require-mode" set to "HT" meaning 802.11n or higher clients may associate.

Control of beacon interval and multicast rates is possible per radio as shown in the "rates" section.

## Interfaces

OpenWiFi 2.0 offers a highly flexible model for arranging network interfaces. Multi-port devices may be easily provisioned for numerous types of network segmentation and logical network configuration. We will start with a simple WAN that has a management IP and also a VLAN sub-interface for a logical SSID in a subsequent step.

```
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "lldp", "dhcp-snooping" ],
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

In the above configuration block we have a WAN interface, its role is "upstream" meaning it faces the upstream in terms of service it provides (WAN). This has a direct alignment to how the device interprets a physical or logical port participates in bridge forwarding domains.

Note we want this port to have an IP address for its management, therefore the "ipv4" configuration is associated as a child of any Ethernet WAN ports and set to DHCP.

### Common Config - VLAN on WAN for SSID

Imagine the OpenWiFi device is an enterprise Access Point mounted on a ceiling. These devices do not always have a LAN port. Also in an enterprise, it is likely the Wi-Fi services are in their own network segments and not subject to Network Address Translation (NAT). Since the enterprise would also not want Wi-Fi on the same network as Management, an 802.1Q Virtual LAN is used.

```
           {
                "name": "WAN100",
                "role": "upstream",
                      "services": [ "lldp", "dhcp-snooping" ],                
                "vlan": {
                    "id": 100
                },
                "ethernet": [
                    {
                        "select-ports": [
                            "WAN*"
                        ]
                    }
                ],
```

In this next section of configuration, an additional logical interface associated to the WAN ports for the VLAN id of "100" is shown. Note there is no IP address associated to this interface, it is a layer 2 interface that will emit on any and all WAN ports with VLAN id 100.

To associate the Wi-Fi with the VLAN interface define, we continue within the WAN100 interface adding SSID services.

```
            "ssids": [
                {
                    "name": "TIP OpenWiFi",
                    "wifi-bands": [
                        "5G", "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "psk2",
                        "key": "OpenWiFi",
                        "ieee80211w": "optional"
                    }
                },
                "services": [ "wifi-frames"]
```

Within the "ssids" configuration block we can process an array of SSIDs. Often there may be separate "2G" and "5G" configurations. We have grouped them in this introductory example for simplicity however "2G", "5G", "5G-lower", "5G-upper", "6G" are all valid options.

The "name" value is the advertised SSID clients will discover for this access point. Hidden is supported by setting the "hidden-ssid" to true. Which operating mode is determined by "bss-mode". The "bss-mode" is a highly flexible operating parameter to determine "ap", "sta", mesh", "wds-ap", "wds-sta", "wds-repeater" radio modes of operation.

Security of the SSID is determined using the "encryption" section. Many options are possible, in this initial example, a WPA-PSK2 shared key encryption is shown. Lastly, for devices that support, 802.11w protected management frames are defined as optional for this SSID. This may also be disabled or required.

Metrics for wifi-frames will be described next.

### Sending Data

Add metrics to our configuration that will help expose state of the Wi-Fi network and its services to the cloud.

```
    "metrics": {
        "statistics": {
            "interval": 120,
            "types": [ "ssids", "lldp", "clients" ]
        },
        "health": {
            "interval": 120
        },
        "wifi-frames": {
            "filters": [ "probe",
                "auth",
                "assoc",
                "disassoc",
                "deauth",
                "local-deauth",
                "inactive-deauth",
                "key-mismatch",
                "beacon-report",
                "radar-detected"]
        },
        "dhcp-snooping": {
            "filters": [ "ack", 
                                    "discover", 
                                    "offer", 
                                    "request", 
                                    "solicit", 
                                    "reply", 
                                    "renew" ]
        }        
    },
```

Within metrics it is possible to define the interval for sending information to the cloud. Additionally the type of information sent is defined here. In this example configuration there are associated services to interfaces along the way. This included LLDP and dhcp-snooping and wifi-frames.

Within each uCentral device, the agent has a global health check feature that includes memory, cpu, temperature operating states in addition to performing various network and service health tests. The interval at which these reports are sent to the cloud is configured within health.

For all SSIDs that have wifi-frames associated as a service, the listed management frame types will be gathered and sent to the cloud, on each interval.

To assist with fingerprinting and client troubleshooting, dhcp-snooping sends the cloud all current client DHCP and DHCPv6 state.

### Global Services

The final section of the simple configuration example turns on LLDP and SSH where those services were associated to interfaces listed above.

```
    "services": {     
        "lldp": {
            "describe": "TIP OpenWiFi",
            "location": "LivingLab"
        },
        "ssh": {
            "port": 22
        }
    }
}
```

The complete simple configuration file as described in this page may be downloaded here:
