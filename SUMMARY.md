# Table of contents

* [OpenWiFi Release 2.6 GA](README.md)

## ABOUT

* [About OpenWifi](about/about-openwifi.md)
* [OpenWiFI First](about/contribute.md)
* [Supported Hardware](about/supported-hardware.md)
* [Device Partner Information](about/device-partner-information.md)
* [Cloud Partner Information](about/cloud-partner-information.md)
* [Ordering OpenWiFi APs](about/ordering-open-wi-fi-aps.md)
* [Example Partner Integrations](about/integrations.md)

## OPENWIFI STACK

* [Overview](openwifi-stack/openwifi-stack.md)
* [SDK](openwifi-stack/about-the-sdk.md)
* [Cloud Discovery](openwifi-stack/cloud-discovery/README.md)
  * [Discovery without Cloud](openwifi-stack/cloud-discovery/discovery-without-cloud.md)
* [Access Points](openwifi-stack/access-points/README.md)
  * [Local Device Settings](openwifi-stack/access-points/local-device-settings.md)
* [Firmware Management](openwifi-stack/firmware.md)
* [Device Provisioning](openwifi-stack/device-provisioning.md)
* [Code Repositories](openwifi-stack/repositories.md)
* [Artifacts](openwifi-stack/artifacts.md)

## SDK

* [Getting Started](sdk/getting-started.md)
* [Release 2.0 SDK](sdk/sdk.md)
* [Provisioning](sdk/provisioning/README.md)
  * [Data Model Introduction](sdk/provisioning/data-model-introduction.md)
  * [Creating a Configuration](sdk/provisioning/creating-a-configuration.md)
* [User Interface](sdk/user-interface/README.md)
  * [Devices](sdk/user-interface/devices-view/README.md)
    * [Commands](sdk/user-interface/devices-view/commands.md)
    * [Statistics](sdk/user-interface/devices-view/statistics.md)
    * [Command History](sdk/user-interface/devices-view/command-history.md)
  * [Firmware](sdk/user-interface/firmware.md)
* [Monitoring](sdk/monitoring/README.md)
  * [ELK Integration](sdk/monitoring/elk-integration.md)

## SDK Installation

* [Overview](sdk-installation/overview.md)
* [Deploy using Docker Compose](sdk-installation/deploy-using-docker-compose.md)
* [Deploy using Helm](sdk-installation/deploy-using-helm.md)

## Configuration Examples

* [Basic Device Provisioning](configuration-examples/basic-device-provisioning/README.md)
  * [Bridge Mode SSID](configuration-examples/basic-device-provisioning/bridge-mode-ssid.md)
  * [NAT Gateway Mode SSID](configuration-examples/basic-device-provisioning/nat-gateway-mode-ssid.md)
  * [Multi-VLAN SSID](configuration-examples/basic-device-provisioning/multi-vlan-ssid.md)
* [Device Feature Configuration Examples](configuration-examples/device-feature-configuration-examples/README.md)
  * [Zero Touch Provisioning](configuration-examples/device-feature-configuration-examples/zero-touch-provisioning.md)
  * [DHCP Relay](configuration-examples/device-feature-configuration-examples/dhcp-relay.md)
  * [Services](configuration-examples/device-feature-configuration-examples/services.md)
  * [Metrics](configuration-examples/device-feature-configuration-examples/metrics.md)
  * [GRE](configuration-examples/device-feature-configuration-examples/gre.md)
  * [L2TP](configuration-examples/device-feature-configuration-examples/l2tp.md)
  * [VxLAN](configuration-examples/device-feature-configuration-examples/vxlan.md)
  * [WDS](configuration-examples/device-feature-configuration-examples/wds-topologies.md)
  * [Mesh](configuration-examples/device-feature-configuration-examples/mesh.md)
  * [QoS](configuration-examples/device-feature-configuration-examples/qos.md)
  * [Dynamic Air Time Fairness](configuration-examples/device-feature-configuration-examples/dynamic-air-time-fairness.md)
  * [Dynamic Subscriber QoS](configuration-examples/device-feature-configuration-examples/dynamic-subscriber-qos.md)
  * [Captive Portal](configuration-examples/device-feature-configuration-examples/captive-portal/README.md)
    * [External Captive Portal](configuration-examples/device-feature-configuration-examples/captive-portal/external-captive-portal.md)
  * [ExpressWiFi](configuration-examples/device-feature-configuration-examples/expresswifi.md)
  * [Roaming RRM and SON](configuration-examples/device-feature-configuration-examples/roaming-rrm-and-son.md)
  * [RADIUS Authenticated SSID](configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/README.md)
    * [Dynamic VLANs with RADIUS](configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/dynamic-vlans-with-radius.md)
  * [Multi-PSK (MDU Shared Key)](configuration-examples/device-feature-configuration-examples/multi-psk-mdu-multiple-shared-key.md)
  * [Dynamic Air-Time Policy](configuration-examples/device-feature-configuration-examples/dynamic-air-time-policy.md)
  * [Passpoint®](configuration-examples/device-feature-configuration-examples/passpoint-r1/README.md)
    * [Configuration Introduction](configuration-examples/device-feature-configuration-examples/passpoint-r1/configuration-introduction.md)
    * [Advertising Services](configuration-examples/device-feature-configuration-examples/passpoint-r1/advertising-services.md)
    * [Passpoint® Configuration](configuration-examples/device-feature-configuration-examples/passpoint-r1/passpoint-r-configuration.md)
  * [Switching](configuration-examples/device-feature-configuration-examples/switching/README.md)
    * [Port Speed](configuration-examples/device-feature-configuration-examples/switching/port-speed.md)

## RELEASE

* [What's New](release/whats-new.md)
* [Features](release/features.md)
* [Security Updates](release/security.md)
* [Resolved Issues](release/resolved-issues.md)

## DEVELOPER RESOURCES

* [SDK API](developer-resources/api/README.md)
  * [OpenAPI Definitions](developer-resources/api/openapi-definitions.md)
  * [Security Service](developer-resources/api/security-service.md)
  * [Gateway Service](developer-resources/api/gateway-service.md)
  * [Firmware Management Service](developer-resources/api/firmware-management-service.md)
  * [Provisioning Service](developer-resources/api/provisioning-service.md)
  * [Analytics Service](developer-resources/api/analytics-service.md)
  * [Postman Collection](developer-resources/api/postman-collection.md)
* [SDK KAFKA](developer-resources/sdk-kafka/README.md)
  * [Connection](developer-resources/sdk-kafka/connection.md)
  * [Device Event Queue](developer-resources/sdk-kafka/device-event-queue.md)
  * [Device Telemetry](developer-resources/sdk-kafka/device-telemetry.md)
  * [Healthcheck](developer-resources/sdk-kafka/healthcheck.md)
  * [Provisioning Change](developer-resources/sdk-kafka/provisioning-change.md)
  * [Service Events](developer-resources/sdk-kafka/service-events.md)
  * [State](developer-resources/sdk-kafka/state.md)
  * [WiFi Scan](developer-resources/sdk-kafka/wifi-scan.md)
