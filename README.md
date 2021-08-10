---
description: Telecom Infra Project OpenWiFi
---

# OpenWiFi Release 2.1

## What is OpenWiFi?

TIP OpenWiFi is an open source community project that believes in democratizing premium Wi-Fi experiences for multiple market use cases. The TIP approach to OpenWiFi creates an open source disaggregated technology stack without any vendor lock in. OpenWiFi offers premium managed Wi-Fi features, local break-out design, cloud native open source controller, and an open source AP firmware operating system tested nightly.

![Open Technology Stack - Many Platforms - Many Service Options](.gitbook/assets/image%20%283%29.png)

TIP OpenWiFi is the industry's first CI/CD open source Wi-Fi eco-system. Built nightly with a strong community of Wi-Fi leaders, new features are unit tested in automated RF chambers and checked from cloud to ground for Wi-Fi performance and conformance.

OpenWiFi 2.0 introduces management and telemetry based on uCentral offering expanded selection of managed devices including smaller APs and PoE access switches.

### High Level Features

#### Each OpenWiFi AP offers:

* Multiple topologies including :
  * Bridging, Virtual LAN, VxLAN, NAT Gateway, Local Breakout, Overlay \(PPPoE, L2oGRE, L2TP\), Mesh, WDS 
* Multiple authentications including WPA, WPA2, WPA3, Enterprise Radius models, M-PSK
* Passpoint R1 and R2 Mobile Offload
* Encrypted Zero Touch Provisioning and Cloud Discovery
* Autonomous RRM and Channel Control
* Captive Portal & ExpressWiFi

#### Each OpenWiFi PoE Switch offers:

* IEEE802.1Q Virtual LAN
* VxLAN
* DHCP Snooping & Relay
* Multicast
* PoE
* IEEE802.1x Access Control

#### Cloud SDK in OpenWiFi offers:

* Zero Touch Provisioning 
* Firmware Management
* Integration Northbound Interface \(NBI\) RESTful
* Data model driven API 
* Enterprise Message Bus data access 

**OpenWiFi AP Detail List:**

* Wi-Fi 4 \(n\) Wi-Fi 5 \(ac\) Wi-Fi 6 \(ax\) 
* Dual Bank Bootloader
* Multi-SSID per Radio
* SSID Authentications: WPA/WPA2/WPA3 - Mixed, Personal, Enterprise
* 802.1Q VLAN per SSID 
* 802.1d Bridge Mode per SSID
* RADIUS Accounting, Interim-Accounting, NAS-IP, CUI
* Network Address Translation Gateway Mode Operation
* Network Time Protocol Client
* Management VLAN 
* Wi-Fi 6 \(ax\) Specific
  * BSS Coloring
  * UL/DL OFDMA sub-carrier allocation
  * Channel Switch Announcement
* Wi-Fi General Features
  * WMM® - Wi-Fi Multi Media
    * UAPSD Procedures \(Unscheduled Power Save\) 
    * Upstream/Downstream Queues & L3 DSCP
    * Over The Air QoS EDCH Procedures
* WMM-Admission Control \(AC\) 
* WMM-Power Save \(PS\)
* Wi-Fi Optimized Connectivity
  * \(ai\) Fast Initial Link Support
* Wi-Fi Agile Multiband
  * \(k\) Client Radio Resource Management - Directed Steering
  * \(v\) Network Assisted Roaming
  * \(r\) Fast BSS Transition
* Protected Management Frames \(PMF\) 
  * \(w\) Management Frame Encryption
* Channel Switch Announcement \(CSA\)
* Dynamic Frequency Selection & Transmit Power Control \(DFS/TPC\)
* Beacon Rate 
* Min Client Noise Immunity
* Basic Rate Control
* De-Auth RSSI Control
* Burst Beacon Support
* Per SSID Client Rate Limiting
* Promiscuous Mode Support 
* **Additional TIP AP NOS Features**
  * ISP WAN Profiles \( PPPoE, L2TP, L2oGRE \)
  * Embedded Captive Portal \(Local Splash non-auth\)
  * Link Layer Discovery Protocol \(LLDP\)
  * Dynamic Airtime Fairness
  * Service Flow QoS 
  * Wireline & Wireless Tracing \(PCAP Cloud Remote Troubleshooting\)
  * Health Check Reports
  * Local Provisioning over SSID \(when Cloud or WAN down\)
  * Multimedia Heuristics \(Detection of Unified Communication Sessions\)
  * SSID Rate Limiting
  * GPS Reporting
  * Autonomous RRM Client Steering 
  * Client / AP / Network Metric Telemetry 

**Cloud SDK additional features**

* **Provisioning** 
  * Device Identity \(Model, MAC, Serial Number\)
  * Device Software Upgrade
  * Multiple SSID Configuration
  * Bandwidth Rate Control per SSID
  * Multi-Radio 2.4/5/6GHz control
  * AP Network Mode Control \(Bridge/NAT mode\)
  * Security \(WPA-Personal/WPA & WPA2/3 Personal Mixed/WPA & WPA2/3 Enterprise Mixed/WPA2/3 Personal/WPA2/3 Enterprise/WEP\)
  * VLAN per SSID
  * VxLAN port configuration
  * NTP Enable/Disable
  * RTLS \(Location Services\) Enable/Disable 
* **RF Control**
  * IEEE802.11r Fast BSS Transition per Radio Control
  * IEEE802.11k RRM Radio Information per Radio Control
  * IEEE802.11v Network Assisted Roaming per Radio Control
  * RRM Location AP Channel \(uChannel\) Provisioning
  * RRM Location Client Steering \(uSteer\) Threshold Provisioning 
* **Remote Troubleshooting and Service Assurance**
  * Syslog 
  * Health Check Reports
    * Remote DHCP, RADIUS, UE Network Analysis 
  * Remote TTY Shell 
  * Remote Packet Capture Analysis 

### **How to contribute**

If you or your company are interested in contributing to TIP Open Wi-Fi, please join the Wi-Fi Product Group by visiting [Telecom Infra Project](https://telecominfraproject.com/apply-for-membership/) to become a member.

