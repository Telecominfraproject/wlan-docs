# WiFi Scan

## Scan Results

```json
{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "serial": "903cb39d6918",
    "status": {
      "error": 0,
      "resultCode": 1,
      "scan": [
        {
          "bssid": "00:06:ae:6f:6f:f6",
          "capability": 305,
          "channel": 52,
          "frequency": 5260,
          "ht_oper": "NAUAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
          "ies": [
            {
              "content": [
                "6(B)",
                "9",
                "12(B)",
                "18",
                "24(B)",
                "36",
                "48",
                "54"
              ],
              "name": "Supported Rates (Mbps)",
              "type": 1
            },
            {
              "content": {
                "current_channel": 52
              },
              "name": "DS Params",
              "type": 3
            },
            {
              "content": {
                "Bitmap control": {
                  "Bitmap Offset": 0,
                  "Multicast": 0,
                  "Partial Virtual Bitmap": "00"
                },
                "DTIM count": 0,
                "DTIM period": 2
              },
              "name": "Traffic Indication Map (TIM)",
              "type": 5
            },
            {
              "content": {
                "Code": "CA",
                "Environment": "Any",
                "constraints": [
                  {
                    "Country Info": {
                      "First Channel Number": 36,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 8
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 100,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 5
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 132,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 4
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 149,
                      "Maximum Transmit Power Level (in dBm)": 30,
                      "Number of Channels": 5
                    }
                  }
                ]
              },
              "name": "country",
              "type": 7
            },
            {
              "content": {
                "Local Power Constraint": 3
              },
              "name": "Local Power Constraint",
              "type": 32
            },
            {
              "content": {
                "802.11e CCA Version": {
                  "Available Admission Capabilities": 0,
                  "Channel Utilization": 0,
                  "QBSS Version": 2,
                  "Station Count": 3
                }
              },
              "name": "QBSS Load",
              "type": 11
            },
            {
              "content": {
                "Alternate Regulatory Classes": "0",
                "Current Regulatory Class": 128
              },
              "name": "Supported Regulatory Classes",
              "type": 59
            },
            {
              "content": {
                "A-MPDU Parameters": {
                  "MPDU Density": 0,
                  "Maximum Rx A-MPDU Length": 3
                },
                "Antenna Selection (ASEL) Capabilities": {
                  "Antenna Indices Feedback": 0,
                  "Antenna Indices Feedback Based Tx ASEL": 0,
                  "Antenna Selection Capable": 0,
                  "Antenna Selection Capable TXCSI": 0,
                  "Explicit CSI Feedback": 0,
                  "Rx ASEL": 0,
                  "Tx Sounding PPDUs": 0
                },
                "HT Capabilities Info": {
                  "HT Delayed Block ACK": true,
                  "HT Forty MHz Intolerant": false,
                  "HT Green Field": 12,
                  "HT L-SIG TXOP Protection support": false,
                  "HT LDPC coding capability": true,
                  "HT Max A-MSDU length": false,
                  "HT PSMP Support": false,
                  "HT Rx STBC": 1,
                  "HT Short GI for 20MHz": true,
                  "HT Short GI for 40MHz": true,
                  "HT Support channel width": true,
                  "HT Tx STBC": true
                },
                "HT Extended Capabilities": {
                  "High Throughput": 0,
                  "MCS Feedback capability": 0,
                  "Reverse Direction Responder": 0,
                  "Time needed to transition between 20MHz and 40MHz": 0,
                  "Transmitter supports PCO": 0
                },
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111111",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "Transmit Beam Forming (TxBF) Capabilities": {
                  "Calibration": "incapable",
                  "Implicit TxBF capable": 0,
                  "Max antennae STA can support when CSI feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when compressed Beamforming feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when uncompressed Beamforming feedback required": "1 TX antenna sounding",
                  "Maximum number of rows of CSI explicit feedback": "1 TX antenna sounding",
                  "Maximum number of space time streams for which channel dimensions can be simultaneously estimated": "1 space time stream",
                  "Minimal grouping used for explicit feedback reports": "No grouping supported",
                  "Receive Null Data packet (NDP)": 0,
                  "Receive Staggered Sounding": 0,
                  "Receiver can return explicit CSI feedback": "not supported",
                  "Receiver can return explicit uncompressed Beamforming Feedback Matrix": "not supported",
                  "STA can apply TxBF using CSI explicit feedback": 0,
                  "STA can apply TxBF using compressed beamforming feedback matrix": 0,
                  "STA can apply TxBF using uncompressed beamforming feedback matrix": 0,
                  "STA can compress and use compressed Beamforming Feedback Matrix": "not supported",
                  "Transmit Beamforming": 0,
                  "Transmit Null Data packet (NDP)": 0,
                  "Transmit Staggered Sounding": 0
                }
              },
              "name": "HT Capabilities",
              "type": 45
            },
            {
              "content": {
                "Extended Capabilities": {
                  "20/40 BSS Coexistence Management Support": 0,
                  "AC Station Count": 0,
                  "BSS Transition": 0,
                  "Channel Usage": 0,
                  "Civic Location": 0,
                  "Collocated Interference Reporting": 0,
                  "DMS": 0,
                  "Diagnostics": 0,
                  "EBR": 0,
                  "Event": 0,
                  "Extended Channel Switching": 1,
                  "FMS": 0,
                  "Geospatial Location": 0,
                  "Identifier Location": 0,
                  "Interworking": 0,
                  "Location Tracking": 0,
                  "MSGCF Capability": 0,
                  "Multicast Diagnostics": 0,
                  "Multiple BSSID": 0,
                  "On-demand beacon": 0,
                  "PSMP Capability": 0,
                  "Peer U-APSD Buffer STA Support": 0,
                  "Proxy ARP Service": 1,
                  "QoS Map": 1,
                  "QoS Traffic Capability": 0,
                  "Reject Unadmitted Frame": 0,
                  "Reserved": 0,
                  "S-PSMP Support": 0,
                  "SSID List": 1,
                  "SSPN Interface": 0,
                  "Service Interval Granularity": "5 ms",
                  "TDLS Channel Switching Prohibited": 0,
                  "TDLS Peer PSM Support": 0,
                  "TDLS Prohibited": 0,
                  "TDLS channel switching": 0,
                  "TDLS support": 0,
                  "TFS": 0,
                  "TIM Broadcast": 0,
                  "Timing Measurement": 0,
                  "U-APSD Coexistence": 0,
                  "UTC TSF Offset": 0,
                  "UTF-8 SSID": 1,
                  "WAVE indication": 0,
                  "WNM-Notification": 0,
                  "WNM-Sleep Mode": 0
                }
              },
              "name": "Extended Capabilities",
              "type": 127
            },
            {
              "content": {
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111010",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "VHT Capabilities Info": {
                  "Compressed Steering Number of Beamformer Antennas Supported": "4",
                  "HTC-VHT Capable VHT variant HT Control field": 0,
                  "MU Beam-formee Capable": 0,
                  "MU Beam-former Capable": "5",
                  "Max A-MPDU Length": "unknown",
                  "Maximum MPDU Length": "11 454",
                  "Number of Sounding Dimensions": "2",
                  "Rx Antenna Pattern Consistency": 1,
                  "Rx LDPC": 1,
                  "Rx STBC": "1 Spatial Stream Supported",
                  "SU Beam-formee Capable": 1,
                  "SU Beam-former Capable": 1,
                  "Short GI for 160MHz and 80+80MHz": 0,
                  "Short GI for 80MHz": 1,
                  "Supported Channel Width Set": "Neither 160MHz nor 80+80 supported",
                  "Tx Antenna Pattern Consistency": 1,
                  "Tx STBC": 1,
                  "VHT Link Adaptation": "No Feedback",
                  "VHT TXOP PS": 0
                }
              },
              "name": "VHT Capabilities Info",
              "type": 191
            },
            {
              "content": {
                "Tx Pwr Info": {
                  "Local Max Tx Pwr Constraint 20MHz": 42,
                  "Local Max Tx Pwr Constraint 40MHz": 42,
                  "Local Max Tx Pwr Constraint 80MHz": 42
                }
              },
              "name": "Tx Pwr Info",
              "type": 195
            },
            {
              "content": {
                "Block": "0d 00 08 9a 40 10 04 70 4c 88 1e c1 83 04 01 2c 00 fa ff fa ff 39 1c c7 71 1c 07",
                "Extension EID": "23"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "f4 3f 00 81 fc ff",
                "Extension EID": "24"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "01 08 a9 ff 2f a9 ff 45 75 ff 65 75 ff",
                "Extension EID": "26"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Auth Key Management (AKM) Suite Count": 1,
                "Multicast Cipher Suite type": "AES (CCM)",
                "Unicast Cipher Suite Count": 1,
                "Unicast Cipher Suite List": [
                  {
                    "Auth Key Management (AKM) OUI": "00 50 f2",
                    "Auth Key Management (AKM) type": "WPA"
                  }
                ],
                "WPA Version": 1,
                "type": "WPA Information Element",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            },
            {
              "content": {
                "Ac Parameters": {
                  "ACI / AIFSN Field": [
                    {
                      "ACI": "Best Effort",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Background",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Video",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 4,
                      "ECW Min": 3,
                      "TXOP Limit": 94
                    },
                    {
                      "ACI": "Voice",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 3,
                      "ECW Min": 2,
                      "TXOP Limit": 47
                    }
                  ]
                },
                "WME QoS Info": {
                  "WME QoS Info": {
                    "AC_BE": 0,
                    "AC_BK": 0,
                    "AC_VI": 0,
                    "AC_VO": 1,
                    "Max SP Length": "WMM AP may deliver all buffered frames (MSDUs and MMPDUs)"
                  }
                },
                "WME Subtype": "Parameter Element",
                "WME Version": 1,
                "type": "WMM/WME",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            }
          ],
          "last_seen": 2730,
          "signal": 3,
          "ssid": "tls_ssid_wpa_eap_5g",
          "tsf": 11150847997,
          "vht_oper": "AToA/P8="
        },
        {
          "bssid": "02:06:ae:6f:6f:f6",
          "capability": 305,
          "channel": 52,
          "frequency": 5260,
          "ht_oper": "NAUAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
          "ies": [
            {
              "content": [
                "6(B)",
                "9",
                "12(B)",
                "18",
                "24(B)",
                "36",
                "48",
                "54"
              ],
              "name": "Supported Rates (Mbps)",
              "type": 1
            },
            {
              "content": {
                "current_channel": 52
              },
              "name": "DS Params",
              "type": 3
            },
            {
              "content": {
                "Bitmap control": {
                  "Bitmap Offset": 0,
                  "Multicast": 0,
                  "Partial Virtual Bitmap": "00"
                },
                "DTIM count": 0,
                "DTIM period": 2
              },
              "name": "Traffic Indication Map (TIM)",
              "type": 5
            },
            {
              "content": {
                "Code": "CA",
                "Environment": "Any",
                "constraints": [
                  {
                    "Country Info": {
                      "First Channel Number": 36,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 8
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 100,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 5
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 132,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 4
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 149,
                      "Maximum Transmit Power Level (in dBm)": 30,
                      "Number of Channels": 5
                    }
                  }
                ]
              },
              "name": "country",
              "type": 7
            },
            {
              "content": {
                "Local Power Constraint": 3
              },
              "name": "Local Power Constraint",
              "type": 32
            },
            {
              "content": {
                "Auth Key Management (AKM) List": [
                  {
                    "Auth Key Management (AKM) OUI": "00:0f:ac",
                    "Auth Key Management (AKM) type": "WPA"
                  },
                  {
                    "Auth Key Management (AKM) OUI": "00:0f:ac",
                    "Auth Key Management (AKM) type": "WPA (SHA256)"
                  }
                ],
                "Auth Key Management (AKM) Suite Count": 2,
                "Group Cipher Suite OUI": "00:0f:ac",
                "Group Cipher Suite type": "AES (CCM)",
                "Pairwise Cipher Suite Count": 1,
                "Pairwise Cipher Suite List": [
                  {
                    "Group Cipher Suite OUI": "00:0f:ac",
                    "Group Cipher Suite type": "AES (CCM)"
                  }
                ],
                "RSN Capabilities": {
                  "Management Frame Protection Capable": 1,
                  "Management Frame Protection Required": 0,
                  "PeerKey Enabled": 0,
                  "RSN GTKSA Replay Counter capabilities": "1 replay counter per PTKSA/GTKSA/STAKeySA",
                  "RSN No Pairwise capabilities": 0,
                  "RSN PTKSA Replay Counter capabilities": "16 replay counters per PTKSA/GTKSA/STAKeySA",
                  "RSN Pre-Auth capabilities": 0
                },
                "RSN Version": 1
              },
              "name": "RSN",
              "type": 48
            },
            {
              "content": {
                "802.11e CCA Version": {
                  "Available Admission Capabilities": 32512,
                  "Channel Utilization": 0,
                  "QBSS Version": 2,
                  "Station Count": 3
                }
              },
              "name": "QBSS Load",
              "type": 11
            },
            {
              "content": {
                "Alternate Regulatory Classes": "0",
                "Current Regulatory Class": 128
              },
              "name": "Supported Regulatory Classes",
              "type": 59
            },
            {
              "content": {
                "A-MPDU Parameters": {
                  "MPDU Density": 0,
                  "Maximum Rx A-MPDU Length": 3
                },
                "Antenna Selection (ASEL) Capabilities": {
                  "Antenna Indices Feedback": 0,
                  "Antenna Indices Feedback Based Tx ASEL": 0,
                  "Antenna Selection Capable": 0,
                  "Antenna Selection Capable TXCSI": 0,
                  "Explicit CSI Feedback": 0,
                  "Rx ASEL": 0,
                  "Tx Sounding PPDUs": 0
                },
                "HT Capabilities Info": {
                  "HT Delayed Block ACK": true,
                  "HT Forty MHz Intolerant": false,
                  "HT Green Field": 12,
                  "HT L-SIG TXOP Protection support": false,
                  "HT LDPC coding capability": true,
                  "HT Max A-MSDU length": false,
                  "HT PSMP Support": false,
                  "HT Rx STBC": 1,
                  "HT Short GI for 20MHz": true,
                  "HT Short GI for 40MHz": true,
                  "HT Support channel width": true,
                  "HT Tx STBC": true
                },
                "HT Extended Capabilities": {
                  "High Throughput": 0,
                  "MCS Feedback capability": 0,
                  "Reverse Direction Responder": 0,
                  "Time needed to transition between 20MHz and 40MHz": 0,
                  "Transmitter supports PCO": 0
                },
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111111",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "Transmit Beam Forming (TxBF) Capabilities": {
                  "Calibration": "incapable",
                  "Implicit TxBF capable": 0,
                  "Max antennae STA can support when CSI feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when compressed Beamforming feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when uncompressed Beamforming feedback required": "1 TX antenna sounding",
                  "Maximum number of rows of CSI explicit feedback": "1 TX antenna sounding",
                  "Maximum number of space time streams for which channel dimensions can be simultaneously estimated": "1 space time stream",
                  "Minimal grouping used for explicit feedback reports": "No grouping supported",
                  "Receive Null Data packet (NDP)": 0,
                  "Receive Staggered Sounding": 0,
                  "Receiver can return explicit CSI feedback": "not supported",
                  "Receiver can return explicit uncompressed Beamforming Feedback Matrix": "not supported",
                  "STA can apply TxBF using CSI explicit feedback": 0,
                  "STA can apply TxBF using compressed beamforming feedback matrix": 0,
                  "STA can apply TxBF using uncompressed beamforming feedback matrix": 0,
                  "STA can compress and use compressed Beamforming Feedback Matrix": "not supported",
                  "Transmit Beamforming": 0,
                  "Transmit Null Data packet (NDP)": 0,
                  "Transmit Staggered Sounding": 0
                }
              },
              "name": "HT Capabilities",
              "type": 45
            },
            {
              "content": {
                "Extended Capabilities": {
                  "20/40 BSS Coexistence Management Support": 0,
                  "AC Station Count": 0,
                  "BSS Transition": 0,
                  "Channel Usage": 0,
                  "Civic Location": 0,
                  "Collocated Interference Reporting": 0,
                  "DMS": 0,
                  "Diagnostics": 0,
                  "EBR": 0,
                  "Event": 0,
                  "Extended Channel Switching": 1,
                  "FMS": 0,
                  "Geospatial Location": 0,
                  "Identifier Location": 0,
                  "Interworking": 0,
                  "Location Tracking": 0,
                  "MSGCF Capability": 0,
                  "Multicast Diagnostics": 0,
                  "Multiple BSSID": 0,
                  "On-demand beacon": 0,
                  "PSMP Capability": 0,
                  "Peer U-APSD Buffer STA Support": 0,
                  "Proxy ARP Service": 1,
                  "QoS Map": 1,
                  "QoS Traffic Capability": 0,
                  "Reject Unadmitted Frame": 0,
                  "Reserved": 0,
                  "S-PSMP Support": 0,
                  "SSID List": 1,
                  "SSPN Interface": 0,
                  "Service Interval Granularity": "5 ms",
                  "TDLS Channel Switching Prohibited": 0,
                  "TDLS Peer PSM Support": 0,
                  "TDLS Prohibited": 0,
                  "TDLS channel switching": 0,
                  "TDLS support": 0,
                  "TFS": 0,
                  "TIM Broadcast": 0,
                  "Timing Measurement": 0,
                  "U-APSD Coexistence": 0,
                  "UTC TSF Offset": 0,
                  "UTF-8 SSID": 1,
                  "WAVE indication": 0,
                  "WNM-Notification": 0,
                  "WNM-Sleep Mode": 0
                }
              },
              "name": "Extended Capabilities",
              "type": 127
            },
            {
              "content": {
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111010",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "VHT Capabilities Info": {
                  "Compressed Steering Number of Beamformer Antennas Supported": "4",
                  "HTC-VHT Capable VHT variant HT Control field": 0,
                  "MU Beam-formee Capable": 0,
                  "MU Beam-former Capable": "5",
                  "Max A-MPDU Length": "unknown",
                  "Maximum MPDU Length": "11 454",
                  "Number of Sounding Dimensions": "2",
                  "Rx Antenna Pattern Consistency": 1,
                  "Rx LDPC": 1,
                  "Rx STBC": "1 Spatial Stream Supported",
                  "SU Beam-formee Capable": 1,
                  "SU Beam-former Capable": 1,
                  "Short GI for 160MHz and 80+80MHz": 0,
                  "Short GI for 80MHz": 1,
                  "Supported Channel Width Set": "Neither 160MHz nor 80+80 supported",
                  "Tx Antenna Pattern Consistency": 1,
                  "Tx STBC": 1,
                  "VHT Link Adaptation": "No Feedback",
                  "VHT TXOP PS": 0
                }
              },
              "name": "VHT Capabilities Info",
              "type": 191
            },
            {
              "content": {
                "Tx Pwr Info": {
                  "Local Max Tx Pwr Constraint 20MHz": 42,
                  "Local Max Tx Pwr Constraint 40MHz": 42,
                  "Local Max Tx Pwr Constraint 80MHz": 42
                }
              },
              "name": "Tx Pwr Info",
              "type": 195
            },
            {
              "content": {
                "Block": "0d 00 08 9a 40 10 04 70 4c 88 1e c1 83 04 01 2c 00 fa ff fa ff 39 1c c7 71 1c 07",
                "Extension EID": "23"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "f4 3f 00 81 fc ff",
                "Extension EID": "24"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "01 08 a9 ff 2f a9 ff 45 75 ff 65 75 ff",
                "Extension EID": "26"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Ac Parameters": {
                  "ACI / AIFSN Field": [
                    {
                      "ACI": "Best Effort",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Background",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Video",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 4,
                      "ECW Min": 3,
                      "TXOP Limit": 94
                    },
                    {
                      "ACI": "Voice",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 3,
                      "ECW Min": 2,
                      "TXOP Limit": 47
                    }
                  ]
                },
                "WME QoS Info": {
                  "WME QoS Info": {
                    "AC_BE": 0,
                    "AC_BK": 0,
                    "AC_VI": 0,
                    "AC_VO": 0,
                    "Max SP Length": "WMM AP may deliver all buffered frames (MSDUs and MMPDUs)"
                  }
                },
                "WME Subtype": "Parameter Element",
                "WME Version": 1,
                "type": "WMM/WME",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            }
          ],
          "last_seen": 2800,
          "signal": 3,
          "ssid": "tls_ssid_wpa2_eap_5g",
          "tsf": 11150779731,
          "vht_oper": "AToA/P8="
        },
        {
          "bssid": "06:06:ae:6f:6f:f6",
          "capability": 305,
          "channel": 52,
          "frequency": 5260,
          "ht_oper": "NAUAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
          "ies": [
            {
              "content": [
                "6(B)",
                "9",
                "12(B)",
                "18",
                "24(B)",
                "36",
                "48",
                "54"
              ],
              "name": "Supported Rates (Mbps)",
              "type": 1
            },
            {
              "content": {
                "current_channel": 52
              },
              "name": "DS Params",
              "type": 3
            },
            {
              "content": {
                "Bitmap control": {
                  "Bitmap Offset": 0,
                  "Multicast": 0,
                  "Partial Virtual Bitmap": "00"
                },
                "DTIM count": 0,
                "DTIM period": 2
              },
              "name": "Traffic Indication Map (TIM)",
              "type": 5
            },
            {
              "content": {
                "Code": "CA",
                "Environment": "Any",
                "constraints": [
                  {
                    "Country Info": {
                      "First Channel Number": 36,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 8
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 100,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 5
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 132,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 4
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 149,
                      "Maximum Transmit Power Level (in dBm)": 30,
                      "Number of Channels": 5
                    }
                  }
                ]
              },
              "name": "country",
              "type": 7
            },
            {
              "content": {
                "Local Power Constraint": 3
              },
              "name": "Local Power Constraint",
              "type": 32
            },
            {
              "content": {
                "Auth Key Management (AKM) List": [
                  {
                    "Auth Key Management (AKM) OUI": "00:0f:ac",
                    "Auth Key Management (AKM) type": "WPA (SHA256)"
                  }
                ],
                "Auth Key Management (AKM) Suite Count": 1,
                "Group Cipher Suite OUI": "00:0f:ac",
                "Group Cipher Suite type": "AES (CCM)",
                "Pairwise Cipher Suite Count": 1,
                "Pairwise Cipher Suite List": [
                  {
                    "Group Cipher Suite OUI": "00:0f:ac",
                    "Group Cipher Suite type": "AES (CCM)"
                  }
                ],
                "RSN Capabilities": {
                  "Management Frame Protection Capable": 1,
                  "Management Frame Protection Required": 1,
                  "PeerKey Enabled": 0,
                  "RSN GTKSA Replay Counter capabilities": "1 replay counter per PTKSA/GTKSA/STAKeySA",
                  "RSN No Pairwise capabilities": 0,
                  "RSN PTKSA Replay Counter capabilities": "16 replay counters per PTKSA/GTKSA/STAKeySA",
                  "RSN Pre-Auth capabilities": 0
                },
                "RSN Version": 1
              },
              "name": "RSN",
              "type": 48
            },
            {
              "content": {
                "802.11e CCA Version": {
                  "Available Admission Capabilities": 32512,
                  "Channel Utilization": 0,
                  "QBSS Version": 2,
                  "Station Count": 3
                }
              },
              "name": "QBSS Load",
              "type": 11
            },
            {
              "content": {
                "Alternate Regulatory Classes": "0",
                "Current Regulatory Class": 128
              },
              "name": "Supported Regulatory Classes",
              "type": 59
            },
            {
              "content": {
                "A-MPDU Parameters": {
                  "MPDU Density": 0,
                  "Maximum Rx A-MPDU Length": 3
                },
                "Antenna Selection (ASEL) Capabilities": {
                  "Antenna Indices Feedback": 0,
                  "Antenna Indices Feedback Based Tx ASEL": 0,
                  "Antenna Selection Capable": 0,
                  "Antenna Selection Capable TXCSI": 0,
                  "Explicit CSI Feedback": 0,
                  "Rx ASEL": 0,
                  "Tx Sounding PPDUs": 0
                },
                "HT Capabilities Info": {
                  "HT Delayed Block ACK": true,
                  "HT Forty MHz Intolerant": false,
                  "HT Green Field": 12,
                  "HT L-SIG TXOP Protection support": false,
                  "HT LDPC coding capability": true,
                  "HT Max A-MSDU length": false,
                  "HT PSMP Support": false,
                  "HT Rx STBC": 1,
                  "HT Short GI for 20MHz": true,
                  "HT Short GI for 40MHz": true,
                  "HT Support channel width": true,
                  "HT Tx STBC": true
                },
                "HT Extended Capabilities": {
                  "High Throughput": 0,
                  "MCS Feedback capability": 0,
                  "Reverse Direction Responder": 0,
                  "Time needed to transition between 20MHz and 40MHz": 0,
                  "Transmitter supports PCO": 0
                },
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111111",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "Transmit Beam Forming (TxBF) Capabilities": {
                  "Calibration": "incapable",
                  "Implicit TxBF capable": 0,
                  "Max antennae STA can support when CSI feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when compressed Beamforming feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when uncompressed Beamforming feedback required": "1 TX antenna sounding",
                  "Maximum number of rows of CSI explicit feedback": "1 TX antenna sounding",
                  "Maximum number of space time streams for which channel dimensions can be simultaneously estimated": "1 space time stream",
                  "Minimal grouping used for explicit feedback reports": "No grouping supported",
                  "Receive Null Data packet (NDP)": 0,
                  "Receive Staggered Sounding": 0,
                  "Receiver can return explicit CSI feedback": "not supported",
                  "Receiver can return explicit uncompressed Beamforming Feedback Matrix": "not supported",
                  "STA can apply TxBF using CSI explicit feedback": 0,
                  "STA can apply TxBF using compressed beamforming feedback matrix": 0,
                  "STA can apply TxBF using uncompressed beamforming feedback matrix": 0,
                  "STA can compress and use compressed Beamforming Feedback Matrix": "not supported",
                  "Transmit Beamforming": 0,
                  "Transmit Null Data packet (NDP)": 0,
                  "Transmit Staggered Sounding": 0
                }
              },
              "name": "HT Capabilities",
              "type": 45
            },
            {
              "content": {
                "Extended Capabilities": {
                  "20/40 BSS Coexistence Management Support": 0,
                  "AC Station Count": 0,
                  "BSS Transition": 0,
                  "Channel Usage": 0,
                  "Civic Location": 0,
                  "Collocated Interference Reporting": 0,
                  "DMS": 0,
                  "Diagnostics": 0,
                  "EBR": 0,
                  "Event": 0,
                  "Extended Channel Switching": 1,
                  "FMS": 0,
                  "Geospatial Location": 0,
                  "Identifier Location": 0,
                  "Interworking": 0,
                  "Location Tracking": 0,
                  "MSGCF Capability": 0,
                  "Multicast Diagnostics": 0,
                  "Multiple BSSID": 0,
                  "On-demand beacon": 0,
                  "PSMP Capability": 0,
                  "Peer U-APSD Buffer STA Support": 0,
                  "Proxy ARP Service": 1,
                  "QoS Map": 1,
                  "QoS Traffic Capability": 0,
                  "Reject Unadmitted Frame": 0,
                  "Reserved": 0,
                  "S-PSMP Support": 0,
                  "SSID List": 1,
                  "SSPN Interface": 0,
                  "Service Interval Granularity": "5 ms",
                  "TDLS Channel Switching Prohibited": 0,
                  "TDLS Peer PSM Support": 0,
                  "TDLS Prohibited": 0,
                  "TDLS channel switching": 0,
                  "TDLS support": 0,
                  "TFS": 0,
                  "TIM Broadcast": 0,
                  "Timing Measurement": 0,
                  "U-APSD Coexistence": 0,
                  "UTC TSF Offset": 0,
                  "UTF-8 SSID": 1,
                  "WAVE indication": 0,
                  "WNM-Notification": 0,
                  "WNM-Sleep Mode": 0
                }
              },
              "name": "Extended Capabilities",
              "type": 127
            },
            {
              "content": {
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111010",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "VHT Capabilities Info": {
                  "Compressed Steering Number of Beamformer Antennas Supported": "4",
                  "HTC-VHT Capable VHT variant HT Control field": 0,
                  "MU Beam-formee Capable": 0,
                  "MU Beam-former Capable": "5",
                  "Max A-MPDU Length": "unknown",
                  "Maximum MPDU Length": "11 454",
                  "Number of Sounding Dimensions": "2",
                  "Rx Antenna Pattern Consistency": 1,
                  "Rx LDPC": 1,
                  "Rx STBC": "1 Spatial Stream Supported",
                  "SU Beam-formee Capable": 1,
                  "SU Beam-former Capable": 1,
                  "Short GI for 160MHz and 80+80MHz": 0,
                  "Short GI for 80MHz": 1,
                  "Supported Channel Width Set": "Neither 160MHz nor 80+80 supported",
                  "Tx Antenna Pattern Consistency": 1,
                  "Tx STBC": 1,
                  "VHT Link Adaptation": "No Feedback",
                  "VHT TXOP PS": 0
                }
              },
              "name": "VHT Capabilities Info",
              "type": 191
            },
            {
              "content": {
                "Tx Pwr Info": {
                  "Local Max Tx Pwr Constraint 20MHz": 42,
                  "Local Max Tx Pwr Constraint 40MHz": 42,
                  "Local Max Tx Pwr Constraint 80MHz": 42
                }
              },
              "name": "Tx Pwr Info",
              "type": 195
            },
            {
              "content": {
                "Block": "0d 00 08 9a 40 10 04 70 4c 88 1e c1 83 04 01 2c 00 fa ff fa ff 39 1c c7 71 1c 07",
                "Extension EID": "23"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "f4 3f 00 81 fc ff",
                "Extension EID": "24"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "01 08 a9 ff 2f a9 ff 45 75 ff 65 75 ff",
                "Extension EID": "26"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Ac Parameters": {
                  "ACI / AIFSN Field": [
                    {
                      "ACI": "Best Effort",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Background",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Video",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 4,
                      "ECW Min": 3,
                      "TXOP Limit": 94
                    },
                    {
                      "ACI": "Voice",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 3,
                      "ECW Min": 2,
                      "TXOP Limit": 47
                    }
                  ]
                },
                "WME QoS Info": {
                  "WME QoS Info": {
                    "AC_BE": 0,
                    "AC_BK": 0,
                    "AC_VI": 0,
                    "AC_VO": 0,
                    "Max SP Length": "WMM AP may deliver all buffered frames (MSDUs and MMPDUs)"
                  }
                },
                "WME Subtype": "Parameter Element",
                "WME Version": 1,
                "type": "WMM/WME",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            }
          ],
          "last_seen": 2760,
          "signal": 3,
          "ssid": "tls_ssid_wpa3_eap_5g",
          "tsf": 11150813864,
          "vht_oper": "AToA/P8="
        }
      ],
      "text": "Success"
    },
    "uuid": 1657164026
  }
}{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "serial": "903cb39d6918",
    "status": {
      "error": 0,
      "resultCode": 1,
      "scan": [
        {
          "bssid": "00:06:ae:6f:6f:f6",
          "capability": 305,
          "channel": 52,
          "frequency": 5260,
          "ht_oper": "NAUAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
          "ies": [
            {
              "content": [
                "6(B)",
                "9",
                "12(B)",
                "18",
                "24(B)",
                "36",
                "48",
                "54"
              ],
              "name": "Supported Rates (Mbps)",
              "type": 1
            },
            {
              "content": {
                "current_channel": 52
              },
              "name": "DS Params",
              "type": 3
            },
            {
              "content": {
                "Bitmap control": {
                  "Bitmap Offset": 0,
                  "Multicast": 0,
                  "Partial Virtual Bitmap": "00"
                },
                "DTIM count": 0,
                "DTIM period": 2
              },
              "name": "Traffic Indication Map (TIM)",
              "type": 5
            },
            {
              "content": {
                "Code": "CA",
                "Environment": "Any",
                "constraints": [
                  {
                    "Country Info": {
                      "First Channel Number": 36,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 8
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 100,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 5
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 132,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 4
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 149,
                      "Maximum Transmit Power Level (in dBm)": 30,
                      "Number of Channels": 5
                    }
                  }
                ]
              },
              "name": "country",
              "type": 7
            },
            {
              "content": {
                "Local Power Constraint": 3
              },
              "name": "Local Power Constraint",
              "type": 32
            },
            {
              "content": {
                "802.11e CCA Version": {
                  "Available Admission Capabilities": 0,
                  "Channel Utilization": 0,
                  "QBSS Version": 2,
                  "Station Count": 3
                }
              },
              "name": "QBSS Load",
              "type": 11
            },
            {
              "content": {
                "Alternate Regulatory Classes": "0",
                "Current Regulatory Class": 128
              },
              "name": "Supported Regulatory Classes",
              "type": 59
            },
            {
              "content": {
                "A-MPDU Parameters": {
                  "MPDU Density": 0,
                  "Maximum Rx A-MPDU Length": 3
                },
                "Antenna Selection (ASEL) Capabilities": {
                  "Antenna Indices Feedback": 0,
                  "Antenna Indices Feedback Based Tx ASEL": 0,
                  "Antenna Selection Capable": 0,
                  "Antenna Selection Capable TXCSI": 0,
                  "Explicit CSI Feedback": 0,
                  "Rx ASEL": 0,
                  "Tx Sounding PPDUs": 0
                },
                "HT Capabilities Info": {
                  "HT Delayed Block ACK": true,
                  "HT Forty MHz Intolerant": false,
                  "HT Green Field": 12,
                  "HT L-SIG TXOP Protection support": false,
                  "HT LDPC coding capability": true,
                  "HT Max A-MSDU length": false,
                  "HT PSMP Support": false,
                  "HT Rx STBC": 1,
                  "HT Short GI for 20MHz": true,
                  "HT Short GI for 40MHz": true,
                  "HT Support channel width": true,
                  "HT Tx STBC": true
                },
                "HT Extended Capabilities": {
                  "High Throughput": 0,
                  "MCS Feedback capability": 0,
                  "Reverse Direction Responder": 0,
                  "Time needed to transition between 20MHz and 40MHz": 0,
                  "Transmitter supports PCO": 0
                },
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111111",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "Transmit Beam Forming (TxBF) Capabilities": {
                  "Calibration": "incapable",
                  "Implicit TxBF capable": 0,
                  "Max antennae STA can support when CSI feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when compressed Beamforming feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when uncompressed Beamforming feedback required": "1 TX antenna sounding",
                  "Maximum number of rows of CSI explicit feedback": "1 TX antenna sounding",
                  "Maximum number of space time streams for which channel dimensions can be simultaneously estimated": "1 space time stream",
                  "Minimal grouping used for explicit feedback reports": "No grouping supported",
                  "Receive Null Data packet (NDP)": 0,
                  "Receive Staggered Sounding": 0,
                  "Receiver can return explicit CSI feedback": "not supported",
                  "Receiver can return explicit uncompressed Beamforming Feedback Matrix": "not supported",
                  "STA can apply TxBF using CSI explicit feedback": 0,
                  "STA can apply TxBF using compressed beamforming feedback matrix": 0,
                  "STA can apply TxBF using uncompressed beamforming feedback matrix": 0,
                  "STA can compress and use compressed Beamforming Feedback Matrix": "not supported",
                  "Transmit Beamforming": 0,
                  "Transmit Null Data packet (NDP)": 0,
                  "Transmit Staggered Sounding": 0
                }
              },
              "name": "HT Capabilities",
              "type": 45
            },
            {
              "content": {
                "Extended Capabilities": {
                  "20/40 BSS Coexistence Management Support": 0,
                  "AC Station Count": 0,
                  "BSS Transition": 0,
                  "Channel Usage": 0,
                  "Civic Location": 0,
                  "Collocated Interference Reporting": 0,
                  "DMS": 0,
                  "Diagnostics": 0,
                  "EBR": 0,
                  "Event": 0,
                  "Extended Channel Switching": 1,
                  "FMS": 0,
                  "Geospatial Location": 0,
                  "Identifier Location": 0,
                  "Interworking": 0,
                  "Location Tracking": 0,
                  "MSGCF Capability": 0,
                  "Multicast Diagnostics": 0,
                  "Multiple BSSID": 0,
                  "On-demand beacon": 0,
                  "PSMP Capability": 0,
                  "Peer U-APSD Buffer STA Support": 0,
                  "Proxy ARP Service": 1,
                  "QoS Map": 1,
                  "QoS Traffic Capability": 0,
                  "Reject Unadmitted Frame": 0,
                  "Reserved": 0,
                  "S-PSMP Support": 0,
                  "SSID List": 1,
                  "SSPN Interface": 0,
                  "Service Interval Granularity": "5 ms",
                  "TDLS Channel Switching Prohibited": 0,
                  "TDLS Peer PSM Support": 0,
                  "TDLS Prohibited": 0,
                  "TDLS channel switching": 0,
                  "TDLS support": 0,
                  "TFS": 0,
                  "TIM Broadcast": 0,
                  "Timing Measurement": 0,
                  "U-APSD Coexistence": 0,
                  "UTC TSF Offset": 0,
                  "UTF-8 SSID": 1,
                  "WAVE indication": 0,
                  "WNM-Notification": 0,
                  "WNM-Sleep Mode": 0
                }
              },
              "name": "Extended Capabilities",
              "type": 127
            },
            {
              "content": {
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111010",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "VHT Capabilities Info": {
                  "Compressed Steering Number of Beamformer Antennas Supported": "4",
                  "HTC-VHT Capable VHT variant HT Control field": 0,
                  "MU Beam-formee Capable": 0,
                  "MU Beam-former Capable": "5",
                  "Max A-MPDU Length": "unknown",
                  "Maximum MPDU Length": "11 454",
                  "Number of Sounding Dimensions": "2",
                  "Rx Antenna Pattern Consistency": 1,
                  "Rx LDPC": 1,
                  "Rx STBC": "1 Spatial Stream Supported",
                  "SU Beam-formee Capable": 1,
                  "SU Beam-former Capable": 1,
                  "Short GI for 160MHz and 80+80MHz": 0,
                  "Short GI for 80MHz": 1,
                  "Supported Channel Width Set": "Neither 160MHz nor 80+80 supported",
                  "Tx Antenna Pattern Consistency": 1,
                  "Tx STBC": 1,
                  "VHT Link Adaptation": "No Feedback",
                  "VHT TXOP PS": 0
                }
              },
              "name": "VHT Capabilities Info",
              "type": 191
            },
            {
              "content": {
                "Tx Pwr Info": {
                  "Local Max Tx Pwr Constraint 20MHz": 42,
                  "Local Max Tx Pwr Constraint 40MHz": 42,
                  "Local Max Tx Pwr Constraint 80MHz": 42
                }
              },
              "name": "Tx Pwr Info",
              "type": 195
            },
            {
              "content": {
                "Block": "0d 00 08 9a 40 10 04 70 4c 88 1e c1 83 04 01 2c 00 fa ff fa ff 39 1c c7 71 1c 07",
                "Extension EID": "23"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "f4 3f 00 81 fc ff",
                "Extension EID": "24"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "01 08 a9 ff 2f a9 ff 45 75 ff 65 75 ff",
                "Extension EID": "26"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Auth Key Management (AKM) Suite Count": 1,
                "Multicast Cipher Suite type": "AES (CCM)",
                "Unicast Cipher Suite Count": 1,
                "Unicast Cipher Suite List": [
                  {
                    "Auth Key Management (AKM) OUI": "00 50 f2",
                    "Auth Key Management (AKM) type": "WPA"
                  }
                ],
                "WPA Version": 1,
                "type": "WPA Information Element",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            },
            {
              "content": {
                "Ac Parameters": {
                  "ACI / AIFSN Field": [
                    {
                      "ACI": "Best Effort",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Background",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Video",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 4,
                      "ECW Min": 3,
                      "TXOP Limit": 94
                    },
                    {
                      "ACI": "Voice",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 3,
                      "ECW Min": 2,
                      "TXOP Limit": 47
                    }
                  ]
                },
                "WME QoS Info": {
                  "WME QoS Info": {
                    "AC_BE": 0,
                    "AC_BK": 0,
                    "AC_VI": 0,
                    "AC_VO": 1,
                    "Max SP Length": "WMM AP may deliver all buffered frames (MSDUs and MMPDUs)"
                  }
                },
                "WME Subtype": "Parameter Element",
                "WME Version": 1,
                "type": "WMM/WME",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            }
          ],
          "last_seen": 2730,
          "signal": 3,
          "ssid": "tls_ssid_wpa_eap_5g",
          "tsf": 11150847997,
          "vht_oper": "AToA/P8="
        },
        {
          "bssid": "02:06:ae:6f:6f:f6",
          "capability": 305,
          "channel": 52,
          "frequency": 5260,
          "ht_oper": "NAUAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
          "ies": [
            {
              "content": [
                "6(B)",
                "9",
                "12(B)",
                "18",
                "24(B)",
                "36",
                "48",
                "54"
              ],
              "name": "Supported Rates (Mbps)",
              "type": 1
            },
            {
              "content": {
                "current_channel": 52
              },
              "name": "DS Params",
              "type": 3
            },
            {
              "content": {
                "Bitmap control": {
                  "Bitmap Offset": 0,
                  "Multicast": 0,
                  "Partial Virtual Bitmap": "00"
                },
                "DTIM count": 0,
                "DTIM period": 2
              },
              "name": "Traffic Indication Map (TIM)",
              "type": 5
            },
            {
              "content": {
                "Code": "CA",
                "Environment": "Any",
                "constraints": [
                  {
                    "Country Info": {
                      "First Channel Number": 36,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 8
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 100,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 5
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 132,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 4
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 149,
                      "Maximum Transmit Power Level (in dBm)": 30,
                      "Number of Channels": 5
                    }
                  }
                ]
              },
              "name": "country",
              "type": 7
            },
            {
              "content": {
                "Local Power Constraint": 3
              },
              "name": "Local Power Constraint",
              "type": 32
            },
            {
              "content": {
                "Auth Key Management (AKM) List": [
                  {
                    "Auth Key Management (AKM) OUI": "00:0f:ac",
                    "Auth Key Management (AKM) type": "WPA"
                  },
                  {
                    "Auth Key Management (AKM) OUI": "00:0f:ac",
                    "Auth Key Management (AKM) type": "WPA (SHA256)"
                  }
                ],
                "Auth Key Management (AKM) Suite Count": 2,
                "Group Cipher Suite OUI": "00:0f:ac",
                "Group Cipher Suite type": "AES (CCM)",
                "Pairwise Cipher Suite Count": 1,
                "Pairwise Cipher Suite List": [
                  {
                    "Group Cipher Suite OUI": "00:0f:ac",
                    "Group Cipher Suite type": "AES (CCM)"
                  }
                ],
                "RSN Capabilities": {
                  "Management Frame Protection Capable": 1,
                  "Management Frame Protection Required": 0,
                  "PeerKey Enabled": 0,
                  "RSN GTKSA Replay Counter capabilities": "1 replay counter per PTKSA/GTKSA/STAKeySA",
                  "RSN No Pairwise capabilities": 0,
                  "RSN PTKSA Replay Counter capabilities": "16 replay counters per PTKSA/GTKSA/STAKeySA",
                  "RSN Pre-Auth capabilities": 0
                },
                "RSN Version": 1
              },
              "name": "RSN",
              "type": 48
            },
            {
              "content": {
                "802.11e CCA Version": {
                  "Available Admission Capabilities": 32512,
                  "Channel Utilization": 0,
                  "QBSS Version": 2,
                  "Station Count": 3
                }
              },
              "name": "QBSS Load",
              "type": 11
            },
            {
              "content": {
                "Alternate Regulatory Classes": "0",
                "Current Regulatory Class": 128
              },
              "name": "Supported Regulatory Classes",
              "type": 59
            },
            {
              "content": {
                "A-MPDU Parameters": {
                  "MPDU Density": 0,
                  "Maximum Rx A-MPDU Length": 3
                },
                "Antenna Selection (ASEL) Capabilities": {
                  "Antenna Indices Feedback": 0,
                  "Antenna Indices Feedback Based Tx ASEL": 0,
                  "Antenna Selection Capable": 0,
                  "Antenna Selection Capable TXCSI": 0,
                  "Explicit CSI Feedback": 0,
                  "Rx ASEL": 0,
                  "Tx Sounding PPDUs": 0
                },
                "HT Capabilities Info": {
                  "HT Delayed Block ACK": true,
                  "HT Forty MHz Intolerant": false,
                  "HT Green Field": 12,
                  "HT L-SIG TXOP Protection support": false,
                  "HT LDPC coding capability": true,
                  "HT Max A-MSDU length": false,
                  "HT PSMP Support": false,
                  "HT Rx STBC": 1,
                  "HT Short GI for 20MHz": true,
                  "HT Short GI for 40MHz": true,
                  "HT Support channel width": true,
                  "HT Tx STBC": true
                },
                "HT Extended Capabilities": {
                  "High Throughput": 0,
                  "MCS Feedback capability": 0,
                  "Reverse Direction Responder": 0,
                  "Time needed to transition between 20MHz and 40MHz": 0,
                  "Transmitter supports PCO": 0
                },
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111111",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "Transmit Beam Forming (TxBF) Capabilities": {
                  "Calibration": "incapable",
                  "Implicit TxBF capable": 0,
                  "Max antennae STA can support when CSI feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when compressed Beamforming feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when uncompressed Beamforming feedback required": "1 TX antenna sounding",
                  "Maximum number of rows of CSI explicit feedback": "1 TX antenna sounding",
                  "Maximum number of space time streams for which channel dimensions can be simultaneously estimated": "1 space time stream",
                  "Minimal grouping used for explicit feedback reports": "No grouping supported",
                  "Receive Null Data packet (NDP)": 0,
                  "Receive Staggered Sounding": 0,
                  "Receiver can return explicit CSI feedback": "not supported",
                  "Receiver can return explicit uncompressed Beamforming Feedback Matrix": "not supported",
                  "STA can apply TxBF using CSI explicit feedback": 0,
                  "STA can apply TxBF using compressed beamforming feedback matrix": 0,
                  "STA can apply TxBF using uncompressed beamforming feedback matrix": 0,
                  "STA can compress and use compressed Beamforming Feedback Matrix": "not supported",
                  "Transmit Beamforming": 0,
                  "Transmit Null Data packet (NDP)": 0,
                  "Transmit Staggered Sounding": 0
                }
              },
              "name": "HT Capabilities",
              "type": 45
            },
            {
              "content": {
                "Extended Capabilities": {
                  "20/40 BSS Coexistence Management Support": 0,
                  "AC Station Count": 0,
                  "BSS Transition": 0,
                  "Channel Usage": 0,
                  "Civic Location": 0,
                  "Collocated Interference Reporting": 0,
                  "DMS": 0,
                  "Diagnostics": 0,
                  "EBR": 0,
                  "Event": 0,
                  "Extended Channel Switching": 1,
                  "FMS": 0,
                  "Geospatial Location": 0,
                  "Identifier Location": 0,
                  "Interworking": 0,
                  "Location Tracking": 0,
                  "MSGCF Capability": 0,
                  "Multicast Diagnostics": 0,
                  "Multiple BSSID": 0,
                  "On-demand beacon": 0,
                  "PSMP Capability": 0,
                  "Peer U-APSD Buffer STA Support": 0,
                  "Proxy ARP Service": 1,
                  "QoS Map": 1,
                  "QoS Traffic Capability": 0,
                  "Reject Unadmitted Frame": 0,
                  "Reserved": 0,
                  "S-PSMP Support": 0,
                  "SSID List": 1,
                  "SSPN Interface": 0,
                  "Service Interval Granularity": "5 ms",
                  "TDLS Channel Switching Prohibited": 0,
                  "TDLS Peer PSM Support": 0,
                  "TDLS Prohibited": 0,
                  "TDLS channel switching": 0,
                  "TDLS support": 0,
                  "TFS": 0,
                  "TIM Broadcast": 0,
                  "Timing Measurement": 0,
                  "U-APSD Coexistence": 0,
                  "UTC TSF Offset": 0,
                  "UTF-8 SSID": 1,
                  "WAVE indication": 0,
                  "WNM-Notification": 0,
                  "WNM-Sleep Mode": 0
                }
              },
              "name": "Extended Capabilities",
              "type": 127
            },
            {
              "content": {
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111010",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "VHT Capabilities Info": {
                  "Compressed Steering Number of Beamformer Antennas Supported": "4",
                  "HTC-VHT Capable VHT variant HT Control field": 0,
                  "MU Beam-formee Capable": 0,
                  "MU Beam-former Capable": "5",
                  "Max A-MPDU Length": "unknown",
                  "Maximum MPDU Length": "11 454",
                  "Number of Sounding Dimensions": "2",
                  "Rx Antenna Pattern Consistency": 1,
                  "Rx LDPC": 1,
                  "Rx STBC": "1 Spatial Stream Supported",
                  "SU Beam-formee Capable": 1,
                  "SU Beam-former Capable": 1,
                  "Short GI for 160MHz and 80+80MHz": 0,
                  "Short GI for 80MHz": 1,
                  "Supported Channel Width Set": "Neither 160MHz nor 80+80 supported",
                  "Tx Antenna Pattern Consistency": 1,
                  "Tx STBC": 1,
                  "VHT Link Adaptation": "No Feedback",
                  "VHT TXOP PS": 0
                }
              },
              "name": "VHT Capabilities Info",
              "type": 191
            },
            {
              "content": {
                "Tx Pwr Info": {
                  "Local Max Tx Pwr Constraint 20MHz": 42,
                  "Local Max Tx Pwr Constraint 40MHz": 42,
                  "Local Max Tx Pwr Constraint 80MHz": 42
                }
              },
              "name": "Tx Pwr Info",
              "type": 195
            },
            {
              "content": {
                "Block": "0d 00 08 9a 40 10 04 70 4c 88 1e c1 83 04 01 2c 00 fa ff fa ff 39 1c c7 71 1c 07",
                "Extension EID": "23"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "f4 3f 00 81 fc ff",
                "Extension EID": "24"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "01 08 a9 ff 2f a9 ff 45 75 ff 65 75 ff",
                "Extension EID": "26"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Ac Parameters": {
                  "ACI / AIFSN Field": [
                    {
                      "ACI": "Best Effort",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Background",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Video",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 4,
                      "ECW Min": 3,
                      "TXOP Limit": 94
                    },
                    {
                      "ACI": "Voice",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 3,
                      "ECW Min": 2,
                      "TXOP Limit": 47
                    }
                  ]
                },
                "WME QoS Info": {
                  "WME QoS Info": {
                    "AC_BE": 0,
                    "AC_BK": 0,
                    "AC_VI": 0,
                    "AC_VO": 0,
                    "Max SP Length": "WMM AP may deliver all buffered frames (MSDUs and MMPDUs)"
                  }
                },
                "WME Subtype": "Parameter Element",
                "WME Version": 1,
                "type": "WMM/WME",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            }
          ],
          "last_seen": 2800,
          "signal": 3,
          "ssid": "tls_ssid_wpa2_eap_5g",
          "tsf": 11150779731,
          "vht_oper": "AToA/P8="
        },
        {
          "bssid": "06:06:ae:6f:6f:f6",
          "capability": 305,
          "channel": 52,
          "frequency": 5260,
          "ht_oper": "NAUAAAAAAAAAAAAAAAAAAAAAAAAAAA==",
          "ies": [
            {
              "content": [
                "6(B)",
                "9",
                "12(B)",
                "18",
                "24(B)",
                "36",
                "48",
                "54"
              ],
              "name": "Supported Rates (Mbps)",
              "type": 1
            },
            {
              "content": {
                "current_channel": 52
              },
              "name": "DS Params",
              "type": 3
            },
            {
              "content": {
                "Bitmap control": {
                  "Bitmap Offset": 0,
                  "Multicast": 0,
                  "Partial Virtual Bitmap": "00"
                },
                "DTIM count": 0,
                "DTIM period": 2
              },
              "name": "Traffic Indication Map (TIM)",
              "type": 5
            },
            {
              "content": {
                "Code": "CA",
                "Environment": "Any",
                "constraints": [
                  {
                    "Country Info": {
                      "First Channel Number": 36,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 8
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 100,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 5
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 132,
                      "Maximum Transmit Power Level (in dBm)": 24,
                      "Number of Channels": 4
                    }
                  },
                  {
                    "Country Info": {
                      "First Channel Number": 149,
                      "Maximum Transmit Power Level (in dBm)": 30,
                      "Number of Channels": 5
                    }
                  }
                ]
              },
              "name": "country",
              "type": 7
            },
            {
              "content": {
                "Local Power Constraint": 3
              },
              "name": "Local Power Constraint",
              "type": 32
            },
            {
              "content": {
                "Auth Key Management (AKM) List": [
                  {
                    "Auth Key Management (AKM) OUI": "00:0f:ac",
                    "Auth Key Management (AKM) type": "WPA (SHA256)"
                  }
                ],
                "Auth Key Management (AKM) Suite Count": 1,
                "Group Cipher Suite OUI": "00:0f:ac",
                "Group Cipher Suite type": "AES (CCM)",
                "Pairwise Cipher Suite Count": 1,
                "Pairwise Cipher Suite List": [
                  {
                    "Group Cipher Suite OUI": "00:0f:ac",
                    "Group Cipher Suite type": "AES (CCM)"
                  }
                ],
                "RSN Capabilities": {
                  "Management Frame Protection Capable": 1,
                  "Management Frame Protection Required": 1,
                  "PeerKey Enabled": 0,
                  "RSN GTKSA Replay Counter capabilities": "1 replay counter per PTKSA/GTKSA/STAKeySA",
                  "RSN No Pairwise capabilities": 0,
                  "RSN PTKSA Replay Counter capabilities": "16 replay counters per PTKSA/GTKSA/STAKeySA",
                  "RSN Pre-Auth capabilities": 0
                },
                "RSN Version": 1
              },
              "name": "RSN",
              "type": 48
            },
            {
              "content": {
                "802.11e CCA Version": {
                  "Available Admission Capabilities": 32512,
                  "Channel Utilization": 0,
                  "QBSS Version": 2,
                  "Station Count": 3
                }
              },
              "name": "QBSS Load",
              "type": 11
            },
            {
              "content": {
                "Alternate Regulatory Classes": "0",
                "Current Regulatory Class": 128
              },
              "name": "Supported Regulatory Classes",
              "type": 59
            },
            {
              "content": {
                "A-MPDU Parameters": {
                  "MPDU Density": 0,
                  "Maximum Rx A-MPDU Length": 3
                },
                "Antenna Selection (ASEL) Capabilities": {
                  "Antenna Indices Feedback": 0,
                  "Antenna Indices Feedback Based Tx ASEL": 0,
                  "Antenna Selection Capable": 0,
                  "Antenna Selection Capable TXCSI": 0,
                  "Explicit CSI Feedback": 0,
                  "Rx ASEL": 0,
                  "Tx Sounding PPDUs": 0
                },
                "HT Capabilities Info": {
                  "HT Delayed Block ACK": true,
                  "HT Forty MHz Intolerant": false,
                  "HT Green Field": 12,
                  "HT L-SIG TXOP Protection support": false,
                  "HT LDPC coding capability": true,
                  "HT Max A-MSDU length": false,
                  "HT PSMP Support": false,
                  "HT Rx STBC": 1,
                  "HT Short GI for 20MHz": true,
                  "HT Short GI for 40MHz": true,
                  "HT Support channel width": true,
                  "HT Tx STBC": true
                },
                "HT Extended Capabilities": {
                  "High Throughput": 0,
                  "MCS Feedback capability": 0,
                  "Reverse Direction Responder": 0,
                  "Time needed to transition between 20MHz and 40MHz": 0,
                  "Transmitter supports PCO": 0
                },
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111111",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "Transmit Beam Forming (TxBF) Capabilities": {
                  "Calibration": "incapable",
                  "Implicit TxBF capable": 0,
                  "Max antennae STA can support when CSI feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when compressed Beamforming feedback required": "1 TX antenna sounding",
                  "Max antennae STA can support when uncompressed Beamforming feedback required": "1 TX antenna sounding",
                  "Maximum number of rows of CSI explicit feedback": "1 TX antenna sounding",
                  "Maximum number of space time streams for which channel dimensions can be simultaneously estimated": "1 space time stream",
                  "Minimal grouping used for explicit feedback reports": "No grouping supported",
                  "Receive Null Data packet (NDP)": 0,
                  "Receive Staggered Sounding": 0,
                  "Receiver can return explicit CSI feedback": "not supported",
                  "Receiver can return explicit uncompressed Beamforming Feedback Matrix": "not supported",
                  "STA can apply TxBF using CSI explicit feedback": 0,
                  "STA can apply TxBF using compressed beamforming feedback matrix": 0,
                  "STA can apply TxBF using uncompressed beamforming feedback matrix": 0,
                  "STA can compress and use compressed Beamforming Feedback Matrix": "not supported",
                  "Transmit Beamforming": 0,
                  "Transmit Null Data packet (NDP)": 0,
                  "Transmit Staggered Sounding": 0
                }
              },
              "name": "HT Capabilities",
              "type": 45
            },
            {
              "content": {
                "Extended Capabilities": {
                  "20/40 BSS Coexistence Management Support": 0,
                  "AC Station Count": 0,
                  "BSS Transition": 0,
                  "Channel Usage": 0,
                  "Civic Location": 0,
                  "Collocated Interference Reporting": 0,
                  "DMS": 0,
                  "Diagnostics": 0,
                  "EBR": 0,
                  "Event": 0,
                  "Extended Channel Switching": 1,
                  "FMS": 0,
                  "Geospatial Location": 0,
                  "Identifier Location": 0,
                  "Interworking": 0,
                  "Location Tracking": 0,
                  "MSGCF Capability": 0,
                  "Multicast Diagnostics": 0,
                  "Multiple BSSID": 0,
                  "On-demand beacon": 0,
                  "PSMP Capability": 0,
                  "Peer U-APSD Buffer STA Support": 0,
                  "Proxy ARP Service": 1,
                  "QoS Map": 1,
                  "QoS Traffic Capability": 0,
                  "Reject Unadmitted Frame": 0,
                  "Reserved": 0,
                  "S-PSMP Support": 0,
                  "SSID List": 1,
                  "SSPN Interface": 0,
                  "Service Interval Granularity": "5 ms",
                  "TDLS Channel Switching Prohibited": 0,
                  "TDLS Peer PSM Support": 0,
                  "TDLS Prohibited": 0,
                  "TDLS channel switching": 0,
                  "TDLS support": 0,
                  "TFS": 0,
                  "TIM Broadcast": 0,
                  "Timing Measurement": 0,
                  "U-APSD Coexistence": 0,
                  "UTC TSF Offset": 0,
                  "UTF-8 SSID": 1,
                  "WAVE indication": 0,
                  "WNM-Notification": 0,
                  "WNM-Sleep Mode": 0
                }
              },
              "name": "Extended Capabilities",
              "type": 127
            },
            {
              "content": {
                "MCS Set": {
                  "Rx Bitmask Bits 0-7": "11111010",
                  "Rx Bitmask Bits 16-23": "00000000",
                  "Rx Bitmask Bits 24-31": "00000000",
                  "Rx Bitmask Bits 8-15": "11111111"
                },
                "VHT Capabilities Info": {
                  "Compressed Steering Number of Beamformer Antennas Supported": "4",
                  "HTC-VHT Capable VHT variant HT Control field": 0,
                  "MU Beam-formee Capable": 0,
                  "MU Beam-former Capable": "5",
                  "Max A-MPDU Length": "unknown",
                  "Maximum MPDU Length": "11 454",
                  "Number of Sounding Dimensions": "2",
                  "Rx Antenna Pattern Consistency": 1,
                  "Rx LDPC": 1,
                  "Rx STBC": "1 Spatial Stream Supported",
                  "SU Beam-formee Capable": 1,
                  "SU Beam-former Capable": 1,
                  "Short GI for 160MHz and 80+80MHz": 0,
                  "Short GI for 80MHz": 1,
                  "Supported Channel Width Set": "Neither 160MHz nor 80+80 supported",
                  "Tx Antenna Pattern Consistency": 1,
                  "Tx STBC": 1,
                  "VHT Link Adaptation": "No Feedback",
                  "VHT TXOP PS": 0
                }
              },
              "name": "VHT Capabilities Info",
              "type": 191
            },
            {
              "content": {
                "Tx Pwr Info": {
                  "Local Max Tx Pwr Constraint 20MHz": 42,
                  "Local Max Tx Pwr Constraint 40MHz": 42,
                  "Local Max Tx Pwr Constraint 80MHz": 42
                }
              },
              "name": "Tx Pwr Info",
              "type": 195
            },
            {
              "content": {
                "Block": "0d 00 08 9a 40 10 04 70 4c 88 1e c1 83 04 01 2c 00 fa ff fa ff 39 1c c7 71 1c 07",
                "Extension EID": "23"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "f4 3f 00 81 fc ff",
                "Extension EID": "24"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Block": "01 08 a9 ff 2f a9 ff 45 75 ff 65 75 ff",
                "Extension EID": "26"
              },
              "name": "EI Extensions",
              "type": 255
            },
            {
              "content": {
                "Ac Parameters": {
                  "ACI / AIFSN Field": [
                    {
                      "ACI": "Best Effort",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Background",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 10,
                      "ECW Min": 4,
                      "TXOP Limit": 0
                    },
                    {
                      "ACI": "Video",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 4,
                      "ECW Min": 3,
                      "TXOP Limit": 94
                    },
                    {
                      "ACI": "Voice",
                      "AIFSN": 0,
                      "Admission Control Mandatory": 0,
                      "ECW Max": 3,
                      "ECW Min": 2,
                      "TXOP Limit": 47
                    }
                  ]
                },
                "WME QoS Info": {
                  "WME QoS Info": {
                    "AC_BE": 0,
                    "AC_BK": 0,
                    "AC_VI": 0,
                    "AC_VO": 0,
                    "Max SP Length": "WMM AP may deliver all buffered frames (MSDUs and MMPDUs)"
                  }
                },
                "WME Subtype": "Parameter Element",
                "WME Version": 1,
                "type": "WMM/WME",
                "vendor": "Wi-Fi : WPA / WME"
              },
              "name": "Vendor Specific",
              "type": 221
            }
          ],
          "last_seen": 2760,
          "signal": 3,
          "ssid": "tls_ssid_wpa3_eap_5g",
          "tsf": 11150813864,
          "vht_oper": "AToA/P8="
        }
      ],
      "text": "Success"
    },
    "uuid": 1657164026
  }
}
```

