---
description: TIP OpenWiFi
---

# Cloud Partner Information

TIP OpenWiFi enables integration by commercial controllers to the OpenWiFi Software Development Kit (SDK).

\
The OpenWiFi SDK is designed to enable cloud partners to consume basic southbound device management and device discovery at a minimum. This is similar to augmenting a southbound device adapter for many orchestration or automation systems.

The OpenWiFi SDK also offers numerous micro services of incremental functionality for cloud partners to optionally consume including:

* Firmware Management
* Device Provisioning
* Subscriber Portal
* Analytics
* User Interface

This independent micro service approach has numerous advantages including ease of integration, ability to leverage more of the stack to accelerate product availability or support only device communication and discovery for partners who seek to maintain more functionality within their own application.

### Step 1 : Join

If your organization is not already a TIP Open Converged Wireless Project Group (OCW PG) member, consider signing up. Joining the OCW PG is free as a Software Participation Tier in TIP.

For more information please visit:[ Becoming a Member](https://telecominfraproject.com/apply-for-membership/)

### Step 2 : Slack, Keys & Atlassian Tools

Introduce your organization to the Community on Slack. All Community members have access to Telecom Infra Project Slack. Send a message to "general" and "open-wifi-ucentral" channels.

Send an email to licensekeys@telecominfraproject.com to request onboarding as a supplier for OpenWiFi Cloud. All OpenWiFi Gateway services in the SDK require a signed key to terminate incoming device connections in the southbound interface.

Ensure your GitHub account was linked in your Telecom Infra Project user profile, this will enable write access to OpenWiFi repositories. Also confirm Atlassian link is also present in user profile.

### Step 3 : Integration

OpenWiFi SDK uses OpenAPI 3.0 compliant northbound Rest API and Kafka for message bus topics. Typical CRUD actions occur via the Rest API, Kafka will present topics for device discovery and all telemetry captured from the network edge.

Please consult the [API topics](../developer-resources/api/) to begin with integration work.

### Summary

Integrations that use the published interfaces are the easiest approach to starting with OpenWiFi SDK.

If a cloud partner seeks to contribute a new SDK micro service, please announce the idea on "general" and "open-wifi-ucentral" slack channels for the Community to help further.\
There is a skeleton micro service example to help developers build new services that inherit SDK service discovery and security design.

Please find skeleton service [here](https://github.com/Telecominfraproject/wlan-cloud-tools).
