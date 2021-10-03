---
description: TIP OpenWiFi 2.0
---

# Cloud Discovery

All TIP OpenWiFi devices use the same cloud discovery mechanism on initial boot.

OpenWiFi devices ship from factory with a unique device certificate signed by the Telecom Infra Project Certificate Authority.

When a device boots for the first time, or is factory reset, a 'first-boot' process occurs within the device.  
First-boot initiates a connection over HTTPs to the Certificate Authority requesting the unique device record information. All connections to the Certificate Authority occur over mTLS encrypted session.  
Devices use their unique certificate identity to authenticate and retrieve the location of the assigned cloud.

![Device First Boot / Factory Cloud Discovery](../../.gitbook/assets/image%20%2824%29.png)

Once the cloud location has been learned from first-boot, the device no longer depends on this cloud discovery and will return to the assigned cloud learned from first-boot.

Devices may periodically initiate connection to the Certificate Authority to validate their unique certificate status. This is a normal process involved in mutual TLS security models.

When an operator or end customer seeks to change the cloud associated with their device\(s\), the value of the cloud stored in the Certificate Authority device record is updated. A factory reset of the device will cause first-boot to re-occur which will then discover the new cloud.

TIP OpenWiFi ODM partners are able to manage device records directly using the Certificate Authority portal. All other users should send an email to licensekeys@telecominfraproject.com to request update of cloud discovery.

