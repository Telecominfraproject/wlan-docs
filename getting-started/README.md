---
description: TIP OpenWiFi 2.0
---

# Getting Started

OpenWiFi 2.0 Minimum Viable Product at the end of July, 2021 enables a cloud native and cloud agnostic Software Development Kit \(SDK\) with management and deployment support for a wide range of Access Point and PoE network switch platforms.

## Initial release 2.0 SDK includes:

* Zero Touch Cloud Discovery
* Firmware Management
* User Interface 
  * Device List
  * Device Reboot
  * Device LED Blink
  * Device Remote Packet Capture
  * Device Configuration
  * Device Factory Reset
  * Device Remote TTY shell
  * Remote Wi-Fi Scan
  * Associations
    * UE \(Wi-Fi Clients\)
    * Mesh and WDS Clients
    * MCS, NSS, RSSI, Channel, SSID, Tx/Rx
  * Device Health Check 
  * Interface Statistics
  * Device Command History

Upcoming sprint for August includes Dynamic Provisioning service support for template based device configuration.

OpenWiFi 2.0 SDK is deployable as both a Docker Compose or a Helm on Kubernetes model. See [Release 2.0 SDK](sdk/) section for installation instructions.

## New in this Release 

* Firmware
  * Basic Features for OpenWiFi Switching
  * Passpoint 
    * NAPTR Functionality
    * Proxy Static Routing
    * HSP Auth / Acc Service Discovery
    * Last Resort Proxy 
    * RADIUS OpenRoaming Compliance 
  * External 3rd Party Captive Portal Redirect
  * Burst Rate Ad-Hoc Telemetry
  * Static Routing
  * CS1 Merge - Wi-Fi 6
  * IEEE802.1d STP Control
  * Timestamp on Health Check messages
  * L2 DHCP Relay
  * Station Association Idle and Session time
* SDK

  * OpenWiFi Provisioning Service
  * OpenWiFi Inventory Service
  * Multi Tenant Support 
  * Service Group - Venues
  * Logical Regions - Entities

