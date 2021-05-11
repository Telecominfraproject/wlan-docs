---
description: General Settings
---

# System

Cloud SDK System configuration permits uploading OUI data file to assist with device fingerprinting as shown on the initial dashboard landing page dials. 

### Device OUI Fingerprints

Obtain the OUI file locally and upload to Cloud SDK via Device Manufacturer

![Device Manufacturer OUI File](../.gitbook/assets/screen-shot-2021-05-11-at-3.59.32-pm.png)

### Firmware

Firmware image upgrades may be triggered from the Cloud SDK. It is necessary to populate Cloud SDK with Model Target information. If your model is not displayed select Add Model Target Version then proceed to defined a firmware version for use. 

{% hint style="info" %}
Note a local web service should be reachable by deployed AP devices from the Fully Qualified Domain Name and file path configured in this step
{% endhint %}

![Firmware Page](../.gitbook/assets/screen-shot-2021-05-11-at-4.04.24-pm.png)

Adding firmware version:

![Specify Firmware Version and Location](../.gitbook/assets/screen-shot-2021-05-11-at-4.05.00-pm.png)

When returning to the Network and selecting an Access Point, available Firmware will be presented for actions on a per device basis.

![Device Firmware Page](../.gitbook/assets/screen-shot-2021-05-11-at-4.06.43-pm.png)

### Auto-Provisioning

Locations defined within the Cloud SDK may be auto-provisioned by default or subject to pre-provisioning logic in the Cloud SDK. When a device associates to the Cloud SDK, a Model : Profile match will be attempted in Auto-Provisioning mode. 

![Auto-Provisioning - Profiles](../.gitbook/assets/screen-shot-2021-05-11-at-4.09.35-pm.png)

### Client Blocked List

If any client should be denied access to any Wi-Fi service visible to Cloud SDK management it may be added through the global Client Blocked List. 

![Client Blocked List - MAC Address Entry](../.gitbook/assets/screen-shot-2021-05-11-at-4.11.26-pm.png)



