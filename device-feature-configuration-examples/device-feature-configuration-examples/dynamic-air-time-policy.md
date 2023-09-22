---
description: TIP OpenWiFi 2.0
---

# Dynamic Air-Time Policy

{% hint style="info" %}
This feature has been deprecated in OpenWiFi 2.6 in order to support both Layer 3 and Layer 2 classification topologies through QoS and Dynamic Airtime Fairness.
{% endhint %}

Dynamic Air-Time Policy is a service to influence underlying co-ordination function of the Wi-Fi MAC domain per associated UE in terms of priority to use the air interface.

It is possible to govern certain application use cases such as streaming media or real time communications based on the resolution of those services through DNS.

This results in the UE, by its IP address having matched a specific fully qualified domain name or a wildcard therein, to having its air-time weighted priority to the value set in the weight parameter.

```
            "services": {     
                "airtime-policies": {
                    "dns-match": ["*.example.com", "host.example2.com" ],
                    "dns-weight": 256
                }
            }
```

{% hint style="info" %}
Note: In release 2.1, airtime-policies must be applied to SSIDs in a NAT configuration. Bridge / VLAN mode SSIDs with airtime-policies will be updated in a future release
{% endhint %}

## Possible Uses

Any application a user may commonly use the OpenWiFi administrator seeks to prioritize air-time for may be triggered via the airtime-policies.

For example:

| Service  | FQDN / URL                                                 |
| -------- | ---------------------------------------------------------- |
| MS Teams | _\*.lync.com, \*_.teams.microsoft.com, teams.microsoft.com |
| Zoom     | \*.zoom.us                                                 |

Any number of services may interest the administrator for airtime-policies. Simply determine the FQDN or wildcard FQDN applicable and update the OpenWiFi device configuration.
