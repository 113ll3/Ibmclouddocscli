---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in components manually
{: #install-devtools-manually}

If you prefer more granular control for installing developer tools components, you can manually install them by using the following steps. Otherwise, all prerequisites are automatically installed for most users by using the [platform installers](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Before you begin
{: cli-before-you-begin}

* Install the stand-alone [{{site.data.keyword.cloud}} CLI](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) so you can support installing command line plug-ins for `ibmcloud`.
* Install the [curl](https://curl.haxx.se/download.html) command for downloading packages through the command line.

## Step 1. Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in
{: #install-devtools-idt}

You can use the {{site.data.keyword.cloud_notm}} developer tools CLI (ibmcloud dev) commands to create an application, manage, deploy, debug, and test it.

Install the `dev` plug-in by running the following command: 
```
ibmcloud plugin install dev
```
{: codeblock}

## Step 2. Installing Docker
{: #install-devtools-docker}

For running and debugging apps locally, install [Docker](https://www.docker.com/get-docker){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon").

## Step 3. Installing Kubernetes:
{: #idt-install-kube}

Kubernetes is an open source container orchestration engine for automating deployment, scaling, and management of containerized applications.

1. To support containerized deployments, install Kubernetes for your platform:
   MacOS:
   ```
   curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
   ```
   {: codeblock}

  Linux&trade;:
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

  Windows&trade;:
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

2. To manage Kubernetes deployments from the command line, install the following container plug-ins:

   Install the `container-registry` plug-in:
   ```
   ibmcloud plugin install container-registry
   ```
   {: codeblock}

   Install the `container-service` plug-in:
   ```
   ibmcloud plugin install container-service
   ```
   {: codeblock}

   For more information, see [Setting up the CLI and API](/docs/containers/cs_cli_install.html#cs_cli_install).

## Step 4. Installing Helm:
{: #idt-install-helm}

Install [Helm](https://helm.sh/docs/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon"), which is a Kubernetes-based package manager.

MacOS and Linux&trade; users, run the following commands:
  ```
  export DESIRED_VERSION=v2.7.2
  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

Windows&trade; users can download and install the Helm [binary](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon").

## Step 5. Installing the {{site.data.keyword.openwhisk_short}} CLI plug-in
{: #idt-install-functions}

You can use the {{site.data.keyword.openwhisk}} CLI plug-in to manage your code snippets in actions, create triggers and rules to enable your actions to respond to events, and bundle actions into packages.

To install the {{site.data.keyword.openwhisk_short}} CLI plug-in, run the following command:
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

For more information, see [Setting up the {{site.data.keyword.openwhisk_short}} CLI plug-in](/docs/openwhisk/bluemix_cli.html#cloudfunctions_cli).

## Step 6. Installing the SDK Generator
{: #idt-install-sdk-gen}

As a developer on {{site.data.keyword.cloud_notm}}, you can use this plug-in to generate SDKs from your [Open API Specification](https://www.openapis.org/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon") compliant REST API definition. As you make changes to your REST API definition, you can use this plug-in to regenerate only the SDK instead of regenerating the entire project.

Install the SDK Generator plug-in:
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

For more information, see [SDK Generator](/docs/cli/sdk/index.html#sdk-cli).
