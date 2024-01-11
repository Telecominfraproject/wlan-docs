# External Captive Portal

When an external access controller, such as a captive portal appliance or a Universal Access Method (UAM) redirector is required to handle subscriber login, OpenWiFi now supports ability to have a native implementation that is equivalent of CoovaChili.

As always first define a captive service as part of the interface -> ssids.

The captive service must have the auth-mode set to "uam"

```
"services": {
                "ssh": {
                        "port": 22
                },
                "captive": {
                        "auth-mode": "uam",
                        "uam-port": 3990,
                        "uam-secret": "xxxxxxx",
                        "uam-server": "xxxxxxx",
                        "nasid": "xxxxxxx",
                        "auth-server": "radius.xxxxxxxxx",
                        "auth-port": 1812,
                        "auth-secret": "xxxxxx",
                        "walled-garden-fqdn": [
                                "*.google.com", "telecominfraproject.com", "xxxxxxxxx", "youtube.com"
                        ]
                }
        }


```

For further details on how to configure with a external service please refer to [this](https://telecominfraproject.atlassian.net/browse/WIFI-11190).
