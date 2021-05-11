---
description: Passpoint® via API
---

# Passpoint® Postman Collection

Cloud SDK accepts all Passpoint® configuration via API if desired. Please refer to  [API](../../../api/)  for additional instructions on use of Cloud SDK OpenAPI. 

For reference:  [Postman collection for Passpoint](https://github.com/Telecominfraproject/wlan-cloud-workspace/blob/master/wlan-cloud-devtools/postman-collections/passpoint/RadSec.postman_collection.json) to assist the reader is available. 

#### RADIUS Profile Example: PLMN ID Based Identity Provider Profile

```text
{
    "model_type": "Profile",
    "id": 3,
    "customerId": 2,
    "profileType": "radius",
    "name": "Identity_Provider-radius-profile",
    "details": {
        "model_type": "RadiusProfile",
        "primaryRadiusAuthServer": {
            "model_type": "RadiusServer",
            "ipAddress": "10.16.10.50",
            "secret": "testing123!",
            "port": 11812,
            "timeout": 0
        },
        "secondaryRadiusAuthServer": null,
        "primaryRadiusAccountingServer": {
            "model_type": "RadiusServer",
            "ipAddress": "10.16.10.60",
            "secret": "testing123!",
            "port": 11813,
            "timeout": 5
        },
        "secondaryRadiusAccountingServer": null,
        "profileType": "radius"
    },
    "childProfileIds": []

```

{% hint style="info" %}
Open WiFi 1.0 SSIDs are mapped to a single RADIUS profile. All Authentication and Accounting will be forwarded to the RADIUS services defined in the Profile. Sub-release 1.1 supports realm-based forwarding and RADSec operations \(RADIUS over TLS\)
{% endhint %}

### Identities

#### Identity Provider Profile Example: PLMN ID Based Identity

```text
{
    "model_type": "Profile",
    "id": 11,
    "customerId": 2,
    "profileType": "passpoint_osu_id_provider",
    "name": "MNO",
    "details": {
        "model_type": "PasspointOsuProviderProfile",
        "mccMncList": [
            {
                "model_type": "PasspointMccMnc",
                "mcc": 3-digit,
                "mnc": 3-digit,
                "iso": "us",
                "country": "USA",
                "countryCode": 1,
                "network": "MNO Name",
                "mccMncPairing": "3-digit,3-digit"
            }
        ],
        "naiRealmList": [],
        "osuIconList": [],
        "osuServerUri": null,
        "osuFriendlyName": [],
        "osuNaiStandalone": "anonymous@mno_fqdn",
        "osuNaiShared": "anonymous@mno_fqdn",
        "osuMethodList": [],
        "osuServiceDescription": [],
        "roamingOi": [],
        "profileType": "passpoint_osu_id_provider"
    },
    "childProfileIds": []
}

```

In the above example, an MNO with PLMN identifiers is configured. The result of this configuration will be a UE mobile handset learns its home network operator is available over Wi-Fi network and attempts authentication seamlessly. The MNO logo will display in the UE home screen top bar.

#### Identity Provider Profile Example: OI / RCOI Based Identity

```text
{
    "model_type": "Profile",
    "id": 16,
    "customerId": 2,
    "profileType": "passpoint_osu_id_provider",
    "name": "RCOI-Member-OpenRoaming",
    "details": {
        "model_type": "PasspointOsuProviderProfile",
        "mccMncList": [],
        "naiRealmList": [],
        "osuIconList": [],
        "osuServerUri": null,
        "osuFriendlyName": [],
        "osuNaiStandalone": "anonymous@member_fqdn",
        "osuNaiShared": "anonymous@member_fqdn",
        "osuMethodList": [],
        "osuServiceDescription": [],
        "roamingOi": [
            "FFFFF00000",
            "FFFFF00100",
            "FFFFF8F5F4",
            "000000",
            "000000"
        ],
        "profileType": "passpoint_osu_id_provider"
    },
    "childProfileIds": []
}

```

In the above example, a settled roaming provider part of the OpenRoaming federated RCOI has been defined. The UE device will automatically discover this network, for many devices with existing OpenRoaming credentials will seamlessly associate to the advertised service from this Wi-Fi network. 

#### Identity Provider Profile Example: Realm Based  

```text
{
    "model_type": "Profile",
    "id": 7,
    "customerId": 2,
    "profileType": "passpoint_osu_id_provider",
    "name": "Realm Operator Name",
    "details": {
        "model_type": "PasspointOsuProviderProfile",
        "mccMncList": [],
        "naiRealmList": [
            {
                "model_type": "PasspointNaiRealmInformation",
                "naiRealms": [
                    "operator.fqdn.com"
                ],
                "encoding": 0,
                "eapMethods": [
                    "EAP-TTLS with username/password"
                ],
                "eapMap": {
                    "EAP-TTLS with username/password": [
                        "Non-EAP Inner Authentication Type:MSCHAPV2"
                    ]
                }
            }
        ],
        "osuIconList": [],
        "osuServerUri": null,
        "osuFriendlyName": [],
        "osuNaiStandalone": "anonymous@operator_fqdn.com",
        "osuNaiShared": "anonymous@operator_fqdn.com",
        "osuMethodList": [],
        "osuServiceDescription": [],
        "roamingOi": [],
        "profileType": "passpoint_osu_id_provider"
    },
    "childProfileIds": []

```

The above example demonstrates a realm-based identity provider configured for authentication using EAP-TTLS.



### Operators and Venues

#### Wi-Fi Operator Profile Example

```text
{
    "model_type": "Profile",
    "id": 12,
    "customerId": 2,
    "profileType": "passpoint_operator",
    "name": "TIP Lab",
    "details": {
      "model_type": "PasspointOperatorProfile",
      "serverOnlyAuthenticatedL2EncryptionNetwork": false,
      "x509CertificateLocation": null,
      "operatorFriendlyName": [
          {
              "model_type": "PasspointDuple",
              "locale": "eng",
              "dupleIso3Language": "eng",
              "dupleName": "Telecom Infra Project",
              "defaultDupleSeparator": ":",
                "asDuple": "eng:Telecom Infra Project"
          },
          {
              "model_type": "PasspointDuple",
              "locale": "fra",
              "dupleIso3Language": "fra",
              "dupleName": "Le Telecom Infra Project",
              "defaultDupleSeparator": ":",
              "asDuple": "fra:Le Telecom Infra Project"
            }
        ],
        "domainNameList": [
            "telecominfraproject.com"
        ],
        "profileType": "passpoint_operator"
    },
    "childProfileIds": []
}

```



#### Venue Profile

```text
{
    "model_type": "Profile",
    "id": 13,
    "customerId": 2,
    "profileType": "passpoint_venue",
    "name": "TIP Lab",
    "details": {
        "model_type": "PasspointVenueProfile",
        "venueNameSet": [
            {
                "model_type": "PasspointVenueName",
                "locale": "fra",
                "dupleIso3Language": "fra",
                "dupleName": "Le TIP Lab c'est Ici",
                "defaultDupleSeparator": ":",
                "venueUrl": null,
                "asDuple": "fra:Le TIP Lab"
            },
            {
                "model_type": "PasspointVenueName",
                "locale": "eng",
                "dupleIso3Language": "eng",
                "dupleName": "TIP Lab",
                "defaultDupleSeparator": ":",
                "venueUrl": null,
                "asDuple": "eng:TIP Lab"
            }
        ],
        "profileType": "passpoint_venue",
        "venueTypeAssignment": {
            "model_type": "PasspointVenueTypeAssignment",
            "venueDescription": "Research and Development Facility",
            "venueGroupId": 7,
            "venueTypeId": 7
        }
    },
    "childProfileIds": []

```



### Passpoint Profile

With all other profile configuration in place, the logical association of these profiles occurs within the Passpoint Profile.

```text
{
    "model_type": "Profile",
    "id": 14,
    "customerId": 2,
    "profileType": "passpoint",
    "name": "test-Passpoint-Profile",
    "details": {
        "model_type": "PasspointProfile",
        "enableInterworkingAndHs20": true,
        "hissed": null,
        "passpointAccessNetworkType": "free_public_network",
        "passpointNetworkAuthenticationType": "acceptance_of_terms_and_conditions",
        "additionalStepsRequiredForAccess": 1,
        "deauthRequestTimeout": 0,
        "operatingClass": 0,
        "termsAndConditionsFile": {
            "model_type": "ManagedFileInfo",
            "md5checksum": null,
            "lastModifiedTimestamp": null,
            "apExportUrl": null,
            "fileCategory": "ExternalPolicyConfiguration",
            "fileType": "TEXT",
            "altSlot": false
        },
        "whitelistDomain": null,
        "emergencyServicesReachable": false,
        "unauthenticatedEmergencyServiceAccessible": false,
        "internetConnectivity": true,
        "connectionCapabilitySet": [
            {
                "model_type": "PasspointConnectionCapability",
                "connectionCapabilitiesPortNumber": 8888,
                "connectionCapabilitiesIpProtocol": "TCP",
                "connectionCapabilitiesStatus": "open"
            }
        ],
        "ipAddressTypeAvailability": "public_IPv4_address_available",
        "qosMapSetConfiguration": null,
        "apGeospatialLocation": null,
        "apCivicLocation": null,
        "apPublicLocationIdUri": null,
        "gasAddr3Behaviour": "p2pSpecWorkaroundFromRequest",
        "anqpDomainId": 5432,
        "disableDownstreamGroupAddressedForwarding": true,
        "enable2pt4GHz": true,
        "enable5GHz": true,
        "associatedAccessSsidProfileIds": [15],
        "osuSsidProfileId": null,
        "passpointOperatorProfileId": 12,
        "passpointVenueProfileId": 13,
        "passpointOsuProviderProfileIds": [
            7,
            11,
	    16
        ],
        "profileType": "passpoint",
        "networkAuthenticationType": "acceptance_of_terms_and_conditions",
        "accessNetworkType": "free_public_network"
    },
    "childProfileIds": [
        7,     // Realm Based Example IDP 
        11,    // MNO Based Example IDP
        12,    // RCOI Based Example / OpenRoaming IDP
        13,    // Venue Profile
	 16    // Wi-Fi Operator Profile
    ]

```



### Passpoint SSID Profile Association 

```text
{
    "model_type": "Profile",
    "id": 15,
    "customerId": 2,
    "profileType": "ssid",
    "name": "passpoint-access-ssid",
    "details": {
        "model_type": "SsidConfiguration",
        "ssid": "OpenRoaming",
        "appliedRadios": [
            "is5GHz",
            "is2dot4GHz"
        ],
        "ssidAdminState": "enabled",
        "secureMode": "wpa2EAP",
        "vlanId": 1,
        "dynamicVlan": "disabled",
        "keyStr": "sdfksfh$%#2f@#$",
        "broadcastSsid": "enabled",
        "keyRefresh": 0,
        "noLocalSubnets": false,
        "radiusServiceId": 3,  // RADIUS Profile
        "radiusAcountingServiceInterval": 60,
        "captivePortalId": null,
        "bandwidthLimitDown": 0,
        "bandwidthLimitUp": 0,
        "clientBandwidthLimitDown": 0,
        "clientBandwidthLimitUp": 0,
        "videoTrafficOnly": false,
        "radioBasedConfigs": {
            "is5GHzU": {
                "model_type": "RadioBasedSsidConfiguration",
                "enable80211r": null,
                "enable80211k": null,
                "enable80211v": null
            },
            "is2dot4GHz": {
                "model_type": "RadioBasedSsidConfiguration",
                "enable80211r": null,
                "enable80211k": null,
                "enable80211v": null
            },
            "is5GHzL": {
                "model_type": "RadioBasedSsidConfiguration",
                "enable80211r": null,
                "enable80211k": null,
                "enable80211v": null
            }
        },
        "bonjourGatewayProfileId": null,
        "enable80211w": null,
        "useRadiusProxy": false,
        "wepConfig": null,
        "forwardMode": "BRIDGE",
        "profileType": "ssid",
        "radiusClientConfiguration": {
            "model_type": "RadiusNasConfiguration",
            "nasClientId": "USER_DEFINED",
            "nasClientIp": "WAN_IP",
            "userDefinedNasId": "FB001AP001",
            "userDefinedNasIp": null,
            "operatorId": "AmeribandTIP"
        }
    },
    "childProfileIds": [
        3,    // RADIUS Profile
        14    // Passpoint Profile
    ]
}
```

{% hint style="info" %}
RADIUS Profile and Passpoint Profile are both Child Profiles of the Access Point Equipment
{% endhint %}

