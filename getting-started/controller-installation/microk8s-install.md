---
description: TIP Controller Local Deployment
---

# microk8s Install

## Base System

Microk8s deployment is considered experimental as there remain certain UI to Ingress SSL related issues as of Release 1.0 candidate.  
API services, database, message bus and ability to adjust Kubernetes POD performance parameters are all possible with this system which may be useful to the Community.

A snap capable operating system is required for microk8s installation.  
TIP Controller has been installed on an Ubuntu 20 system with 32Gb memory, 500Gb disk and Gigabit Ethernet network interface with a user account tip created.

The system should have a fully qualified domain name and the deployment of TIP controller will require additional DNS records to be created.

Local /etc/hosts should contain the following DNS entires for your controller assigned to the IP address your machine is using to connect to the network. This same IP will be used when configuring metallb address in a subsequent step.

When accessing the UI from a workstation or when AP is connecting to the local controller the local DNS server will need to provide authoritative response for these A records in the wlan.local domain.  
In a future release of TIP Controller instructions will be provided to modify the FQDN of all Controller services.

DNS default entries for /etc/hosts

```text
## Replace with your system IP address 
<IP Address> wlan-ui.wlan.local wlan-ui-graphql.wlan.local opensync-redirector.wlan.local opensync-controller.wlan.local opensync-mqtt-broker.wlan.local wlan-filestore.wlan.local
```

Install microk8s

```text
$ sudo snap install microk8s --classic --channel=latest/stable
```

{% hint style="info" %}
The above specifies latest stable release will be installed
{% endhint %}

Set user permissions

```text
sudo usermod -a -G microk8s tip
sudo chown -f -R tip ~/.kube
```

{% hint style="info" %}
source or re-login to shell for environment to be applied
{% endhint %}

Setup microk8s

```text
microk8s enable helm3 dns storage metallb
```

{% hint style="info" %}
metlalb will request an IP address range. Specify the IP of Gigabit Ethernet interface.  
If your interface address is 10.1.1.1 then provide metallb with: 10.1.1.1-10.1.1.1
{% endhint %}

### Begin Controller Setup

TIP Controller may be deployed with self-signed certificates for a local lab environment. The following steps will guide the reader through that process.

Install Keytool

```text
sudo apt install -y openjdk-11-jre-headless 
sudo apt install -y default-jdk
```

Enable Firewall to permit Controller traffic from Container Network Interface

```text
sudo ufw allow in on cni0 && sudo ufw allow out on cni0
sudo ufw default allow routed
```

#### Downloading TIP Controller Software

{% hint style="info" %}
Change to a directory for configuring certificates and running controller. This can be within the tip home directory.
{% endhint %}

#### Obtain Controller PKI Certs Locally

```text
git clone https://github.com/Telecominfraproject/wlan-pki-cert-scripts.git
```

#### Obtain Controller Locally

```text
git clone https://github.com/Telecominfraproject/wlan-cloud-helm.git
```

From the current directory, two sub-directories now exist for wlan-pki-certs and wlan-cloud-helm.  
Enter the PKI directory and the configs sub-directory `cd /wlan-pki-cert-scripts/configs`

Modify all certificate configuration files for the value of your organizationalUnitName\_default value set to your organizational name or other string value used in each of the PKI certificate files. Optionally this may be left unchanged.

Within the following files, ensure the FQDN \(Fully Qualified Domain Name\) based on local setup for DNS aligns accordingly. The following files are updated per:

* mqtt-server.cnf

  `commonName_default = opensync-mqtt-broker.FQDN`

* openssl-server.cnf

  `DNS.1 = opensync-redirector.FQDN`

  `DNS.2 = opensync-controller.FQDN`

Once complete generate the service certificates and copy these to the controller.

```text
cd wlan-pki-cert-scripts 
./generate_all.sh 
./copy-certs-to-helm.sh ~/wlan-cloud-helm/
```

{% hint style="info" %}
`Note within the wlan-pki-cert-scripts folder, a subfolder /generated is present after key creation.`

`The AP.zip archive in the generated folder contains the Access Point certificates for loading onto APs in the AP /usr/opensync/certs device folder`
{% endhint %}

### Deploy Controller

TIP controller defaults to a domain of wlan.local. It is possible to operate a lab DNS service permitting local resolution of this domain for the TIP controller services. Certificate instructions for a self-signed private domain will follow in a subsequent release of service and documentation.

