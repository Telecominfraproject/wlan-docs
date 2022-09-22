# Artifacts

**Access Point Firmware**

The Access Point firmware for all supported devices are built on every pull request to the wlan-ap repository. Please see this github workflow for current supported devices:

[https://github.com/Telecominfraproject/wlan-ap/blob/main/.github/workflows/build-dev.yml](https://github.com/Telecominfraproject/wlan-ap/blob/main/.github/workflows/build-dev.yml)

\
These images are then pushed to jfrog in each device specific target directory:

[https://tip.jfrog.io/artifactory/tip-wlan-ap-firmware/uCentral/](https://tip.jfrog.io/artifactory/tip-wlan-ap-firmware/uCentral/)



**Controller SDK**

The SDK micro-services are built on every pull request on their respective repositories. These images are then containerized and pushed to jfrog here:

[https://tip.jfrog.io/ui/repos/tree/General/tip-wlan-cloud-ucentral](https://tip.jfrog.io/ui/repos/tree/General/tip-wlan-cloud-ucentral)\
