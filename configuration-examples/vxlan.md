---
description: OpenWiFi 2.0
---

# VxLAN

VXLAN’s goal is allowing dynamic large scale isolated virtual L2 networks to be created for virtualized and multi-tenant environments. It does this by encapsulating Ethernet frames in VXLAN packets which when deployed in Wi-Fi topologies can create highly extensible Layer 2 inter-network domains over large campus, MDU, venue service networks.

VxLAN header uses a 24-bit VNID as a unique layer 2 forwarding domain value. VxLAN maintains layer 2 isolation between the forwarding domains and does not leak MAC addresses into upstream switches. Through the use of 24 bits in VNID VxLAN scales up to 16 million unique LAN forwarding domains.

The VXLAN encapsulation method is IP based and provides for a virtual L2 network. With VXLAN the full Ethernet Frame \(with the exception of the Frame Check Sequence: FCS\) is carried as the payload of a UDP packet. VXLAN utilizes a 24-bit VXLAN header, to identify virtual networks. This header provides for up to 16 million virtual L2 networks.

Frame encapsulation is done by an entity known as a VxLAN Tunnel Endpoint \(VTEP.\) A VTEP has two logical interfaces: an uplink and a downlink. The uplink is responsible for receiving VxLAN frames and acts as a tunnel endpoint with an IP address used for routing VxLAN encapsulated frames.

The VTEP in a TIP OpenWiFi device would be a management interface or designated uplink port\(s\). VTEP in an AP would be the AP WAN interface, or otherwise designated management interface \(such as sub-interface on bridge wan\).

In a traditional L2 switch a behavior known as flood and learn is used for unknown destinations \(i.e. a MAC not stored in the MAC table\). This means that if there is a miss when looking up the MAC the frame is flooded out all ports except the one on which it was received. When a response is sent the MAC is then learned and written to the table.

The next frame for the same MAC will not incur a miss because the table will reflect the port it exists on. VXLAN preserves this behavior over an IP network using IP multicast groups.

## Configure VxLAN

OpenWiFi device will establish a VTEP adjacency to the upstream switch. It is anticipated that any Wi-Fi networks in a VxLAN topology are associated to "upstream" interface\(s\).

The following example creates a VxLAN endpoint from a WAN upstream port that will participate in VLAN 100, encapsulate this into VxLAN where it may be distributed across the campus or venue transparently.

```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
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
            "name": "VXLAN",
            "role": "upstream",
            "vlan": {
                "id": 100
            },
            "tunnel": {
                "proto": "vxlan",
                "peer-address": "192.168.178.9",
                "peer-port": 4789
            },
            "ipv4": {
                "addressing": "static",
                "subnet": "10.0.0.1/24"
            }
        },
```

