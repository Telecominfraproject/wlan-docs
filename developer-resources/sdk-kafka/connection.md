# Connection

Here are the current messages related to connection topic:

## Ping Message

```json
{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "ping": {
      "compatible": "cig_wf194c4",
      "connectionIp": "f40b9fe78d3d@10.10.10.48:35510",
      "firmware": "OpenWrt 21.02-SNAPSHOT r16399+136-c67509efd7 / TIP-v2.6.0-rc4-eebe021",
      "locale": "US",
      "serialNumber": "f40b9fe78d3d",
      "timestamp": 1656513408
    }
  }
}
```

## Capability Message

```json
{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "capabilities": {
      "compatible": "cig_wf196",
      "label_macaddr": "82:4f:81:60:11:e4",
      "macaddr": {
        "lan": "82:4f:81:60:11:e5",
        "wan": "82:4f:81:60:11:e4"
      },
      "model": "CIG WF196",
      "network": {
        "lan": [
          "eth1"
        ],
        "wan": [
          "eth0"
        ]
      },
      "platform": "ap",
      "switch": {
        "switch0": {
          "enable": false,
          "reset": false
        }
      },
      "wifi": {
        "platform/soc/c000000.wifi1": {
          "band": [
            "5G"
          ],
          "channels": [
            36,
            40,
            44,
            48,
            52,
            56,
            60,
            64,
            100,
            104,
            108,
            112,
            116,
            120,
            124,
            128,
            132,
            136,
            140,
            144,
            149,
            153,
            157,
            161,
            165
          ],
          "dfs_channels": [
            52,
            56,
            60,
            64,
            100,
            104,
            108,
            112,
            116,
            120,
            124,
            128,
            132,
            136,
            140,
            144
          ],
          "frequencies": [
            5180,
            5200,
            5220,
            5240,
            5260,
            5280,
            5300,
            5320,
            5500,
            5520,
            5540,
            5560,
            5580,
            5600,
            5620,
            5640,
            5660,
            5680,
            5700,
            5720,
            5745,
            5765,
            5785,
            5805,
            5825
          ],
          "he_mac_capa": [
            13,
            39448,
            4160
          ],
          "he_phy_capa": [
            24604,
            34892,
            56191,
            40067,
            3073,
            0
          ],
          "ht_capa": 6639,
          "htmode": [
            "HT20",
            "HT40",
            "VHT20",
            "VHT40",
            "VHT80",
            "VHT80+80",
            "VHT160",
            "HE20",
            "HE40",
            "HE80",
            "HE160",
            "HE80+80"
          ],
          "rx_ant": 240,
          "tx_ant": 240,
          "vht_capa": 1939601914
        },
        "platform/soc/c000000.wifi1+1": {
          "band": [
            "2G"
          ],
          "channels": [
            1,
            2,
            3,
            4,
            5,
            6,
            7,
            8,
            9,
            10,
            11
          ],
          "frequencies": [
            2412,
            2417,
            2422,
            2427,
            2432,
            2437,
            2442,
            2447,
            2452,
            2457,
            2462
          ],
          "he_mac_capa": [
            13,
            39448,
            4160
          ],
          "he_phy_capa": [
            24578,
            34892,
            50047,
            40067,
            3073,
            0
          ],
          "ht_capa": 6639,
          "htmode": [
            "HT20",
            "HT40",
            "VHT20",
            "VHT40",
            "VHT80",
            "HE20",
            "HE40"
          ],
          "rx_ant": 15,
          "tx_ant": 15,
          "vht_capa": 1939569042
        },
        "soc/20000000.pci/pci0000:00/0000:00:00.0/0000:01:00.0": {
          "band": [
            "6G"
          ],
          "channels": [
            1,
            5,
            9,
            13,
            17,
            21,
            25,
            29,
            33,
            37,
            41,
            45,
            49,
            53,
            57,
            61,
            65,
            69,
            73,
            77,
            81,
            85,
            89,
            93,
            97,
            101,
            105,
            109,
            113,
            117,
            121,
            125,
            129,
            133,
            137,
            141,
            145,
            149,
            153,
            157,
            161,
            165,
            169,
            173,
            177,
            181,
            185,
            189,
            193,
            197,
            201,
            205,
            209,
            213,
            217,
            221,
            225,
            229,
            233
          ],
          "frequencies": [
            5955,
            5975,
            5995,
            6015,
            6035,
            6055,
            6075,
            6095,
            6115,
            6135,
            6155,
            6175,
            6195,
            6215,
            6235,
            6255,
            6275,
            6295,
            6315,
            6335,
            6355,
            6375,
            6395,
            6415,
            6435,
            6455,
            6475,
            6495,
            6515,
            6535,
            6555,
            6575,
            6595,
            6615,
            6635,
            6655,
            6675,
            6695,
            6715,
            6735,
            6755,
            6775,
            6795,
            6815,
            6835,
            6855,
            6875,
            6895,
            6915,
            6935,
            6955,
            6975,
            6995,
            7015,
            7035,
            7055,
            7075,
            7095,
            7115
          ],
          "he_mac_capa": [
            13,
            39448,
            4160
          ],
          "he_phy_capa": [
            24604,
            34892,
            56319,
            40067,
            3089,
            0
          ],
          "htmode": [
            "HE20",
            "HE40",
            "HE80",
            "HE160",
            "HE80+80"
          ],
          "rx_ant": 15,
          "tx_ant": 15
        }
      }
    },
    "connectionIp": "824f816011e4@10.10.11.185:50412",
    "firmware": "OpenWrt 21.02-SNAPSHOT r16399+136-c67509efd7 / TIP-v2.6.0-rc4-eebe021",
    "locale": "US",
    "serial": "824f816011e4",
    "timestamp": 1656516572,
    "uuid": 1
  }
}
```

## Disconnection Message

```json
{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "disconnection": {
      "serialNumber": "824f816011e4",
      "timestamp": 1656516851
    }
  }
}
```
