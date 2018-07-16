---

copyright:

  years: 2015, 2018

lastupdated: "2018-07-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Getting started with the {{site.data.keyword.Bluemix_notm}} CLI
{: #overview}

In this tutorial, you install a set of {{site.data.keyword.Bluemix}} developer tools, verify the installation, and configure your environment. {{site.data.keyword.Bluemix}} developer tools offer a command-line approach to creating, developing, and deploying end-to-end web, mobile, and microservice applications. 
{:shortdesc}

With this installation, you get the {{site.data.keyword.Bluemix_notm}} CLI, plus the following tools: 

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
{: #prereq}

You need an [{{site.data.keyword.Bluemix_notm}} account](https://console.bluemix.net/){: new_window} ![External link icon](../icons/launch-glyph.svg "External link icon") and the following system requirements:

* If you're using Microsoft Windows &trade;, you must use Windows 10 or later.
* You must use the stable channel for Docker with a minimum version of 1.13.1.

## Step 1: Run the install command
{: #step1}

* For Mac and Linux, run the following command:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br>
* For Windows 10, run the following command as an administrator:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br>

  Right-click the Windows PowerShell icon, and select **Run as administrator**.
  {: tip}

## Step 2: Verify the installation
{: #step2}

To verify that the CLI and developer tools were installed successfully, run the `help` command:

```
ibmcloud dev help
```
{: codeblock}
<br>
The output lists the usage instructions, the current version, and the supported commands.

## Step 3: Configure your environment
{: #step3}

1. Connect to an API endpoint in your {{site.data.keyword.Bluemix_notm}} region. For example, enter the following command to connect to the {{site.data.keyword.Bluemix_notm}} US South region:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Log in to {{site.data.keyword.Bluemix_notm}} with your IBMid.

	```
	ibmcloud login
	```
	{: codeblock}
    <br>
    
	If your credentials are rejected, you might be using a federated ID. See [Logging in with a federated ID](/docs/iam/login_fedid.html#federated_id) for more details.
	{: tip}

3. Set your org and space.

	```
	ibmcloud target --cf
	```
	{: codeblock}
	
	Optionally, you can use the output from the command above to manually set your org and space with the following command:

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}
	
To report issues or provide feedback you can use the [IBM Cloud Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - Request team access [here](https://slack-invite-ibm-cloud-tech.mybluemix.net/).

## Next steps
{: #next-steps}

You're now ready to develop and deploy your first app! See [Developing and deploying your apps](/docs/cli/idt/index.html) for more information.
