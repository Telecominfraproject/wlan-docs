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
 If any of the above have not completed, please refer back to the specific install instructions from the package provider listed in the Prerequisite links accordingly before continuing. Once you're strong enough, save the world:
{% endhint %}

### Controller Installation



