# Dynamic Multi PSK

When venue authentication will support client mobility it is desirable to not cause re-authentication from one AP to another.

As with the Multi PSK feature that locally provides this functionality to enable a subscriber to have a subscriber based PSK when authenticated creates a private network, this functionality may also be handled via RADIUS to support large venue topologies.&#x20;

The authentication protocol type is `psk2-radius` . Add the RADIUS system appropriate for the network.&#x20;

&#x20;

```json
	"ssids": [
		{
			"name": "OpenWifi",
			"wifi-bands": [
				"2G"
			],
			"bss-mode": "ap",
			"encryption": {
				"proto": "psk2-radius",
				"ieee80211w": "optional"
			},
			"radius": {
				"authentication": {
					"host": "192.168.50.30",
					"port": 1812,
					"secret": "secret"
				},
				"accounting": {
					"host": "192.168.50.30",
					"port": 1813,
					"secret": "secret"
				}
			}
		}
	]

```
