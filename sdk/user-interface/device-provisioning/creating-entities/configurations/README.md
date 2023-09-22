# Configurations

Device provisioning occurs based on inventory association to configuration templates.

Creating a template begins with the Configurations tab and creating a new template.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.27.42 AM.png>)

### Create

Create Configuration dialog requires a name and one or multiple device types to apply configuration with. If device inventory within an Entity or a Venue exist with no configuration templates matching Device Types of the associated inventory, no associated provisioning will apply to those devices. This is the basic logic that enables unique Wi-Fi device type configurations to be layered through the system.

###

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.28.28 AM.png>)

Limiting the configuration to a subset of device types is done through selection of available Device Types via pull down menu.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.34.02 AM.png>)

A possible scenario may be that at such a top level, the operator wishes to set transmit power, MIMO operation where the Wi-Fi 6 2x2 top level configuration is defined.

To include configuration parameters, select Add Subsection and choose the appropriate values.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.36.08 AM.png>)

In this example we will choose Radios and define the MIMO and Tx Power.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.37.22 AM.png>)

Begin with describing the Radio operating mode, assign a weight that may be either low enough to be overridden by further entity or venues or high enough to not be overridden, then Add Radio.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.38.58 AM.png>)

OpenWiFi supports all possible Wi-Fi radio bands. Select the desired radio(s) and continue.

#### Radio General

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.40.03 AM.png>)

General properties, the following may be configured:

| Option          | Description                          |
| --------------- | ------------------------------------ |
| Band            | Frequency Band                       |
| Bandwidth       | 5,10,20 MHz channel narrow operation |
| Country         | Operating Country aka Country Code   |
| Channel-Mode    | Operating Mode HT, VHT, HE           |
| Channel-Width   | Total channel bandwidth              |
| Channel         | Operating channel frequency          |
| MIMO            | Values of 1x1 - 8x8                  |
| TX-Power        | Transmission power in dBm            |
| Legacy-Rates    | Allow 802.11b rates                  |
| Maximum-Clients | Total UEs Permitted                  |
| Multiple-BSSID  | Multiple BSSID IE advertisment       |

#### Radio Advanced

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.48.24 AM.png>)

Advanced Settings, the following may be configured:

|                   |                                                                                                                       |
| ----------------- | --------------------------------------------------------------------------------------------------------------------- |
| Beacon-Rate       | Value 1-54Mb/s Beacon Frame Rate                                                                                      |
| Beacon-Interval   | Interval of Beacon Frames in ms                                                                                       |
| DTIM-Period       | Value 1-255 Delivery Traffic Information Message                                                                      |
| Hostapd-iface-raw | Directly configure hostapd parameters not part of OpenWiFi data model                                                 |
| Multicast         | Multicast frame rate in Mb/s                                                                                          |
| EMA               | Multi-BSSID broadcast using EMA                                                                                       |
| BSS-Color         | BSS Coloring 0-disable, 1-63 manual, 64 random                                                                        |
| Require-Mode      | Minimum 802.11 UE standard permitted to associate. None - disabled, HT - a,b,g,n, VHT - a,b,g,n,ac, HE- a,b,g,n,ac,ax |

When complete, Save the "Top Level Wi-Fi 6 2x2" configuration for the device types chosen that align to such a radio mode.

### Inheriting Advanced Radio Configuration

For purpose of demonstration, if the admin were to create another Configuration template with the same weight as the previous template defining the Advanced parameters, these could then be broken down for example by device type.

Create another template as described for only one of the Wi-Fi 6 2x2 APs we have shown thus far.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 12.01.11 PM.png>)

Setting specific configuration for the EAP 101 advanced radio parameters. For example, if a device in this entity is an EAP 101, it will have advanced radio properties of 12Mb/s beacon rate, 24Mb/s multicast rate, random BSS color and require HE mode.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 12.03.23 PM.png>)

With these settings saved, multiple configuration templates are now shown that will influence radio operating parameters equally yet separately based on device type.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 12.04.00 PM.png>)
