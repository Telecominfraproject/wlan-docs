# Service Events

## Keep-alive

This message is sent by all SDK micro-services.

```json
{
  "event": "keep-alive",
  "id": 1651799646949140500,
  "key": "c34b2bcafc78460025740e82922dc43ccb41d40d8d474e909a4b7065005e595e",
  "privateEndPoint": "https://owanalytics-owanalytics:17009",
  "publicEndPoint": "https://analytics-qa01.cicd.lab.wlan.tip.build:16009",
  "type": "owanalytics",
  "version": "2.6.0(69) - v2.6.0-RC3"
}
```

## Remove Token

```json
{
  "event": "remove-token",
  "id": 1637312489719148300,
  "token": "0a6cdf595818e6da496c11a6794a6084b456425fa87181e1d350175096729f6a"
}
```
