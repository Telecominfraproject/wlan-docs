# Access Points

TIP OpenWiFi devices are available from many hardware partners. All TIP OpenWiFi devices have the same standard image of open source software.

TIP OpenWiFi 1.0 devices run OpenWrt operating system with OpenSync as a management stack.   
The use of OpenWrt is largely upstream based on OpenWrt 19.07 in OpenWiFI 1.0.

When a TIP firmware image is created, the system will merge TIP specific patches, kernel specific patches, and build this with the target OpenWrt 19.07 operating system as one complete firmware image. From this process a TIP OpenWiFi standard firmware results with the following settings.

### Device Defaults

| Defaults | Values |
| :--- | :--- |
| Login: root | Password: openwifi |
| Default LAN | 192.168.1.1/24  |
| Default WAN | DHCP |

### Unable to Connect to WAN or Controller

If the OpenWiFi device has been unable to reach the internet or the assigned controller, the 'Maverick' SSID will appear. Joining this Wi-Fi network will join the local management interface to help onboard the device to the internet and controller.

After joining Maverick SSID, opening a web browser to the address 192.168.1.1 where the following login displays. Enter root login and password.

![Maverick Local Web Page](../.gitbook/assets/image%20%2811%29.png)

Common setup to enable internet access is available. WAN interface defaults to DHCP, if the WAN requires static configuration select the drop down to continue:

![Connectivity Maverick Page](../.gitbook/assets/image%20%2815%29.png)

Changing the Local Area Network is also possible from Maverick mode. There may be cases where an IP overlap has occurred in certain double NAT internal networks. For this reason it may be necessary to change this value, else no change is required here:

![Maverick LAN Page](../.gitbook/assets/image%20%2814%29.png)

It is possible to apply a firmware update from the Maverick interface. This operation is normally performed by the controller however in the event it is desired, have the `sysupgrade` image downloaded locally before continuing:

![Maverick based firmware upgrade](../.gitbook/assets/image%20%289%29.png)

Manually setting the cloud location may be done using its Fully Qualified Domain Name \(FQDN\) in the Redirector field. Device certificates are unique per TIP OpenWiFi access point or switch. It should not be required to change these values at any time. Please exercise caution if replacing certificates manually. 

![Maverick set Cloud &apos;Redirector&apos;](../.gitbook/assets/image%20%2817%29.png)

###
