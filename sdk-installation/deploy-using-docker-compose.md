---
description: TIP OpenWiFi 2.0 SDK
---

# Deploy using Docker Compose

The docker-compose  [directory](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/release/v2.4.0/docker-compose) within the deploy repository contains all the relevant files for various modes of SDK.&#x20;

### Modes&#x20;

The following two modes are currently supported by docker-compose:

*   Deployments without a Load Balancer

    This model is suitable for scenarios where there are no additional needs on handling number of APs. This model contains single instances of SDK micro-services. A single local docker-compose deployment performance is listed [here](../performance/sdk.md). Additionally this deployment includes options to use either self-signed certificates or user provided certificates: &#x20;

    * [Non-LB deployment with self-signed certificates](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/release/v2.4.0/docker-compose#non-lb-deployment-with-self-signed-certificates)
    * [Non-LB deployment with own certificates](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/release/v2.4.0/docker-compose#non-lb-deployment-with-own-certificates)
*   Deployments with a Load Balancer

    This model is suitable for deployments where there is a need to scale performance and/or use Letsencrypt certificates for northbound service interactions. This deployment allows the user to scale up number of instances of micro-services to handle a larger load than listed [here](../performance/sdk.md).  The repository contains the instructions here:&#x20;

    * [LB deployment with self-signed certificates](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/release/v2.4.0/docker-compose#lb-deployment-with-self-signed-certificates)
    * [LB deployment with Letsencrypt certificates](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/release/v2.4.0/docker-compose#lb-deployment-with-letsencrypt-certificates)

&#x20;The  docker-compose yaml files are related as follows to the modes above:

* docker-compose.yml : manages Non-LB deployment with self-signed and own certificates
* docker-compose.lb.selfsigned.yml: manages LB deployment with self-signed certificates
* docker-compose.lb.letsencrypt.yml: manages LB deployment with Letencrypt certificates

### Docker Compose Environment Variables

The deployments are managed using different environment files for docker-compose:

* .env : used for non LB deployments with either self-signed or own certificate deployments executed by docker-compose. For additional information please read [this](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/main/docker-compose#non-lb-deployment-with-self-signed-certificates).
* .env.selfsigned: used for LB with self-signed deployments executed by alias docker-compose-lb-selfsigned. For additional information please read [this](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/main/docker-compose#lb-deployment-with-self-signed-certificates).
* .env.letsencrypt: used for LB with letsencrypt deployments executed by alias docker-compose-lb-letsencrypt. For additional information please read [this](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/tree/main/docker-compose#lb-deployment-with-letsencrypt-certificates).

### Volumes

The deployment creates local volumes to persist mostly application and database data. In addition to that several bind mounts are created:

`docker-compose/certs/` directory used by multiple services

`docker-compose/{microservice}_data/` directory used by each service for configuration and data. Where {microservice} is one of: owgw, owsec, owfms and owprov.&#x20;

{% hint style="info" %}
Be aware that the deployment uses bind mounts on the host to mount certificate and configuration data for the micro services and therefore these files and directories will be owned by the user in the container.\
Since the files are under version control, you may have to change the ownership to your user again before pulling changes.
{% endhint %}

### Configuration

This configuration information specific to the deployment is kept in environment files per microservices. These files are: owgw.env, owgw-ui.env, owsec.env, owfms.env, owprov.env and owprov-ui.env. These env files are used to generated the runtime configuration(properties) file when no configuration is found in their respective {microservices}-data directory. &#x20;

### Ports

Exposed port dependencies by application are listed below:

`127.0.0.1:80/443 tcp` - OpenWiFi-uCentralGW-UI\
`127.0.0.1:8080/8443 tcp` - OpenWiFi-Provisoning-UI\
`127.0.0.1:5912/tcp` - rttys dev\
`127.0.0.1:5913/tcp` - rttys user\
`0.0.0.0:15002/tcp` - OpenWiFi-uCentralGW websocket\
`127.0.0.1:16002/tcp` - OpenWiFi-uCentralGW REST API public\
`0.0.0.0:16003/tcp` - OpenWiFi-uCentralGW fileupload\
`127.0.0.1:16102/tcp` - OpenWiFi-uCentralGW alivecheck\
`127.0.0.1:16001/tcp` - OpenWiFi-uCentralSec REST API public\
`127.0.0.1:16101/tcp` - OpenWiFi-uCentralSec alivecheck

{% hint style="info" %}
By default only the websocket and fileupload component of the OpenWiFi uCentralGW (Gateway) micro service are exposed on all interfaces. All other exposed services listen on localhost. You can change that according to your needs in the `ports` sections of`docker-compose/docker-compose.yml`.
{% endhint %}

### Certificates

The repository includes a TIP Root CA Digicert-signed (for the Gateway websocket to devices) and a self-signed certificate (for the REST API northbound and other components), which you can use to create a local deployment out of the box.

The certificates are valid for the `*.wlan.local` domain.

## How to

1. First you'll have to [install Docker Compose](https://docs.docker.com/compose/install/) according to your platform specific instructions. After that clone the repository with `git clone https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy`. &#x20;
2. The Docker Compose uCentral micro service configs use `openwifi.wlan.local` as a hostname, so make sure you add an entry in your hosts file (or in your local DNS solution) which points to `127.0.0.1` or whatever the IP of the host running the deployment is. &#x20;
3. Switch to the Compose project directory with `cd docker-compose/`. &#x20;
4. Set the default user and temporary password by following instruction of security service [here](https://github.com/Telecominfraproject/wlan-cloud-ucentralsec/tree/main#default-username-and-password).
5.  Edit owsec.env and ensure the following variable contains the username and shasum from step 4:

    ```
    AUTHENTICATION_DEFAULT_USERNAME=##username from step 4##
    AUTHENTICATION_DEFAULT_PASSWORD=##hash from step 4##
    ```
6. Spin up the deployment with `docker-compose up -d`. If your deployment was successfully created, you should see the following output with `docker-compose ps`:

```
          Name                      Command               State                                                   Ports
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
openwifi_kafka_1       /opt/bitnami/scripts/kafka ...   Up      9092/tcp
openwifi_owfms_1       /docker-entrypoint.sh /ope ...   Up      0.0.0.0:16004->16004/tcp,:::16004->16004/tcp, 0.0.0.0:16104->16104/tcp,:::16104->16104/tcp, 17004/tcp
openwifi_owgw-ui_1     /docker-entrypoint.sh ngin ...   Up      0.0.0.0:443->443/tcp,:::443->443/tcp, 0.0.0.0:80->80/tcp,:::80->80/tcp
openwifi_owgw_1        /docker-entrypoint.sh /ope ...   Up      0.0.0.0:15002->15002/tcp,:::15002->15002/tcp, 0.0.0.0:16002->16002/tcp,:::16002->16002/tcp,
                                                                0.0.0.0:16003->16003/tcp,:::16003->16003/tcp, 0.0.0.0:16102->16102/tcp,:::16102->16102/tcp, 17002/tcp
openwifi_owprov-ui_1   /docker-entrypoint.sh ngin ...   Up      80/tcp, 0.0.0.0:8080->8080/tcp,:::8080->8080/tcp, 0.0.0.0:8443->8443/tcp,:::8443->8443/tcp
openwifi_owprov_1      /docker-entrypoint.sh /ope ...   Up      0.0.0.0:16005->16005/tcp,:::16005->16005/tcp, 0.0.0.0:16105->16105/tcp,:::16105->16105/tcp, 17005/tcp
openwifi_owsec_1       /docker-entrypoint.sh /ope ...   Up      0.0.0.0:16001->16001/tcp,:::16001->16001/tcp, 0.0.0.0:16101->16101/tcp,:::16101->16101/tcp, 17001/tcp
openwifi_rttys_1       /rttys/rttys                     Up      0.0.0.0:5912->5912/tcp,:::5912->5912/tcp, 0.0.0.0:5913->5913/tcp,:::5913->5913/tcp
```

1.  Since the certificate for the REST API and other components is self-signed, you have to add it to the system trust store of the containers communicating together internally via TLS. The `add-ca-cert.sh` script located in the Compose project directory does the work for you.

    You also have to trust the self-signed REST API certificate on your local machine. To achieve that you either have to add `certs/restapi-ca.pem` to your trusted browser certificates or add certificate exceptions in your browser by visiting `https://ucentral.wlan.local:16001` and `https://ucentral.wlan.local:16002` and accepting the self-signed SSL certificate warnings (make sure to visit both and add the exceptions).
2. Connect to your AP via SSH and add a static hosts entry in `/etc/hosts` for `openwifi.wlan.local` which points to the address of the host the Compose deployment runs on.
3. While staying in the SSH session, copy the content of `certs/restapi-ca.pem` on your local machine to your clipboard and append it to the file `/etc/ssl/cert.pem` on the AP. This way your AP will also trust the self-signed certificate. &#x20;
4. Go to `http://openwifi.wlan.local` to visit the UI and login with default username and password. You will now be prompted to change this default password to something more secured. &#x20;
5. To use the curl test scripts which are included in the  micro service repositories make sure to set the following environment variables before issuing a request:

```
export UCENTRALSEC="openwifi.wlan.local:16001"
export FLAGS="-s --cacert <your-wlan-cloud-ucentral-deploy-location>/docker-compose/certs/restapi-ca.pem"
```

### Upgrading Compose Deployments

Stop the running containers with `docker-compose down`

Check out the new branch by repeating _Step 1_ from _How to_ above for the given release and `docker-compose up -d`.

Don’t forget to re-add the self-signed certificates to the containers with the provided script.\
Also be aware that you may have to change back some file permissions. To obtain the most recent changes as the files are under version control, you may have to change the ownership to your user again before pulling changes.
