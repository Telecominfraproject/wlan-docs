---
description: TIP OpenWiFi 2.0
---

# Advanced Device Feature Configuration Examples

OpenWiFi device features are configurable through understanding the uCentral device data model.

For integrators of commercial controllers, these feature examples may help guide development of device provisioning within a partner controller products.

Experimentation with device features often occurs initially through static configuration as JSON document sent to a device using the OpenWiFi Gateway.&#x20;

Commercial products with OpenWiFi device provisioning will be using the northbound API to create, update, delete per device configurations. These APIs are then inter-worked southbound via the OpenWiFi Gateway to devices.&#x20;

Some of the available device features are exposed in this same manner using the OpenWiFi Provisioning service. This provisioning service offers an additional way for commercial partners to consume OpenWiFi and integrate a controller or back office environment that may require device provisioning when that functionality is not present as part of a controller or other commercial product. &#x20;

The following pages guide the user to understanding each of these features individually including example configuration information.

For complete reference to the device data model please refer [here.](../../sdk/provisioning/data-model-introduction.md)
