---



copyright:

  years: 2015, 2019
lastupdated: "2019-01-04"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 安装独立 {{site.data.keyword.Bluemix_notm}} CLI
{: #install_use}

{{site.data.keyword.Bluemix}} CLI 提供命令行界面用于管理 {{site.data.keyword.Bluemix_notm}} 中的资源。您仍可以使用 cf CLI 登录到 {{site.data.keyword.Bluemix_notm}}，但是只能用于 {{site.data.keyword.Bluemix_notm}} 中的 Cloud Foundry 服务。 

如果要安装 {{site.data.keyword.Bluemix}} CLI 以及其他建议的插件和工具来开发 {{site.data.keyword.Bluemix_notm}} 应用程序，请参阅 [{{site.data.keyword.Bluemix_notm}} CLI 入门](/docs/cli/index.html)。
{: tip}

要安装独立 {{site.data.keyword.Bluemix_notm}} CLI，请执行以下操作：

1. 选择要下载的适用于您操作系统的安装程序。

   Mac OS X 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 位 (ppc64le)：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window}<br>

   对于 32 位和更早版本，请转至 [{{site.data.keyword.Bluemix_notm}} CLI 发行版](/docs/cli/reference/ibmcloud/all_versions.html)页面进行下载。

1. 运行安装程序
   * 对于 macOS 和 Windows，只需运行安装程序即可。
   * 对于 Linux，请解压缩软件包，并运行 `install` 脚本

1. 将 API 端点定为目标并登录到 {{site.data.keyword.Bluemix_notm}}

   ```
ibmcloud login
```
   {: codeblock}
   
现在，您可以随时管理 {{site.data.keyword.Bluemix_notm}} 资源。输入 `ibmcloud help` 以查看命令描述。

如果要使用联合标识，请遵循[此处](/docs/iam/login_fedid.html#federated_id)的指示信息，以使用一次性密码或 API 密钥进行登录。
  
{: tip}

除了安装程序外，您还可以使用其他选项来安装 {{site.data.keyword.Bluemix_notm}} CLI：

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

将以下命令复制并粘贴到 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 终端控制台，然后运行该命令：

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## 安装到定制目录

使用安装程序或 shell 脚本安装 {{site.data.keyword.Bluemix_notm}} CLI 时，二进制文件将转至系统目录。如果要指定其他目录，请使用以下步骤。

### 步骤 1：使用以下链接，根据您的操作系统下载二进制文件包。

|平台|下载|校验和|
|---------|----------|---------|
|macOS|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum)|
|linux32|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum)|
|linux64|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum)|
|ppc64le|[tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum)|
|win32|[zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum)|
|win64|[zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive)|[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum)|

### 步骤 2：将包解压缩到指定的目录。

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
### 步骤 3：添加到 `PATH` 环境变量并启用 shell 自动完成。

   * 将 `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` 添加到 `PATH` 环境变量。
   * 有关 shell 自动完成支持（仅限 MacOS 和 Linux）的信息，请参阅[本指南](enable_cli_autocompletion.html)。
   
## 卸载独立 {{site.data.keyword.Bluemix_notm}} CLI

以下各部分提供了有关如何在特定平台上卸载独立 {{site.data.keyword.Bluemix_notm}} CLI 的详细信息。

### 在 Windows 上卸载

1. 单击`开始`按钮，然后选择`控制面板`。
2. 在弹出窗口中，单击`卸载程序`。
3. 在弹出应用程序列表中，找到 `IBM Cloud 命令行界面`。
4. 右键单击 `IBM Cloud 命令行界面`，然后选择`卸载`。
5. 这将启动卸载程序。遵循指示信息来完成卸载。

### 在 Linux/macOS 上卸载

#### 早于 V`0.9.0` 的版本

1. 打开终端，然后运行以下命令：
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. 如果已配置自动完成脚本，请清除这些脚本。有关更多详细信息，请参阅[对 IBM Cloud CLI 启用 shell 自动完成（仅限 Linux/MacOS）](enable_cli_autocompletion.html)。

#### V`0.9.0` 和更高版本

1. 打开终端，然后运行以下命令：
  * `/usr/local/ibmcloud/bin/uninstall`
2. 如果已配置自动完成脚本，请清除这些脚本。有关更多详细信息，请参阅[对 IBM Cloud CLI 启用 shell 自动完成（仅限 Linux/MacOS）](enable_cli_autocompletion.html)。


## 用于进一步探索 {{site.data.keyword.Bluemix_notm}} CLI 的其他链接

* [使用插件扩展 {{site.data.keyword.Bluemix_notm}} CLI](/docs/cli/reference/ibmcloud/extend_cli.html)
* [常规 CLI (ibmcloud) 命令](/docs/cli/reference/ibmcloud/bx_cli.html)

## 报告问题并提交反馈
{: #issues}

使用以下选项来报告问题或提交新的功能请求：
 * 在 [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 中创建问题。
 * 在 [IBM Cloud Tech 的 Slack - #developer-tools 通道](https://ibm-cloud-tech.slack.com) - 请求团队访问[此处](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 中留言。
