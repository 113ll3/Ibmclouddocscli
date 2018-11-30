---



copyright:

  years: 2015, 2018
lastupdated: "2018-11-15"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 安装独立 {{site.data.keyword.Bluemix_notm}} CLI
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI 提供命令行界面用于管理 {{site.data.keyword.Bluemix_notm}} 中的资源。您依旧可以使用 `cf` CLI 登录到 {{site.data.keyword.Bluemix_notm}}，但这仅适用于 {{site.data.keyword.Bluemix_notm}} 中的 Cloud Foundry 服务。 

如果要安装 {{site.data.keyword.Bluemix}} CLI 以及其他建议的插件和工具来开发 {{site.data.keyword.Bluemix_notm}} 应用程序，请按照[此处](/docs/cli/index.html)所述的方法来执行操作。
{: tip}

要安装独立 {{site.data.keyword.Bluemix_notm}} CLI，请执行以下操作：

1. 选择要下载的适用于您操作系统的安装程序

   Mac OS X 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 位：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 位 (ppc64le)：[安装程序](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window}<br>

   对于 32 位和更早版本，请转至[所有版本](/docs/cli/reference/ibmcloud/all_versions.html)页面进行下载

1. 运行安装程序
   * 对于 macOS 和 Windows，请运行安装程序。
   * 对于 Linux，请解压缩程序包，并运行 `install` 脚本。

1. 将 API 端点定为目标，然后登录到 {{site.data.keyword.Bluemix_notm}}

   ```
ibmcloud login
```
   {: codeblock}
   
现在，您可以管理 {{site.data.keyword.Bluemix_notm}} 资源了。输入 `ibmcloud help` 以查看命令描述。

如果您使用的是联合标识，请按照[此处](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)的指示信息，使用一次性密码或 API 密钥进行登录。  
{: tip}

除了使用安装程序，您还可以使用其他选项来安装 {{site.data.keyword.Bluemix_notm}} CLI：

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

使用安装程序或 shell 脚本来安装 {{site.data.keyword.Bluemix_notm}} CLI 时，二进制文件将位于系统目录中。如果要指定其他目录，请使用以下步骤。

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

   解压缩包后，将会看到如下所示的内容：

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
   * 有关 shell 自动完成支持（仅限 MacOS 和 Linux）的信息，请参阅[启用 CLI 自动完成](enable_cli_autocompletion.html)。
   
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
2. 如果配置了自动完成脚本，请清除这些脚本。有关更多信息，请参阅[启用 CLI 自动完成](enable_cli_autocompletion.html)。

#### V`0.9.0` 和更高版本

1. 打开终端，然后运行以下命令：
  * `/usr/local/ibmcloud/bin/uninstall`
2. 如果配置了自动完成脚本，请清除这些脚本。有关更多信息，请参阅[启用 CLI 自动完成](enable_cli_autocompletion.html)。


## 用于进一步探索 {{site.data.keyword.Bluemix_notm}} CLI 的其他链接

* [使用插件扩展 {{site.data.keyword.Bluemix_notm}} CLI 功能](/docs/cli/reference/ibmcloud/extend_cli.html)
* [{{site.data.keyword.Bluemix_notm}} CLI 参考](/docs/cli/reference/ibmcloud/bx_cli.html)

## 报告问题并提交反馈
{: #issues}

使用以下选项来报告问题或提交新的功能请求：
 * 在 [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 中创建问题。
 * 在 [IBM Cloud Tech 的 Slack - #developer-tools 通道](https://ibm-cloud-tech.slack.com) - 请求团队访问[此处](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 中留言。
