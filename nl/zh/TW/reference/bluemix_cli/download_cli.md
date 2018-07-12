---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-27"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 安裝獨立式 {{site.data.keyword.Bluemix_notm}} CLI
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI 提供指令行介面，來管理應用程式、容器、基礎架構、服務及 {{site.data.keyword.Bluemix_notm}} 中的其他資源。

如果您想要安裝 {{site.data.keyword.Bluemix}} CLI 及其他建議外掛程式和工具來開發 {{site.data.keyword.Bluemix_notm}} 的應用程式，請遵循在[這裡](/docs/cli/index.html)說明的方法。
{: tip}

請使用下列步驟，以安裝獨立式 {{site.data.keyword.Bluemix_notm}} CLI：

1. 選取要下載的 OS 安裝程式

   Mac OS X 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 位元 (ppc64le)：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **在[這裡](all_versions.html)可以找到 32 位元版次及舊版本

1. 執行安裝程式
   * 若為 macOS 及 Windows，僅執行安裝程式。
   * 若為 Linux，擷取套件並執行 `install_bluemix_cli` Script。

1. 將目標設為 API 端點並登入 {{site.data.keyword.Bluemix_notm}}

  ![範例](example.gif){: gif}

現在，您已準備好管理 {{site.data.keyword.Bluemix_notm}} 資源。鍵入 `ibmcloud help` 以查看指令說明。

如果您使用聯合 ID，請遵循[這裡](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)的指示，使用一次性密碼或 API 金鑰進行登入。  
{: tip}

## 安裝 {{site.data.keyword.Bluemix_notm}} CLI 的其他選項
{: #more_options_install}


除了[安裝程式](install_use_cli.html#getting_started)之外，您也可以使用 Shell 來下載及安裝 CLI。 


### 從 Shell 安裝
{: #shell_install}


### MacOS

複製下列指令，並將其貼入 Mac OS 的終端機，然後予以執行：

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

複製下列指令，並將其貼入 Linux OS 的終端機，然後予以執行：

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

複製下列指令，並將其貼入 [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 終端機主控台，然後予以執行：

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## 可進一步探索 {{site.data.keyword.Bluemix_notm}} CLI 的其他鏈結

* [使用外掛程式延伸 {{site.data.keyword.Bluemix_notm}} CLI 功能](extend_cli.html)
* [{{site.data.keyword.Bluemix_notm}} CLI 指令用法的文件](ic_cli_cmds.html)


## 報告問題及提交意見
{: #issues}

使用下列選項，以報告問題或提交新的特性要求：
 * 在 [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 中建立問題
 * 在 [Slack 頻道](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 中留言
