---
description: OpenWiFi 2.0 SDK
---

# OpenAPI Definitions

## Where is the OpenAPI?

This uses OpenAPI definition 3.0 and can be found [here](https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/master/openapi/ucentral/owgw.yaml). All endpoints begin with `/api/v1`.

## API Flow

API endpoints are secured with bearer-token authentication using end-point `/oauth2`. Once you obtain `access-token`, you will need to pass it in the headers under `Authorization: Bearer <place your token here>`.

## Basic Entities

The API revolves around `devices`, `commands`, and `default_configurations`. To retrieve a list of `devices` to know what is available and then use the endpoint `device` to access all device specific information. To retrieve `commands` and `default_configurations` follow those endpoints. Most operations rely on the `serialNumber` of a device. That `serialNumber` is unique and generated on the device. Serial Number matches the device's MAC address.

* `devices`: The list of all devices in the system. This maybe very large, pagination is recommended.
* `commands`: The list of commands issued by the system. This list could also be large.
* `default_configurations`: A list of default configurations used to supply existing devices.

## Relationships

A device is a physical (or potentially logical) entity using the ucentral protocol. Currently, APs and Switches are the only devices used. A device has several attributes. Additionally, other collections are supported for each device:

* `logs`: Specific for a device. Logs originate from the device or associated with the device by some mechanism.
* `healthchecks`: Reports from the device coming periodically after device self tests.
* `statistics`: Periodically produced by the devices and document actual state data from each device.
* `capabilities`: This details the actual data model supported by the device.

The `device` entry point is also used to query about the `status` of the device and used to inject certain commands for a specific device. Commands supported for each device:

* `reboot`: This will force the device to reboot.
* `configure`: Configure sends a new configuration to a device.
* `factory`: Forces the device to perform a factory-reset.
* `upgrade`: Forces the device to do a firmware upgrade.
* `leds`: Ask the device to flash its LEDs or turn them on or off.
* `trace`: Performs a remove LAN trace. Once the trace is completed, the produced file may be removed using the `file` endpoint.
* `command`: Performs a proprietary command. The meaning depends on the device.
* `request`: Request an immediate message of type `state` or `healthcheck`.

The `file` end point is used to retrieve and remove files produced by the Gateway. Currently this is limited to the results of a `trace` command. The file name will always match the `uuid` of the command that produced it. If several files are needed, the files will be named `uuid`, `uuid.1`, `uuid.2`, etc.

## Dates

All dates should use the format defined in [RFC3339](https://tools.ietf.org/html/rfc3339). All times are UTC based. Here is an example:

```
1985-04-12T23:20:50.52Z
```

## Command `when` parameter

Most commands use a `when` parameter to suggest to the device when to perform the command. This is a _suggestion_ only. The device may decide to perform the command when it is optimal for itself. It maybe busy doing something and decline to do a reboot for several minutes for example. The device may reply with the actual `when` it will perform the command.

## Configuration UUID

The gateway manages the configuration UUID. So if you set a UUID for a configuration, it will be ignored. The gateway uses UUID as versioning. The UUID is unique within a single device. The resulting UUID or a configuration change is returned as part of the `configure` command.
