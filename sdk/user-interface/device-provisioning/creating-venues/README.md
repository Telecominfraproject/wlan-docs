# Creating Venues

Venues are an important concept in OpenWIFi Provisioning. Venues inherit access to Analytics where incoming telemetry and client events are aggregated from the message bus, transformed and correlated based on the members of the Venue resulting in Venues Dashboard, Live Client quality connection analysis, and client tracking through the venue.

{% hint style="info" %}
Venues may not exist beneath the root entity. Create an entity prior to defining a venue
{% endhint %}

### Create a Venue

Within a non-root entity, Create a Venue.

![](<../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.21.43 PM.png>)

Once the Venue exists, navigate into the Venue.

### Venue Configurations

Within a Venue, the RRM and Firmware management rules may be defined. Note Analytics are now an available option within the Venue. To track device and client statistics, enable Analytics.

![](<../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.24.18 PM.png>)

Choose Edit and Start Monitoring. This will enable the admin to determine the interval of analytic data aggregation, and the data retention window in days.

![](<../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.25.43 PM.png>)

When Analytics are enabled, the Dashboard is populated. As devices are associated to the Venue, their telemetry data is aggregated by Analytics service and correlated for display via Dashboard, Live View and Client Lifecycle.

![](<../../../../.gitbook/assets/Screen Shot 2022-07-20 at 1.29.54 PM.png>)
