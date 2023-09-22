# Provisioning

The OpenWiFi solution can be applied to a diverse number of use cases from enterprise networks, service provider access, and hotspots. OpenWiFi offers a variety of managed services from small to very large venues of roaming, client shared-key management, client steering, mobile offload, QoS-based services, and Layer 2 and Layer 3 breakout and overlay options.

The Provisioning service provides a view into the network as a whole, and venues with entity-based control.

The provisioning service for OpenWiFi supports weighted order inheritance of configuration templates. These services and networks provide the greatest level of flexibility.

The system functions from a starting point of managed inventory assigned into entities, venues and optionally end subscribers. From this association, inheritance of entity, venue and subscriber configuration becomes possible where one to many configurations are processed including one to one when an inventory device such as a P2P link or Subscriber Gateway have unique operating data.

These features are present from the service over the web interface as well as via API for controller integration and OSS/BSS integration purposes.

With template inheritance, the aggregate of all inherited templates in the device association to Entity, Child, Venue, Child, Device Specific is possible. Overlapping configuration is controlled by the inherited template weight.

### Entities

Initial deployment of the Provisioning service will have an empty Entities tree. The Top Entity may be used for a number of actions or simply as a description for structure below this level.

![](<../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.17.56 AM.png>)

For example, an operator may choose to simply rename this Top Entity as "Operator Name" and set Firmware Upgrade and RRM policies to no actions accordingly. Creating child entities from this point defining perhaps an operational break down such as divisions within the operator, within which setting Firmware and or RRM rules may apply per division is possible.

![](<../../../.gitbook/assets/Screen Shot 2022-07-20 at 11.17.24 AM.png>)
