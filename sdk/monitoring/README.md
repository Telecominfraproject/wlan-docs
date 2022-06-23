---
description: OpenWiFi 2.0 Telemetry and Analysis
---

# Monitoring

TIP OpenWiFi software stack is envisioned to have a rich telemetry data that can be extracted, transformed and stored for analytics purposes. This section will outline various integration using the current capabilities of the OpenWiFi release. These integrations will provide examples for the community to enrich, adopt and productize.

The current release of OpenWiFi utilizes both a rich open API and Kafka for retrieving telemetry information from Access Points and SDK services. For the purpose of this section and Release 2.0 we will be showcasing Kafka integration with third party monitoring subsystems.

## Kafka Data Source

The current release of 2.0 SDK architecture contains a Kafka broker for the purposes inter-services communication, state, healthcheck, device provisioning state producing and consuming Kafka topics. You can find the latest information related to Kafka topics here: [https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/master/KAFKA.md#kafka-integration](https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/master/KAFKA.md#kafka-integration)

The current Kafka topics used for this monitoring integration are:

* state
* healthcheck

All Kafka messages carry a JSON payload, example of a healthcheck message is as follow:

```
{
   "system":{
      "id":179033843641952,
      "host":"https://gw-ucentral-dev01.cicd.lab.wlan.tip.build:17002"
   },
   "payload":{
      "data":{
         "interfaces":{
            "up0v0":{
               "dhcp":false,
               "location":"/interfaces/0"
            }
         },
         "unit":{
            "memory":36
         }
      },
      "sanity":67,
      "serial":"112233445566",
      "uuid":1627357625
   }
}
```

A state Kafka message looks like:

```
{
   "system":{
      "id":179033843641952,
      "host":"https://gw-ucentral-dev01.cicd.lab.wlan.tip.build:17002"
   },
   "payload":{
      "serial":"112233445566",
      "state":{
         "interfaces":[
            {
               "clients":[
                  {
                     "ipv6_addresses":[
                        "fe80:0:0:0:206:aeff:fee0:69ad"
                     ],
                     "mac":"07:06:06:06:06:06",
                     "ports":[
                        "eth1"
                     ]
                  },
                  {
                     "ipv4_addresses":[
                        "192.168.4.1"
                     ],
                     "mac":"01:02:03:04:05:06",
                     "ports":[
                        "eth1"
                     ]
                  }
               ],
               "counters":{
                  "collisions":0,
                  "multicast":63,
                  "rx_bytes":14725,
                  "rx_dropped":0,
                  "rx_errors":0,
                  "rx_packets":209,
                  "tx_bytes":13571,
                  "tx_dropped":0,
                  "tx_errors":0,
                  "tx_packets":80
               },
               "dns_servers":[
                  "1.1.1.1",
                  "9.9.9.9"
               ],
               "ipv4":{
                  "addresses":[
                     "192.168.4.33/24"
                  ],
                  "leasetime":600
               },
               "location":"/interfaces/0",
               "name":"up0v0",
               "uptime":31349
            },
            {
               "counters":{
                  "collisions":0,
                  "multicast":0,
                  "rx_bytes":0,
                  "rx_dropped":0,
                  "rx_errors":0,
                  "rx_packets":0,
                  "tx_bytes":1058,
                  "tx_dropped":0,
                  "tx_errors":0,
                  "tx_packets":5
               },
               "ipv4":{
                  "addresses":[
                     "192.168.1.1/24"
                  ]
               },
               "location":"/interfaces/1",
               "name":"down1v0",
               "uptime":31355
            }
         ],
         "radios":[
            {
               "active_ms":24459917,
               "busy_ms":1173593,
               "channel":149,
               "channel_width":"80",
               "noise":4294967198,
               "phy":"soc/40000000.pci/pci0000:00/0000:00:00.0/0000:01:00.0",
               "receive_ms":4647,
               "transmit_ms":88272,
               "tx_power":30
            },
            {
               "active_ms":24456321,
               "busy_ms":11878205,
               "channel":11,
               "channel_width":"20",
               "noise":4294967204,
               "phy":"platform/soc/a000000.wifi",
               "receive_ms":1329,
               "transmit_ms":73228,
               "tx_power":30
            },
            {
               "active_ms":24458178,
               "busy_ms":1162312,
               "channel":36,
               "channel_width":"80",
               "noise":4294967192,
               "phy":"platform/soc/a800000.wifi",
               "receive_ms":12339,
               "transmit_ms":86904,
               "tx_power":23
            }
         ],
         "unit":{
            "load":[
               0.190921,
               0.263188,
               0.240726
            ],
            "localtime":1627418941,
            "memory":{
               "free":348540928,
               "total":520409088
            },
            "uptime":31386
         }
      },
      "uuid":1627357625
   }
}
```