```text
cd ~/wlan-cloud-helm
microk8s helm3 dependency update tip-wlan
microk8s kubectl create namespace tip
microk8s helm3 upgrade --install tip-wlan tip-wlan/ --namespace tip -f tip-wlan/resources/environments/dev-microk8s.yaml
```

Helm will deploy the Controller containers within a TIP namespace to microk8s on the machine.

```text
Release "tip-wlan" does not exist. Installing it now.
NAME: tip-wlan
LAST DEPLOYED: Wed Feb  3 20:45:13 2021
NAMESPACE: tip
STATUS: deployed
REVISION: 1
TEST SUITE: NoneCheck Controller Status
```

To check status of the PODs, Services, and Persistent Volume Claims \(storage\) use the following commands. Please note, depending on your server, all PODs may take several minutes to fully initialize.

```text
microk8s kubectl get services -n tip
microk8s kubectl get pvc -n tip
microk8s kubectl get pods -n tip
```

{% hint style="info" %}
Get svc will return the network Services of each container port maps as well as list of containers mapped to external IP address defined during the metallb config stage earlier.

Get pvc will return the Persistent Volume Claims of the containers to the microk8s storage service

Get pods will return the current state of all containers. The controller will require two to four minutes for all pods to reach 'Running' state.
{% endhint %}

Examples of all three commands:

```text
tip@microk8slocal:~$ microk8s kubectl get svc -n tip
NAME                                TYPE           CLUSTER-IP       EXTERNAL-IP   PORT(S)                                                       AGE
tip-wlan-postgresql-headless        ClusterIP      None             <none>        5432/TCP                                                      47h
tip-wlan-kafka-headless             ClusterIP      None             <none>        9093/TCP                                                      47h
tip-wlan-cassandra-headless         ClusterIP      None             <none>        7000/TCP,7001/TCP,7199/TCP,9042/TCP,9160/TCP                  47h
tip-wlan-zookeeper-headless         ClusterIP      None             <none>        2181/TCP,3888/TCP,2888/TCP                                    47h
tip-wlan-postgresql-read            ClusterIP      10.152.183.145   <none>        5432/TCP                                                      47h
tip-wlan-cassandra                  ClusterIP      10.152.183.31    <none>        9042/TCP,9160/TCP                                             47h
tip-wlan-zookeeper                  ClusterIP      10.152.183.75    <none>        2181/TCP                                                      47h
tip-wlan-wlan-cloud-static-portal   NodePort       10.152.183.7     <none>        80:32186/TCP                                                  47h
tip-wlan-wlan-cloud-graphql-gw      NodePort       10.152.183.117   <none>        4000:30223/TCP                                                47h
tip-wlan-kafka                      ClusterIP      10.152.183.42    <none>        9093/TCP                                                      47h
tip-wlan-wlan-spc-service           ClusterIP      10.152.183.165   <none>        9041/TCP,9042/TCP                                             47h
tip-wlan-postgresql                 ClusterIP      10.152.183.216   <none>        5432/TCP                                                      47h
tip-wlan-nginx-ingress-controller   LoadBalancer   10.152.183.232   10.75.0.9     80:32101/TCP,443:31122/TCP                                    47h
tip-wlan-wlan-ssc-service           ClusterIP      10.152.183.189   <none>        9031/TCP,9032/TCP                                             47h
tip-wlan-wlan-prov-service          ClusterIP      10.152.183.160   <none>        9091/TCP,9092/TCP                                             47h
tip-wlan-opensync-mqtt-broker       LoadBalancer   10.152.183.32    10.75.0.9     1883:31511/TCP,9001:32046/TCP                                 47h
tip-wlan-wlan-portal-service        LoadBalancer   10.152.183.246   10.75.0.9     9051:30504/TCP,9052:31817/TCP                                 47h
tip-wlan-opensync-gw-cloud          LoadBalancer   10.152.183.97    10.75.0.9     6640:31000/TCP,6643:31932/TCP,9096:30749/TCP,9097:31793/TCP   47h
tip@microk8slocal:~$
```

