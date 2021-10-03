---
description: TIP OpenWiFi 2.0
---

# RADIUS Authenticated SSID

When authenticating clients with back office RADIUS systems, the configuration of OpenWiFi permits this on a per SSID basis.

{% tabs %}
{% tab title="Simple RADIUS" %}
```text
    "interfaces": [
        {
            "name": "WAN",
            "role": "upstream",
            "ethernet": [
                {
                    "select-ports": [
                        "WAN*"
                    ]
                }
            ],
            "ipv4": {
                "addressing": "dynamic"
            },
            "ssids": [
                {
                    "name": "OpenWifi",
                    "wifi-bands": [
                        "5G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "wpa2",
                        "ieee80211w": "optional"
                    },
                    "radius": {
                        "authentication": {
                            "host": "192.168.178.192",
                            "port": 1812,
                            "secret": "secret"
                        },
                        "accounting": {
                            "host": "192.168.178.192",
                            "port": 1813,
                            "secret": "secret"
                        }
                    }
                }
            ]
        },
```
{% endtab %}

{% tab title="EAP-Local SSID" %}
```text
            "ssids": [
                {
                    "name": "OpenWifi",
                    "wifi-bands": [
                        "2G"
                    ],
                    "bss-mode": "ap",
                    "encryption": {
                        "proto": "wpa2",
                        "ieee80211w": "optional"
                    },
                    "certificates": {
                        "ca-certificate": "/etc/ucentral/cas.pem",
                        "certificate": "/etc/ucentral/cert.pem",
                        "private-key": "/etc/ucentral/key.pem"
                    },
                    "radius": {
                        "local": {
                            "server-identity": "OpenWiFi-Local-EAP",
                            "users": [
                                {
                                    "user-name": "open",
                                    "password": "wifi"
                                }
                            ]
                        }
                    }
                }
            ]
        },
```
{% endtab %}
{% endtabs %}

Many parameters are possible with RADIUS authentications given the many methods in use worldwide. Many of the EAP methods have configuration options described below.

<table>
  <thead>
    <tr>
      <th style="text-align:left">RADIUS Attribute</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">nas-identifier</td>
      <td style="text-align:left">Unique NAS Id used with RADIUS server</td>
    </tr>
    <tr>
      <td style="text-align:left">chargeable-user-id</td>
      <td style="text-align:left">Chargeable User Entity per RFC4372</td>
    </tr>
    <tr>
      <td style="text-align:left">local</td>
      <td style="text-align:left">
        <p>Local RADIUS within AP device</p>
        <ul>
          <li>server-identity
            <ul>
              <li>users - Local EAP users based on username, PreShared Key and VLAN id</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">authentication</td>
      <td style="text-align:left">
        <p>RADIUS server</p>
        <ul>
          <li>host IP address</li>
          <li>port ( example 1812)</li>
          <li>secret ( Shared secret with RADIUS server )</li>
        </ul>
        <p>Additional methods within Access-Request</p>
        <ul>
          <li>request-attribute ( id of RADIUS server )
            <ul>
              <li>id ( numeric value of RADIUS server )</li>
              <li>
                <p>value</p>
                <p>Any sub-value defined as integer RADIUS attribute value</p>
              </li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">accounting</td>
      <td style="text-align:left">
        <p>RADIUS server</p>
        <ul>
          <li>host IP address</li>
          <li>port ( example 1813)</li>
          <li>secret ( Shared secret with RADIUS server )</li>
        </ul>
        <p>Additional methods within Access-Request sent in Accounting</p>
        <ul>
          <li>request-attribute ( id of RADIUS server )
            <ul>
              <li>id ( numeric value of RADIUS server )</li>
              <li>
                <p>value</p>
                <p>Any sub-value defined as integer RADIUS attribute value</p>
              </li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">accounting</td>
      <td style="text-align:left">interval ( Interim accounting interval defined in seconds )</td>
    </tr>
  </tbody>
</table>

