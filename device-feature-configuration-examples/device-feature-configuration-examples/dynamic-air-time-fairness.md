---
description: TIP OpenWiFi 2.0
---

# Dynamic Air Time Fairness

Complimenting enterprise QoS in OpenWiFi is support for Dynamic Air Time Fairness.&#x20;

Air Time Fairness (ATF) governs the Wireless Multimedia (WMM) operations on the air interface with influence of the scheduler.

The Distributed Coordination Function (DCF) which is the underlying Media Access Control system to Wi-Fi is generally governed by equality rules at the air interface, every UE is equal.&#x20;

Traffic handling building blocks over time have layered onto Wi-Fi to handle contention access in certain queueing terms.

OpenWiFi WMM Supports the following class selector profiles:

* Enterprise
* RFC8325
* 3GPP



Air Time Fairness Example:

```
"services": {
                "airtime-fairness": {
                        "voice-weight": 4,
                        "packet-threshold": 100,
                        "bulk-threshold": 50,
                        "priority-threshold": 30,
                        "weight-normal": 256,
                        "weight-priority": 384,
                        "weight-bulk": 128
                }
        }
```

