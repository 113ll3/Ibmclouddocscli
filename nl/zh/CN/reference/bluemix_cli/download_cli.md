---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# 下载并安装 {{site.data.keyword.Bluemix_notm}} CLI
{: #download_install}

您可以使用安装程序或 shell 来下载和安装 CLI。

## 使用安装程序
{: #installer}

要安装 {{site.data.keyword.Bluemix_notm}} CLI，请执行以下操作：
* 转至[此处](all_versions.html)以下载安装程序。
* 对于 macOS 和 Windows，请运行安装程序。 
* 对于 Linux，下载安装程序包后，将其解压缩并以 root 用户许可权运行安装脚本。

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## 通过 shell 安装
{: #shell_install}


### macOS

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
