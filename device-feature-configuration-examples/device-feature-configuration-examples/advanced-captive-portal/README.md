# Advanced Captive Portal

Release 2.7 onwards, OpenWiFi supports a brand new implementation of captive portal leveraging user space application and eBPF based packet filtering. This new implementation allows the APNOS to support functionality previously supported by CoovaChili.

OpenWiFi support two types of captive portal:

* Internal/Local Captive Portal
* External Captive Portal

## Local Captive Portal

The internal captive portal supports the following modes of authentication.

1. **Click-to-continue :** In this mode the client will be redirected to a page where the client needs to accept the terms of service before accessing data.
2. **Credentials:** In this mode the client needs to enter the valid credentials that are configured in the AP to access data.
3. **Radius:** In this mode the client needs to enter the valid credentials that are configured in the radius server being used to access data.

On authentication failures there is further functionality to limit access to the network by providing a wall garden feature. This includes a files of

#### Click-to-continue configuration

First define a captive service as part of the interface -> ssids.

```
"interfaces": [
    {
     :
      "ssids": [
        {
          "name": "OpenWifi-hotspot",
          "services": [
            "captive"
          ],
          "wifi-bands": [
            "5G",
            "2G"
          ],
          "bss-mode": "ap",
          "encryption": {
            "proto": "none",
            "ieee80211w": "optional"
          }
        }
      ]
    }
  ]
```

Then ensure there is a configuration present for the services section of the schema

```
  "services": {
    "captive": {
      "auth-mode": "click-to-continue",
      "walled-garden-fqdn": [
        "*.google.com",
        "telecominfraproject.com"
      ]
    }
  }
```

#### User credentials

After configuring a captive services inside interfaces -> ssids, the services block will look as follows

```
  "services": {
    "ssh": {
      "port": 22
    },
    "captive": {
      "auth-mode": "credentials",
      "credentials": [
        {
          "username": "user1",
          "password": "password1"
        },
        {
          "username": "user2",
          "password": "password2"
        }
      ],
      "walled-garden-fqdn": [
        "*.google.com",
        "telecominfraproject.com"
      ]
    }
  }

```

#### Radius based credentials

After configuring a captive services inside interfaces -> ssids, the services block will look as follows

```
  "services": {
    "ssh": {
      "port": 22
    },
    "captive": {
      "auth-mode": "radius",
      "auth-server": "10.28.3.100",
      "auth-port": 1812,
      "auth-secret": "testing123",
      "walled-garden-fqdn": [
        "*.google.com",
        "telecominfraproject.com"
      ]
    }
  }
```