```text
tip@microk8slocal:~$ microk8s kubectl get pvc -n tip
NAME                                             STATUS   VOLUME                                     CAPACITY   ACCESS MODES   STORAGECLASS        AGE
datadir-tip-wlan-kafka-0                         Bound    pvc-df6a471f-6a79-4a60-8e83-6c89326b6152   1Gi        RWO            microk8s-hostpath   4d2h
data-tip-wlan-zookeeper-0                        Bound    pvc-d139d789-123c-41e4-a299-2c1dc001a044   1Gi        RWO            microk8s-hostpath   4d2h
data-tip-wlan-opensync-mqtt-broker-0             Bound    pvc-d31682b7-db86-4022-8079-2acb3689ef68   1Gi        RWO            microk8s-hostpath   4d2h
data-tip-wlan-postgresql-master-0                Bound    pvc-127bc86a-acc1-420c-8cca-d3d619615cba   1Gi        RWO            microk8s-hostpath   4d2h
data-tip-wlan-postgresql-slave-0                 Bound    pvc-f000dbd6-dcd7-4fd1-8dfb-056475e4b9dc   1Gi        RWO            microk8s-hostpath   4d2h
db-tip-wlan-opensync-mqtt-broker-0               Bound    pvc-9d6c25ce-0712-4660-ad3e-cdc4ce41bdf7   1Gi        RWO            microk8s-hostpath   4d2h
data-tip-wlan-cassandra-0                        Bound    pvc-645ae94f-36e7-4fe3-a093-c66c56e82092   1Gi        RWO            microk8s-hostpath   4d2h
file-store-data-tip-wlan-wlan-portal-service-0   Bound    pvc-530ed2bf-b120-4eee-b6d5-0d7cdd468d2b   4Gi        RWX            microk8s-hostpath   4d2h
tip@microk8slocal:~$ tip@microk8slocal:~
```

```text
$ microk8s kubectl get pods -n tip
NAME                                                 READY   STATUS    RESTARTS   AGE
tip-wlan-kafka-0                                     0/1     Pending   0          4d1h
tip-wlan-wlan-cloud-static-portal-bdfcb4559-9wt9r    0/1     Pending   0          4d1h
tip-wlan-wlan-spc-service-68cffddd96-prppd           0/1     Pending   0          4d1h
tip-wlan-wlan-ssc-service-66dbdd89f4-rhfxv           0/1     Pending   0          4d1h
tip-wlan-nginx-ingress-controller-7458d6f654-cwnw6   0/1     Pending   0          4d1h
tip-wlan-postgresql-slave-0                          0/1     Pending   0          4d1h
tip-wlan-opensync-gw-cloud-7b69865fcc-8fzbw          0/1     Pending   0          4d1h
tip-wlan-wlan-cloud-graphql-gw-bc897994b-gpf8b       1/1     Running   0          4d1h
tip-wlan-cassandra-0                                 0/1     Pending   0          4d1h
tip-wlan-opensync-mqtt-broker-0                      1/1     Running   0          4d1h
tip-wlan-zookeeper-0                                 1/1     Running   0          4d1h
tip-wlan-postgresql-master-0                         1/1     Running   0          4d1h
tip-wlan-wlan-portal-service-0                       1/1     Running   0          4d1h
tip-wlan-wlan-prov-service-84fc7bfc5f-xqjgx          1/1     Running   0          4d1h
tip@microk8slocal:~$
```

### Access Point Self-Signed Keys

In the earlier stage when self-signed keys were created for the controller, keys were also created to support Access Point connections over SSL to the newly deployed controller.  
To obtain these keys, return to the `/wlan-pki-cert-scripts/generated` folder and copy `AP.zip` containing the Access Point keys.  
Extract this archive and using sing secure copy \(SCP\) transfer keys to the `/usr/opensync/certs` folder on the AP.

{% hint style="info" %}
The above assumes the microk8s system has IP connectivity to the Access Point  
If this is not possible, copy the AP.zip file to a machine that will have SCP access to the AP, extract the files and copy to the AP folder per above.
{% endhint %}

### Directing Access Point To Controller

In the current release of a TIP Controller using self-signed certificates, Access Points communicate to the TIP Controller using OpenSync. Access Points are directed to the controller at this time using local configuration.

> **The default TIP Open AP username and login are 'root' and 'openwifi'**

```text
/bin/wlan_ap_redirector.sh ssl:<IP or FQDN of controller>:6643
```

{% hint style="info" %}
The IP address \(or FQDN\) are the same as the metallb exposed External IP as shown in earlier steps
{% endhint %}

