---
description: Telecom Infra Project OpenWiFi
---

# OpenWiFi Release 3.0.0

## What is OpenWiFi?

TIP OpenWiFi is an open source community project that believes in democratizing premium Wi-Fi experiences for multiple market use cases. The TIP approach to OpenWiFi creates an open source disaggregated technology stack without any vendor lock in.

Features normally only present in commercial enterprise WLAN offerings are available in TIP OpenWiFi. These premium Wi-Fi features enable a number of market solutions for developers, integrators and operators to explore.

TIP OpenWiFi stack enables commercial integrations via cloud native open source services for management and network visibility combined with an open source AP firmware operating system tested nightly.

TIP OpenWiFi Continuous Integration quality testing runs nightly exercising thousands of Wi-Fi performance, conformance and feature unit tests.

Support for a broad range of device platforms with the ability for Community to contribute additional device support and or cloud features sets TIP OpenWiFi apart from all other open projects.

Joining TIP and the OpenWiFi project is both free and easy.

Learn more here: [https://telecominfraproject.com/openwifi/](https://telecominfraproject.com/openwifi/)

### Getting Started

The most common use cases for TIP OpenWiFi are managed WLAN most often associated with premium enterprise Wi-Fi service offerings. TIP OpenWiFi presents these premium features over a number of deployment options.

TIP OpenWiFi devices have management and telemetry exposed via a single websocket to the OpenWiFi Gateway (OWGW) microservice. The OWGW is supported by database, message bus, and the OpenWiFi Security (OWSEC) microservice for northbound API integration. This represents the minimum to deploy TIP OpenWiFi.

This minimum set of services enables commercial vendor integration adding TIP OpenWiFi device support to existing Wi-Fi controllers.

Refer to the sections on SDK Installation and Overview for further information.

For additional value added services, TIP OpenWiFi also provides User Interface, Firmware Management, Provisioning and Analytics services. All services are independently deployed and integrated based on commercial adoption model.

See [Developer Resources](https://github.com/Telecominfraproject/wlan-docs/blob/2.9.0/broken-reference/README.md) for API level information and [Code Repositories](openwifi-stack/repositories.md) for source code guidance.

### High Level Features

#### Each OpenWiFi AP offers:

* Multiple topologies including :
  * Local Breakout
  * Overlay including PPPoE, L2TP, L2oGRE
  * IEEE802.11s Mesh and Wireless Distribution System
  * Bridging, Virtual LAN, VxLAN, NAT Gateway
* Multiple authentications including WPA, WPA2, WPA3, Enterprise Radius models, M-PSK
* Passpoint R1 and R2 Mobile Offload
* Encrypted Zero Touch Provisioning and Cloud Discovery
* Autonomous RRM and Channel Control
* Wi-Fi Agile Multiband
* Multi-VAP including topology features per VAP
* Dynamic Air Time Fairness
* Over the air EDCH QoS, WMM QoS, 802.11-2016 Enterprise QoS
* Captive Portal
* Station and Network Telemetry

#### Cloud SDK in OpenWiFi offers:

* Zero Touch Provisioning & Discovery
* Integration Northbound Interface (NBI) RESTful
* Data model driven OpenAPI design
* Enterprise Message Bus data access
* Cloud Native & Agnostic micro services
  * Gateway Southbound
  * Security Northbound
  * Firmware Management
  * Web User Interface
  * Provisioning
  * Analytics

**OpenWiFi AP Detail List:**

* Wi-Fi 5 (ac) Wi-Fi 6 (ax) Wi-Fi 6E
* Dual Bank Bootloader
* Multi-SSID per Radio
* SSID Authentications: WPA/WPA2/WPA3 - Mixed, Personal, Enterprise
* 802.1Q VLAN per SSID
* 802.1d Bridge Mode per SSID
* RADIUS Accounting, Interim-Accounting, NAS-IP, CUI
* Network Address Translation Gateway Mode Operation
* Network Time Protocol Client
* Management VLAN
* Wi-Fi 6 (ax) Specific
  * BSS Coloring
  * UL/DL OFDMA sub-carrier allocation
  * Channel Switch Announcement
* Wi-Fi General Features
  * WMM® - Wi-Fi Multi Media
    * UAPSD Procedures (Unscheduled Power Save)
    * Upstream/Downstream Queues & L3 DSCP
    * Over The Air QoS EDCH Procedures
* WMM-Admission Control (AC)
* WMM-Power Save (PS)
* Wi-Fi Optimized Connectivity
  * (ai) Fast Initial Link Support
* Wi-Fi Agile Multiband
  * (k) Client Radio Resource Management - Directed Steering
  * (v) Network Assisted Roaming
  * (r) Fast BSS Transition
* Protected Management Frames (PMF)
  * (w) Management Frame Encryption
* Channel Switch Announcement (CSA)
* Dynamic Frequency Selection & Transmit Power Control (DFS/TPC)
* Beacon Rate
* Min Client Noise Immunity
* Basic Rate Control
* De-Auth RSSI Control
* Burst Beacon Support
* Per SSID Client Rate Limiting
* Promiscuous Mode Support
* **Additional TIP AP NOS Features**
  * ISP WAN Profiles ( PPPoE, L2TP, L2oGRE )
  * Embedded Captive Portal (Local Splash non-auth)
  * Link Layer Discovery Protocol (LLDP)
  * Dynamic Airtime Fairness
  * Service Flow QoS
  * Wireline & Wireless Tracing (PCAP Cloud Remote Troubleshooting)
  * Health Check Reports
  * Local Provisioning over SSID (when Cloud or WAN down)
  * Multimedia Heuristics (Detection of Unified Communication Sessions)
  * SSID Rate Limiting
  * GPS Reporting
  * Autonomous RRM Client Steering
  * Client / AP / Network Metric Telemetry

**Cloud SDK additional features**

* **Provisioning**
  * Device Identity (Model, MAC, Serial Number)
  * Device Software Upgrade
  * Multiple SSID Configuration
  * Bandwidth Rate Control per SSID
  * Multi-Radio 2.4/5/6GHz control
  * AP Network Mode Control (Bridge/NAT mode)
  * Security (WPA-Personal/WPA & WPA2/3 Personal Mixed/WPA & WPA2/3 Enterprise Mixed/WPA2/3 Personal/WPA2/3 Enterprise/WEP)
  * VLAN per SSID
  * VxLAN port configuration
  * NTP Enable/Disable
  * RTLS (Location Services) Enable/Disable
* **RF Control**
  * IEEE802.11r Fast BSS Transition per Radio Control
  * IEEE802.11k RRM Radio Information per Radio Control
  * IEEE802.11v Network Assisted Roaming per Radio Control
  * RRM Location AP Channel (uChannel) Provisioning
  * RRM Location Client Steering (uSteer) Threshold Provisioning
* **Remote Troubleshooting and Service Assurance**
  * Syslog
  * Health Check Reports
    * Remote DHCP, RADIUS, UE Network Analysis
  * Remote TTY Shell
  * Remote Packet Capture Analysis

### **How to contribute**

If you or your company are interested in contributing to TIP Open Wi-Fi, please join the Wi-Fi Product Group by visiting [Telecom Infra Project](https://telecominfraproject.com/apply-for-membership/) to become a member.
