# WAN

Configure WAN interface as an upstream interface role type.

OpenWiFi has the concept of a virtual dataplane where the definition of the interface role as upstream or downstream defines if the port involved will be mapped to WAN or LAN operation.

It is possible to re-map any LAN port to function as a normal WAN port in this way.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.37.02 PM.png>)

When the above Interfaces configuration section is created, respond to the dialog prompt to define an upstream WAN then select from the available configuration options to suit the local environment.

![](<../../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.38.22 PM.png>)

Within WAN(upstream) select the port(s) for use as WAN.

A variety of Services features may be associated to logical interfaces. For this example, enable LLDP.

IP Addressing set as IPv4 Dynamic will cause the WAN port to use DHCP for its provisioned internet access. IPv6 dual stack is also supported.
