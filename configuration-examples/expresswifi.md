---
description: OpenWiFi 2.1
---

# ExpressWiFi

At home, in a cafe, or on the go, Express Wi-Fi gives you access to fast, affordable, and reliable internet so you can make connections that matter.

Express Wi-Fi partners with service providers to deliver great wi-fi to people when and where it's needed.

For information about becoming an expressWIFI partner please visit their [site.](https://expresswifi.fb.com/)

![](../.gitbook/assets/image%20%2840%29.png)

## Configuration

ExpressWiFi builds a captive portal experience using a control plane protocol called OpenFlow.  
Configuring OpenWiFi for use with expressWiFi is as simple as defining a downstream interface and associating with an SSID and the open-flow service.

{% tabs %}
{% tab title="expressWIFI" %}
```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "services": [ "lldp" ],
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
            "name": "LAN",
            "role": "downstream",
            "services": [ "ssh", "lldp", "open-flow"],
            "ethernet": [
                {
                    "select-ports": [
                        "LAN*"
                    ]
                }
            ],
            "ipv4": {
                "addressing": "static",
                "subnet": "192.168.1.1/24",
                "dhcp": {
                    "lease-first": 10,
                    "lease-count": 100,
                    "lease-time": "6h"
                }
            },
            "ssids": [
                {
                    "name": "ExpressWiFi",
                    "wifi-bands": [
                        "5G", "2G"
                    ],
                    "bss-mode": "ap"
                }
            ]
        }
    ],
        "services": {
        "lldp": {
            "describe": "OpenWiFi - expressWiFi",
            "location": "Hotspot"
        },
        "ssh": {
            "port": 22
        },
        "open-flow": {
            "controller": " IP / FQDN of expressWiFi Controller ",
            "ca-certificate": " the client cert as string pasted here ",
            "server-certificate": "the shared ca as string pasted here",
            "private-key": "client key as string pasted here" 
        }
    }
```
{% endtab %}
{% endtabs %}

{% hint style="info" %}
Contact expressWiFi for appropriate CA, Client Cert, and Key for TLS Security mode in addition to the specific expressWiFi Controller FQDN 
{% endhint %}

