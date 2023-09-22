---
description: OpenWiFi 2.0
---

# Basic Device Provisioning

OpenWiFi device features are configurable through understanding the uCentral device data model.

For integrators of commercial controllers, these feature examples may help guide development of device provisioning within a partner controller products.

Experimentation with device features often occurs initially through static configuration as JSON document sent to a device using the OpenWiFi Gateway.

Commercial products with OpenWiFi device provisioning will be using the northbound API to create, update, delete per device configurations. These APIs are then inter-worked southbound via the OpenWiFi Gateway to devices.

Some of the available device features are exposed in this same manner using the OpenWiFi Provisioning service. This provisioning service offers an additional way for commercial partners to consume OpenWiFi and integrate a controller or back office environment that may require device provisioning when that functionality is not present as part of a controller or other commercial product.

The following pages guide the user to understanding each of these features individually including example configuration information.

#### Basic Examples

One of the benefits of the new data plane in OpenWiFi 2.0 is the flexibility of physical port to logical forwarding that is easily conveyed through configuration structures.

New protocol support is both easily added to the system as well as associated with interfaces by their role in the device.

The following sections offer feature configuration examples.

For complete reference to the device data model please refer [here.](../../sdk/provisioning/data-model-introduction.md)
