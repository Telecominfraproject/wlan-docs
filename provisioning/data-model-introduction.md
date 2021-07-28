---
description: OpenWiFi 2.0
---

# Data Model Introduction

OpenWiFi 2.0 data model for device management is based on uCentral. 

uCentral is set to become a leading component of OpenWrt, as such will have a diverse, and worldwide developer and support base in open source. 

Within the model it is possible to provision or return state for all aspects of an OpenWiFi based device easily structured as a JSON payload. 

The complete data model may be found here : [https://ucentral.io/docs/ucentral-schema.html](https://ucentral.io/docs/ucentral-schema.html) 

### Organization

Each device has a Universally Unique Identifier \(UUID\).   
For each UUID 'unit' a Description, Location, TimeZone may be set.    
  
Globals may be defined which the rendered in the uCentral Agent will determine apply to certain portions of the configuration once processed.   
  
Common data such as RADIUS or wireless encryption information may be referenced within 'definitions' to avoid duplication of configuration data within the device when multiple SSIDs share the same values.  
  
Radios permit configuration of all Wi-Fi settings including support for passing in raw commands to hostapd gaining direct control of the hostapd.conf configuration from the cloud.   
  
Interfaces define upstream and downstream configuration over both Wi-Fi logical \(SSID\) and wired physical ports. 

Services enable configuration of features such as LLDP or SSH, rTTY, IGMP, 802.1x, RADIUS Proxy, WiFi-Steering, or NTP and are then associated with Interfaces as desired. 

Metrics enable visibility to the cloud for numerous states of the device. These are associated per interface and may be sent in 60 second or greater intervals and include Statistics of SSID, LLDP, Clients. Also include Health check reports of device load, network reachability, temperature.   
To assist with fingerprinting DHCP-Snooping exposes numerous interactions of IP binding to clients. Additionally wifi-frames expose all 802.11 management frames to the SDK Gateway. 

It is also possible to configure config-raw elements that will parse direct UCI commands once the device provisioning has been completed by the uCentral agent. 

