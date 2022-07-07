# Device Event Queue

## Single Event (DHCP Example)

```json
{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "events": {
      "dhcp": []
    },
    "serial": "c44bd1005b30",
    "status": {
      "error": 0,
      "text": "Success"
    },
    "uuid": 1656049674
  }
```

## Multiple Events

```json
{
  "system": {
    "id": 1637414624750592500,
    "host": "https://owgw-owgw:17002"
  },
  "payload": {
    "events": {
      "dhcp": [],
      "wifi": []
    },
    "serial": "0000c1018812",
    "status": {
      "error": 0,
      "text": "Success"
    },
    "uuid": 1657087470
  }
}
```
