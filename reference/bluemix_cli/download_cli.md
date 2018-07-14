---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-13"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Installing the stand-alone {{site.data.keyword.Bluemix_notm}} CLI
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI provides the command line interface to manage applications, containers, infrastructures, services and other resources in {{site.data.keyword.Bluemix_notm}}.

If you want to install both the {{site.data.keyword.Bluemix}} CLI and other recommended plugins and tools for developing applications for {{site.data.keyword.Bluemix_notm}}, follow the method described [here](/docs/cli/index.html).
{: tip}

Use the following steps to install the stand-alone {{site.data.keyword.Bluemix_notm}} CLI:

1. Select the installer of your OS to download

   Mac OS X 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bit: [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64-bit (ppc64le): [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **32 bit releases and previous versions can be found [here](all_versions.html)

1. Run the installer
   * For macOS and windows, just run the installer.
   * For Linux, extract the package and run `install_bluemix_cli` script

1. Target an API endpoint and login to {{site.data.keyword.Bluemix_notm}}

   ```
   ibmcloud login
   ```
   {: codeblock}
   
Now you are ready to manage {{site.data.keyword.Bluemix_notm}} resouces. Type `ibmcloud help` to see the command descriptions.

If you are using a federated ID, follow the instructions [here](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) to log in with a one-time passcode or an API key.  
{: tip}


Besides [installers](install_use_cli.html#getting_started), you can have other options to install the {{site.data.keyword.Bluemix_notm}} CLI:

* Install from shell
* Download binary package and install to a custom directory

## Install from shell
{: #shell_install}

### MacOS

Copy and paste the following command to a terminal of your Mac OS and run it:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copy and paste the following command to a terminal of your Linux OS and run it:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copy and paste the following command into a [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} terminal console and run it:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Install to a custom directory

When you use installers or a shell script to install the {{site.data.keyword.Bluemix_notm}} CLI, the binaries will go to your system directories. If you want to specify a different directory, use the following steps.

1. Download the binaries.

   Use the following links and download the binary package based on your OS.

| Platform | Downloads | Checksum |
|-----|-----|-----|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. Extract the package to a directory that you specify.

   After extracting the package, the content will look like the following:

   For Linux and MacOS

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

1. Add to the `PATH` environment variable and enable shell autocompletion.

   * Add the `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` to the `PATH` environment variable.
   * For shell autocompletion support (MacOS and Linux only), refer to [this guide](enable_cli_autocompletion.html).

## Other links to further explore {{site.data.keyword.Bluemix_notm}} CLI

* [Extend {{site.data.keyword.Bluemix_notm}} CLI capabilities with plugins](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [General {{site.data.keyword.Bluemix_notm}} CLI commands usage](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [General {{site.data.keyword.Bluemix_notm}} (ibmcloud sl) commands usage](/docs/cli/reference/softlayer/index.html)

## Report issues and submit feedback
{: #issues}

Use the following options to report issues or submit new feature requests:
 * Create issues in [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![External link icon](../../../icons/launch-glyph.svg).
 * Leave messages in the [IBM Cloud Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - Request team access [here](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![External link icon](../../../icons/launch-glyph.svg).
