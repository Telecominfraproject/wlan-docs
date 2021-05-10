---
description: Root Certificate Trust
---

# Device and Cloud Keys

## Device and Cloud Certificates 

TIP Open Wi-Fi program ensures unique identity of all devices, encryption of traffic to and from the management cloud, discovery of management cloud, and ability to change device to cloud service discovery. TIP model ensures worldwide Zero Touch Provisioning, unique identity of all device and cloud conversation with no vendor lock in.

![TIP CA Cloud &amp; ODM Partners](../.gitbook/assets/image%20%286%29.png)

TIP device and cloud partners in Open Wi-Fi are uniquely managed members within a division of the Telecom Infra Project CA within DigiCert. 

### Device Onboarding

TIP ODM partners have the ability to generate signed certificates from the TIP Root Certificate Authority. This is done during manufacture for any TIP SKU product using signed certificates. 

Each ODM partner will use the Manufacturer name, device MAC address, and optionally a value for Redirector and Model of device when requesting a new certificate. 

The Redirector value is what determines cloud discovery and may be empty for example if the devices being manufactured do not yet have a cloud service provider assigned, for example a retail distribution model. Alternatively the value of the Redirector may be set at the same time as the certificate generation occurs. 

TIP provides an automated script to perform the device certificate request. 

### Cloud Onboarding

TIP Cloud partners have the ability to generate signed certificates for the cloud SDK. 

Similar to device onboarding, TIP provides a script to automate this process. For the cloud components the Operator name and a Fully Qualified Domain Name of the cloud are sent with each cloud key request. In addition, local configuration files are set in the request script to generate certificates matched to the operating name of certain services such as the opensync-controller and the mqtt-broker. 

### Cloud Discovery

Each device on initial startup or when factory reset will connect to the Certificate Authority using its unique device credentials requesting its current 'cloud' value. This functions both as cloud discovery as well as redirector in the event the device owner wishes to change the cloud or cloud service provider relationship with their device.

![TIP Device Cloud Discovery](../.gitbook/assets/image%20%282%29.png)

### Configuration without Internet Connection

In certain situations, a connection to the cloud or the root authority may not be possible. When this occurs, each TIP Open Wi-Fi Access Point device on factory boot presents an initial configuration Wi-Fi Management SSID called 'Maverick'. Connecting to Maverick presents a web page where updating WAN interface settings and the fully qualified domain name of the cloud may be entered.  

![Cloud and WAN Setup without Internet Access](../.gitbook/assets/image%20%281%29.png)

When the device is a PoE Ethernet switch, a local management interface exists where the same configuration of cloud and WAN are possible. 

![Local Configuration either via Wi-Fi Web GUI or LAN CLI ](../.gitbook/assets/image%20%287%29.png)

 

