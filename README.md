---
description: Telecom Infra Project Open WiFi
---

# OpenWiFi

## What is OpenWiFi?

TIP OpenWiFi is an open source community project that believes in democratizing premium Wi-Fi experiences for multiple market use cases. The TIP approach to OpenWiFi creates an open source disaggregated technology stack without any vendor lock in. OpenWiFi offers premium managed Wi-Fi features, local break-out design, cloud native open source controller, and an open source AP firmware operating system tested nightly.

![TIP Open Wi-Fi 1.x Solution](.gitbook/assets/image%20%285%29.png)

TIP OpenWiFi is the industry's first CI/CD open source Wi-Fi eco-system. Built nightly with a strong community of Wi-Fi leaders, new features are unit tested in automated RF chambers and checked from cloud to ground for Wi-Fi performance and conformance.

### High Level Features

#### Cloud SDK in OpenWiFi offers:

* Zero Touch Provisioning 
* Firmware Management
* Integration Northbound Interface \(NBI\) RESTful
* Data model driven API 
* Template based device provisioning with RADIUS profile management 
* Advanced RF control with RRM  

#### Each OpenWiFi AP offers:

* Multiple topologies including Bridging, Virtual LAN, NAT Gateway, Local Breakout, Overlay 
* Multiple authentications WPA2, WPA3, Enterprise Radius models
* Passpoint® Release 2 and above
* Zero Touch Provisioning 
* Captive Portal

**OpenWiFi AP Detail List:**

* Wi-Fi 4 \(n\) Wi-Fi 5 \(ac\) Wi-Fi 6 \(ax\) 
* Dual Bank Bootloader
* Multi-SSID per Radio
* SSID Authentications: WPA/WPA2/WPA3 - Mixed, Personal, Enterprise
* Un-Authorized Device Control
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
  * Embedded Captive Portal \(Local Splash non-auth\)
  * Link Layer Discovery Protocol \(LLDP\)
  * Airtime Fairness
  * Wireline & Wireless Tracing \(PCAP Cloud Remote Troubleshooting\)
  * Synthetic Client \(Cloud Remote Troubleshooting\)
  * Flight Recorder \(Stack Remote Collection\)
  * Local Provisioning over SSID \(when Cloud or WAN down\)
  * Multimedia Heuristics \(Detection of Unified Communication Sessions\)
  * SSID Rate Limiting
  * Inter-AP Communication \(Client - Session Signalling\)
  * Client / AP / Network Metric Telemetry \(MQTT\)

**Cloud SDK additional features**

* **Provisioning** 
  * Device Identity \(Model, MAC, Serial Number\)
  * AP Software Upgrade
  * Profile Provisioning Templates
  * Multiple SSID Configuration
  * Bandwidth Rate Control per SSID
  * Multi-Radio 2.4/5GHz control
  * AP Network Mode Control \(Bridge/NAT mode\)
  * Basic Captive Portal \(Local Splash Page admin from Controller\)
  * Security \(WPA2/WPA3 Personal/Enterprise Mixed\)
  * VLAN per SSID
  * NTP Enable/Disable
  * RTLS \(Location Services\) Enable/Disable 
* **RF Control**
  * Wi-Fi Agile Multiband
    * \(k\) Client Radio Resource Management - Directed Steering
    * \(v\) Network Assisted Roaming
    * \(r\) Fast BSS Transition
  * RRM Location AP Channel Table Provisioning
  * RRM Location AP Cell Size Table Provisioning
  * RRM Location Client Steering Threshold Table Provisioning 
* **Remote Troubleshooting and Service Assurance**
  * Syslog 
  * Synthetic Client
    * Remote DHCP, RADIUS, UE Network Analysis 
  * Remote Shell 
  * Remote Packet Capture Analysis

### **How to contribute**

If you or your company are interested in contributing to TIP Open Wi-Fi, please join the Wi-Fi Product Group by visiting [Telecom Infra Project](https://telecominfraproject.com/apply-for-membership/) to become a member.

