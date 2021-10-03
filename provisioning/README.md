---
description: uCentral Data Model Introduction
---

# Provisioning

OpenWiFi 2.0 makes it possible for integrators of the SDK to implement commercial products leveraging OpenWiFi Gateway service with vendor supplied provisioning above OpenWiFi SDK.  
As a minimum, the OpenWiFi 2.0 SDK framework offers a Security service which handles all OpenAPI authentication northbound, and the Gateway service which provides all uCentral websocket interface functionality southbound.

![Minimum 2.0 SDK - Assumes DB is either SQLite or PGSql](../.gitbook/assets/image%20%2828%29.png)

OpenWiFi also provides options to receive telemetry and events over both OpenAPI interface as well as Kafka message bus. When using Kafka, OpenWiFi Gateway directly publishes telemetry and event topics to the bus.

In future sprints of OpenWiFi dynamic device provisioning will be available as an added micro service.

## Gateway

OpenWiFi 2.0 Gateway implements the uCentral device management interface. uCentral specifies the data model and interface for management and telemetry of OpenWrt based devices.  
Gateway uCentral interface is a websocket JSON-RPC based design between OpenWiFi Gateway and the device running uCentral agent.

![Southbound Interface to Devices](../.gitbook/assets/image%20%2831%29.png)

All communications from Gateway to Device are secured using mutual Transport Layer Security \(mTLS\). In mTLS systems each endpoint is a unique device sharing the same signed root or intermediate trust. In OpenWiFi each device has a signed certificate, key and device identifier. These are validated by the uCentral-Gateway to establish mTLS session.

Upon successful connection the device exchanges its capabilities with the OpenWiFi SDK. OpenWIFi SDK, via the Gateway micro service will send the entire device provisioning data as a JSON payload.  
Within OpenWiFi devices, the uCentral agent has a reader and renderer process providing serialization and validation of data sent from cloud.  
If any data presented can not be processed by the local agent, this is returned within an ERROR message using the same websocket connection.

![High Level SDK Gateway to uCentral Agent](../.gitbook/assets/image%20%2822%29%20%282%29.png)

If the device agrees with provisioning information presented, the render process builds calls into the operating system configuration sub-system known as UCI. The Unified Configuration Interface ensures OpenWrt compliant syntax is persisted within the device.

Configuration source of truth is the OpenWiFi SDK. Consistency of device configuration is handled with an applied hash compared by the Gateway for each device. If the value differs on device from that of the stored information in cloud, the device will be immediately resent its configuration from the OpenWiFi SDK Gateway service.

Once present, all configuration data is preserved on device restart.

It is possible to generate device configurations outside of the OpenWiFi 2.0 SDK as shown in the minimum SDK image at the start of this page. This may occur for some integrations or may occur when the OpenWiFi Provisioning micro service is not present. In this way, integrators of commercial products are welcome to build device provisioning outside of OpenWiFi and use the OpenWiFi cloud to manage the scale, state, security and validation of device websocket communications.

