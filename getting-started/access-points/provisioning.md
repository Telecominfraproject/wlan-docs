---
description: uCentral Data Model Introduction
---

# Provisioning

OpenWiFi 2.0 uses the uCentral data model for OpenWrt. It is possible for integrators of the SDK to implement commercial products leveraging OpenWiFi uCentral-Gateway service with vendor supplied provisioning above OpenWiFi. 

OpenWiFi provides options to receive telemetry and events over both OpenAPI interface as well as Kafka message bus. When using Kafka, OpenWiFi uCentral-Gateway directly publishes telemetry and event topics to the bus.

![3rd Party Minimum SDK Use](../../.gitbook/assets/image%20%2826%29.png)

In future sprints of OpenWiFi dynamic device provisioning will be available as an added micro service. 

### uCentral

uCentral specifies the data model and interface for management and telemetry of OpenWrt based devices.   
Interface is a websocket JSON-RPC based design between OpenWiFi uCentral-Gateway and the device running uCentral agent.

  
All communications from uCentral-Gateway to Device are secured using mutual Transport Layer Security \(mTLS\). In mTLS systems each endpoint is a unique device sharing the same signed root or intermediate trust. In OpenWiFi each device has a signed certificate, key and device identifier. These are validated by the uCentral-Gateway to establish mTLS session. 

Upon successful connection the device exchanges its capabilities with the OpenWiFi cloud. OpenWIFi cloud, via the uCentral-Gateway micro service will send the entire device provisioning data as a JSON payload.   
Within OpenWiFi devices, the uCentral agent has a reader and renderer process providing serialization and validation of data sent from cloud.   
If any data presented can not be processed by the local agent, this is returned within an ERROR message using the same websocket connection. 

  
If the device agrees with provisioning information presented, the render process builds calls into the operating system configuration sub-system known as UCI. The Unified Configuration Interface ensures OpenWrt compliant syntax is persisted within the device. 

uCentral framework configuration source of truth is the uCentral-Gateway or essentially the OpenWiFi cloud. Consistency of device configuration is handled with an applied hash compared by the uCentral-Gateway for each device. If the value differs on device from that of the stored information in cloud, the device will be immediately resent its configuration from the OpenWiFi cloud. 

Once present, all configuration data is preserved on device restart.

It is possible to generate device configurations outside of the OpenWiFi 2.0 cloud when the OpenWiFi Provisioning micro service is not present. In this way, integrators of commercial products are welcome to build device provisioning outside of OpenWiFi and use the OpenWiFi cloud to manage the scale, state, and validation of device websocket communications. 

