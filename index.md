---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-13"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Getting started with the {{site.data.keyword.cloud_notm}} CLI
{: #overview}

In this tutorial, you install a set of {{site.data.keyword.cloud}} Developer tools, verify the installation, and configure the environment. {{site.data.keyword.cloud_notm}} Developer tools offer a command line approach to creating, developing, and deploying web, mobile, and microservice applications.
{: shortdesc}

With this installation, you get the stand-alone {{site.data.keyword.cloud_notm}} CLI, plus the following tools:

* `Homebrew` (Mac only)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} plug-in
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} plug-in
* {{site.data.keyword.registrylong_notm}} plug-in
* {{site.data.keyword.containerlong_notm}} plug-in
* `sdk-gen` plug-in

## Before you begin
{: #idt-prereq}

You need an [{{site.data.keyword.cloud_notm}} account](https://cloud.ibm.com/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon") and the following system requirements:

* If you are running Windows, some functions are not supported unless you are not running Windows 10 Pro.
* You must use the stable channel for Docker with a minimum version of 1.13.1.

## Step 1. Run the installation command
{: #step1-install-idt}

* For Mac and Linux, run the following command:
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* For Windows 10 Pro, run the following command as an administrator:
  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Right-click the Windows PowerShell icon, and select **Run as administrator**.
  {: tip}

  You can also download the installer script from this [GitHub repo](https://github.com/IBM-Cloud/ibm-cloud-developer-tools).

  For the steps to install these tools manually, see [Reinstalling tools](/docs/cli/ts_createapps.html#appendix).

## Step 2. Verify the installation
{: #step2-verify-idt}

To verify that the CLI and Developer tools were installed successfully, run the `help` command:
```
ibmcloud dev help
```
{: codeblock}

The output lists the usage instructions, the current version, and the supported commands.

## Step 3. Configure your environment
{: #step3-configure-idt-env}

1. Log in to {{site.data.keyword.cloud_notm}} with your IBMid. If you have multiple accounts, you are prompted to select which account to use. If you do not specify a region with the `-r` flag, you must also choose a region.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  If your credentials are rejected, you might be using a federated ID. To log in with a federated ID, use the `--sso` flag. See [Logging in with a federated ID](/docs/iam/login_fedid.html#federated_id) for more details.
  {: tip}

2. To use Cloud Foundry services, target an org and space.
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  Optionally, you can use the output from the previous command to manually set your org and space with the following command:
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## Next steps
{: #next-steps}

You're now ready to develop and deploy your first application! See [Creating and deploying apps by using the CLI](/docs/apps/create-deploy-cli.html#create-deploy-app-cli) for more information.
