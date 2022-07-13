---
description: TIP OpenWiFi 2.0
---

# Configuration Introduction

TIP OpenWiFi devices implement support for both the air interface and systems interfaces necessary to support Passpoint® Release 2 and above. Once also termed Hotspot 2.0, IEEE 802.11u specified added air interface fields exposing Access Network Query Protocol interactions for clients to discovery Access Point capabilities.

Wi-Fi Alliance expanded ANQP to include Online Signup (OSU) concepts to leverage seamless onboarding and client security for Passpoint® networks. Following on from these efforts, Wireless Broadband Alliance has provided the necessary system interfaces for identity, security, mobile offload within a common federated operator solution known as OpenRoaming.

TIP OpenWiFi enables operators to deploy the full range of Passpoint® and OpenRoaming solutions.

| Term              | Description                                                                                                                                                                                                                                                                                                                    |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Operator          | <p>Wi-Fi Infrastructure Operator</p><p>Access Network Provider (ANP) as defined by OpenRoaming</p>                                                                                                                                                                                                                             |
| Venue             | Deployed location of Wi-Fi service                                                                                                                                                                                                                                                                                             |
| Identity Provider | <p>Subscriber authenticating service provider</p><p>Home Service Provider (HSP) as defined by OpenRoaming</p>                                                                                                                                                                                                                  |
| Roaming Exchange  | Operator and Identity Provider Authentication, Authorization, Accounting                                                                                                                                                                                                                                                       |
| ANQP              | <p>Access Network Query Protocol contains:</p><ul><li>Domain</li><li>Venue Name</li><li>Venue Info</li><li>Operator Friendly Name</li><li>IP Type</li><li>WAN Metric</li><li>Connection Capability</li><li>Operating Class</li><li>Authentication Type</li><li>Service Providers List</li></ul>                                |
| GAS               | <p>Generic Advertisement Layer 2 Service for client query</p><ul><li><p>Client query returns:</p><ul><li>Organization Identifier / Service Provider Identity</li><li>Domain</li><li>Authentication</li><li>Roaming Consortium List</li><li>Network Access Identifier Realm (NAI)</li><li>3GPP Network Data</li></ul></li></ul> |
| OSU               | <p>Online Signup - Advertised over ANQP contains:</p><ul><li>OSU SSID</li><li>OSU URI</li><li>OSU Method</li><li>OSU Available Icons</li><li>OSU ESS (OSEN) SSID</li><li>OSU Description</li></ul>                                                                                                                             |
| OSEN              | OSU Server Authenticated Layer 2 Encryption Network                                                                                                                                                                                                                                                                            |
