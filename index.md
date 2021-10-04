---

copyright:
  years: 2015, 2021
lastupdated: "2021-10-01"

keywords: command line interface, cli, getting started, getting started with IBM Cloud CLI, getting started with IBM Cloud CLI and developer tools tutorial, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, cloud command line, developer tools, dev tools, install cloud cli, getting started cli, ibm cloud cli, IBM Cloud CLI installer, installing IBM Cloud CLI, install IBM Cloud CLI
content-type: tutorial
services: 
account-plan: lite
completion-time: 30m
subcollection: cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:external: target="_blank" .external}
{:step: data-tutorial-type='step'}
{:note: .note}

# Getting started with the {{site.data.keyword.cloud_notm}} CLI
{: #getting-started}
{: toc-content-type="tutorial"} 
{: toc-services=""} 
{: toc-completion-time="30m"}

In this tutorial, you install the {{site.data.keyword.cloud}} Command Line Interface, along with the option to install popular plug-ins and tools so that you can work with apps, toolchains, pipelines, Kubernetes clusters, and more in {{site.data.keyword.cloud_notm}}.
{: shortdesc}

The installation command in this tutorial installs the latest stand-alone {{site.data.keyword.cloud_notm}} CLI version available, with the option of installing the following tools manually:

* `Homebrew` (Mac only)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl` (Linux&trade; only)
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} plug-in
* {{site.data.keyword.cos_full_notm}} plug-in
* {{site.data.keyword.registrylong_notm}} plug-in
* {{site.data.keyword.containerlong_notm}} plug-in

Want to start working with the {{site.data.keyword.cloud_notm}} CLI? Try out {{site.data.keyword.cloud-shell_notm}}, which gives you a personal cloud-based shell workspace with the full {{site.data.keyword.cloud_notm}} CLI and tons of command-line tools - no installation needed. To get started, click the {{site.data.keyword.cloud-shell_short}} icon ![{{site.data.keyword.cloud-shell_notm}} icon](../icons/terminal-cloud-shell.svg) in the {{site.data.keyword.cloud_notm}} console menu bar. For more information, see [Getting started with {{site.data.keyword.cloud-shell_notm}}](/docs/cloud-shell?topic=cloud-shell-getting-started).
{: tip}

## Before you begin
{: #idt-prereq}

* Depending on your [{{site.data.keyword.cloud}} account type](https://{DomainName}/registration), access to certain resources might be limited or constrained. Depending on your plan limits, certain capabilities that are required by some toolchains might not be available. For more information, see [Setting up your IBM Cloud account](/docs/account?topic=account-account-getting-started).
* You must use the stable channel for Docker with a minimum version of 1.13.1.
* For Linux&trade;, install the [curl](https://curl.haxx.se/download.html){: external} command for downloading packages through the command line. If `curl` is already installed, the installer updates it to the latest version.
* For Windows&trade;, some functions are not supported unless you are running Windows&trade; 10 Pro.

If you need to use a 32-bit version of the CLI, or a previous version other than the latest for {{site.data.keyword.cloud_notm}} Dedicated environments, see [{{site.data.keyword.cloud_notm}} CLI releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external}.
{: note}

## Run the installation command
{: #step1-install-idt}
{: step}

The latest version of the {{site.data.keyword.cloud_notm}} CLI is installed when you run the command. As the CLI installs, keep an eye on the command line to authenticate as needed.

* For MacOS, run the following command:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* For Linux&trade;, run the following command:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* For Windows&trade; 10 Pro, run the following command in PowerShell as an administrator:
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

  To open PowerShell, right-click the Windows&trade; PowerShell icon, and select **Run as administrator**.
  {: tip}


## Verify the installation
{: #step2-verify-idt}
{: step}

To verify that the CLI was installed successfully, run the `help` command:
```
ibmcloud help
```
{: codeblock}

The output lists the usage instructions, the current version, and the supported commands.

## Install CLI plug-ins and tools
{: #step3-install-idt-manually}
{: step}

To manually install the CLI plug-ins and tools, see [installing the tools and plug-ins manually](/docs/cli?topic=cli-install-devtools-manually).

## Configure your environment
{: #step4-configure-idt-env}
{: step}

1. Log in to {{site.data.keyword.cloud_notm}} with your IBMid. If you have multiple accounts, you are prompted to select which account to use. If you do not specify a region with the `-r` flag, you must also select a region.
```
ibmcloud login
```
{: codeblock}

If your credentials are rejected, you might be using a federated ID. To log in with a federated ID, use the `--sso` flag. See [Logging in with a federated ID](/docs/account?topic=account-federated_id) for more details.
{: tip}

2. If you plan to access Cloud Foundry services, specify a Cloud Foundry org and space. You can run the following command to interactively identify the org and space:
```
ibmcloud target --cf
```
{: codeblock}

Or, if you know which org and space that the service belongs to, you can use the following command:
```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

## Next steps
{: #next-steps}

If you installed the CLI plug-ins and tools, you're now ready to develop and deploy your first app. For more information, see [Creating and deploying apps by using the CLI](/docs/apps?topic=apps-create-deploy-app-cli#create-deploy-app-cli).

Stay up to date with the {{site.data.keyword.cloud_notm}} CLI by subscribing to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external}. You'll receive notifications about new {{site.data.keyword.cloud_notm}} CLI releases.

{{site.data.keyword.cloud_notm}} CLI supports a plug-in framework to extend its capability. [Discover and install new CLI plugins](/docs/cli?topic=cli-plug-ins)!

Need a hand with remembering {{site.data.keyword.cloud_notm}} CLI commands? Print the [{{site.data.keyword.cloud_notm}} CLI quick reference](https://cloud.ibm.com/media/docs/downloads/IBM%20Cloud%20CLI%20quick%20reference.pdf){:external} to keep commands for common tasks at your fingertips.
{:tip}
