---
description: TIP OpenWiFi 2.0
---

# Services

OpenWiFi devices have global services that operate either independently system wide or as an association to a physical or logical interface.

Within the "services" configuration block, define the operating mode for each service, then associate a service with an interface.

## SSH

Secure shell may optionally be enabled on OpenWiFi devices, associated to specific interface\(s\), and optionally support operator defined keys or password authentication.

```text
    "services": {
        "ssh": {
            "port": 22,
            "authorized-keys": {
                "items": [
                "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAAAgQC0ghdSd2D2y08TFowZLMZn3x1/Djw3BkNsIeHt/Z+RaXwvfV1NQAnNdaOngMT/3uf5jZtYxhpl+dbZtRhoUPRvKflKBeFHYBqjZVzD3r4ns2Ofm2UpHlbdOpMuy9oeTSCeF0IKZZ6szpkvSirQogeP2fe9KRkzQpiza6YxxaJlWw== user@example",
          "ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJ4FDjyCsg+1Mh2C5G7ibR3z0Kw1dU57kfXebLRwS6CL bob@work",
          "ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBP/JpJ/KHtKKImzISBDwLO0/EwytIr4pGZQXcP6GCSHchLMyfjf147KNlF9gC+3FibzqKH02EiQspVhRgfuK6y0= alice@home"
                ]
            }
        }
    }
```

### Associate Service to Interface

```text
        {
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh" ],
            "ethernet": [
                {
                    "select-ports": [
                        "LAN*"
                    ]
                }
            ],
```

### Operator Key Management

For production deployments, it is recommended to assign operator SSH key from the OpenWiFi Provisioning configuration of the Venue or Entity which the device associates. 

In this way, an operator may ensure their standard SSH key is delivered to all devices on a network operating region basis. All keys remain base64 encoded when added to the device. 

## NTP

Network time protocol for OpenWiFi devices may be configured to listen for time synchronization from NTP sources and may also be configured to supply NTP source.

```text
    "services": {
        "ntp": {
            "servers": [
            "0.openwrt.pool.ntp.org",
            "1.openwrt.pool.ntp.org"
            ]
        }
    }
```

### Associate to an Interface

```text
        {
            "name": "WAN",
            "role": "downstream",
            "services": [ "ntp" ],
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

## LLDP

Link Layer Discovery Protocol describes interfaces and capabilities between directly attached neighbors over Layer 2.

```text
        "lldp": {
            "describe": "OpenWiFi",
            "location": "Stadium Level 2"
        },
```

Associate "lldp" as a services attribute to any interface.

## MDNS

To assist in device or service discovery over smaller networks, multicast DNS \(mDNS\) protocol if often used. In an mDNS environment there is no local name server for resources to leverage. mDNS zero-configuration service effectively behaves as unicast Domain Name Service \(DNS\).

```text
        "mdns": {
            "enable": true
        },
```

Associate "mdns" as a services attribute to any interface.

## Syslog

Remote syslog systems may be configured to receive device logs in a central location. This content is standard device log and not related to telemetry for metrics and service information received by the OpenWiFi Gateway. Valid port range is from 100 - 65535 with operation over UDP or TCP.

```text
        "log": {
            "host": "Syslog Server IP",
            "port": 514,
            "proto": "udp"
        },
```

Associate "log" as a services attribute to appropriate interface.

## IGMP

When enabled the OpenWiFi device will process IGMP Proxy.

```text
        "igmp": {
            "enable": true
        },
```

Associate "igmp" as a services attribute to any interface participating in IGMP Proxy.

