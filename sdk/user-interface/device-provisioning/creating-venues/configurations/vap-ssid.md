# VAP - SSID

An SSID may be associated to any defined interface. This association ties the dataplane of the VAP together with the underlying interface services.&#x20;

Most common SSID configuration parameters have been exposed via the Provisioning UI. Consult the OpenWiFi data model for the full list of available configurations.&#x20;

From an interface select Add SSID.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 4.54.58 PM.png>)

Assigning the name of the SSID is also the name of the Wi-Fi network itself. Operating band of the SSID is configurable by radio.&#x20;

#### SSID Configuration Options

| Option                    | Description                                                                                                                                                                                                                                                               |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Name                      | SSID name                                                                                                                                                                                                                                                                 |
| BSS-Mode                  | <p>Operating mode of the wireless interface<br>Options: ap, sta, mesh, wds-ap, wds-sta</p>                                                                                                                                                                                |
| WiFi-Bands                | Radio selection(s) of the SSID                                                                                                                                                                                                                                            |
| Authentication Protocol   | <p>Wireless encryption of the BSS<br>Options: None, WPA-PSK, WPA2-PSK, PSK2-RADIUS, WPA-PSK/WPA2-PSK Personal Mixed, WPA-Enterprise, WPA2-Enterprise EAP-TLS, WPA-Enterprise-Mixed, SAE, WPA2/WPA3 Transitional, WPA3-Enterprise EAP-TLS, WPA3-192-Enterprise EAP-TLS</p> |
| Authentication Key        | Pre-Share dKey (when applicable)                                                                                                                                                                                                                                          |
| Authentication IEEE80211w | <p>Management Frame Protection <br>Options: disabled, optional, required</p>                                                                                                                                                                                              |
| Advanced                  |                                                                                                                                                                                                                                                                           |
|      Hidden-SSID          | Disable Beacon Frame Broadcast                                                                                                                                                                                                                                            |
|      Services             | Services associated to the SSID logical interface                                                                                                                                                                                                                         |
|      Maximum-Clients      | Total associations permitted to the SSID                                                                                                                                                                                                                                  |
|      Purpose              | <p>Role the SSID performs<br>Options: Default, Onboarding-AP, Onboarding-sta</p>                                                                                                                                                                                          |
|      Isolate-Clients      | BSS client isolation                                                                                                                                                                                                                                                      |
|      Power-Save           | Unscheduled Automatic Power Save Delivery                                                                                                                                                                                                                                 |
|      Broadcast-Time       | Beacon Time Broadcast                                                                                                                                                                                                                                                     |
|      Unicast-Conversion   | Convert Multicast to Unicast over BSS                                                                                                                                                                                                                                     |
|      Proxy-ARP            | BSS respond to host ARP on behalf of another client                                                                                                                                                                                                                       |
|      Disassoc-Low-Ack     | Disassociate stations based on excessive transmission failures or other indications of connection loss                                                                                                                                                                    |
|      Vendor-Elements      | This option allows embedding custom vendor specific IEs inside the beacons of a BSS in AP mode.                                                                                                                                                                           |
|      Multi-PSK            | Per device shared key to associate with unique VLAN                                                                                                                                                                                                                       |
| Rate Limit                | Ingress-rate and Egress-rate in Mb/s                                                                                                                                                                                                                                      |
| RRM                       | <p>Neighbor reporting<br>LCI measurement element content<br>Civic-Location element content<br>FTM-Responder Fine Timing Measurement<br>Stationary-AP</p>                                                                                                                  |
| Roaming                   | <p>Message-Exchange <br>Generate PSK<br>Domain-Identifier<br>PMK-R0-Key-Holder<br>PMK-R1-Key-Holder</p>                                                                                                                                                                   |



