---

copyright:
  years: 2022, 2023
lastupdated: "2023-02-03"

keywords: IBM Cloud CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, cli, command line, command-line, developer tools, kubernetes, kubectl, git

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Installing the tools and plug-ins manually
{: #install-devtools-manually}

You can manually install the {{site.data.keyword.cloud}} Command Line Interface and other plug-ins and tools for developing applications for {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## Before you begin
{: #cli-before-you-begin}

* Install the stand-alone [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-install-ibmcloud-cli#install-ibmcloud-cli) to get support for installing command line plug-ins for {{site.data.keyword.cloud_notm}}.
* Install the [curl](https://curl.haxx.se/download.html){: external} command for downloading packages through the command line.

## Installing Docker
{: #install-devtools-docker}

To run and debug apps locally, install [Docker](https://www.docker.com/get-started){: external}.

## Installing the Kubernetes command line tool
{: #idt-install-kube}

To view a local version of the Kubernetes dashboard, and to deploy apps into your clusters, install the [Kubernetes command line tool](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: external} for your platform:

* Mac:
   ```curl
   curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
   ```
   {: codeblock}

* Linux&trade;:
   ```curl
   curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
   ```
   {: codeblock}

* Windows&trade;:
   ```curl
   curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
   ```
   {: codeblock}

The prefix for running commands by using the Kubernetes command line tool is `kubectl`. For more information, see [Setting up the CLI and API](/docs/containers?topic=containers-cs_cli_install).

## Installing {{site.data.keyword.cos_full_notm}} CLI plug-in
{: #install-cos-cli-plugin}

The {{site.data.keyword.cos_full_notm}} plug-in extends the {{site.data.keyword.cloud_notm}} command line interface (CLI) with an API wrapper for working with Object Storage resources.

* To install the {{site.data.keyword.cos_full_notm}} plug-in, run the following command:
   ```text
   ibmcloud plugin install cloud-object-storage
   ```
   {: codeblock}

For more information, see the [{{site.data.keyword.cos_full_notm}} command reference](/docs/cloud-object-storage?topic=cloud-object-storage-cli-plugin-ic-cos-cli).

## Installing {{site.data.keyword.registrylong_notm}} CLI plug-in
{: #idt-install-container-registry-cli-plugin}

You can use the `container-registry` CLI plug-in to set up your own image namespace in an IBM-hosted, and managed, private registry. Where you can store and share Docker images with all users in your {{site.data.keyword.cloud_notm}} account.

* To install the {{site.data.keyword.registrylong}} plug-in, run the following command:
   ```text
   ibmcloud plugin install container-registry
   ```
   {: codeblock}

For more information, see the [{{site.data.keyword.registrylong}} command reference](/docs/Registry?topic=container-registry-cli-plugin-containerregcli).

## Installing {{site.data.keyword.containerlong_notm}} CLI plug-in
{: #idt-install-kubernetes-cli-plugin}

To create and manage Kubernetes clusters in {{site.data.keyword.containerlong}}:

* To install the {{site.data.keyword.containershort_notm}} plug-in, run the following command:
   ```text
   ibmcloud plugin install container-service
   ```
   {: codeblock}

For more information, see the [{{site.data.keyword.containershort_notm}} command reference](/docs/containers?topic=containers-kubernetes-service-cli).

## Installing Helm
{: #idt-install-helm}

Install [Helm](https://helm.sh/docs/){: external}, which is a Kubernetes-based package manager.

* Mac and Linux&trade; users, run the following commands:
   ```text
   curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
   ```
   {: codeblock}

* Windows&trade; users can download and install the Helm [binary](https://github.com/helm/helm/releases){: external}.

## Installing the {{site.data.keyword.openwhisk_short}} CLI plug-in
{: #idt-install-functions}

You can use the {{site.data.keyword.openwhisk}} CLI plug-in to manage your code snippets in actions, bundle actions into packages, and create triggers and rules to enable your actions to respond to events.

To install the {{site.data.keyword.openwhisk_short}} CLI plug-in, run the following command:
```text
ibmcloud plugin install cloud-functions
```
{: codeblock}

For more information, see [Installing the {{site.data.keyword.openwhisk_short}} CLI plug-in](/docs/openwhisk?topic=openwhisk-cli_install).

## Installing {{site.data.keyword.bplong_notm}} CLI plug-in
{: #idt-install-schematics-cli-plugin}

To create and manage {{site.data.keyword.bpshort}} in {{site.data.keyword.bplong_notm}} service:

* To install the {{site.data.keyword.bplong_notm}} plug-in, run the following command:
   ```text
   ibmcloud plugin install schematics
   ```
   {: codeblock}

For more information, see the [{{site.data.keyword.bplong_notm}} command reference](/docs/schematics?topic=schematics-setup-cli).

## Installing Git
{: #idt-install-git}

You can download and install Git. For more information, see [Git downloads](https://git-scm.com/downloads){: external}.
