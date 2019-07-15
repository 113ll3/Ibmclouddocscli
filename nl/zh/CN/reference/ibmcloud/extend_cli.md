---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-21"

keywords: extend cli, ibmcloud repo-plugins, repo-plugins, plug-in, plugin, ibmcloud cli, ibmcloud, ibmcloud dev, cli, command line, command-line, developer tools, plugin install

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 使用插件扩展 {{site.data.keyword.cloud_notm}} CLI
{: #plug-ins}

{{site.data.keyword.cloud}} CLI 支持通过插件框架来扩展其功能。您可以从存储库或 Web URL 安装插件，也可以在本地安装插件二进制文件。

[{{site.data.keyword.cloud_notm}} CLI 插件存储库](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![外部链接图标](../../../icons/launch-glyph.svg) 是用于托管插件的官方存储库。

有关管理插件的更多命令，请运行 `ibmcloud plugin` 以查看帮助消息。
{: tip}

## 从 {{site.data.keyword.cloud_notm}} CLI 存储库安装插件
{: #install-from-repo}

### 搜索插件
{: #cli-search-plugin}

使用 `ibmcloud plugin repo-plugins -r REPO_NAME` 命令在存储库中查找插件。

{{site.data.keyword.cloud_notm}} CLI 提供名称为“IBM Cloud”的正式插件存储库，您可以进行搜索，如以下示例所示：
```
ibmcloud plugin repo-plugins -r "IBM Cloud"
```
{: codeblock}

```
Status             Name                                        Versions                       Description   
Update Available   container-service/kubernetes-service        0.3.49, 0.3.47, 0.3.34...      IBM Cloud Kubernetes Service for management of Kubernetes clusters   
Update Available   cloud-functions                             1.0.32, 1.0.30, 1.0.29...      Manage Cloud Functions 
...
```
{: screen}

### 安装插件
{: #cli-install-plugin}

使用 `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` 命令安装插件。例如，使用以下命令安装官方 IBM 插件存储库“IBM Cloud”中的插件：
```
ibmcloud plugin install auto-scaling
```
{: codeblock}

```
Looking up 'auto-scaling' from repository 'IBM Cloud'...
Plug-in 'auto-scaling 0.2.7' found in repository 'IBM Cloud'
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [============================================] 100.00% 1s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
```
{: screen}

## 在本地安装插件
{: #install-plugin-locally}

使用 `ibmcloud plugin install LOCAL_FILE_NAME` 命令在本地计算机上安装插件二进制文件。例如：
```
ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Installing plugin './auto-scaling-darwin-amd64-0.2.7'...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}

## 通过 Web URL 安装插件
{: #install-plugin-from-url}

使用 `ibmcloud plugin install URL` 命令直接通过 Web URL 安装插件。例如：
```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/auto-scaling/0.2.7/auto-scaling-darwin-amd64-0.2.7
```
{: codeblock}

```
Attempting to download the binary file...
 7.28 MiB / 7.28 MiB [===========================================] 100.00% 0s
7636608 bytes downloaded
Installing binary...
OK
Plug-in 'auto-scaling 0.2.7' was successfully installed into /Users/username/.bluemix/plugins/auto-scaling. Use 'ibmcloud plugin show auto-scaling' to show its details.
$
```
{: screen}
