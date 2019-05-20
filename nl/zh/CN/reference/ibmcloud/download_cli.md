---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# 安装独立 {{site.data.keyword.cloud_notm}} CLI
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI 提供命令行界面用于管理 {{site.data.keyword.cloud_notm}} 中的资源。您仍可以使用 `cf` CLI 登录到 {{site.data.keyword.cloud_notm}}，但是只能用于 {{site.data.keyword.cloud_notm}} 中的 Cloud Foundry 服务。 

如果要安装最新的 {{site.data.keyword.cloud}} CLI 以及其他建议的插件和工具来开发 {{site.data.keyword.cloud_notm}} 应用程序，请参阅 [{{site.data.keyword.cloud_notm}} CLI 入门](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)。
{: tip}

## 开始之前
{: #before-download-cli}

如果需要使用 32 位版本或 {{site.data.keyword.cloud_notm}} Dedicated 环境的最新版本之外的先前版本，请参阅 [{{site.data.keyword.cloud_notm}} CLI 发行版](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")。


## 使用安装程序进行安装
{: #ibmcloud-cli-installer}

要安装最新的独立 {{site.data.keyword.cloud_notm}} CLI，请使用以下步骤：

1. 选择要下载的适用于您操作系统的安装程序：
  *  macOS X 64 位：[installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * Windows 64 位：[installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * Linux x86 64 位：[installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * Linux LE 64 位 (ppc64le)：[installer](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")

2. 运行安装程序：
  * 对于 Mac 和 Windows&trade;，运行安装程序。
  * 对于 Linux&trade;，解压缩软件包，然后运行 `install` 脚本。

3. 登录到 {{site.data.keyword.cloud_notm}}：
  ```
    ibmcloud login
    ```
  {: codeblock}
   
  现在，您可以开始管理 {{site.data.keyword.cloud_notm}} 资源。输入 `ibmcloud help` 以查看命令描述。

  如果使用的是联合标识，请[使用一次性密码或 API 密钥进行登录](/docs/iam?topic=iam-federated_id)。
  {: tip}

## 通过 shell 进行安装
{: #shell_install}

要通过 shell 手动为操作系统安装最新的 CLI，请使用适用于您操作系统的以下命令：

* 对于 **Mac**，将以下命令复制并粘贴到终端，然后运行该命令：
  ```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
  {: codeblock}

* 对于 **Linux&trade;**，将以下命令复制并粘贴到终端，然后运行该命令：
  ```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
  {: codeblock}

* 对于 **Windows&trade;**，将以下命令复制并粘贴到 [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") 终端控制台，然后运行该命令：
  ```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
  {: codeblock}

## 安装到定制目录
{: #install-custom-dir}

使用安装程序或 shell 脚本安装 {{site.data.keyword.cloud_notm}} CLI 时，会将其安装在系统目录中。如果要指定其他目录，请使用以下步骤。

1. 使用以下链接，下载适用于您操作系统的二进制文件包：
  * macOS：[tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * linux32：[tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * linux64：[tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * ppc64le：[tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * win32：[zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") /[sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")
  * win64：[zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标") / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")

2. 将包解压缩到指定的目录。

   您可以看到以下解压缩的内容：

   对于 Linux&trade; 和 Mac：
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

   对于 Windows：
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

3. 添加到 `PATH` 环境变量并启用 shell 自动完成。
  * 将 `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` 添加到 `PATH` 环境变量。
  * 有关 shell 自动完成支持（仅限 Mac 和 Linux&trade;）的信息，请参阅[本指南](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。

## 更新 {{site.data.keyword.cloud_notm}} CLI
{: #update-ibmcloud-cli}

您必须使用 CLI 的最新版本。如果使用的不是最新版本，请运行以下命令来更新 CLI：

```
ibmcloud update
```
{: codeblock}

要确定 {{site.data.keyword.cloud_notm}} CLI 版本，请运行以下命令：
```
ibmcloud -v
```
{: codeblock}

如果运行的是当前发行版，那么将显示以下输出：
```
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

要获取有关新 {{site.data.keyword.cloud_notm}} CLI 发行版的通知，请预订 [{{site.data.keyword.cloud_notm}} CLI 发行版存储库](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")。
