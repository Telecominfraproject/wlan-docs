# Metrics Settings Example

A common example is to inherit the desired telemetry for all devices spanning all types, at a top level.

It remains possible to override the values shown here, perhaps to a faster interval, for the required telemetry data defined at the top level.

### Create Configuration

Create a general configuration, select Metrics as the Configuration Section.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.07.24 PM.png>)

Within the Subsections select all metrics types to be included and a weight for this template.

Available metrics:

| Metric        | Description                                                                                                                                                               |
| ------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| WiFi Frames   | Select Management Frame reports to send. Values include: Probe, Auth, Assoc, DeAuth, Disassoc, Local-Deauth, Inactive-Deauth, Key-Mismatch, Beacon-Report, Radar-Detected |
| Statistics    | Set Interval of all Statistics and types including: SSID, LLDP, Clients                                                                                                   |
| DHCP Snooping | Select the DHCP & DHCPv6 frames to send in telemetry including: ACK, DISCOVER, OFFER, REQUEST, REPLY, RENEW, SOLICIT                                                      |
| Health        | Interval to send automated health check score                                                                                                                             |
