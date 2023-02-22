# Restricted Unit Support

Starting release v2.8.0, APNOS allows the ability for community members to provide regulatory domain restrictions as their end product use cases.  APNOS and the SDK provides generic building blocks for restricting various aspects of the unit.&#x20;

The initial requirements for this feature are captured [here](https://telecominfraproject.atlassian.net/wiki/spaces/WIFI/pages/1717338113/Standard+TIP+AP+SKU+with+FCC+certification).&#x20;

By default APNOS is open and not considered restricted. To enable restriction the unit must have restrictions.json file in the /certificate directory at the time of factory. The restrictions.json file has the following format:

```
{
    "commands": true,
    "country": [
      "US",
      "CA"
    ],
    "dfs": true,
    "key_info": {
      "algo": "static",
      "vendor": "dummy"
    },
    "rtty": true,
    "sysupgrade": true,
    "tty": true
}
```

Here are description of the keys above:\
country:\
commands:\
dfs:\
key\_info:\
rtty:\
sysupdate:\
tty:
