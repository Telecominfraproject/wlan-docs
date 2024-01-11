---
description: Early Preview Feature
---

# Wireguard

Wireguard is an overlay technology supporting both Layer 2 and Layer 3 operations. In TIP OpenWiFi this is designed as a configured service that is associated to any logical interface.

As a fully encrypted overlay, key negotiation and exchange of peers is required. This peer endpoint exchange conversation is known as PEX.

A PEX service is deployed with public network visibility and defined in the wireguard-overlay root-node configuration section of the client.

Endpoints to be key negotiated with are defined as hosts.

When this wireguard-overlay is then associated as a service to a layer 3 interface either upstream (WAN) or downstream (LAN) then a layer 3 path is available between the define host endpoints.

When the wireguard-overlay is associated as a service with vxlan configured, the host adjacencies become layer 2 paths.

**Example:**

```
“wireguard-overlay”: {
                        “private-key”: “####AAAABBBBCCCDDDDEEEFFFFFGGGG“,
                        “root-node”: {
                                “key”: “ZZZZWWWWQQQEEERRRTTYYYY“,
                                “endpoint”: “148.251.188.218",
                                “ipaddr”: [ “192.168.3.1" ]
                        },
                        “hosts”: [
                                {
                                        “name”: “ap1”,
                                        “key”: “CCCCDDDDEEEEFFFFGGGHHHHIIII“,
                                        “ipaddr”: [ “192.168.4.1" ]
                                }, {
                                        “name”: “ap2",
                                        “key”: “JJJKKKLLLAAABBBBBNCCCC####“,
                                        “ipaddr”: [ “192.168.5.1" ]
                                }
                        ],
                        “vxlan”: {
                                “isolate”: false
                        }
                }
```

#### Peer Endpoint eXchange Service (PEX)

Currently TIP OpenWiFi wireguard services are an early preview feature. The PEX network discovery daemon service is intended to be containerized and likely re-written as a core service of the TIP OpenWiFi SDK cloud.

For development members in the Community who wish to begin with this feature, the following repo should be consulted for functional information on a base Linux deployment of PEX via: [https://github.com/nbd168/unetd/blob/master/PEX.md](https://github.com/nbd168/unetd/blob/master/PEX.md)

Please connect with the Community maintainers via Slack if working on this early access feature.
