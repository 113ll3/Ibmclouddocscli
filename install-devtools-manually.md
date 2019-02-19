---

copyright:
  years: 2019
lastupdated: "2019-02-18"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installing the {{site.data.keyword.cloud_notm}} Developer tools CLI plug-in components manually
{: #install-devtools-manually}

All prerequisites are installed for most users by using the [platform installers](/docs/cli/index.html#step1-install-idt). If you need to manually install any components, see the following instructions.

## Installing the {{site.data.keyword.cloud_notm}} Developer tools CLI plug-in
{: #install-devtools-idt}

To install the dev plug-in, you must first install the [{{site.data.keyword.cloud}} CLI](https://cloud.ibm.com/docs/cli/reference/ibmcloud/download_cli.html#install-ibmcloud-cli).

To use the dev plug-in, you must install it by running the following command: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Installing Docker
{: #install-devtools-docker}

For running and debugging apps locally, you must install [Docker](https://www.docker.com/get-docker).
 
## Installing Kubernetes:
{: #idt-install-kube}

For supporting container deployments, you must install Kubernetes.

* MacOS:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* Linux&trade;:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* Windows&trade;:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

## Installing Helm:
{: #idt-install-helm}

* MacOS and Linux&trade; users, run the following commands:
  ```
  export DESIRED_VERSION=v2.7.2
  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade; users can download and install the Helm [binary](https://github.com/kubernetes/helm/releases/tag/v2.7.2).

## Installing container plug-ins:
{: #idt-install-container-registry}

To support container deployments, install the following {{site.data.keyword.cloud_notm}} plug-ins.

1. Install the `container-registry` plug-in:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

2. Install the `container-service` plug-in:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}
