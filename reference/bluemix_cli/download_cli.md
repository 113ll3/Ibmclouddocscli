---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# Download and install {{site.data.keyword.Bluemix_notm}} CLI
{: #download_install}

You can use an installer or shell to download and install the CLI.

## Use installer
{: #installer}

To install the {{site.data.keyword.Bluemix_notm}} CLI:
* Go [here](all_versions.html) to download the installer.
* For macOS and Windows, run the installer. 
* For Linux, after downloading the installer package, extract it and run the installation script with root permission.

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## Install from the shell
{: #shell_install}


### macOS

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
