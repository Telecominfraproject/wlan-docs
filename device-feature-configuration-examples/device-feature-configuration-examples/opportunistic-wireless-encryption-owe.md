# Opportunistic Wireless Encryption (OWE)

APNOS now support OWE mode of authentication. In addition OWE Transition mode is support for clients that are not able to support OWE mode. In transition mode, there should be two SSIDs, one is Open SSID and other one is OWE SSID. The open SSID should broadcast and the OWE SSID should be hidden.

The following encryption block is added to interfaces->ssids block:

```
"encryption": {
    "proto": "owe",
    "ieee80211w": "required"
}
```

Configuration with owe transition mode block is done by using the following encryption block:

<pre><code>"encryption": {
<strong>    "proto": "owe-transition",
</strong>    "ieee80211w": "required"
}
</code></pre>
