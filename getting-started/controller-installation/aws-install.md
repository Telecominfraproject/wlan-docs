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

