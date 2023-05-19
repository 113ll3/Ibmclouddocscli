---

copyright:
  years: 2021, 2023
lastupdated: "2022-05-19"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI
{: #install-ibmcloud-cli}

The {{site.data.keyword.cloud}} Command Line Interface provides commands for managing resources in {{site.data.keyword.cloud_notm}}. When you install the standalone {{site.data.keyword.cloud_notm}} CLI, you get only the CLI itself without any recommended plug-ins or tools.
{: shortdesc}

If you want to install both the latest {{site.data.keyword.cloud_notm}} CLI and other recommended plug-ins and tools for developing applications for {{site.data.keyword.cloud_notm}}, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-getting-started) and [Extending IBM Cloud CLI with plug-ins](/docs/cli?topic=cli-plug-ins).
{: tip}

## Before you begin
{: #before-download-cli}

If you need to use a 32-bit version, or a previous version other than the latest for {{site.data.keyword.cloud_notm}} Dedicated environments, see [{{site.data.keyword.cloud_notm}} CLI releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external}.

## Installing with an installer
{: #ibmcloud-cli-installer}

Use the following steps to install the latest stand-alone {{site.data.keyword.cloud_notm}} CLI:

1. Use a browser to access the official [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub repository, and **select** the installer of your OS to begin the download. The following operating systems are supported: macOS X 64-bit, Windows&trade; 64-bit, Linux&trade; x86 64-bit, and Linux&trade; LE 64-bit (ppc64le).

2. Run the installer:
   * For Mac and Windows&trade;, run the installer.
   * For Linux&trade;, extract the package and run the `install` script.

3. Log in to {{site.data.keyword.cloud_notm}}:
   ```bash
   ibmcloud login
   ```
   {: codeblock}
   
   Now, you're ready to manage {{site.data.keyword.cloud_notm}} resources. Enter `ibmcloud help` to view the command descriptions.

   If you're using a federated ID, [log in with a one-time passcode or an API key](/docs/account?topic=account-federated_id).
   {: tip}

## Installing from the shell
{: #shell_install}

To install the latest CLI for your OS from the shell manually, use the following command for your OS:

   If you don't want to install from the shell because it might utilize root permissions, you can [download and run the installer](/docs/cli?topic=cli-install-ibmcloud-cli#ibmcloud-cli-installer).
   {: tip}

* For **Mac**, copy and paste the following command to a terminal and run it:
   ```bash
   curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
   ```
   {: codeblock}

* For **Linux&trade;**, copy and paste the following command to a terminal and run it:
   ```bash
   curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
   ```
   {: codeblock}

* For **Windows&trade;**, copy and paste the following command to a [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: external} terminal console and run it:
   ```bash
   iex (New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
   ```
   {: codeblock}

   If you encounter errors like `The underlying connection was closed: An unexpected error occurred on a send`, make sure you have .Net Framework 4.5 or later installed. Also try to enable TLS 1.2 protocol by running the following command:
  
   ```bash
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
   ```
   {: codeblock}

## Installing to a custom directory
{: #install-custom-dir}

When you use installers or a shell script to install the {{site.data.keyword.cloud_notm}} CLI, it is installed in your system directories. If you want to specify a different directory, use the following steps.

If you install the {{site.data.keyword.cloud_notm}} CLI to a custom directory, the `ibmcloud update` command can't be used to update the CLI.
{: note}

1. Use a browser to access the official [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub repository, and **select** the matching binary of your platform to begin the download. The following platforms are supported: macOS, linux32, linux64, ppc64le, win32, and win64.

2. Extract the package to a directory that you specify.

   You can see the following extracted content:

   For Linux&trade; and Mac:
   ```bash
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   For Windows&trade;:
   ```bash
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Add to the `PATH` environment variable and enable shell autocompletion.
   * Add the `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` to the `PATH` environment variable.
   * For shell autocompletion support (Mac and Linux&trade; only), see [Enabling shell autocompletion for IBM Cloud CLI](/docs/cli/reference/ibmcloud?topic=cli-shell-autocomplete#shell-autocomplete).

## Updating the {{site.data.keyword.cloud_notm}} CLI
{: #update-ibmcloud-cli}

You must use the latest version of the CLI. If you aren't using the latest version, run the following command to update your CLI:

```bash
ibmcloud update
```
{: codeblock}

To determine your {{site.data.keyword.cloud_notm}} CLI version, run the following command:
```bash
ibmcloud -v
```
{: codeblock}

If you are running the current release, the following output is displayed:
```bash
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

To get notified about new {{site.data.keyword.cloud_notm}} CLI releases, subscribe to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: external}.
