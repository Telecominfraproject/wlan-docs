---
description: OpenWiFi SDK 2.0
---

# Command History

Multiple events are recorded in the Command History tile. Each line item will have a Result, Details, and Delete action.

![Command History Tile](../../.gitbook/assets/screen-shot-2021-07-29-at-3.10.22-pm.png)

When an rTTY session is executed, this is a displayed command history. Selecting the Result icons will display the Success or Fail of the command.

![rTTY Command History](../../.gitbook/assets/screen-shot-2021-07-29-at-3.12.02-pm.png)

Each provisioning event is reflected as a configure command history. To see the entire JSON payload and the result, including success or error with message, simply select Details to expand the dialog below with this data. A date and time in the third column indicates when the configure command was executed successfully.

![Configure Command History](../../.gitbook/assets/screen-shot-2021-07-29-at-3.12.27-pm.png)

If a provisioning event has failed to complete, its command history for configure will show as pending.

![configure Pending Command History](../../.gitbook/assets/screen-shot-2021-07-29-at-3.18.12-pm.png)

Remote packet capture is shown as the trace command history. When packet captures are persisted in the OpenWiFi SDK, they may be downloaded again through the cloud download icon.

![trace Command History](../../.gitbook/assets/screen-shot-2021-07-29-at-3.16.52-pm.png)

