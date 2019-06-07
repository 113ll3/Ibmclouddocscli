---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-15"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI provides the command-line interface for managing resources in {{site.data.keyword.cloud_notm}}. You can still use the `cf` CLI to log in to {{site.data.keyword.cloud_notm}}, but it works with a Cloud Foundry service in {{site.data.keyword.cloud_notm}}. 

If you want to install both the latest {{site.data.keyword.cloud}} CLI and other recommended plug-ins and tools for developing applications for {{site.data.keyword.cloud_notm}}, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started).
{: tip}

## Before you begin
{: #before-download-cli}

If you need to use a 32-bit version, or a previous version other than the latest for {{site.data.keyword.cloud_notm}} Dedicated environments, see [{{site.data.keyword.cloud_notm}} CLI releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon").

## Installing with an installer
{: #ibmcloud-cli-installer}

Use the following steps to install the latest stand-alone {{site.data.keyword.cloud_notm}} CLI:

1. Select the installer of your OS to download:
  *  macOS X 64 bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * Windows 64 bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * Linux x86 64 bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * Linux LE 64-bit (ppc64le): [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")

2. Run the installer:
  * For Mac and Windows&trade;, run the installer.
  * For Linux&trade;, extract the package and run the `install` script.

3. Log in to {{site.data.keyword.cloud_notm}}:
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  Now, you're ready to manage {{site.data.keyword.cloud_notm}} resources. Enter `ibmcloud help` to view the command descriptions.

  If you're using a federated ID, [log in with a one-time passcode or an API key](/docs/iam?topic=iam-federated_id).
  {: tip}

## Installing from the shell
{: #shell_install}

To install the latest CLI for your OS from the shell manually, use the following command for your OS:

* For **Mac**, copy and paste the following command to a terminal and run it:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* For **Linux&trade;**, copy and paste the following command to a terminal and run it:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* For **Windows&trade;**, copy and paste the following command to a [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") terminal console and run it:
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## Installing to a custom directory
{: #install-custom-dir}

When you use installers or a shell script to install the {{site.data.keyword.cloud_notm}} CLI, it is installed in your system directories. If you want to specify a different directory, use the following steps.

1. Download the binary package for your OS by using the following links:
  * macOS: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * linux32: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * linux64: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * ppc64le: [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * win32: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") /[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")
  * win64: [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon")

2. Extract the package to a directory that you specify.

   You can see the following extracted content:

   For Linux&trade; and Mac:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   For Windows:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Add to the `PATH` environment variable and enable shell autocompletion.
  * Add the `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` to the `PATH` environment variable.
  * For shell autocompletion support (Mac and Linux&trade; only), refer to [this guide](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Updating the {{site.data.keyword.cloud_notm}} CLI
{: #update-ibmcloud-cli}

You must use the latest version of the CLI. If you aren't using the latest version, run the following command to update your CLI:

```
ibmcloud update
```
{: codeblock}

To determine your {{site.data.keyword.cloud_notm}} CLI version, run the following command:
```
ibmcloud -v
```
{: codeblock}

If you are running the current release, the following output is displayed:
```
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

To get notified about new {{site.data.keyword.cloud_notm}} CLI releases, subscribe to the [{{site.data.keyword.cloud_notm}} CLI releases repository](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon").
