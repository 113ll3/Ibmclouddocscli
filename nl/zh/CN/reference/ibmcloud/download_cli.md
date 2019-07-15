---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-10"

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

如果要安装最新的 {{site.data.keyword.cloud}} CLI 以及其他建议的插件和工具来开发 {{site.data.keyword.cloud_notm}} 应用程序，请参阅 [{{site.data.keyword.cloud_notm}} CLI 入门](/docs/cli?topic=cloud-cli-getting-started)。
{: tip}

## 开始之前
{: #before-download-cli}

如果需要使用 32 位版本或 {{site.data.keyword.cloud_notm}} Dedicated 环境的最新版本之外的先前版本，请参阅 [{{site.data.keyword.cloud_notm}} CLI 发行版](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg "外部链接图标")。


## 使用安装程序进行安装
{: #ibmcloud-cli-installer}

要安装最新的独立 {{site.data.keyword.cloud_notm}} CLI，请使用以下步骤：

1. 使用浏览器访问正式的 [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub 存储库，并**选择**操作系统的安装程序以开始下载。支持以下操作系统：macOS X 64 位、Windows&trade; 64 位、Linux&trade; x86 64 位和 Linux&trade; LE 64 位 (ppc64le)。

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

1. 使用浏览器访问正式的 [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) GitHub 存储库，并**选择**与您的平台匹配的二进制文件以开始下载。支持以下平台：macOS、linux32、linux64、ppc64le、win32 和 win64。

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

   对于 Windows&trade;：
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
  * 有关 shell 自动完成支持（仅限 Mac 和 Linux&trade;）的信息，请参阅[对 IBM Cloud CLI 启用 shell 自动完成](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。

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
