---
description: TIP OpenWiFi 2.0
---

# Dynamic Air Time Fairness

Complimenting enterprise QoS in OpenWiFi is support for Dynamic Air Time Fairness.

Air Time Fairness (ATF) governs the Wireless Multimedia (WMM) operations on the air interface with influence of the scheduler based on the QoS classification that has been applied to the flow.

The Distributed Coordination Function (DCF) which is the underlying Media Access Control system to Wi-Fi is generally governed by equality rules at the air interface, every UE is equal.

Traffic handling in Wi-Fi is a balance of application of QoS marked flows to scheduling of contention access in certain queueing terms to the air interface medium.

OpenWiFi WMM Supports the following class selector profiles:

* Enterprise
* RFC8325 - default
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

Airtime weights have a valid range of 0 - 511. Airtime Fairness works using sliding averages of total packets per second to approximate influence to the scheduler.

Voice weight operates as a multiplier of traffic marked CS5 / UP5 which is equivalent to DSCP EF. When voice-weight is set to 4 this directs the scheduler to assume it should set aside four (4) times the average bandwidth granted for this flow in order to move it through the air interface as quickly as possible.

Packet threshold will reclassify every number of packets from the UE station ( in the example every 100 ).

When arriving traffic for the UE are classified as bulk, and in the above example over 50% of total arriving traffic appear with the same QoS classification the UE airtime priority will fall into bulk-threshold.

When more than 30% of arriving traffic for the UE are classified as CS4 or equivalent to AC\_VI / AF3x realtime interactive, the UE airtime priority will rise to priority airtime.
