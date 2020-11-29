# Swagger

TIP Open Wi-Fi controller implements an Open API compliant NorthBound Interface \(NBI\) to assist with integration and related back office features.  

Swagger is a useful tool to explore and learn any system API. 

### Obtain latest TIP Controller Open API data model

{% embed url="https://github.com/Telecominfraproject/wlan-cloud-services/blob/master/portal-services/src/main/resources/portal-services-openapi.yaml" caption="TIP Github repo link to Open API data model " %}

### Install Swagger

```text
mkdir ~/swagger
cd ~/swagger
git clone https://github.com/swagger-api/swagger-editor.git
cd swagger-editor
git clone https://github.com/swagger-api/swagger-ui.git
cd ~/swagger/swagger-editor
npm install
npm run build
npm start
```

With Swagger running, open the Open API data model file and begin to use locally on port 9091 or add your own TIP Open Wi-Fi controller to the Swagger definitions. Remember to obtain an [OAuth bearer ](./#curl-request-to-controller-for-bearer-token)token to 'Authorize' your session. 

![Successful login to Swagger on localhost:9091 ](../.gitbook/assets/swagger.jpeg)



