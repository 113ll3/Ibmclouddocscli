---

copyright:
  years: 2019
lastupdated: "2019-08-05"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# 卸载独立 {{site.data.keyword.cloud_notm}} CLI
{: #uninstall-ibmcloud-cli}

要卸载特定平台上的独立 {{site.data.keyword.cloud_notm}} CLI，请执行以下步骤：
{: shortdesc}

## 在 Windows 上卸载
{: #uninstall-cli-windows}

1. 单击**开始**按钮，然后选择**控制面板**。
2. 在弹出窗口中，单击**卸载程序**。
3. 在弹出应用程序列表中，找到 **IBM Cloud 命令行界面**。
4. 右键单击 **IBM Cloud 命令行界面**，然后选择**卸载**。
5. 这将启动卸载程序。遵循指示信息来完成卸载。

## 在 Linux 和 macOS 上卸载
{: #uninstall-cli-linux-macos}

卸载步骤根据安装的 CLI 的版本不同而有所不同。

要确定 {{site.data.keyword.cloud_notm}} CLI 版本，请运行：
```
ibmcloud -v
```
{: codeblock}

要卸载早于 `0.9.0` 的版本，请运行以下命令：
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

如果已配置自动完成脚本，请清除这些脚本。有关更多详细信息，请参阅[启用 {{site.data.keyword.cloud_notm}} CLI 的 shell 自动完成（仅限 Linux 和 MacOS）](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。

要卸载 V`0.9.0` 和更高版本，请运行以下命令：
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

清除所有定制自动完成脚本。有关更多详细信息，请参阅[启用 {{site.data.keyword.cloud_notm}} CLI 的 shell 自动完成（仅限 Linux 和 MacOS）](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。
