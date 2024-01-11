---
description: TIP OpenWiFi
---

# Cloud Partner Information

The OpenWiFi SDK is designed to enable Cloud Partners to consume basic southbound device management and device discovery. This is similar to augmenting a southbound device adapter for many orchestration or automation systems.

## OpenWiFi Microservices

The OpenWiFi SDK also offers microservices for Cloud Partners including the following:

* Firmware Management
* Device Provisioning
* Subscriber Portal
* Analytics
* User Interface

This independent microservice approach has numerous advantages including ease of integration, ability to leverage more of the stack to accelerate product availability or support only device communication and discovery for partners who seek to maintain more functionality within their own application.

### Step 1 : Join

If your organization is not already a TIP Open Converged Wireless Project Group (OCW PG) member, consider signing up. Joining the OCW PG is free as a Software Participation Tier in TIP.

For more information please visit:[ Becoming a Member](https://telecominfraproject.com/apply-for-membership/)

### Step 2 : Slack, Keys & Atlassian Tools

Introduce your organization to the Community on Slack. All Community members have access to Telecom Infra Project Slack. Send a message to the **#general** and **#open-wifi-ucentral** Slack channels.

Send an email to licensekeys@telecominfraproject.com to request onboarding as a supplier for OpenWiFi Cloud. All OpenWiFi Gateway services in the SDK require a signed key to terminate incoming device connections in the southbound interface.

Ensure your GitHub account is linked in your Telecom Infra Project user profile. Linking your GitHub account to your TIP user account enables write access to OpenWiFi repositories. Also confirm that the Atlassian link is also present in your user profile.

### Step 3 : Integration

The OpenWiFi SDK uses OpenAPI 3.0 compliant northbound Rest API and Kafka for message bus topics. Typical CRUD actions occur via the Rest API. Kafka presents topics for device discovery and all telemetry captured from the network edge.

Please consult the [API topics](../developer-resources/api/) to begin with integration work.

### Summary

Integrations that use the published interfaces are the easiest approach to starting with OpenWiFi SDK.

As a Cloud Partner who intends to contribute a new SDK microservice, please announce the idea on the **#general** and **#open-wifi-ucentral** Slack channels for the Community to provide feedback. There is a skeleton microservice example to help you build new services that inherit the SDK service discovery and security design. For more information about building a service, see the API section in the [Developer Resources](../developer-resources/api/) section. An example used for building a service is located in [GitHub](https://github.com/Telecominfraproject/wlan-cloud-tools).
