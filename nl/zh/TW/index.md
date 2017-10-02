---



copyright:

  years: 2015, 2017

lastupdated: "2017-06-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# 手動 CLI 安裝
{: #cli}

{{site.data.keyword.Bluemix}} CLI 提供指令行體驗來管理 {{site.data.keyword.Bluemix_notm}} 環境。它也會在其安裝中包括 Cloud Foundry 指令行介面 cf，用來管理 Cloud Foundry 應用程式及服務。
{:shortdesc}

這兩個 CLI 工具依預設都會使用 443 埠。如果您在 CLI 工具與 {{site.data.keyword.Bluemix_notm}} 環境之間有 HTTP Proxy，則必須使用實際 HTTP Proxy URL 及埠（如果有的話）來配置 `HTTP_PROXY` 環境變數。如需詳細資料，請參閱 [Using the CLI with an HTTP Proxy Server ![外部鏈結圖示](../icons/launch-glyph.svg)](http://docs.cloudfoundry.org/cf-cli/http-proxy.html){: new_window}。

[下載 {{site.data.keyword.Bluemix_notm}} CLI](/docs/cli/reference/bluemix_cli/all_versions.html){: new_window} 

如果您是在 macOS 上，則開始使用 IBM Cloud 工具的最簡單方式是使用 [IBM Cloud Application Tools 2](/docs/cli/icat.html)。
{: tip}

## ![](./images/CLI_Plugin.svg) 指令行介面外掛程式
{: #cliplugins notoc}

使用其他指令，輕鬆延伸您的 {{site.data.keyword.Bluemix_notm}} 指令行介面。若要存取 {{site.data.keyword.Bluemix_notm}} 指令行介面外掛程式，請參閱 [CLI 外掛程式儲存庫 ![外部鏈結圖示](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window}。

### 延伸 {{site.data.keyword.Bluemix_notm}} 指令行介面：bx
{: #cli_bluemix_ext notoc}


在您安裝 {{site.data.keyword.Bluemix_notm}} cli 工具之後，依預設會預先配置儲存庫別名為 `Bluemix` 的 [CLI 外掛程式儲存庫 ![外部鏈結圖示](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window}。您可以直接安裝可用的外掛程式。

```
bluemix plugin install plugin_name -r Bluemix
```

| *{{site.data.keyword.autoscaling}} CLI* |  *IBM Bluemix Container Service*  |
|-----|-----|
| 外掛程式名稱：auto-scaling <br> [檢視文件](/docs/cli/plugins/auto-scaling/index.html) |  外掛程式名稱：container-service  <br> [檢視文件](/docs/containers/cs_cli_devtools.html) |
{: caption="表 2. 外掛程式" caption-side="top"}

|  *專用網路對等作業* | *Schematics* | *VPN*  |
|-----|-----|-----|
| 外掛程式名稱：private-network-peering  <br> [檢視文件](/docs/cli/plugins/pnp/index.html) | 外掛程式名稱：Schematics  <br> [檢視文件](/docs/services/schematics/schematics_reference.html) | 外掛程式名稱：VPN <br> [檢視文件](/docs/cli/plugins/bx_vpn/index.html) |
{: caption="表 3. 外掛程式" caption-side="top"}

您也可以從符合 {{site.data.keyword.Bluemix_notm}} CLI 架構的其他儲存庫新增外掛程式。
1. 若要從另一個儲存庫安裝 {{site.data.keyword.Bluemix_notm}} CLI 外掛程式，請設定外掛程式登錄端點：
```
bluemix plugin repo-add bluemix-other-repo [repo_url]
```
其中 `repo_url` 是外掛程式儲存庫的 HTTPS URL。

2. 執行下列指令，以安裝外掛程式：
```
bluemix plugin install plugin_name -r bluemix-other-repo
```

### 延伸 Cloud Foundry 指令行介面：bx cf
{: #cli_cf_ext notoc}

在您安裝 {{site.data.keyword.Bluemix_notm}} 指令行介面之後，也會在 {{site.data.keyword.Bluemix_notm}} CLI 目錄內安裝 Cloud Foundry 指令行介面。請使用 `bluemix cf` 執行 Cloud Foundry CLI 指令。

* 若要從 {{site.data.keyword.Bluemix_notm}} 登錄安裝 cf CLI 外掛程式，請設定外掛程式登錄端點：

```
bluemix cf add-plugin-repo bluemix-cf-repo https://plugins.ng.bluemix.net
```
{: codeblock}

* 然後，執行下列指令，以安裝外掛程式：

```
bluemix cf install-plugin plugin_name -r bluemix-cf-repo
```
{: codeblock}

| *管理主控台* | *VPN* |
|-----------------|-----------------|
|  外掛程式名稱：bluemix-admin<br> [檢視文件](/docs/cli/plugins/bluemix_admin/index.html) | 外掛程式名稱：VPN <br> [檢視文件](/docs/cli/plugins/vpn/index.html) |
{: caption="表 4. 外掛程式" caption-side="top"}


## ![](./images/Integrated_Dev_Tools.svg) 整合式開發工具
{: #ide notoc}

下載並安裝外掛程式以整合您最愛的 {{site.data.keyword.Bluemix_notm}} 服務。

| *Liberty for Java* | *MobileFirst* | *{{site.data.keyword.rules_short}}* | *API Connect* | *Eclipse Tools for Bluemix* |
|----------|----------|----------|----------|----------|
| [Liberty Eclipse 外掛程式 ![外部鏈結圖示](../icons/launch-glyph.svg)](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/){: new_window} | [Eclipse 外掛程式 ![外部鏈結圖示](../icons/launch-glyph.svg)](https://marketplace.eclipse.org/content/ibm-mobilefirst-platform-studio){: new_window} | [Rules Designer Eclipse 外掛程式](../services/rules/index.html#rulov002) | [Developer Toolkit](/docs/services/apiconnect/creating_apis.html#install_dev_tk ) | [Bluemix Eclipse 外掛程式](/docs/manageapps/eclipsetools/eclipsetools.html) |
{: caption="表 5. 外掛程式" caption-side="top"}
