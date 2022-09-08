---

copyright:
  years: 2021, 2022
lastupdated: "2022-09-08"

keywords: IBM Cloud CLI, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, private endpoints, shell, cli private endpoints

subcollection: cli

---

{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}
{:deprecated: .deprecated}
{:important: .important}
{:tip: .tip}
{:external: target="_blank" .external}

# Installing and using private endpoints
{: #cli-private-endpoints}

To ensure that you have enhanced control and security over your data when you use the {{site.data.keyword.cloud_notm}} Command Line Interface (CLI), you have the option of using private routes to {{site.data.keyword.cloud_notm}} endpoints. Private routes are not accessible or reachable over the internet. By using the {{site.data.keyword.cloud_notm}} private endpoints feature, you can protect your data from threats from the public network and logically extend your private network.
{: shortdesc}

The CLI uses the private endpoint support that is provided by the {{site.data.keyword.cloud}} platform. Platform services that are used by the core CLI provide private endpoint support.

## Before you begin
{: #cli-private-endpoints-prereqs}

You must first enable virtual routing and forwarding in your account, and then you can enable the use of {{site.data.keyword.cloud_notm}} private service endpoints. For more information about setting up your account to support the private connectivity option, see [Enabling VRF and service endpoints](/docs/account?topic=account-vrf-service-endpoint). In addition to enabling VRF, you must be on a private network on `ibmcloud`. For more information, see [how to connect to the {{site.data.keyword.cloud_notm}} VPN](/docs/iaas-vpn?topic=iaas-vpn-getting-started).

To learn more about private connections on {{site.data.keyword.cloud_notm}}, see [Secure access to services by using service endpoints](/docs/account?topic=account-service-endpoints-overview).

## Installing from the shell
{: #cli-private-endpoints-shell}

To install the latest CLI for your OS from the shell manually, use the following command for your OS:

If you don't want to install from the shell because it might use root permissions, you can [download and run the installer](/docs/cli?topic=cli-cli-private-endpoints#cli-private-endpoints-download).
{: tip}

* For **Mac**, copy and paste the following command to a command line and run it:
   ```curl
   curl -fsSL https://ibm-cloud-cli-installer-scripts.s3.private.us.cloud-object-storage.appdomain.cloud/osx_private | sh
   ```
   {: codeblock}

* For **Linux&trade;**, copy and paste the following command to a command line and run it:
   ```curl
   curl -fsSL https://ibm-cloud-cli-installer-scripts.s3.private.us.cloud-object-storage.appdomain.cloud/linux_private | sh
   ```
   {: codeblock}

* For **Windows&trade;**, copy and paste the following command to a [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: external} command prompt and run it:
   ```bash
   iex (New-Object Net.WebClient).DownloadString('https://ibm-cloud-cli-installer-scripts.s3.private.us.cloud-object-storage.appdomain.cloud/powershell_private')
   ```
   {: codeblock}

   If you encounter errors like `The underlying connection was closed: An unexpected error occurred on a send`, make sure you have .Net Framework 4.5 or later installed. Also, try to enable TLS 1.2 protocol by running the following command:

   ```bash
   [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
   ```
   {: codeblock}

## Downloading installation packages with private endpoints
{: #cli-private-endpoints-download}

Use the following steps to install the latest stand-alone {{site.data.keyword.cloud_notm}} CLI:

1. Select the installer of your OS to begin the download. The following operating systems are supported: macOS X 64-bit, Windows™ 64-bit, Linux&trade; x86 64-bit, Linux&trade; LE 64-bit (ppc64le), and System/390 Linux&trade;.

2. Run the installer:
   * For Mac and Windows&trade;, run the installer.
   * For Linux&trade;, extract the package and run the `install` script.

   **Installers:**
   - [Mac OS X 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0.pkg)
   - [Mac OS X M1/ARM](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_arm64.pkg) **(provided as-is)**
   - [Windows&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_amd64.exe)
   - [Windows&trade; 32-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_386.exe)
   - [Linux&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_amd64.tar.gz)
   - [Linux&trade; 64-bit ARM](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_arm64.tar.gz)
   - [Linux&trade; 32-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_386.tar.gz)
   - [PowerLinux&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_ppc64le.tar.gz)
   - [System/390 Linux&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/IBM_Cloud_CLI_2.10.0_s390x.tar.gz)

3. Log in to {{site.data.keyword.cloud_notm}} by using the CLI:
   ```bash
   ibmcloud login
   ```
   {: codeblock}

   Now, you're ready to manage {{site.data.keyword.cloud_notm}} resources. Enter `ibmcloud help` to view the command descriptions.

   If you're using a federated ID, [log in with a one-time passcode or an API key](/docs/account?topic=account-federated_id).
   {: tip}

## Installing packages from previous releases for private endpoints
{: #cli-private-endpoints-previous}

If you want to install these packages from previous releases, follow this template to construct the private endpoint link of the package that you want to download, replacing *release_tag* with the release version that you want to download.

To view previous releases, access the official [ibm-cloud-cli-releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/tags) GitHub repository.

### Mac OS X 64-bit
{: #cli-private-endpoints-mac64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>.pkg
   ```
   {: codeblock}

### Windows&trade; 64-bit
{: #cli-private-endpoints-windows64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>_amd64.exe
   ```
   {: codeblock}

### Windows&trade; 32-bit
{: #cli-private-endpoints-windows32}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>_386.exe
   ```
   {: codeblock}

### Linux&trade; 64-bit
{: #cli-private-endpoints-linux64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>_amd64.tar.gz
   ```
   {: codeblock}

### Linux&trade; 32-bit
{: #cli-private-endpoints-linux32}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>_386.tar.gz
   ```
   {: codeblock}

### PowerLinux&trade; 64-bit
{: #cli-private-endpoints-powerlinux64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>_ppc64le.tar.gz
   ```
   {: codeblock}

### System/390 Linux&trade; 64-bit
{: #cli-private-endpoints-s390linux64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/IBM_Cloud_CLI_<release_tag>_s390x.tar.gz
   ```
   {: codeblock}

## Installing to a custom directory
{: #install-private-custom-dir}

When you use installers or a shell script to install the {{site.data.keyword.cloud_notm}} CLI, it is installed in your system directories. If you want to specify a different directory, use the following steps.

If you install the {{site.data.keyword.cloud_notm}} CLI to a custom directory, the `ibmcloud update` command can't be used to update the CLI.
{: important}

1. **Select** the matching binary of your platform to begin the download. The following platforms are supported: macOS, linux32, linux64, ppc64le, win32, win64, and s390x.

2. Extract the package to a directory that you specify.

   You can see the following extracted content:

   For Linux&trade; and Mac:
   ```text
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   └──  ibmcloud

   ```
   {: screen}

   For Windows&trade;:
   ```text
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   └── ibmcloud.exe
   ```
   {: screen}

3. Add to the `PATH` environment variable and enable shell autocompletion.
   * Add the `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` to the `PATH` environment variable.
   * For shell autocompletion support (Mac and Linux&trade; only), see [Enabling shell autocompletion for IBM Cloud CLI](/docs/cli/reference/ibmcloud?topic=cli-shell-autocomplete#shell-autocomplete).

### Binary files
{: #install-custom-binary-files}

   - [Mac OS X 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_macos.tgz)
   - [Windows&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_windows_amd64.zip)
   - [Windows&trade; 32-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_windows_386.zip)
   - [Linux&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_linux_amd64.tgz)
   - [Linux&trade; 64-bit ARM](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_linux_arm64.tgz)
   - [Linux&trade; 32-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_linux_386.tgz)
   - [PowerLinux&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_linux_ppc64le.tgz)
   - [System/390 Linux&trade; 64-bit](https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/2.10.0/binaries/IBM_Cloud_CLI_2.10.0_linux_s390x.tgz)

   If you want to install binaries from previous releases, follow this template to construct the private endpoint link of the binary that you want to download, replacing *release_tag* with the release version that you want to download.

   To view previous releases, access the official [ibm-cloud-cli-releases](https://github.com/IBM-Cloud/ibm-cloud-cli-release/tags) Github repository.

#### Mac OS X 64-bit
{: #binary-mac64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_macos.tgz
   ```
   {: codeblock}

#### Windows 64-bit
{: #binary-windows64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_windows_amd64.zip
   ```
   {: codeblock}

#### Windows 32-bit
{: #binary-windows32}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_windows_386.zip
   ```
   {: codeblock}

#### Linux 64-bit
{: #binary-linux64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_linux_amd64.tgz
   ```
   {: codeblock}

#### Linux 32-bit
{: #binary-linux32}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_linux_386.tgz
   ```
   {: codeblock}

#### Power Linux 64-bit
{: #binary-powerlinux64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_linux_ppc64le.tgz
   ```
   {: codeblock}

#### System/390 Linux 64-bit
{: #binary-s390linux64}

   ```bash
   https://ibm-cloud-cli.s3.private.us.cloud-object-storage.appdomain.cloud/<release_tag>/binaries/IBM_Cloud_CLI_<release_tag>_linux_s390x.tgz
   ```
   {: codeblock}

## Using private endpoints in the CLI
{: #cli-private-endpoints-using}

For instructions on how to use private endpoints in the CLI, and to view the list of commands that support private endpoints, see [Logging in to the CLI with a private endpoint](/docs/cli?topic=cli-service-connection#cli-private-login)

## Related information
{: #cli-private-endpoints-related}

For more information, see [Securing your connection when using the {{site.data.keyword.cloud_notm}} CLI](/docs/cli?topic=cli-service-connection).
