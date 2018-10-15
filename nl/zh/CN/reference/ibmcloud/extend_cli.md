---

copyright:

  years: 2015, 2018
lastupdated: "2018-10-04"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 使用插件扩展 {{site.data.keyword.Bluemix_notm}} CLI
{: #plug-ins}

{{site.data.keyword.Bluemix_notm}} CLI 支持通过插件框架来扩展其功能。您可以从存储库或 Web URL 安装插件，也可以在本地安装插件二进制文件。

[{{site.data.keyword.Bluemix_notm}} CLI 插件存储库](https://tools.ng.bluemix.net){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 是用于托管插件的官方存储库。

有关管理插件的更多命令，请运行 `ibmcloud plugin` 以查看帮助消息。
{: tip}

## 从 {{site.data.keyword.Bluemix_notm}} CLI 存储库安装插件

### 步骤 1：搜索插件

1. 使用 `ibmcloud plugin repo-plugins -r REPO_NAME` 命令在存储库中查找插件。
2. {{site.data.keyword.Bluemix_notm}} CLI 具有名称为“IBM Cloud”的官方存储库，您可以搜索官方插件，如以下示例所示：

  ```
  $ ibmcloud plugin repo-plugins -r IBM Cloud
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### 步骤 2：安装插件

使用 `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` 命令安装插件。例如，使用以下命令安装官方 IBM 插件存储库“IBM Cloud”中的插件：

  ```
  $ ibmcloud plugin install auto-scaling -r IBM Cloud
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/IBMCLoudFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## 本地安装插件

使用 `ibmcloud plugin install LOCAL_FILE_NAME` 命令在本地计算机上安装插件二进制文件。例如：

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## 通过 Web URL 安装插件

使用 `ibmcloud plugin install URL` 命令直接通过 Web URL 安装插件。例如：

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/IBMCloudFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
