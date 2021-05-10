---
description: Consuming Open Source Stack
---

# Creating Your Own Cloud Solution

Consuming the stack is exciting, and up to you how to integrate into a complete solution. 

### Initial Lab Setup

Deploying the TIP Open Wi-Fi solution into a lab or into production is simple to do.  
Some basic pre-requisites should be satisfied before beginning.

Ensure the following are known before beginning installation:

* Fully Qualified Domain Name \(FQDN\) is available and configurable
* Internet Protocol \(IP\) subnet with Dynamic Host Configuration Protocol \(DHCP\) for access points is available
* Internet Protocol \(IP\) subnet with static addressing is available for Cloud SDK
* If using VLAN features of the access points, an IEEE 802.1q compliant Ethernet switch and VLAN topology are supported in your network
* Network traffic is permitted for the following ports from Access Points to Cloud SDK:
  * 80
  * 443
  * 1883
  * 6640
  * 6643

### Cloud Discovery 

All TIP Open Wi-Fi devices implement discovery of the cloud SDK through a Zero Touch Provisioning design based on the unique signed certificate present on each device. 

Each device contacts the Certificate Authority \(CA\) using its certificate credentials to lookup the current value of the cloud SDK. 

Once the configured cloud is returned from CA to the device, a connection is created to the cloud SDK where provisioning of the device will occur.

For more information on cloud discovery, devices and obtaining keys please proceed to the next section. 

For questions on how to obtain keys or support related to certificates please contact: licensekeys@telecominfraproject.com



