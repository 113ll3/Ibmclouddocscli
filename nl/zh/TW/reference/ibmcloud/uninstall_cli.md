---

copyright:
  years: 2019
lastupdated: "2019-04-26"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# 解除安裝獨立式 {{site.data.keyword.cloud_notm}} CLI
{: #uninstall-ibmcloud-cli}

請使用下列步驟，在特定平台上解除安裝獨立式 {{site.data.keyword.cloud_notm}} CLI：
{: shortdesc}

## 在 Windows 上解除安裝
{: #uninstall-cli-windows}

1. 按一下**開始**按鈕，然後選取**控制台**。
2. 在蹦現視窗中，按一下**解除安裝程式**。
3. 在蹦現應用程式清單中，找到 **IBM Cloud Command Line Interface**。
4. 在 **IBM Cloud Command Line Interface** 按一下滑鼠右鍵，然後選取**解除安裝**。
5. 即會啟動解除安裝程式。遵循指示以完成解除安裝。

## 在 Linux 及 macOS 上解除安裝
{: #uninstall-cli-linux-macos}

解除安裝步驟會有所不同，取決於已安裝的 CLI 版本。

若要判定您的 {{site.data.keyword.cloud_notm}} CLI 版本，請執行：
```
ibmcloud -v
```
{: codeblock}

若要解除安裝 `0.9.0` 之前的版本，請執行下列指令：
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

清除已配置的自動完成 Script。如需詳細資料，請參閱[啟用 {{site.data.keyword.cloud_notm}} CLI 的 Shell 自動完成（僅限 Linux 及 Mac）](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。

若要解除安裝 `0.9.0` 版以及更新版本，請執行下列指令：
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

清除任何自訂自動完成 Script。如需詳細資料，請參閱[啟用 {{site.data.keyword.cloud_notm}} CLI 的 Shell 自動完成（僅限 Linux 及 Mac）](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)。
