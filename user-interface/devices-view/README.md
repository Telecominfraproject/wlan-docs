---
description: OpenWiFi 2.0 SDK
---

# Devices

Each device presents Metrics and Health check data to the Gateway. Devices view displays this information in the following organization:

* Status&#x20;
* Configuration
* Logs
* Health
* Commands
* Statistics
* Command History

![Initial Device View](<../../.gitbook/assets/Screen Shot 2021-07-28 at 5.15.03 PM.png>)

## Status

Connection status reflects the Gateway to Device current communications status.\
Uptime and Last Contact reflect communication state.\
Load indicates processing load on the device.\
Memory Used indicates free memory on the device.

![Device Status](<../../.gitbook/assets/Screen Shot 2021-07-28 at 5.17.59 PM.png>)

## Configuration

Device UUID, Serial Number, MAC Address and Device Type are displayed.\
Last configuration update date and timestamp reflects the last time a "configure" action completed on the device.\
Password may be set and device notes may be added.

![Device view Configuration Panel](<../../.gitbook/assets/Screen Shot 2021-07-28 at 5.21.07 PM.png>)

## Logs

Log history of the device is presented within Logs. Expand the tile selecting the down arrow.

![](<../../.gitbook/assets/Screen Shot 2021-07-28 at 5.25.29 PM.png>)

## Health

Health score is an active tile reflecting the device health out of a score reported by the device to Gateway. Health metrics are configured on the device based on chosen data model options. When the device falls out of 100%, this tile changes to red. Expanding the tile will present all health reports. Those with less than 100% score will contain reasons for the result from this interface.

![](<../../.gitbook/assets/Screen Shot 2021-07-28 at 5.24.00 PM.png>)

## Commands

Commands tile provides a number of administrative actions for the user:

| Command          | Action                                                  |
| ---------------- | ------------------------------------------------------- |
| Reboot           | Warm Restart remote device                              |
| Firmware Upgrade | Initiate firmware upgrade process                       |
| WiFi Scan        | Initiate remote scan of surrounding Wi-Fi               |
| Connect          | Initiate an rTTY Remote Shell session                   |
| Blink            | Set LEDs to On, Off or Blinking state                   |
| Trace            | Initiate a remote Packet Capture                        |
| Factory Reset    | Hard Reset remote device - destroys device local config |
| Configure        | Upload Device Configuration                             |

![Commands Tile](<../../.gitbook/assets/Screen Shot 2021-07-28 at 5.25.50 PM.png>)
