---
description: TIP OpenWiFi
---

# WISPr Subscriber Bandwidth

OpenWiFi supports WISPr Attribute Value Pairs (AVP)s for setting per authenticated subscriber bandwidth in uplink and downlink.

Provided the SSID has been configured for RADIUS authentication, any access-accept retuned with WISPr Max-Up and Max-Down values, OpenWiFi will restrict per subscriber traffic to these rates.

**RADIUS Subscriber WISPr Speed Definition:**

```
        WISPr-Bandwidth-Max-Up := 100,
        WISPr-Bandwidth-Max-Down := 100
```
