---
description: OpenWiFi 2.0 SDK
---

# Deploy using Helm

OpenWi-Fi 2.0 SDK can be deployed to Kubernetes using a Helm package. The Helm package code is located at [https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/) repository.

Each micro service in the OpenWiFi SDK system has its own Helm chart that is managed in the micro service’s own repository. The assembly chart collects all the relevant micro service charts and other external dependencies like kafka, rtty, etc. and deploys them together as one cohesive release.

You can review the full list of all the assembled micro services and related dependencies here: [https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/blob/main/chart/Chart.yaml\#L6](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/blob/main/chart/Chart.yaml#L6)

## Installation

There are multiple ways you can install OpenWiFi SDK with assembly charts:

1. One way is by installing directly from the assembly chart’s repository. For that, you’ll need to install and extra Helm plugin that is used to pull the latest charts code from all the referenced micro services: [https://github.com/aslafy-z/helm-git](https://github.com/aslafy-z/helm-git).
2. Another way, which is considered more stable, is by installing from a prepackaged bundle that is published to [https://tip.jfrog.io/ui/native/tip-wlan-cloud-ucentral-helm/](https://tip.jfrog.io/ui/native/tip-wlan-cloud-ucentral-helm/) on every official uCentral release. For this approach to work, you don’t need to install any additional plugins or dependencies, just to make sure you’ve got Helm installed on your local system.

#### Directly from the Assembly repository

1. Install the helm-git pluging according to the official documentation
2. Run helm upgrade --install tip-ucentral git+https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/@chart?ref=main
3. You can also reference any other open branch from the deployment repository. For example, if you want to deploy using the assembly code from the v2.0.0-rc1 branch, you can just run helm upgrade --install tip-ucentral git+https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/@chart?ref=v2.0.0-rc1

#### Using the pre-built Helm package

1. This method doesn’t require to install anything locally other than Helm
2.  Start by adding the wlan-cloud-ucentral Helm repository to your local list of repositories by running helm repo add tip-ucentral https://tip.jfrog.io/artifactory/tip-wlan-cloud-ucentral-helm/
3. helm upgrade --install tip-ucentral wlan-cloud-ucentral to install the latest version, or specify the release you want to install by adding the --version x.y.z flag.

## Chart configuration using the Values file

The configuration of OpenWiFi SDK using Helm chart may be separated into layers:

1. Micro services default values - values files that are stored in micro service helm charts \(i.e. [https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/master/helm/values.yaml](https://github.com/Telecominfraproject/wlan-cloud-ucentralgw/blob/master/helm/values.yaml) \). These values are used by default if no other parameters are supplied, so in case you have any microservice-related variables that need to be added in default installation \(for example new application configuration properties\), add them in the related helm chart values as they will be applied in next release update.
2. Assembly chart values - values that are stored in the assembly repository \([https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/blob/main/chart/values.yaml](https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/blob/main/chart/values.yaml) \) – these are values that override default micro services values so that all uCentral components could connect to each other correctly, and the whole system can be installed as one bundle. These parameters are environment specific, and can differ between and installation of the bundle on an EKS cluster or a MicroK8s local setup.
3. Helm upgrade/install flag overwrites - these values cam be specific for each specific helm install command during execution and usually contain installation-specific values like TLS certificates, security credentials, loadbalancer configuration parameters and so on. These may be passed using --set flag or --values flag \(details may be found in [https://helm.sh/docs/chart\_best\_practices/values/](https://helm.sh/docs/chart_best_practices/values/) and in micro services helm charts\), or you can also save them into one file and reference this file during the helm upgrade command using the --values flag.

During deployment all values are merged as maps with priority to the level of deployment \(so Environment-specific values will override any overrides from Assembly chart values and so on\).

**Example**: Let’s pass environment-specific ucentralgw.properties configuration parameter \(which is probably quite common thing to test\). For example, we have an environment that requires to set parameter ucentral.websocket.host.0.backlog to 1000. For that we would need to run following command, extending our base command:

```text
helm upgrade --install tip-ucentral git+https://github.com/Telecominfraproject/wlan-cloud-ucentral-deploy/@chart?ref=main --set ucentralgw.configProperties."ucentral\.websocket\.host\.0\.backlog"=1000
```

## Automated community deployment

OpenWiFi SDK can also be deployed to an AWS labs environment using a Github actions workflow: [https://github.com/Telecominfraproject/wlan-testing/actions/workflows/ucentralgw-deployment.yaml](https://github.com/Telecominfraproject/wlan-testing/actions/workflows/ucentralgw-deployment.yaml).

The configuration is dynamic, and new namespaces \(a.k.a environments\) may be created by adjusting the json configuration in the workflow.

The json format allows to deploy or upgrade and existing environment using the latest Docker images or to specify a specific version of each micro service.

To deploy specific version to the specific environment a list of things must be done:

1. First, you need to make sure that the Docker image with the correct version exists in Artifactory, otherwise, the Helm upgrade will fail.
2. Update the json configuration in the workflow to reference the require version for the require micro service \(examples are attached in the json file itself\)
3. Re-run the deployment in Github actions. You can also make all the above changes in a separate branch, and re-run the workflow from that branch \(using a drop-down in the top left corner in Github’s UI\).

