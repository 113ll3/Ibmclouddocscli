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

# 使用外掛程式延伸 {{site.data.keyword.cloud_notm}} CLI
{: #plug-ins}

{{site.data.keyword.cloud}} CLI 支援可延伸其功能的外掛程式架構。您可以從儲存庫或 Web URL 安裝外掛程式，或者在本端安裝外掛程式二進位檔。

[{{site.data.keyword.cloud_notm}} CLI 外掛程式儲存庫](https://plugins.cloud.ibm.com/ui/repository.html){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 是管理外掛程式的正式儲存庫。

如需其他可管理外掛程式的指令，請執行 `ibmcloud plugin` 以查看說明訊息。
{: tip}

## 從 {{site.data.keyword.cloud_notm}} CLI 儲存庫安裝外掛程式
{: #install-from-repo}

### 搜尋外掛程式
{: #cli-search-plugin}

使用 `ibmcloud plugin repo-plugins -r REPO_NAME` 指令來尋找儲存庫中的外掛程式。

{{site.data.keyword.cloud_notm}} CLI 提供名稱為 'IBM Cloud' 的正式儲存庫，您可以如範例中所示地進行搜尋：
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

### 安裝外掛程式
{: #cli-install-plugin}

使用 `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` 指令來安裝外掛程式。例如，使用下列指令，從正式 IBM 外掛程式儲存庫 'IBM Cloud' 安裝外掛程式：
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

## 在本端安裝外掛程式
{: #install-plugin-locally}

使用 `ibmcloud plugin install LOCAL_FILE_NAME` 指令，將外掛程式二進位檔安裝至本端機器。例如：
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

## 從 Web URL 安裝外掛程式
{: #install-plugin-from-url}

使用 `ibmcloud plugin install URL` 指令，直接從 Web URL 安裝外掛程式。例如：
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
