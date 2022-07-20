---
description: OpenWiFi 2.0
---

# User Interface for Admins

Release 2.0 user interfaces (UI) are designed as a Single-Page Application (SPA). \
The UI serves as an example user interface built using React to demonstrate several interactions using the northbound OpenAPI. \
Release 2.0 to 2.5 had a first generation of the UI framework. This first generation UI framework is seen for the Gateway and Firmware service. With the introduction of 2.6 and the Provisioning and Analytics services, a new UI for those specific SDK services has been introduced.&#x20;

All UI interactions consume the OpenAPI of the SDK services.&#x20;

The following describes the likely starting point for an Administrator. Using the Provisioning service to define how the Wi-Fi networks in Entity, Venue and device provisioning terms may optionally be defined.&#x20;

## Login to OpenWiFi SDK - Provisioning



![Login to Provisioning](<../../.gitbook/assets/Screen Shot 2022-07-19 at 2.36.39 PM.png>)

Default username is: **`tip@ucentral.com`** and password is: **`openwifi`**

On first login, the default user account will prompt to change password. This behavior is also available for all admin defined accounts added to the system.&#x20;

## **Base Navigation**

On initial login the Provisioning service places the user on the Inventory screen.&#x20;

![Provisioning Inventory](<../../.gitbook/assets/Screen Shot 2022-07-19 at 2.39.45 PM.png>)

Inventory enables the admin to visually identify OpenWiFi devices not currently assigned to an Entity, Create a new device, execute commands per device, inspect device details and view the device active state as shown in the Gateway service.&#x20;

#### Device Actions

![Device Actions](<../../.gitbook/assets/Screen Shot 2022-07-19 at 2.42.29 PM.png>)



#### View Details

![Device Details](<../../.gitbook/assets/Screen Shot 2022-07-19 at 2.44.19 PM.png>)

Within Device Details, found via the magnifying glass per Inventory row, association to an Entity Parent is possible. Additionally setting the device Firmware policy to inherit the rule assigned based on its membership to a Parent and to require Release Candidates or permit any nightly build upgrade to apply. Additionally the device may be enrolled within RRM should its Entity and Venue membership be part of RRM processing. Device Class determines if the device should be restricted to an Entity, Venue, and an end Subscriber.&#x20;

Device-Specific Configuration will expose any overriding configuration data present for this specific device. Device specific configuration will override inherited configurations from lower priority templates.&#x20;

Computed Configuration will display the enumeration of all provisioned templates the device is associated with. These templates are inherited as a result of device membership within an Entity, Child Entity, Venue and or Child Venue from which configuration templates may have been defined based on the admin deployment.&#x20;



### Bulk Inventory API

The service API could be used to bulk load record formats in a common .csv structure using JSON. For example

\`\`\`

"SerialNumber",Name,Description,DeviceType,NoteText for example: d1300f7b0732,Manufacturer,Desc, edgecore\_spw2ac1200,OutdoorAP

\`\`\`

For each inventory record, the \`\`\`deviceType\`\`\` must match a valid OpenWiFi device type. For example:

\`\`\`

"deviceTypes": \[ "cig\_wf160d", "cig\_wf188", "cig\_wf194c", "edgecore\_eap101", "edgecore\_eap102",

"edgecore\_ecs4100-12ph", "edgecore\_ecw5211",

> ...]

\`\`\`

When inventory is assigned to a Venue, it can be allocated into a top-level parent such as the operator. Then, based on role access, operation's teams may choose to assign the device to a child entity within an operating division, or setup the device as a tenant of a managed Wi-Fi service for example.

Choosing to assign the device to a specific MDU location as an example can be done in one step from above.

##
