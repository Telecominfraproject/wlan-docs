# Table of contents

* [OpenWiFi Release 2.7](README.md)

## ABOUT

* [About OpenWiFi](about/about-openwifi.md)
* [Supported Hardware](about/supported-hardware.md)
* [Device Partner Information](about/device-partner-information.md)
* [Cloud Partner Information](about/cloud-partner-information.md)
* [Ordering OpenWiFi APs](about/ordering-open-wi-fi-aps.md)
* [Example Partner Integrations](about/integrations.md)

## OPENWIFI STACK

* [Overview](openwifi-stack/openwifi-stack.md)
* [SDK](openwifi-stack/about-the-sdk.md)
* [Access Points](openwifi-stack/access-points/README.md)
  * [Local Device Settings](openwifi-stack/access-points/local-device-settings.md)
* [Cloud Discovery](openwifi-stack/cloud-discovery/README.md)
  * [Discovery without Cloud](openwifi-stack/cloud-discovery/discovery-without-cloud.md)
* [Code Repositories](openwifi-stack/repositories.md)
* [Artifacts](openwifi-stack/artifacts.md)

## SDK

* [Getting Started](sdk/getting-started.md)
* [Architecture](sdk/sdk.md)
* [Provisioning for Integrators](sdk/provisioning/README.md)
  * [Data Model Introduction](sdk/provisioning/data-model-introduction.md)
  * [Creating a Configuration](sdk/provisioning/creating-a-configuration.md)
* [User Interface for Admins](sdk/user-interface/README.md)
  * [Provisioning](sdk/user-interface/device-provisioning/README.md)
    * [Creating Entities](sdk/user-interface/device-provisioning/creating-entities/README.md)
      * [Configurations](sdk/user-interface/device-provisioning/creating-entities/configurations/README.md)
        * [Metrics Settings Example](sdk/user-interface/device-provisioning/creating-entities/configurations/metrics-settings-example.md)
    * [Creating Venues](sdk/user-interface/device-provisioning/creating-venues/README.md)
      * [Configurations](sdk/user-interface/device-provisioning/creating-venues/configurations/README.md)
        * [WAN](sdk/user-interface/device-provisioning/creating-venues/configurations/wan.md)
        * [VAP - SSID](sdk/user-interface/device-provisioning/creating-venues/configurations/vap-ssid.md)
  * [Inventory Association](sdk/user-interface/inventory-association.md)
  * [Gateway](sdk/user-interface/gateway.md)
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

## Device Feature Configuration Examples

* [Basic Device Provisioning](device-feature-configuration-examples/basic-device-provisioning/README.md)
  * [Bridge Mode SSID](device-feature-configuration-examples/basic-device-provisioning/bridge-mode-ssid.md)
  * [NAT Gateway Mode SSID](device-feature-configuration-examples/basic-device-provisioning/nat-gateway-mode-ssid.md)
  * [Multi-VLAN SSID](device-feature-configuration-examples/basic-device-provisioning/multi-vlan-ssid.md)
* [Advanced Device Feature Configuration Examples](device-feature-configuration-examples/device-feature-configuration-examples/README.md)
  * [Zero Touch Provisioning](device-feature-configuration-examples/device-feature-configuration-examples/zero-touch-provisioning.md)
  * [DHCP Relay](device-feature-configuration-examples/device-feature-configuration-examples/dhcp-relay.md)
  * [Services](device-feature-configuration-examples/device-feature-configuration-examples/services.md)
  * [Metrics](device-feature-configuration-examples/device-feature-configuration-examples/metrics.md)
  * [GRE](device-feature-configuration-examples/device-feature-configuration-examples/gre.md)
  * [L2TP](device-feature-configuration-examples/device-feature-configuration-examples/l2tp.md)
  * [VxLAN](device-feature-configuration-examples/device-feature-configuration-examples/vxlan.md)
  * [WDS](device-feature-configuration-examples/device-feature-configuration-examples/wds-topologies.md)
  * [Mesh](device-feature-configuration-examples/device-feature-configuration-examples/mesh.md)
  * [QoS](device-feature-configuration-examples/device-feature-configuration-examples/qos.md)
  * [Dynamic Air Time Fairness](device-feature-configuration-examples/device-feature-configuration-examples/dynamic-air-time-fairness.md)
  * [Captive Portal](device-feature-configuration-examples/device-feature-configuration-examples/captive-portal/README.md)
    * [External Captive Portal](device-feature-configuration-examples/device-feature-configuration-examples/captive-portal/external-captive-portal.md)
  * [Roaming RRM and SON](device-feature-configuration-examples/device-feature-configuration-examples/roaming-rrm-and-son.md)
  * [RADIUS Authenticated SSID](device-feature-configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/README.md)
    * [Dynamic VLANs with RADIUS](device-feature-configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/dynamic-vlans-with-radius.md)
    * [WISPr Subscriber Bandwidth](device-feature-configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/wispr-subscriber-bandwidth.md)
    * [Dynamic Multi PSK](device-feature-configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/dynamic-multi-psk.md)
    * [RADIUS MAC-Auth](device-feature-configuration-examples/device-feature-configuration-examples/radius-authenticated-ssid/radius-mac-auth.md)
  * [Multi-PSK (MDU Shared Key)](device-feature-configuration-examples/device-feature-configuration-examples/multi-psk-mdu-multiple-shared-key.md)
  * [Wireguard](device-feature-configuration-examples/device-feature-configuration-examples/wireguard.md)
  * [Dynamic Air-Time Policy](device-feature-configuration-examples/device-feature-configuration-examples/dynamic-air-time-policy.md)
  * [Passpoint®](device-feature-configuration-examples/device-feature-configuration-examples/passpoint-r1/README.md)
    * [Configuration Introduction](device-feature-configuration-examples/device-feature-configuration-examples/passpoint-r1/configuration-introduction.md)
    * [Advertising Services](device-feature-configuration-examples/device-feature-configuration-examples/passpoint-r1/advertising-services.md)
    * [Passpoint® Configuration](device-feature-configuration-examples/device-feature-configuration-examples/passpoint-r1/passpoint-r-configuration.md)

## RELEASE

* [What's New](release/whats-new.md)
* [Features](release/features.md)
* [Security Updates](release/security.md)
* [Resolved Issues](release/resolved-issues.md)
* [Outstanding Items](release/outstanding-items.md)
* [Testing Results](release/testing-results.md)

## DEVELOPER RESOURCES

* [SDK API](developer-resources/api/README.md)
  * [OpenAPI Definitions](developer-resources/api/openapi-definitions.md)
  * [Security Service](developer-resources/api/security-service.md)
  * [Gateway Service](developer-resources/api/gateway-service.md)
  * [Firmware Management Service](developer-resources/api/firmware-management-service.md)
  * [Provisioning Service](developer-resources/api/provisioning-service.md)
  * [Analytics Service](developer-resources/api/analytics-service.md)
  * [Radio Resource Management Service](developer-resources/api/radio-resource-management-service.md)
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
