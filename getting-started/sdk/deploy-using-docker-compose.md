---
description: OpenWiFi 2.0 SDK
---

# Deploy using Docker Compose

The [wlan-cloud-ucentral-deploy repository](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy) contains a Compose file and the related files and directories to set up a local uCentral instance with Docker Compose. You'll find all related data under the `docker-compose/` directory.

### Volumes

The deployment creates local volumes to persist mostly application and database data. In addition to that several bind mounts are created:

`docker-compose/certs/` directory used by multiple services

Service specific data directories and configuration files located under `docker-compose/` mounted into the appropriate containers.

{% hint style="info" %}
Be aware that the deployment uses bind mounts on the host to mount certificate and configuration data for the micro services and therefore these files and directories will be owned by the user in the container.  
Since the files are under version control, you may have to change the ownership to your user again before pulling changes.
{% endhint %}

### Configuration

Changing image tags used in the deployments may be performed in `docker-compose/.env`.

By default this file specifies the micro service image tags according to the release branch you have checked out.

Additional configuration changes such as database settings or passwords are found in the various other service specific `.env` files.

The rest of the configuration is done through the config files located in the appropriate subdirectories of the Compose project directory.

### Ports

Exposed port dependencies by application are listed below:

`127.0.0.1:80/tcp` - OpenWiFi-UI  
`127.0.0.1:5912/tcp` - rttys dev  
`127.0.0.1:5913/tcp` - rttys user  
`0.0.0.0:15002/tcp` - OpenWiFi-uCentralGW websocket  
`127.0.0.1:16002/tcp` - OpenWiFi-uCentralGW REST API public  
`0.0.0.0:16003/tcp` - OpenWiFi-uCentralGW fileupload  
`127.0.0.1:16102/tcp` - OpenWiFi-uCentralGW alivecheck  
`127.0.0.1:16001/tcp` - OpenWiFi-uCentralSec REST API public  
`127.0.0.1:16101/tcp` - OpenWiFi-uCentralSec alivecheck

{% hint style="info" %}
By default only the websocket and fileupload component of the OpenWiFi uCentralGW \(Gateway\) micro service are exposed on all interfaces. All other exposed services listen on localhost. You can change that according to your needs in the `ports` sections of`docker-compose/docker-compose.yml`.
{% endhint %}

### Certificates

The repository includes a TIP Root CA Digicert-signed \(for the Gateway websocket to devices\) and a self-signed certificate \(for the REST API northbound and other components\), which you can use to create a local deployment out of the box.

The certificates are valid for the `*.wlan.local` domain.

## How to

1. First you'll have to [install Docker Compose](https://docs.docker.com/compose/install/) according to your platform specific instructions. After that clone the repository with `git clone https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy`.  
2. The Docker Compose uCentral micro service configs use `ucentral.wlan.local` as a hostname, so make sure you add an entry in your hosts file \(or in your local DNS solution\) which points to `127.0.0.1` or whatever the IP of the host running the deployment is.  
3. Switch to the Compose project directory with `cd docker-compose/`.  
4. Spin up the deployment with `docker-compose up -d`. If your deployment was successfully created, you should see the following output with `docker-compose ps`:

```text
              Name                             Command               State                                                             Ports
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
ucentral_kafka_1                    /opt/bitnami/scripts/kafka ...   Up      9092/tcp
ucentral_rttys_1                    /rttys/rttys                     Up      127.0.0.1:5912->5912/tcp, 127.0.0.1:5913->5913/tcp
ucentral_ucentralgw-ui_1            /docker-entrypoint.sh ngin ...   Up      127.0.0.1:80->80/tcp
ucentral_ucentralgw.wlan.local_1    /bin/sh -c /ucentral/ucent ...   Up      0.0.0.0:15002->15002/tcp, 127.0.0.1:16002->16002/tcp, 0.0.0.0:16003->16003/tcp, 127.0.0.1:16102->16102/tcp, 17002/tcp
ucentral_ucentralsec.wlan.local_1   /bin/sh -c /ucentral/ucent ...   Up      127.0.0.1:16001->16001/tcp, 127.0.0.1:16101->16101/tcp, 17001/tcp
ucentral_zookeeper_1                /docker-entrypoint.sh zkSe ...   Up      2181/tcp, 2888/tcp, 3888/tcp, 8080/tcp
```

1. Since the certificate for the REST API and other components is self-signed, you have to add it to the system trust store of the containers communicating together internally via TLS. The `add-ca-cert.sh` script located in the Compose project directory does the work for you.  

   You also have to trust the self-signed REST API certificate on your local machine. To achieve that you either have to add `certs/restapi-ca.pem` to your trusted browser certificates or add certificate exceptions in your browser by visiting `https://ucentral.wlan.local:16001` and `https://ucentral.wlan.local:16002` and accepting the self-signed SSL certificate warnings \(make sure to visit both and add the exceptions\).  

2. Connect to your AP via SSH and add a static hosts entry in `/etc/hosts` for `ucentral.wlan.local` which points to the address of the host the Compose deployment runs on.  
3. While staying in the SSH session, copy the content of `certs/restapi-ca.pem` on your local machine to your clipboard and append it to the file `/etc/ssl/cert.pem` on the AP. This way your AP will also trust the self-signed certificate.  
4. Go to `http://ucentral.wlan.local` to visit the UI and login with username `tip@ucentral.com` and password `openwifi` if you didn't change the default credentials in the uCentralSec configuration.  
5. To use the curl test scripts which are included in the  micro service repositories make sure to set the following environment variables before issuing a request:

```text
export UCENTRALSEC="ucentral.wlan.local:16001"
export FLAGS="-s --cacert <your-wlan-cloud-ucentral-deploy-location>/docker-compose/certs/restapi-ca.pem"
```

