---

copyright:

  years: 2015, 2018
lastupdated: "2018-06-21"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# 使用外掛程式延伸 {{site.data.keyword.Bluemix_notm}} CLI
{: #plug-ins}

{{site.data.keyword.Bluemix_notm}} CLI 支援可延伸其功能的外掛程式架構。您可以從儲存庫或 Web URL 安裝外掛程式，或者在本端安裝外掛程式二進位檔。

[{{site.data.keyword.Bluemix_notm}} CLI 外掛程式儲存庫](https://tools.ng.bluemix.net){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 是管理外掛程式的正式儲存庫。

如需其他可管理外掛程式的指令，請執行 `ibmcloud plugin` 以查看說明訊息。
{: tip}

## 從 {{site.data.keyword.Bluemix_notm}} CLI 儲存庫安裝外掛程式

### 步驟 1：搜尋外掛程式

1. 使用指令 `ibmcloud plugin repo-plugins -r REPO_NAME`，以尋找儲存庫中的外掛程式。
2. {{site.data.keyword.Bluemix_notm}} CLI 具有名稱為 `Bluemix` 的正式儲存庫，您可以搜尋正式外掛程式，如下列範例中所示：

  ```
  $ ibmcloud plugin repo-plugins -r Bluemix
  Getting plug-ins from repository 'Bluemix'...

  Repository: Bluemix
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### 步驟 2：安裝外掛程式

使用 `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` 指令來安裝外掛程式。例如，使用下列指令，從正式 IBM 外掛程式儲存庫 `Bluemix` 安裝外掛程式：

  ```
  $ ibmcloud plugin install auto-scaling -r Bluemix
  Looking up 'auto-scaling' from repository 'Bluemix'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## 在本端安裝外掛程式

使用 `ibmcloud plugin install LOCAL_FILE_NAME` 指令，將外掛程式二進位檔安裝至本端機器。例如：

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing pluign './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## 從 Web URL 安裝外掛程式

使用 `ibmcloud plugin install URL` 指令，直接從 Web URL 安裝外掛程式。例如：

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
