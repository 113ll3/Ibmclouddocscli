---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 解除安裝 {{site.data.keyword.Bluemix_notm}} CLI

請參閱下列各節以取得如何在特定平台上解除安裝 {{site.data.keyword.Bluemix_notm}} 的指示。

## 在 Windows 上解除安裝

* 按一下`開始`按鈕，然後選取`控制台`。
* 在蹦現視窗中，按一下`解除安裝程式`。
* 在蹦現應用程式清單中，找到 `IBM Cloud Command Line Interface`。
* 在 `IBM Cloud Command Line Interface` 按一下滑鼠右鍵，然後選取`解除安裝`。
* 將會啟動解除安裝程式。遵循指示以完成解除安裝。

## 在 Linux/macOS 上解除安裝

### `0.9.0` 版之前

* 開啟終端機，然後執行下列指令：
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* 清除自動完成 Script，如果已配置的話。如需詳細資料，請參閱[啟用 CLI 自動完成](enable_cli_autocompletion.html)。

### `0.9.0` 版以及更新版本

* 開啟終端機，然後執行下列指令：
  * `/usr/local/ibmcloud/uninstall`
* 清除自動完成 Script，如果已配置的話。如需詳細資料，請參閱[啟用 CLI 自動完成](enable_cli_autocompletion.html)。
