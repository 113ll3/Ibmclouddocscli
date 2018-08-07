---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 用于安装 {{site.data.keyword.Bluemix_notm}} CLI 的更多选项
{: #more_options_install}

除了[安装程序](install_use_cli.html#getting_started)外，您还可以使用其他选项来安装 {{site.data.keyword.Bluemix_notm}} CLI：

* 从 shell 安装
* 下载二进制文件包并将其安装到定制目录

## 从 shell 安装
{: #shell_install}

### MacOS

将以下命令复制并粘贴到 Mac OS 终端，然后运行该命令：

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

将以下命令复制并粘贴到 Linux 操作系统终端，然后运行该命令：

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

将以下命令复制并粘贴到 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 终端控制台，然后运行该命令：

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## 安装到定制目录

使用安装程序或 shell 脚本安装 {{site.data.keyword.Bluemix_notm}} CLI 时，二进制文件将转至系统目录。如果要指定其他目录，请使用以下步骤。

1. 下载二进制文件。

   使用以下链接，根据您的操作系统下载二进制文件包。

   |平台|下载|校验和|
   |----|----| --- |
   |macOS|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum)|
   |linux32|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum)|
   |linux64|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum)|
   |ppc64le|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum)|
   |win32|[zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum)|
   |win64|[zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum)|

1. 将包解压缩到指定的目录。

   解压缩包后，内容将如下所示：

   对于 Linux 和 MacOS

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

   对于 Windows

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

1. 添加到 `PATH` 环境变量并启用 shell 自动完成。

   * 将 `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` 添加到 `PATH` 环境变量。
   * 有关 shell 自动完成支持（仅限 MacOS 和 Linux）的信息，请参阅[本指南](enable_cli_autocompletion.html)。

