---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in manually
{: #install-devtools-manually}

You can manually install the {{site.data.keyword.cloud}} developer tools command line interface (CLI) plug-in if you prefer more granular control for installing the components. Otherwise, all prerequisites are automatically installed for most users by using the [platform installers](/docs/cli?topic=cloud-cli-getting-started#step1-install-idt).
{: shortdesc}

## Before you begin
{: cli-before-you-begin}

* Install the stand-alone [{{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) to get support for installing command line plug-ins for {{site.data.keyword.cloud_notm}}.
* Install the [curl](https://curl.haxx.se/download.html){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon") command for downloading packages through the command line.

## Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in
{: #install-devtools-idt}

You can use the {{site.data.keyword.cloud_notm}} developer tools CLI commands to create an application, manage, deploy, debug, and test it.

To install the {{site.data.keyword.cloud_notm}} developer tools plug-in, run the following command: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Installing Docker
{: #install-devtools-docker}

For running and debugging apps locally, install [Docker](https://www.docker.com/get-started){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon").

## Installing the Kubernetes command line tool
{: #idt-install-kube}

To view a local version of the Kubernetes dashboard, and to deploy apps into your clusters, install the [Kubernetes command line tool](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon") for your platform:

* Mac:
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

The prefix for running commands by using the Kubernetes command line tool is `kubectl`. For more information, see [Setting up the CLI and API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Installing {{site.data.keyword.registrylong_notm}} CLI plug-in
{: #idt-install-container-registry-cli-plugin}

You can use the `container-registry` CLI plug-in to set up your own image namespace in an IBM-hosted, and managed, private registry. Where you can store and share Docker images with all users in your {{site.data.keyword.cloud_notm}} account.

* To install the {{site.data.keyword.registrylong}} plug-in, run the following command:
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

For more information, see the [{{site.data.keyword.registrylong}} command reference](/docs/services/Registry?topic=container-registry-cli-plugin-containerregcli).

## Installing {{site.data.keyword.containerlong_notm}} CLI plug-in
{: #idt-install-kubernetes-cli-plugin}

To create and manage Kubernetes clusters in {{site.data.keyword.containerlong}}:

* To install the {{site.data.keyword.registryshort_notm}} plug-in, run the following command:
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

For more information, see the [{{site.data.keyword.registryshort_notm}} command reference](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference).

## Installing Helm
{: #idt-install-helm}

Install [Helm](https://helm.sh/docs/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon"), which is a Kubernetes-based package manager.

* Mac and Linux&trade; users, run the following commands:
  ```
  export DESIRED_VERSION=v2.7.2
  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Windows&trade; users can download and install the Helm [binary](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon").

## Installing the {{site.data.keyword.openwhisk_short}} CLI plug-in
{: #idt-install-functions}

You can use the {{site.data.keyword.openwhisk}} CLI plug-in to manage your code snippets in actions, bundle actions into packages, and create triggers and rules to enable your actions to respond to events.

To install the {{site.data.keyword.openwhisk_short}} CLI plug-in, run the following command:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

For more information, see [Installing the {{site.data.keyword.openwhisk_short}} CLI plug-in](/docs/openwhisk?topic=cloud-functions-cli_install).

## Installing the SDK Generator CLI plug-in
{: #idt-install-sdk-gen}

As an {{site.data.keyword.cloud_notm}} developer you can use the plug-in to generate SDKs from your [Open API Specification](https://www.openapis.org/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon")-compliant REST API definition. As the REST API definition evolves, you can use the plug-in to regenerate only the SDK instead of regenerating the entire project.

To install the SDK Generator CLI plug-in, run the following command:
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

For more information, see [SDK Generator](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
