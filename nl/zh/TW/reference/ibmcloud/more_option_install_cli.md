---



copyright:

  years: 2018
lastupdated: "2018-07-12"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# 安裝 {{site.data.keyword.Bluemix_notm}} CLI 的其他選項
{: #more_options_install}

除了[安裝程式](install_use_cli.html#getting_started)之外，您也有其他選項可以安裝 {{site.data.keyword.Bluemix_notm}} CLI：

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

1. 下載二進位檔。

   根據您的 OS 使用下列鏈結下載二進位套件。

   |平台|下載|總和檢查|
   |----|----| --- |
   |macOS  | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
   | linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
   | linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
   | ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
   | win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
   | win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

1. 將套件解壓縮到您指定的目錄。

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

1. 新增至 `PATH` 環境變數並啟用 Shell 自動完成。

   * 將 `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` 新增至 `PATH` 環境變數。
   * 如需 Shell 自動完成支援（僅限 MacOS 及 Linux），請參閱[本手冊](enable_cli_autocompletion.html)。

