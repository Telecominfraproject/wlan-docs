---
description: OpenWiFi 2.1
---

# Port Speed

Configuring port speed and operation is most commonly done with PoE access switches however the same configurations are possible for all OpenWiFi device types.

By default all ports attempt 1,000 Mb/s full duplex operation.

```text
 "ethernet": [
            {
                    "select-ports": [
                            "WAN1"
                    ],
                    "speed": 100,
                    "duplex": "half"
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
                    "speed": 100,
                    "duplex": "half"
            }
    ],
```

