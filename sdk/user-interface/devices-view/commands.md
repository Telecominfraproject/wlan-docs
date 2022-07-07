---
description: OpenWiFi 2.0 SDK
---

# Commands

Within the devices view, the Commands tile offers a number of features and administrative actions. Each of these represent API calls exposed on the OpenAPI northbound interface from the SDK.

## Reboot

Selecting the Reboot action will prompt the below dialog. Options presented permit an immediate reboot or a scheduled reboot based on date and time.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.25.03 PM.png>)

## Firmware Upgrade

Multiple methods exist to execute a remote Firmware Upgrade of a device. When selecting Firmware Upgrade via the Commands tile, a simple dialog to upgrade immediately or at a scheduled time is presented. Alternatively using the Firmware Management Service provides a complete solution including managed access to all TIP firmware images.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.28.44 PM (1).png>)

## Wi-Fi Scan

OpenWiFi devices may perform channel scanning and return this neighbor and RF data to the SDK in an on demand or ongoing manner.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.31.03 PM.png>)

### Wi-Fi Scan Results

Scan operations function over all channels. If 5GHz channels do not display in the returned results ( either via the UI or over API ) this indicates the device is configured in a DFS channel for which it may not return survey scans at this time.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.33.58 PM (1).png>)

## Connect

OpenWiFi enables remote connection to any managed device using rTTY encrypted shell session. Selecting Connect will cause a browser tab to open with the login session to current device.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.35.48 PM.png>)

## Blink

To assist with remote identification of devices in the network, it is possible to turn the LED lights On, Off, of continuous blinking. This may be run on-demand or scheduled.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.37.30 PM (1).png>)

## Trace

Trace feature enables a remote packet capture to occur on the managed device, over a specified period of time or amount of traffic, returning the "pcap" packet capture file locally to the OpenWiFi admin user.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.39.24 PM (1).png>)

Once complete the user is asked to open or save the packet capture file locally.

![](<../../../.gitbook/assets/image (33).png>)

## Factory Reset

It is possible to revert a device to initial out of box state from the OpenWiFi SDK. Sending a Factory Reset will remove all configuration on the device and optionally reset the discovered cloud stored as the 'Redirector' in the device configuration.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.46.29 PM.png>)

{% hint style="info" %}
Note: When Redirector is not kept, devices will re-contact the Certificate Authority to re-discover their OpenWiFi cloud address
{% endhint %}

## Configure

Prior to the introduction of OpenWiFi 2.0 Provisioning Service, device configuration is done through creation of the JSON provisioning file and either loading that file or applying its contents using the dialog presented via Configure. The same options exist when using the API directly.

![](<../../../.gitbook/assets/Screen Shot 2021-07-29 at 2.48.31 PM.png>)
