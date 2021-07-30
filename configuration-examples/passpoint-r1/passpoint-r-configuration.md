---
description: OpenWiFi 2.0
---

# Passpoint® Configuration

Ahead of the Provisioning service coming in release 2.1 sprint, it is possible to configure all Passpoint attributes as OpenWiFi has tested in prior OpenWiFi releases. 

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
					"name": "OpenRoaming",
					"wifi-bands": [
						"5G"
					],
					"bss-mode": "ap",
					"encryption": {
						"proto": "wpa-mixed",
						"ieee80211w": "optional"
					},
					"radius": {
						"nas-identifier": "TIPLABAP101",
						"chargeable-user-id": true,
						"authentication": {
							"host": "IP Address of RADIUS",
							"port": 11812,
							"secret": "passphrase",
							"request-attribute": [
								{
									"id": 126,
									"value": "s:TIP"
								}
							]
						},
						"accounting": {
							"host": "IP Address of RADIUS",
							"port": 11813,
							"secret": "passphrase",
							"request-attribute": [
								{
									"id": 126,
									"value": "s:TIP"
								}
							],
							"interval": 600
						}
					},
					"pass-point": {
						"venue-name": [
							"eng:Example passpoint_venue",
							"fra:Exemple de lieu"
						],
						"venue-group": 2,
						"venue-type": 8,
						"venue-url": [
							"http://www.example.com/info-fra",
							"http://www.example.com/info-eng"
						],
						"auth-type": {
							"type": "terms-and-conditions"
						},
						"domain-name": "onboard.example.com",
						"nai-realm": [
							"0,oss.example.com,21[5:7][2:4]"
						],
						"osen": false,
						"anqp-domain": 1234,
						"anqp-3gpp-cell-net": [
							"310,260",
							"310,410"
						],
						"friendly-name": [
							"eng:TIPLabs",
							"fra:TIPLabs"
						],
						"icons": [
							{
								"icon": "iVBORw0KGgoAAAANSUhEUgAAACIAAAAiCAYAAAA6RwvCAAAACXBIWXMAAAsSAAALEgHS3X78AAAEDklEQVRYhc1YTUgUcRR/q7uGUzsuYSClNRcbymS3wII6KNF0Cly7dHSNioIiD3Ppg9IOETHQB50S2vUqhBt1qBZ0pWuQG3VYJJ1SI8h0d4qRsnbjrW+Xv+N87VbYg2H/M/P/v/d732/W499+KA9rTFo64fECLSqBoitCBwDEAGCbxZYxAOjjZDVpxYMXpYIhqiq1BYEYtQGB1I57dEWIOPErG4iuCAKBuM08TgFAFyerHrxwDQCPmPdROmNJ3jIAoFZ9JhZAEB2crGaKDzhZjQNAnM5E6TGetQTjyiK6IsSIoZkbwiwIljhZxXOD9KgdrWklw9EiuiKEAaCbbrMUnKhxCAAynKyqDixuM+cRiOl+UyCEvI+EBRkQ6IJxurfMBJZwv66UDBHRFWHczIKrXEN+nSItgsyrGAOiRLwoPedF6YoVEIM7kGdSV4SQLRCK7KhhT4rqQcwExGMAkACgnxelUxZYUPs7ZFEg5VbxMlqk1wBgNyerIU5WO8ysAQA36XcRAIbMUKAbOFntJTe/L4Ix1hYjkE5mHbYQXiItnXhB67taOmGaOQwgleKuxN8UiMGXKRfZUAmxigXY82zW8EzOT7oRwotS0bwRXpRuOFmFUtdUBuuajRTVeB0sU9sA1QhborQ1lVFx04PlGClGf0xLJ2zjyYlKrjkz0jC/wZcrmG0p55m8L5fFZ5PbjYeHtxZk1HpzkwlGRgnI8Dt/0TVIY/cBrjkx5UXpAS07eVEKubHK67l1JRnAyKjYNRSoPXRbjRWTFyXHOLEiFsgvKmJ4zTqAMFZgPFOHzZAXpYDNUbCSwQJBrYJUgrfYgAhR9wXGInEahILMOysylVGWa0jbOGnfz2QNUoQ0bedFaVUvcSLXQAhEkoajQS2dYMs1UDELU3PrZord3wVCAw6aNKWlEzhXBHRFKMwk8p75q9jEtHRCpXEQwUR5UQo7s3UBBKczFHbiyL4ZqoYpZu6MZH9U4ZQOQxP+BRqQBUrhQhev9eaHRuUdL3VFwPnVNogtgVATHD490tA6NMFv4WtycKHtyz2mnwSeqhve4mLmm4+b/uqDYpnH2DkXWniz+NPjO/qkMTT9zdtpNoO4tYiAzOPLhQ4iOzPZ86H5RuZ98th2reXy3rlXz8Iflpr8S1n2Q+pS29yu9b7c/K88VHc9bpq1m+CdgKhN/iW4vv/z9IHNi1MX277UsYMvCe06G1zQWuu/PzQR9Ch+ZKaG8+YWotLHOqcZ12qKFxoGmjOfTk70HG/J9B1vyaBV+unzoETF7xcLHpHW+u/xyZ537VRjIlSDygKCKZpsGGjupfqwTAOSrXlXUjMYJjLkc6tcIECpOupe8J8RGyPo/+y/EGJBK6a5/+b/EU8+v+Y4AADgN/LdfxH+Qd9IAAAAAElFTkSuQmCC",
								"width": 32,
								"height": 32,
								"type": "image/png",
								"language": "fra"
							},
							{
								"icon": "iVBORw0KGgoAAAANSUhEUgAAACIAAAAiCAYAAAA6RwvCAAAACXBIWXMAAAsSAAALEgHS3X78AAAEDklEQVRYhc1YTUgUcRR/q7uGUzsuYSClNRcbymS3wII6KNF0Cly7dHSNioIiD3Ppg9IOETHQB50S2vUqhBt1qBZ0pWuQG3VYJJ1SI8h0d4qRsnbjrW+Xv+N87VbYg2H/M/P/v/d732/W499+KA9rTFo64fECLSqBoitCBwDEAGCbxZYxAOjjZDVpxYMXpYIhqiq1BYEYtQGB1I57dEWIOPErG4iuCAKBuM08TgFAFyerHrxwDQCPmPdROmNJ3jIAoFZ9JhZAEB2crGaKDzhZjQNAnM5E6TGetQTjyiK6IsSIoZkbwiwIljhZxXOD9KgdrWklw9EiuiKEAaCbbrMUnKhxCAAynKyqDixuM+cRiOl+UyCEvI+EBRkQ6IJxurfMBJZwv66UDBHRFWHczIKrXEN+nSItgsyrGAOiRLwoPedF6YoVEIM7kGdSV4SQLRCK7KhhT4rqQcwExGMAkACgnxelUxZYUPs7ZFEg5VbxMlqk1wBgNyerIU5WO8ysAQA36XcRAIbMUKAbOFntJTe/L4Ix1hYjkE5mHbYQXiItnXhB67taOmGaOQwgleKuxN8UiMGXKRfZUAmxigXY82zW8EzOT7oRwotS0bwRXpRuOFmFUtdUBuuajRTVeB0sU9sA1QhborQ1lVFx04PlGClGf0xLJ2zjyYlKrjkz0jC/wZcrmG0p55m8L5fFZ5PbjYeHtxZk1HpzkwlGRgnI8Dt/0TVIY/cBrjkx5UXpAS07eVEKubHK67l1JRnAyKjYNRSoPXRbjRWTFyXHOLEiFsgvKmJ4zTqAMFZgPFOHzZAXpYDNUbCSwQJBrYJUgrfYgAhR9wXGInEahILMOysylVGWa0jbOGnfz2QNUoQ0bedFaVUvcSLXQAhEkoajQS2dYMs1UDELU3PrZord3wVCAw6aNKWlEzhXBHRFKMwk8p75q9jEtHRCpXEQwUR5UQo7s3UBBKczFHbiyL4ZqoYpZu6MZH9U4ZQOQxP+BRqQBUrhQhev9eaHRuUdL3VFwPnVNogtgVATHD490tA6NMFv4WtycKHtyz2mnwSeqhve4mLmm4+b/uqDYpnH2DkXWniz+NPjO/qkMTT9zdtpNoO4tYiAzOPLhQ4iOzPZ86H5RuZ98th2reXy3rlXz8Iflpr8S1n2Q+pS29yu9b7c/K88VHc9bpq1m+CdgKhN/iW4vv/z9IHNi1MX277UsYMvCe06G1zQWuu/PzQR9Ch+ZKaG8+YWotLHOqcZ12qKFxoGmjOfTk70HG/J9B1vyaBV+unzoETF7xcLHpHW+u/xyZ537VRjIlSDygKCKZpsGGjupfqwTAOSrXlXUjMYJjLkc6tcIECpOupe8J8RGyPo/+y/EGJBK6a5/+b/EU8+v+Y4AADgN/LdfxH+Qd9IAAAAAElFTkSuQmCC",
								"width": 32,
								"height": 32,
								"type": "image/png",
								"language": "eng"
							}
						]
					}
				}
			]
		},
```

