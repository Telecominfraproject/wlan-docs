---
description: OpenWiFi 2.1
---

# Dynamic Air-Time Policy

Dynamic Air-Time Policy is a service to influence underlying co-ordination function of the Wi-Fi MAC domain per associated UE in terms of priority to use the air interface. 

It is possible to govern certain application use cases such as streaming media or real time communications based on the resolution of those services through DNS.   
This results in the UE, by its IP address having matched a specific fully qualified domain name or a wildcard therein, to having its air-time weighted priority to the value set in the weight parameter.

```text
            "services": {     
                "airtime-policies": {
                    "dns-match": "*.example.com",
                    "dns-weight": 256
                }
            }
```

