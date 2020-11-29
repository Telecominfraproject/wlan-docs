# API

TIP Open Wi-Fi project is a data-model driven design, meaning the features in the solution are designed as interfaces to be consumed either by micro-services, network devices, or other applications integrating with the solution. 

The most useful way to learn the TIP Open Wi-Fi API is to consume the Swagger interface that fully describes all implemented REST methods. 

TIP Open Wi-Fi controller uses OAuth for authentication. A bearer token must first be obtained for subsequent API calls to succeed. 

### Curl Request to controller for Bearer Token

```text
curl -k --request POST --header "Content-Type: application/json; charset=utf-8" --data '{"userId":"support@example.com","password":"support"}'   https://${portal-service-ip:port}/management/v1/oauth2/token
```

### Successful Response

```text
{
  "model_type" : "WebTokenResult",
  "twoFactorAuthenticationRequired" : false,
  "resetPassword" : false,
  "access_token" : "eyJpc3MiOiJ0aXAiLCJqdGkiOiI2OTM1NTg3OC1jOGVhLTRiMTItOWU3OS0zMTMyOGJlNWQ1NTEiLCJleHBpcnlUaW1lIjoxNjA2Njg5MjA2MjEyLCJjdXN0b21lcklkIjoyLCJ1c2VyTmFtZSI6InN1cHBvcnRAZXhhbXBsZS5jb20iLCJ1c2VySWQiOjAsInVzZXJSb2xlIjoiU3VwZXJVc2VyIn0=.UYKrayawxxtw9qLbqW70rgOcjSY7oUp8XpalyiGAwUF6zRRsXQ0ILJxvKZxpAwftU4nNosmSS3i2j/vRr5gtD.",
  "refresh_token" : "eyJpc3MiOiJ0aXAiLCJqdGkiOiIwZWU2MjAzZi1iNWI0LTRlZGMtYTM1My0yZWUxZGMwOTUzMzMiLCJleHBpcnlUaW1lIjoxNjA2Njg5ODA2MjMyLCJjdXN0b21lcklkIjoyLCJ1c2VyTmFtZSI6InN1cHBvcnRAZXhhbXBsZS5jb20iLCJ1c2VySWQiOjAsInVzZXJSb2xlIjoiU3VwZXJVc2VyIiwicmVmcmVzaCI6dHJ1ZX0=.hiE1Pcb2O0wUNw/ySga6IqPtmgcAkeMAxrMOC85ZN1AJ2v/WLik6DCVoBk8VZXcJNoEc9Gr6WE7RrtMpJGSee1",
  "id_token" : null,
  "token_type" : "Bearer",
  "expires_in" : 3000,
  "idle_timeout" : 3600,
  "aclTemplate" : {
    "model_type" : "WebTokenAclTemplate",
    "aclTemplate" : {
      "Delete" : true,
      "Read" : true,
      "PortalLogin" : true,
      "ReadWrite" : true,
      "ReadWriteCreate" : true
    },
    "alias" : 2,
    "id" : "",
    "name" : "Webtoken Portal Login",
    "versionTimestamp" : 1551549825443000
  }
}
```

Use the value from access\_token for subsequent API calls into the controller

