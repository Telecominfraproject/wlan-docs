---
description: TIP Controller Deployment Instructions
---

# AWS Install

## Prerequisites

The following must be available to start this installation:

* AWS Account
* AWS Route 53 Hosted Zone

The steps outlined in this guide will create a local installation of the Terraform automation environment that will also depend on the AWS command line interface, Helm and Kubectl local command line packages.

Each of these applications provide detailed instructions for installation on multiple client operating systems.

* Install Kubectl [https://kubernetes.io/docs/tasks/tools/install-kubectl/](https://kubernetes.io/docs/tasks/tools/install-kubectl/) 
* Install Helm [https://helm.sh/docs/intro/install/](https://helm.sh/docs/intro/install/)
* Install AWS CLI [https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
* Install Terraform [https://learn.hashicorp.com/tutorials/terraform/install-cli\#install-terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli#install-terraform)

### Example Local Prerequisites Installation on MAC OS

 If the instructions for Terraform were followed, a Docker container was locally created, nginx was run with a default localhost:80 nginx returned web page displayed. After which 'terraform destroy' was run to remove the local test of Terraform.

If the instructions for AWS CLI were followed, AWS CLI version 2 has been installed. This may be verified using the command `which aws` and `aws --version`. If these succeed installation of AWS CLI has completed. 

If the instructions for Helm were followed, Helm has now been locally installed. This may be verified using the command `which helm` and `helm version`. If these succeed installation of Helm has completed.

If the instructions for Kubectl were followed, Kubectl has not been locally installed. This may be verified using the command which `kubectl` and `kubectl version --client`. If these succeed installation of Kubectl has completed.

{% hint style="info" %}
 If any of the above have not completed, please refer back to the specific install instructions from the package provider listed in the Prerequisite links accordingly before continuing. 
{% endhint %}

Access to AWS should have been satisfied with an AWS account as noted in Prerequisites. This account is entitled with Administrator level permissions. For information on this process please refer to: [https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)

### Controller Installation

Create a workspace on your local system and clone in the TIP Controller project.

```text
git clone https://github.com/Telecominfraproject/wlan-cloud-helm/
### A merge of final AWS deployments is pending. 
### At this time, switch to the following branch
git checkout cloudsdk-aws-deployment
cd /terraform/aws-cloudsdk
```

  Create a Terraform file in the `aws-cloudsdk` directory named `aws.tf`adding the following to that new file:

```text
provider "aws" {
        region = "Replace with your preferred AWS region here"
}
```

If a specific authentication method previously exists depending on your local machine environment when connecting to AWS, adjustments may be required. Please consult Terraform instructions accordingly: [https://registry.terraform.io/providers/hashicorp/aws/latest/docs\#authentication](https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication)

### Initialize Terraform 

Terraform will use the initial configuration of your environment variables from the previous step when communicating with AWS. Prior to initializing Terraform, ensure authentication is successful. 

```text
terraform init

### Several emitted lines will occur.
### When succesful the following will display:

Terraform has been successfully initialized!
```

### Adjusting to AWS Environment

Within the `/wlan-cloud-helm/terraform/aws-cloudsdk` directory, copy the `terraform.tfvars.sample` file to `terraform.tfvars` and edit the content of the new `terraform.tfvars`     replacing parameter values for cidr and route53\_zone\_name accordingly: 

```text
name = "cloudsdk"
cidr = "Enter a valid CIDR Range of your AWS VPC"
route53_zone_name = "Enter a valid Route53 Hosted-Zone"
subdomain = "cloudsdk"
```

Once these steps have been completed, it is now possible to deploy the TIP Controller to AWS. 

```text
terraform apply
```

If Terraform is able to connect and authenticate to AWS, a prompt to accept the creation of the deployment is presented. Answer `yes` to proceed. Terraform will execute for 10-15 minutes during which time the following are being configured:

* EKS cluster with three nodes where CloudSDK will run on
* VPC for the EKS cluster
* ACM that will sign the certificate for the public HTTPS services exposed by CloudSDK
* Route53 record to let ACM know that you own the domain
* [external-dns](https://github.com/kubernetes-sigs/external-dns) that will take care of creating DNS entries for all CloudSDK components
* [aws-load-balancer-controller](https://kubernetes-sigs.github.io/aws-load-balancer-controller/latest/) which will take care of exposing CloudSDK components to the public
* Required IAM roles for all components

### Terraform Results

When Terraform completes the following should have emitted:

> **Apply complete! Resources: 57 added, 0 changed, 0 destroyed.**

> **Outputs:**
>
> **acm\_arn = "arn:aws:acm:ca-central-1:1**_**xxxxxxx**_**68:certificate/7e3**_**xxxx**_**7-74**_**xx**_**-4**_**xxx**_**-8bef-d6**_**xxxxxx**_**5a3"**

### Deploy TIP Controller

TIP Controller services use SSL certificates to ensure inter-service security. These certificates must be generated. To generate TIP Controller certificates, navigate out of the tip-wlan-cloud directory to a directory where cloning the TIP PKI repository may occur:

```text
git clone https://github.com/Telecominfraproject/wlan-pki-cert-scripts.githelm dependency update tip-wlan
```

Enter the PKI directory and the configs sub-directory `cd /wlan-pki-cert-scripts/configs`

Modify all certificate configuration files for the value of your organizationalUnitName\_default value set to your organizational name or other string value used in each of the PKI certificate files. Optionally this may be left unchanged.

Within the following files, ensure the FQDN \(Fully Qualified Domain Name\) based on the Terraform setup for Route53 hosted-zone aligns accordingly. If the defaults were not changed Terraform will have created a sub-domain `cloudsdk` within the supplied Route53 hosted-zone. The following files are updated per:

* mqtt-server.cnf 

  `commonName_default          = opensync-mqtt-broker.cloudsdk.route53hosted-zone_name`

*  openssl-server.cnf

  `DNS.1  = opensync-redirector.cloudsdk.route53hosted-zone_name`

  `DNS.2  = opensync-controller.cloudsdk.route53hosted-zone_name`

To generate keys, ensure necessary Java resources are installed for your operating system:

* openjdk-11-jre-headless
* default-jdk

From within the `wlan-pki-cert-scripts` folder execute `./generate_all.sh` script.

Copy the generated keys assuming the wlan-cloud-helm folder is at the same level as the wlan-pki-certs folder per: `./copy-certs-to-helm.sh ~/wlan-cloud-helm/`

### Satisfy Cloud Deployment Charts

Certain TIP Charts have upstream dependencies, form the wlan-cloud-helm folder execute:

```text
helm dependency update tip-wlan
```

Various Bitnami charts will be brought into the deployment such as Kafka, PostGres, Cassandra.

###  Deploy Controller to AWS

With all dependencies met, certificates created and in place, using Helm and the authenticated session to AWS, execute the following:

```text
helm upgrade --install cloudsdk tip-wlan -f tip-wlan/example-values/aws-basic/values.yml --namespace tip --create-namespace
```

If a connection error occurs, AWS CLI may need to re-authenticate. This can be done with `aws configure`.

If Helm has a succesful connection to AWS the following returns:

> Release "cloudsdk" does not exist. Installing it now.

> NAME: cloudsdk
>
> LAST DEPLOYED: Sun Feb  7 14:00:28 2021
>
> NAMESPACE: tip
>
> STATUS: deployed
>
> REVISION: 1
>
> TEST SUITE: None

To check on status of PODs now launching in AWS enter `kubectl get pods -n tip` to return results from the operational EKS Kubernetes CloudSDK cluster:

```text
NAME                                                             READY   STATUS            RESTARTS   AGE
cloudsdk-cassandra-0                                             0/1     Running           0          99s
cloudsdk-kafka-0                                                 0/1     Running           0          99s
cloudsdk-kafka-config-1-qnf7j                                    0/1     Init:0/1          0          100s
cloudsdk-opensync-gw-cloud-685b5c9d4-t485c                       0/1     Init:0/1          0          100s
cloudsdk-opensync-mqtt-broker-0                                  1/1     Running           0          99s
cloudsdk-postgresql-primary-0                                    1/1     Running           1          99s
cloudsdk-postgresql-read-0                                       1/1     Running           0          99s
cloudsdk-wlan-cloud-graphql-gw-76c69db46d-cc2zv                  1/1     Running           0          100s
cloudsdk-wlan-cloud-static-portal-8595fd964d-fkd6g               1/1     Running           0          100s
cloudsdk-wlan-port-forwarding-gateway-service-68d745b84b-2xmvq   0/1     Init:0/1          0          100s
cloudsdk-wlan-portal-service-0                                   0/1     Running           0          99s
cloudsdk-wlan-prov-service-944f44d67-4p5z5                       0/1     PodInitializing   0          100s
cloudsdk-wlan-spc-service-596ff5c546-bmgw5                       0/1     Init:0/1          0          100s
cloudsdk-wlan-ssc-service-6db4c8c8b8-jrmrc                       0/1     Init:0/2          0          100s
cloudsdk-zookeeper-0                                             1/1     Running           0          99s

```

After 5 to 8 minutes elapse, all POD services should be operational for example:

```text
NAME                                                             READY   STATUS      RESTARTS   AGE
cloudsdk-cassandra-0                                             1/1     Running     0          11m
cloudsdk-kafka-0                                                 1/1     Running     0          11m
cloudsdk-kafka-config-1-qnf7j                                    0/1     Completed   0          11m
cloudsdk-opensync-gw-cloud-685b5c9d4-t485c                       1/1     Running     0          11m
cloudsdk-opensync-mqtt-broker-0                                  1/1     Running     0          11m
cloudsdk-postgresql-primary-0                                    1/1     Running     1          11m
cloudsdk-postgresql-read-0                                       1/1     Running     0          11m
cloudsdk-wlan-cloud-graphql-gw-76c69db46d-cc2zv                  1/1     Running     0          11m
cloudsdk-wlan-cloud-static-portal-8595fd964d-fkd6g               1/1     Running     0          11m
cloudsdk-wlan-port-forwarding-gateway-service-68d745b84b-2xmvq   1/1     Running     0          11m
cloudsdk-wlan-portal-service-0                                   1/1     Running     0          11m
cloudsdk-wlan-prov-service-944f44d67-4p5z5                       1/1     Running     0          11m
cloudsdk-wlan-spc-service-596ff5c546-bmgw5                       1/1     Running     0          11m
cloudsdk-wlan-ssc-service-6db4c8c8b8-jrmrc                       1/1     Running     0          11m
cloudsdk-zookeeper-0                                             1/1     Running     0          11m
```



