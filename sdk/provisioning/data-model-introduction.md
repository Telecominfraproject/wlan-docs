---
description: OpenWiFi 2.0
---

# Data Model Introduction

OpenWiFi 2.0 data model for device management is based on uCentral.

uCentral is set to become a leading component of OpenWrt, as such will have a diverse, and worldwide developer and support base in open source.

Within the model it is possible to provision or return state for all aspects of an OpenWiFi based device easily structured as a JSON payload.

The complete data model may be found here : [https://ucentral.io/docs/ucentral-schema.html](https://ucentral.io/docs/ucentral-schema.html)

## Organization

Each device has a Universally Unique Identifier (UUID). For each device, the configuration presented either manually, via the future Provisioning service from OpenWifi or via a commercial controller generation of provisioning data, the high level relationships of the schema may be understood as follows.

![uCentral Agent Schema Processing](<../../.gitbook/assets/image (37).png>)

The unique device record has a set of top level configurations. A device is referred to as a 'unit' that may have a Description, Location, TimeZone as example. Each unit may have globals for IPv4 and IPv6 networks that are derived to lower lever interfaces in later generation.

Services and Metrics are associated with logical and physical interfaces. Services enable configuration of features such as LLDP or SSH, rTTY, IGMP, 802.1x, RADIUS Proxy, WiFi-Steering, or NTP and are then associated with Interfaces as desired.

Interfaces define upstream and downstream configuration over both Wi-Fi logical (SSID) and wired physical ports.

Metrics enable visibility to the cloud for numerous states of the device. These are associated per interface and may be sent in 60 second or greater intervals and include Statistics of SSID, LLDP, Clients. Also include Health check reports of device load, network reachability, temperature.\
To assist with fingerprinting DHCP-Snooping exposes numerous interactions of IP binding to clients. Additionally wifi-frames expose all 802.11 management frames to the SDK Gateway.

It is also possible to configure config-raw elements that will parse direct UCI commands once the device provisioning has been completed by the uCentral agent.
