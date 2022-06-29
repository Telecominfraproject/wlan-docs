# New in this release

The latest release includes the following new features.

## APNOS

* Ath11k Ath12k CSU updates
  * Latest stable Qualcomm patches
  * Kernel and back port handling 5.10 – 5.4


* L3 Collision Enhancement
  * Second device WAN detects itself in the same IP space as its own LAN
  * Second LAN Auto-Select Non-Overlapping next nibble subnet


* OpenRoaming Feature Parity

* Expanded Wi-Fi Scan
  * \>30 IEs now available using the API


* RADIUS Proxy – Gateway • TIP Vendor 58888

  * Device Serial Number added by host apd
  * Gateway sends to pool of RADIUS servers
  * Response handled cloud native to Gateway Northbound
  * Gateway over WebSocket to AP (hostapdonlocalhost)


* Enables Dynamic Multi-PSK
  * KeyNonce shared via RADIUS


* Per UE
  * Uplink/Downlink Traffic Control over WISPr AVPs
  * PSK per VLAN


* Enables Change of Authorization (CoA) and Disconnect Message (DM) via Cloud Managed Service Provider (MSP)

  * Re-use of the WebSocket requires no additional networking or device agent support
  * Permits all Cloud MSPs to use the Cloud SDK for any AAA messaging
  * AAA builds knowledge of the TIPPEN 5888 Serial Number


## SDK

The latest release includes the following new SDK features.

### Provisioning Service

* New UI with Quality Dashboard per Venue/Entity
* Operators, Subscriber Devices, Subscribers
* Device Specific Configurations
* Venue Resources
* Interface Configuration
* Venue Notifications WebSocket
* Google Authenticator for Multi-Factor
* Self-care Portal API for mobile app devs
* Analytics
  * Client Lifecycle ( life of a UE )
  * Venue dashboard ( Associations, AP health, Status )
  * Live View ( Active UE Associations, Connection Quality )

### Gateway Service

* Bandwidth and IE options in the WiFi Scan API
* Entity/Venue/Subscriber device association
* Ping device RTT latency
* Telemetry via WebSocket or Kafka
* WebSocket state for device reboot/firmware update in device page updates and device list tables
* RADIUS Pool ( Proxy )

### Analytics Service

* Aggregation of telemetry per Venue
* Enables Provisioning Dashboards and any dev seeking aggregation by Venue or Entity
