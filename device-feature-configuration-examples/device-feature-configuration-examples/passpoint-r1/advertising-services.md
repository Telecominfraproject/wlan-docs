---
description: TIP OpenWiFi 2.0
---

# Advertising Services

Passpoint® requires ANQP to supply three information elements from the Access Point.

## PLMN-Id

Public Land Mobile Network Id is defined by 3GPP and comprised of two, three digit numbers to uniquely identify the Mobile Network Operator (MNO).

## Realm

A Fully Qualified Domain Name (FQDN) is a realm representing the service provider of the Wi-Fi service. Non MNO operators are an example of 'realm-based' service advertisements. Examples include Cable MSOs, Enterprises or other on MNO providers. Authentication methods used with realm-based configuration are EAP-TLS and EAP-TTLS.

## OI / RCOI

Organization Id or as defined by Wireless Broadband Alliance, Roaming Consortium Organization Id indicate the federated identity capable of authentication. Examples would be OpenRoaming, Eduroam and follow the Passpoint® EAP authentication methods.
