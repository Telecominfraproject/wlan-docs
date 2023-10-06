---
description: OpenWiFi
---

# QoS

Quality of service for Wi-Fi involves multiple functions.

IEEE802.11e says stations will send multiple QoS data frames followed by a block ack request (BAR). The AP will send a block ack frame back that includes a bitmap that indicates which frames were received.

The 802.11ac-2013 standard states that all data frames be sent as QoS data frames.

IEEE802.11-2016 Enterprise QoS Includes action frames for many categories such as spectrum management, QoS, HT, VHT, radio measurements, and more 802.11 QoS is achieved by giving high priority queues a statistical advantage at winning contention.

TIP OpenWiFi implements IEEE802.11-2016 Enterprise QoS features in the following way:

* Traffic Classifiers fully mapping Wireless Multi-Media with DSCP in 802.11-2016 terms
* Matches by port, range, and or DNS FQDN
* Designed as eBPF Traffic Classifiers TIP OpenWiFi QoS works in Bridge, NAT & VLAN modes
* Enables total Bandwidth to rate-cap forwarding Future per SSID based Traffic Classifiers

OpenWiFi additionally implements standard buffer bloat control when handling queue behavior during shaping. This feature is known as Qosify. Qosify will set Cake queue discipline behavior using an eBPF classifier to set DSCP per packet as part of wirespeed operations in the Linux kernel.

### How it works

Follow the OpenWiFi data model for QoS rules bound to interface via select-ports setting upstream and downstream bandwidth, DSCP marking, protocol and port with an optional FQDN dynamic application match via DNS. Define the wireless-multimedia chosen behavior to set air interface queues.

TIP OpenWiFi enumerates defined QoS provisioning, as applications or port and protocol matches occur, the Wi-Fi Traffic Identifier (TID) value is set accordingly.

OpenWiFi WMM Supports the following class selector profiles:

* Enterprise
* RFC8325 - default
* 3GPP

#### Example QoS Definition

```
     "globals": {
                "wireless-multimedia": {
                        "profile": "rfc8325"
                }  
                
     "services": {
              "quality-of-service": {
                        "select-ports": [ "WAN" ],
                        "bandwidth_up": 1000,
                        "bandwidth_down": 1000,
                        "bulk-detection": {
                                "dscp": "CS1",
                                "packets-per-second": 500
                        },
                        "classifier": [
                                {
                                        "dscp":  "CS1",
                                        "ports": [
                                                { "protocol": "any", "port": 53 },
                                                { "protocol": "tcp", "port": 80 }
                                        ],
                                        "dns": [
                                                { "fqdn": "telecominfraproject.com", "suffix-matching": false }
                                        ]
                                }, {
                                        "dscp":  "AF41",
                                        "dns": [
                                                { "fqdn": "zoom.us" }
                                        ]
                                }
                        ]
                }
```

In the above example, select-ports was set as WAN. Should the access point have an SSID associated to the WAN interface, the defined QoS settings become applied to both Wi-Fi air interface and the Ethernet interface. By default WAN is chosen for all classification and shaping.

Bulk detection functions to optimize bulk traffic flows measured in average packet size and packets per second. When bulk-detection is triggered, marking with Diffserv Code Point (DSCP) is possible. Default is CS0.

Classifier works to specifically trigger on conditional criteria of ports, dns matching individually or in combination with either or both tcp or udp protocols for classification in DSCP terms. When port is set it may be individual or up to an end port when setting range-end value.

If matching traffic enters already classified in DSCP terms, OpenWiFi by default will reclassify based on the classifier conditions defined unless reclassify is set to false.
