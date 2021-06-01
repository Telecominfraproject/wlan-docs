---
description: TIP OpenWiFi
---

# Cloud SDK

With the Cloud SDK now installed into either a public cloud or on premises, logging in with default username **support@example.com** and password **support** are now possible.

![Default Login Page](../.gitbook/assets/screen-shot-2020-11-29-at-4.25.44-pm.png)

Once successfully logged in, please refer to [User Interface](../user-interface/) documentation for further details of specific configuration.

{% hint style="info" %}
Current TIP Cloud SDK deploys using self-signed certificates. This requires accepting the self-signed certificate in the UI for the following URLs:  
[https://wlan-ui.wlan.local](https://wlan-ui.wlan.local)  
[https://wlan-ui-graphql.wlan.local](https://wlan-ui-graphql.wlan.local)  
Navigate to both URLs and accept the certificate exception.  
Once the client browser has these certificate exceptions loaded login will succeed.
{% endhint %}

