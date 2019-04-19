---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-19"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Installing the stand-alone {{site.data.keyword.cloud_notm}} CLI
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI provides the command-line interface for managing resources in {{site.data.keyword.cloud_notm}}. You can still use the `cf` CLI to log in to {{site.data.keyword.cloud_notm}}, but it works with a Cloud Foundry service in {{site.data.keyword.cloud_notm}}. 

If you want to install both the {{site.data.keyword.cloud}} CLI and other recommended plug-ins and tools for developing applications for {{site.data.keyword.cloud_notm}}, see [Getting started with the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

Use the following steps to install the stand-alone {{site.data.keyword.cloud_notm}} CLI:

1. Select the installer of your OS to download.

   Mac OS X 64 bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bit: [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64-bit (ppc64le): [installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   For 32 bit and earlier versions, go to the [{{site.data.keyword.cloud_notm}} CLI releases](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) page to download.

2. Run the installer
   * For MacOS and Windows&trade;, run the installer.
   * For Linux&trade;, extract the package and run `install` script

3. Target an API endpoint and login to {{site.data.keyword.cloud_notm}}:
   ```
   ibmcloud login
   ```
   {: codeblock}
   
Now, you're ready to manage {{site.data.keyword.cloud_notm}} resources. Type `ibmcloud help` to see the command descriptions.

If you're using a federated ID, follow the instructions [here](/docs/iam?topic=iam-federated_id#federated_id) to log in with a one-time passcode or an API key.  
{: tip}

Besides installers, you can have other options to install the {{site.data.keyword.cloud_notm}} CLI:

* Install from shell
* Download binary package and install to a custom directory

## Install from shell
{: #shell_install}

### macOS
{: #shell-install-macos}

Copy and paste the following command to a terminal of your Mac OS and run it:
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

Copy and paste the following command to a terminal of your Linux&trade; OS and run it:
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

Copy and paste the following command into a [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") terminal console and run it:
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## Install to a custom directory
{: #install-custom-dir}

When you use installers or a shell script to install the {{site.data.keyword.cloud_notm}} CLI, the binaries go to your system directories. If you want to specify a different directory, use the following steps.

### Step 1: Download the binary package based on your OS by using the following links.
{: #step1-custom-dir}

| Platform | Downloads | Checksum |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### Step 2: Extract the package to a directory that you specify.
{: #step2-custom-dir}

   After extracting the package, you can see the following content:

   For Linux&trade; and macOS:

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
   {: codeblock}

   For Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### Step 3: Add to the `PATH` environment variable and enable shell autocompletion.
{: #step3-custom-dir}

   * Add the `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` to the `PATH` environment variable.
   * For shell autocompletion support (MacOS and Linux&trade; only), refer to [this guide](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Uninstalling the stand-alone {{site.data.keyword.cloud_notm}} CLI
{: #uninstall-ibmcloud-cli}

The following sections provide details on how to uninstall the stand-alone {{site.data.keyword.cloud_notm}} CLI on specific platforms.

### Uninstalling on Windows
{: #uninstall-cli-windows}

1. Click the `Start` button, and then select `Control Panel`.
2. In the pop-up window, click `Uninstall a program`.
3. In the pop-up application list, locate `IBM Cloud Command Line Interface`.
4. Right click `IBM Cloud Command Line Interface`, and select `Uninstall`.
5. The uninstaller is started. Follow the instructions to finish the uninstallation.

### Uninstalling on Linux and macOS
{: #uninstall-cli-linux-macos}

#### Versions earlier than `0.9.0`

1. Open a terminal, and run the following commands:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. Clean up the autocompletion scripts, if you configured them. For more details, see [Enabling shell autocompletion for {{site.data.keyword.cloud_notm}} CLI (Linux and macOS only)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

#### Version `0.9.0` and later

1. Open a terminal, and run the following command:
  * `/usr/local/ibmcloud/uninstall`
2. Clean up any custom autocompletion scripts. For more details, see [Enabling shell autocompletion for {{site.data.keyword.cloud_notm}} CLI (Linux and macOS only)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Other links to further explore {{site.data.keyword.cloud_notm}} CLI
{: #other-cli-links}

* [Extend {{site.data.keyword.cloud_notm}} CLI with plug-ins](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [General CLI (ibmcloud) commands](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## Report issues and submit feedback
{: #issues}

Use the following options to report issues or submit new feature requests:
* Create issues in [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon").
* Leave messages in the [{{site.data.keyword.cloud_notm}} Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon") - Request team access [here](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![External link icon](../../../icons/launch-glyph.svg "External link icon").
