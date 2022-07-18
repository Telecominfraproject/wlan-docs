---
description: TIP OpenWiFi 2.0
---

# Passpoint® Configuration

It is possible to configure all Passpoint attributes required for production deployment.

Capabilities for Hotspot 2.0 / Passpoint® include:

* venue-name
* venue-group
* venue-type
* venue-url
* auth-type
* domain-name
* nai-realm
* osen
* anqp-domain
* anqp-3gpp-cell-net
* firendly-name
* icons

#### Example Passpoint Configuration

```
    	"interfaces": [{
			
			"ssids": [{
				"name": "Mobile Offload",
				"wifi-bands": [
					"5G"
				],
				"bss-mode": "ap",
				"encryption": {
					"proto": "wpa-mixed",
					"ieee80211w": "optional"
				},
                "services": [
                    "radius-proxy"
                ],
				"radius": {
					"nas-identifier": "NAS-Lab",
					"chargeable-user-id": true,
					"authentication": {
						"host": "127.0.0.1",
						"port": 1812,
						"secret": "secret",
						"request-attribute": [{
							"id": 126,
							"value": "s:TIP"
						}]
					},
					"accounting": {
						"host": "127.0.0.1",
						"port": 1813,
						"secret": "secret",
						"request-attribute": [{
							"id": 126,
							"value": "s:TIP"
						}],
						"interval": 600
					}
				},
				"pass-point": {
					"venue-name": [
						"eng:Example passpoint_venue",
						"fra:Exemple de lieu"
					],
					"domain-name": [
                        "operator.com"
                    ],
					"asra": false,
					"internet": true,
					"esr": false,
					"uesa": false,
					"access-network-type": 0,
					"hessid":"11:22:33:44:55:66",
					"venue-group": 2,
					"venue-type": 8,
					"connection-capability":[
						"1:0:2",
						"6:22:1",
						"17:5060:0"
					],
					"roaming-consortium": [
                        			"A4F5E8F5F4",
						"BAA2D00100",
						"CAA2D00000",
						"DA03BA0000"
					],
					"disable-dgaf": true,
					"anqp-domain": 8888,
					"ipaddr-type-available": 14,
					"nai-realm": [
						"0,ooperator.com,21[5:7][2:4],13[5:-1]",
                        "0,boingo.com,21[5:7][2:4],13[5:-1]"
					],
					"osen": false,
					"anqp-3gpp-cell-net": [
						"310,410"
					],
					"friendly-name": [
						"eng:Operator Labs",
						"fra:Operator Labs"
					],
					"venue-url": [
						"http://www.example.com/info-fra",
						"http://www.example.com/info-eng"
					],
					"auth-type": {
						"type": "terms-and-conditions"
					}
				}
			}]
		},
		
"services": {

        "radius-proxy":{
            "realms":[
                {
                    "protocol": "radsec",
                    "realm": ["*.mobile.operator.com"],
                    "host": "ipv4 address",
                    "port": 2083,
                    "auto-discover": false,
                    "secret": "radsec",
                    "use-local-certificates": false,
                    "ca-certificate": "AAAAABBBBBCCCCDDDEEEEEEFFFFNPZ0F3SUJBZ0lKQUxIQmJFWmU3QTBzTUEwR0NTcUdTSWIzRFFFQkN3VUFNSUdvTVFzd0NRWUQKVlFRR0V3SlZVekVUTUJFR0ExVUVDQXdLUTJGc2FXWnZjbTVwWVRFUk1BOEdBMVVFQnd3SVUyRnVJRXB2YzJVeApIREFhQmdOVkJBb01FME5wYzJOdklGTjVjM1JsYlhNc0lFbHVZeTR4RkRBU0JnTlZCQXNNQzA5d1pXNXliMkZ0CmFXNW5NUmd3RmdZRFZRUUREQTl2Y0dWdWNtOWhiV2x1Wnk1dmNtY3hJekFoQmdrcWhraUc5dzBCQ1FFV0ZHVnUKWWkxa1pYWnZjSE5BWTJselkyOHVZMjl0TUI0WERURTVNRGt4TmpFeU1EYzFPVm9YRFRNNU1Ea3hNVEV5TURjMQpPVm93Z2FneEN6QUpCZ05WQkFZVEFsVlRNUk13RVFZRFZRUUlEQXBEWVd4cFptOXlibWxoTVJFd0R3WURWUVFICkRBaFRZVzRnU205elpURWNNQm9HQTFVRUNnd1RRMmx6WTI4Z1UzbHpkR1Z0Y3l3Z1NXNWpMakVVTUJJR0ExVUUKQ3d3TFQzQmxibkp2WVcxcGJtY3hHREFXQmdOVkJBTU1EMjl3Wlc1eWIyRnRhVzVuTG05eVp6RWpNQ0VHQ1NxRwpTSWIzRFFFSkFSWVVaVzVpTFdSbGRtOXdjMEJqYVhOamJ5NWpiMjB3Z2dJaU1BMEdDU3FHU0liM0RRRUJBUVVBCkE0SUNEd0F3Z2dJS0FvSUNBUUMwSmM0V3d2QlJJa3BsU0pmdVdZaWo1TTZ2WkRtYVpRNk82YjhGRjBNRVdhZ3UKRFZpVkpRM0JVZ1oyUUtET25JcktNZUlmS3ZWUzRNRWJMM3U0OHgveUtqb09IRkQ0aUhRRTdBUFBvd1BvZkVTcwp4emZveGkwYnozQ3FvK3pXRzVESVJ5V3krNFNDRGlsc2xBN25XU1l5TTdGeUZGWUxvWHdEZVY1N1MzNnJqN3hGClpXdjJ3NjI3dkNPUjJKM2RiYkRLR0ZneEZSVHhMK3I0SWlIWGN5Mm8zaUlwK3R3bDBablJydzBEME5aUmxwNzkKZ2VCS2E5VHZ1MUQxMDcxVWRDQjlaK3VZMFBrNEVaN1dlWVNjWjJhdkxtQjl3cVpkU1F0U2pTQ0xqNVlTOTZzTwpodmlOTWxDb1pNbDBkUE14T2RCb3JZOE52L1VodWk3WDBseUpjKytYaVVuVCs2c05KTXJUeWQ1bCt5OTBmZ0RrCmVqUTNhcWZsTDdRTy9SWjRGejhpL3dCQTRmTWR5TDkvYThqUzBiYWZlc01PZFFDUEd4TThNYXF3QUhZOUN0Z1cKWFFuWi9CT3l3bTArY1gxMkwyd3R3SGFjZ1F6bUROZ2R3NU5PdUdIVEdFcTBpUFVITFBrUXZWc1VTRTBpSUxmZgpXWkhpN2RhOHlsZi9WVktDVjN3U3pKdjc4NXB1c0Z6QVNxbHpLZnErYUs5T1A4bVhyS1dibFZCWHR0aE5mSWJ1CmcvaXNoWW4rYXIrcnlEdmRvL05vL202QjhCemNqVzRWWlIxQkszZUd1R3k2MkhxbTdHMkdZS1FpbkhzdElTYWsKeFFMK3IxOW1HcEhkbzdXcWgyd3ZVZmd6MXN4QjZxOVRhaWZoS21nbEJiSnV1dHpQRFViRHRqWHVlbGcvS1FJRApBUUFCbzJZd1pEQWRCZ05WSFE0RUZnUVVER1Z5QWU4THpNSjR0NVRuRVplVUpXeGVGcE13SHdZRFZSMGpCQmd3CkZvQVVER1Z5QWU4THpNSjR0NVRuRVplVUpXeGVGcE13RWdZRFZSMFRBUUgvQkFnd0JnRUIvd0lCQXpBT0JnTlYKSFE4QkFmOEVCQU1DQVlZd0RRWUpLb1pJaHZjTkFRRUxCUUFEZ2dJQkFGcnlOZldoU2J4RitYS3Nhd29MT2l0bgpDd2ZkTUNrQUJvMWlvWFhyclB1M0xzYm9keXBEdUIwQ2NHdEI1WlZiQ1pSWXBTVFNWMjcramdhRVZlMG1zSk9vCjRoNVBYdnM0QklseTJ6RE1yaE9rTmIxSXN0Y1kyNFdtbGJRYUlBTGcwUW4zQXJTWStITUtUMjhoWjR6bVM3N3QKKzg3d0FYNmlBaGF5QktLWHhJQnQ4VEVTL0hXU0RWczl1RFY4ZjRNTzI0TGozQXBhQkpaV2dFcFpXYi9LdkRmSQp4ckJUK1loL2xTSWpvWGNvZHdNT2dMeTcrLzJrQjZQcXJtWktMcnFWZ3Byd3VXNDJVYVh4YkpYQnFvdmVURkxiCnhXaHA5T1kzbWxnTy9IbWthdS8rUnNLelJzYnJJWGZqRzRDT1ViOHh1ajV1WmZkQ2FYRVlWNnZwdnUwN0NTVEgKZk51VnlZYlMxampLZHRoWE9JQ2YvN3N4YTdiVlpOTkNOQWFwK21FcldPNXQxTEhXdi9ZL0ZYYk5TTVdadlozVApPM0RYc0p5K3grU1piZ283OWhzUktxeDFDSjQybktBaGM2WFZZUkRTOGs0SHZVSzBxbnpTaExvMm5MYTFCVUVMCkkzVnkybDVVMkMxMUYvTDRhNE1Pb2R0Z3h4L0Q5VjI0cWZnTVRPY3Q4bS9QRFB6b1ovL2NoTUpQUU5pWHV5SUEKWmlOUWRxRngrYWI2N1ErM3kwcGxKRDVjVk81Z01MN0F5dXZuMDJlalRhWFYrUkQxVmpoSkRCM0l1Y0FHUnIxLwpVTVVNbmlTZSt4S2FaVHA5SGtza0x2K051ZjV1Slc2VXVHZ0RIbUFCYUFEWUdTMGhKTFU2MjMxMTE3OWh4Q3NmCmVMNXJQdlVtMitRZWhDWURBUjR1Ci0tLS0tRU5EIENFUlRJRklDQVRFLS0tLS0=",
                    "certificate":"AAAAABBBBBCCCCDDDEEEEEEFFFFS0tCk1JSUNHVENDQWNDZ0F3SUJBZ0lVUjEwVFR5NThxNVF2d1VlVEVsWnZRNE1tYzYwd0NnWUlLb1pJemowRUF3SXcKUVRFTE1Ba0dBMVVFQmhNQ1ZWTXhFekFSQmdOVkJBb1RDa0oxZEhSdmJuZHZiMlF4SFRBYkJnTlZCQU1URkVKMQpkSFJ2Ym5kdmIyUWdVbUZrYzJWaklFTkJNQjRYRFRJeE1EY3hNVEUyTXpNeE5Wb1hEVEl6TURjeE1URTJNek14Ck5Wb3dZakVMTUFrR0ExVUVCaE1DVlZNeEV6QVJCZ05WQkFvVENrSjFkSFJ2Ym5kdmIyUXhJekFoQmdOVkJBTVQKR21aaFkyVmliMjlyTG05eWFXOXVMbUZ5WldFeE1qQXVZMjl0TVJrd0Z3WUtDWkltaVpQeUxHUUJBUk1KUjI5dgpaMnhsT2xWVE1Ga3dFd1lIS29aSXpqMENBUVlJS29aSXpqMERBUWNEUWdBRTAvdXpKQ1FZVU1uTXpjMHFzaXBYClZreXkzdkdIM0hOZWxJQnkzTzFGaVMrdVVBa1NUS0VUSHduK1Nza3N1WjIzZnV0bWJzcEQ4bXZQUkI3bXlwZ24KZDZOMU1ITXdEZ1lEVlIwUEFRSC9CQVFEQWdlQU1CTUdBMVVkSlFRTU1Bb0dDQ3NHQVFVRkJ3TUNNQXdHQTFVZApFd0VCL3dRQ01BQXdKUVlEVlIwUkJCNHdISUlhWm1GalpXSnZiMnN1YjNKcGIyNHVZWEpsWVRFeU1DNWpiMjB3CkZ3WURWUjBnQkJBd0RqQU1CZ29yQmdFRUFlNHFBUUVGTUFvR0NDcUdTTTQ5QkFNQ0EwY0FNRVFDSUVKZ00yenoKUXJiR3NZMWticmNOZ1p2QTdBbE02WTllS3d6VWZHSzNGN2d3QWlBbDFmNlVBSGMxVlFmNUgwUVlRbjh4QW1WWAp6azJIQmI3MHMxQjEwN2NKY3c9PQotLS0tLUVORCBDRVJUSUZJQ0FURS0tLS0t",
                    "private-key":"AAAAABBBBBCCCCDDDEEEEEEFFFF0tLS0tCk1IY0NBUUVFSUg0cXVHblBndUIxckk1TnlXejc3ejBvOXRUOGhxN1dBbXVrcFRXa3J2cHdvQW9HQ0NxR1NNNDkKQXdFSG9VUURRZ0FFMC91ekpDUVlVTW5NemMwcXNpcFhWa3l5M3ZHSDNITmVsSUJ5M08xRmlTK3VVQWtTVEtFVApId24rU3Nrc3VaMjNmdXRtYnNwRDhtdlBSQjdteXBnbmR3PT0KLS0tLS1FTkQgRUMgUFJJVkFURSBLRVktLS0tLQ=="
                },
                {
                    "protocol": "radius",
                    "realm": ["*.3gppnetwork.org"],
                    "auth-server": "ipv4 address",
                    "auth-port": 11812,
                    "auth-secret": "secret",
                    "acct-server": "ipv4 address",
                    "acct-port": 11813,
                    "acct-secret": "secret"
                },
                {
                    "protocol": "radius",
                    "realm": ["operator.com"],
                    "auth-server": "ipv4 address",
                    "auth-port": 1812,
                    "auth-secret": "secret",
                    "acct-server": "ipv4 address",
                    "acct-port": 1813,
                    "acct-secret": "secret"
                },
                {
                    "protocol": "block",
                    "realm": ["*"],
                    "message": "realm-not-allowed"
                }
            ]
        }
	}
```

The above configuration example mobile offload has been configured for two realms that will both have radius traffic sent as radius-proxy via the OpenWiFi Gateway to enable cloud native AAA support for any customer premises topology services are operating from.&#x20;

