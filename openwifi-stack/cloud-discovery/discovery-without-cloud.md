---
description: TIP OpenWiFi 2.0
---

# Discovery without Cloud

There could be reasons cloud discovery does not complete.
These include:

* Lack of Internet Connectivity
  * Device may require additional WAN settings
  * Network may not be connected to Internet
* No Configuration of Cloud in Certificate Authority
  * Manufacturer may have left this value blank in the device record stored in Certificate Authority

![Manual Cloud Entry](<../../.gitbook/assets/image (23).png>)

When the cloud can not be automatically discovered, OpenWiFi devices will turn on a local admin web UI made available via SSID "Maverick".

The Maverick UI will support configuring WAN interface parameters, including DHCP, Static, PPPoE, and LTE/5G settings. Please see [Local Device Settings](../access-points/local-device-settings.md) for details on using Maverick.
[  \
](../access-points/local-device-settings.md)Additionally the Maverick UI supports direct entry of the cloud for cases when the cloud value has not been supplied during manufacture.

For non-Wi-Fi devices such as PoE access switches, the same cloud location information may be configured using local management interface.

![Admin / User Entered WAN or Cloud](<../../.gitbook/assets/image (24).png>)
