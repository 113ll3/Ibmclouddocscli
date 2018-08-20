---



copyright:

  years: 2015, 2018
lastupdated: "2018-08-15"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# 安裝獨立式 {{site.data.keyword.Bluemix_notm}} CLI
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI 提供指令行介面，以便在 {{site.data.keyword.Bluemix_notm}} 中管理資源。您仍可以使用 cf CLI 登入 {{site.data.keyword.Bluemix_notm}}，但它僅適用於 {{site.data.keyword.Bluemix_notm}} 中的 Cloud Foundry 服務。

如果您想要安裝 {{site.data.keyword.Bluemix}} CLI 及其他建議外掛程式和工具來開發 {{site.data.keyword.Bluemix_notm}} 的應用程式，請遵循在[這裡](/docs/cli/index.html)說明的方法。
{: tip}

請使用下列步驟，以安裝獨立式 {{site.data.keyword.Bluemix_notm}} CLI：

1. 選取要下載的 OS 安裝程式

   Mac OS X 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 位元：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window}/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 位元 (ppc64le)：[安裝程式](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

1. 執行安裝程式
   * 若為 macOS 及 Windows，僅執行安裝程式。
   * 若為 Linux，擷取套件並執行 `install_bluemix_cli` Script。

1. 將目標設為 API 端點並登入 {{site.data.keyword.Bluemix_notm}}

   ```
   ibmcloud login
   ```
   {: codeblock}
   
現在，您已準備好管理 {{site.data.keyword.Bluemix_notm}} 資源。鍵入 `ibmcloud help` 以查看指令說明。

如果您使用聯合 ID，請遵循[這裡](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)的指示，使用一次性密碼或 API 金鑰進行登入。  
{: tip}

除了安裝程式之外，您也有其他選項可以安裝 {{site.data.keyword.Bluemix_notm}} CLI：

* 從 Shell 安裝
* 下載二進位套件並安裝至自訂目錄

## 從 Shell 安裝
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

## 安裝至自訂目錄

當您使用安裝程式或 Shell Script 來安裝 {{site.data.keyword.Bluemix_notm}} CLI 時，二進位檔將移至您的系統目錄。如果您想要指定不同目錄，請使用下列步驟。

### 步驟 1：根據您的 OS 使用下列鏈結下載二進位套件。

|平台|下載|總和檢查|
|---------|----------|---------|
|macOS  | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### 步驟 2：將套件解壓縮到您指定的目錄。

   解壓縮套件之後，內容將類似如下：

   若為 Linux 及 MacOS

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: codeblock}

   若為 Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}
### 步驟 3：新增至 `PATH` 環境變數並啟用 Shell 自動完成。

   * 將 `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` 新增至 `PATH` 環境變數。
   * 如需 Shell 自動完成支援（僅限 MacOS 及 Linux），請參閱[本手冊](enable_cli_autocompletion.html)。
   
## 解除安裝獨立式 {{site.data.keyword.Bluemix_notm}} CLI

下節提供如何在特定平台上解除安裝獨立式 {{site.data.keyword.Bluemix_notm}} CLI 的詳細資料。

### 在 Windows 上解除安裝

1. 按一下`開始`按鈕，然後選取`控制台`。
2. 在蹦現視窗中，按一下`解除安裝程式`。
3. 在蹦現應用程式清單中，找到 `IBM Cloud Command Line Interface`。
4. 在 `IBM Cloud Command Line Interface` 按一下滑鼠右鍵，然後選取`解除安裝`。
5. 將會啟動解除安裝程式。遵循指示以完成解除安裝。

### 在 Linux/macOS 上解除安裝

#### `0.9.0` 版之前

1. 開啟終端機，然後執行下列指令：
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. 清除自動完成 Script，如果已配置的話。如需詳細資料，請參閱[啟用 CLI 自動完成](enable_cli_autocompletion.html)。

#### `0.9.0` 版以及更新版本

1. 開啟終端機，然後執行下列指令：
  * `/usr/local/ibmcloud/uninstall`
2. 清除自動完成 Script，如果已配置的話。如需詳細資料，請參閱[啟用 CLI 自動完成](enable_cli_autocompletion.html)。


## 可進一步探索 {{site.data.keyword.Bluemix_notm}} CLI 的其他鏈結

* [使用外掛程式延伸 {{site.data.keyword.Bluemix_notm}} CLI 功能](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [一般 {{site.data.keyword.Bluemix_notm}} CLI 指令用法](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [一般 {{site.data.keyword.Bluemix_notm}} (ibmcloud sl) 指令用法](/docs/cli/reference/softlayer/index.html)

## 報告問題及提交意見
{: #issues}

使用下列選項，以報告問題或提交新的特性要求：
 * 在 [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg) 中建立問題。
 * 在 [IBM Cloud Tech 的 Slack - #developer-tools 頻道](https://ibm-cloud-tech.slack.com)留言 - 在[這裡](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![外部鏈結圖示](../../../icons/launch-glyph.svg)。
