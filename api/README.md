---
description: OpenWiFi 2.0 SDK
---

# API

OpenWiFi services follow the OpenAPI 3.0 definition.   
The complete API is described here: [OpenWiFi SDK OpenAPI](https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/master/openapi/ucentral/ucentral.yaml)

### Devices

OpenWiFi devices are Access Points or Switches \(and other forms in the future\), that support the uCentral configuration schema. Devices contact a controller using the uCentral protocol.

### Communication

The communication between the controller and the devices use the uCentral protocol. This protocol is defined in this [document](https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/main/PROTOCOL.md).

### Device Configuration

A device is configured by ingesting a uCentral configuration. That configuration will be provided by the SDK Gateway as a result of a command through the API. Command processing occurs when the device's configuration is older than what is known in the SDK Gateway. The uCentral schema is a JSON document containing parameters to set on a particular device.

### SDK Gateway Communication

In order to speak to the Gateway, you must implement a client that uses the OpenAPI definition for the gateway. You can find its [definition here](https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/main/openapi/ucentral/ucentral.yaml). You cannot talk to a device directly.

### API Basics

#### Device `serialNumber`

Throughout the API, the `serialNumber` of the device is used as the key. The `serialNumber` is actual the MAC address of the device, without its `:`. The `serialNumber` is guaranteed to be unique worldwide. The device uses its serial number to identify itself to the controller.

#### Device Configuration

The configuration can be supplied when the device is created. After the device is created, the only way to modify the configuration is by using the `/device/{serialNumber}/configure` endpoint. The Gateway maintains the versioning of the configuration through the use of a `uuid`. The Gateway maintains that number and will ignore anything your supply. The controller also does minimum validation on the configuration: it must be a valid JSON document and must have a `uuid` field which will be ignored.

#### Device Capabilities

Device capabilities are uploaded to the Gateway when the device performs its initial connection. Capabilities tell the Gateway what the device is able to support. The Gateway uses this information to provide a configuration matched to the device type.

#### Command Queue

The Gateway will send commands to the devices. These commands are kept in a table and are sent at the appropriate time or immediately when the device connects.   
For example, you could ask a device to change its configuration, however it might be unreachable. Upon next device connection, this configure command will be sent. The list of commands is retrieved using the `/commands` endpoint.

#### Commands

Several commands maybe sent to a device: reboot, configure, factory reset, firmware upgrade, LEDs, trace, message request, etc. The API endpoint `/device/{serialNumber}/{command}` details all the available commands.

#### Device Specific Collections

For each device, a number of collections are collected and kept in the database. Here's a brief list:

* `logs`: device specific logs are kept. A device amy also send something it wants added into its own logs. `crashlogs` are a special type of logs created after a device has had a hard crash.
* `statistics`: statistics about the device. This is current la JSON document and will be documented at a later date.
* `healthchecks`: periodically, a device will run a self-test and report its results. These includes anything that maybe going wrong with the current device configuration. A `sanity` level is associated to the degree of health of the device. 100 meaning a properly operating device.
* `status`: tells you where the device is and how much data is used for protocol communication.

### The API is for an operator

This API is meant for an operator who would have to help a subscriber in configuring devices, reboot, manage  firmware, etc. 

