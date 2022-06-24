# What's New

**APNOS**\
Ath11k Ath12k CSU updates \
\- Latest stable Qualcomm patches in\
\- Kernel and back port handling 5.10 – 5.4

L3 Collision Enhancement\
\- Second device WAN detects itself in same IP space as its own LAN\
\- Second LAN Auto-Select Non-Overlapping next nibble subnet

OpenRoaming Feature Parity

Expanded Wi-Fi Scan\
\- >30 IEs now available via API

RADIUS Proxy – Gateway • TIP Vendor 58888

* DeviceSerialNumberaddedbyhostapd
* GatewaysendstopoolofRADIUSservers
* ResponsehandledcloudnativetoGatewayNorthbound • GatewayoverWebSockettoAP(hostapdonlocalhost)

Enables Dynamic Multi-PSK \
• KeyNoncesharedviaRADIUS

Per UE\
\- Uplink/DownlinkTrafficControloverWISPrAVPs \
• PSKperVLAN

Enables CoA and DM ( Disconnect Message ) via Cloud MSP

* Re-useofWebSocketrequiresnoadditionalnetworkingordeviceagentsupport
* PermitsallCloudMSPstointerfaceattheCloudSDKforanyAAAmessaging • AAAbuildsknowledgeoftheTIPPEN5888SerialNumber(seenextslide)

\
**SDK**\
Provisioning Service

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

Gateway Service

* Bandwidth and IE options in Wi-Fi Scan API
* Entity/Venue/Subscriber device association
* Ping device RTT latency
* Telemetry via WebSocket or Kafka
* WebSocket state for device reboot/firmware update in device page updates and device list tables
* RADIUS Pool ( Proxy )

Analytics Service

* Aggregation of telemetry per Venue
* Enables Provisioning Dashboards and any dev seeking aggregation by Venue or Entity
