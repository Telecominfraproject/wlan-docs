---
description: OpenWiFi 2.0
---

# Roaming RRM and SON

Radio Resource Management and Self Organizing Network features in OpenWiFi 2.0 operate by default in local mode from the Access Point device without dependency on the cloud. Data and state related to client steering and roaming is also possible in co-operation with the cloud when so configured.

 Metrics and telemetry are sent to the cloud as desired based on configuration however operation of 802.11k/v/r behavior and autonomous channel control are built in features of all OpenWiFi 2.0 Access Points. 

### Steering

 OpenWiFi services feature "wifi-steering" determines the operating parameters of RRM on the Access Point. 

```text
	"services": {
      "wifi-steering": {
			"mode": "local",
			"network": "upstream",
			"assoc-steering": true,
			"required-snr": -75,
			"required-probe-snr": -70,
			"required-roam-snr": -85,
			"load-kick-threshold": 90
		},  
```

When mode is set to local, the Access Point handles steering decisions autonomously with the surrounding OpenWifi devices.   
Which network association, in this case "upstream" will steering be operating on. Note in prior examples most service provider, venue, enterprise services operate on the WAN side upstream network of the Access Point. 

| Parameter | Value |
| :--- | :--- |
| mode: local | autonomous operation |
| network: upstream | performs roaming among SSIDs on upstream interfaces |
| assoc-steering | reject client association requests when the UE is subject to a steering event |
| required-snr | minimum signal in dBm a client will be permitted to remain connected |
| required-probe-snr | minimum signal level in dBm for management probes to be replied to |
| required-roam-snr | minimum signal level in dBm client roaming threshold |
| load-kick-threshold | minimum channel load as % available before clients are kicked |

### Apply Wi-Fi Steering to enable 802.11r Fast Roaming SSIDs

```text
			"ssids": [
				{
					"name": "OpenWiFi Roaming",
					"wifi-bands": [
						"2G", "5G"
					],
           "bss-mode": "ap",
           "encryption": {
                "proto": "psk2",
                "key": "OpenWiFi",
                "ieee80211w": "optional"
                 },                   
					"roaming": {
						"message-exchange": "air",
						"generate-psk": true,
						"domain-identifier": "EFAB"
					},
					"services": [ "wifi-steering" ]
                }
			]
		},
```

Each SSID to participate in roaming must have "services" : \[ "wifi-steering" \] associated. 

Additional fast roaming configuration is possible including setting message-exchange either to "air" or "ds" to determine pre authenticated message exchange occurs over the air or distribution system. 

  
The generate-psk option generates FT response locally for PSK networks. This avoids use of PMK-R1 push/pull from other APs with FT-PSK networks.  


Configuring domain-identifier sets Mobility Domain identifier \(dot11FTMobilityDomainID, MDID\) permitting segmentation of fast roaming RF topologies.  


When pmk-r0-key-holder and pmk-r1-key-holder are left un-configured, the pairwise master key R0 and R1 will generate a deterministic key automatically for fast mobility domain exchange over the air. 

### RRM 802.11k 

To enable 80211k parameters, associate these on a participating SSID basis.

```text
			"ssids": [
				{
					"name": "OpenWiFi Roaming",
					"wifi-bands": [
						"2G", "5G"
					],
           "bss-mode": "ap",
           "encryption": {
                "proto": "psk2",
                "key": "OpenWiFi",
                "ieee80211w": "optional"
                 },                   
					"roaming": {
						"message-exchange": "air",
						"generate-psk": true,
						"domain-identifier": "EFAB"
					},
					"rrm": {
						"neighbor-reporting": true,
						"ftm-responder": true, 
						"stationary-ap": true
					},
					"services": [ "wifi-steering" ]
                }
			]
		},
```

In addition to 802.11k features for neighbor reporting, fine timing measurement responder and stationary ap indication, OpenWiFi also supports LCI measurement, Civic Location subelement as well. 

### Automatic Channel Balancing

As part of "wifi-steering" feature, autonomous channel management algorithm may be enabled to establish a self organizing Wi-Fi network. 

The auto-channel setting operates in co-ordination with other OpenWiFi Access Points by enumerating the newest AP in the network, then running neighbor and RF scans to determine the best channel of operation. Once the newest AP completes this process, the next AP is sequence will run the same algorithm for channel balancing until all APs in the network complete. The entire process may take up to 5 minutes the first time a network is powered on. The algorithm will re-run every 12 hours. 

```text
	"services": {
      "wifi-steering": {
			"mode": "local",
			"network": "upstream",
			"auto-channel": true,
			"assoc-steering": true,
			"required-snr": -75,
			"required-probe-snr": -70,
			"required-roam-snr": -85,
			"load-kick-threshold": 90
		},  
```

