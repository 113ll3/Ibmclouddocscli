---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 卸载 {{site.data.keyword.Bluemix_notm}} CLI

有关如何在特定平台上卸载 {{site.data.keyword.Bluemix_notm}} 的指示信息，请参阅以下各部分。

## 在 Windows 上卸载

* 单击`开始`按钮，然后选择`控制面板`
* 在弹出窗口中，单击`卸载程序`
* 在弹出应用程序列表中，找到 `IBM Cloud 命令行界面`
* 右键单击 `IBM Cloud 命令行界面`，然后选择`卸载`
* 这将启动卸载程序。遵循指示信息来完成卸载。

## 在 Linux/macOS 上卸载

### 早于 V`0.9.0` 的版本

* 打开终端，然后执行以下命令：
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* 如果已配置自动完成脚本，请清除这些脚本。有关更多详细信息，请参阅[启用 CLI 自动完成](enable_cli_autocompletion.html)。

### V`0.9.0` 和更高版本

* 打开终端，然后执行以下命令：
  * `/usr/local/ibmcloud/uninstall`
* 如果已配置自动完成脚本，请清除这些脚本。有关更多详细信息，请参阅[启用 CLI 自动完成](enable_cli_autocompletion.html)。
