---
description: TIP OpenWiFi 2.0
---

# Access Points

Initial Minimum Viable Product Release 2.0 does not include template driven device provisioning, this will be available in the next sprint.

Given many cloud and ODM partners wish to consume the 2.0 reference stack early, some with their own device provisioning logic as part of commercial cloud controllers, the following describes uCentral based management and telemetry, interactions with the OpenWiFi SDK processing provisioning and telemetry data.

## Device Interactions with SDK

![OpenWiFi with uCentral Management](../../.gitbook/assets/image%20%2822%29.png)

OpenWiFi 2.0 follows the uCentral system. Complete data model is available [here](http://ucentral.io/docs/ucentral-schema.html). Upon discovery of the cloud, a device default or specific configuration is transferred.

All devices are known to the cloud by their unique id and provisioned based on advertised capabilities. Each configuration generates a new unique hash value to ensure as devices report back to the cloud, their configuration state is guaranteed.

If the cloud sends invalid configuration data or the device has insufficient ability to complete the provisioning commands, the error handling process will send this response back to the cloud.

For example results returned to SDK from a device configuration error:

```text
"results": { 
  "serial": "aabbcc00120a",  
       "status": {    
          "error": 0,  
                "rejected": [   
                             "[W] ("A Reason will be given"
                             ],
```

