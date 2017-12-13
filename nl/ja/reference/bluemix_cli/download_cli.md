---



copyright:

  years: 2015, 2017
lastupdated: "2017-010-13"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# {{site.data.keyword.Bluemix_notm}} CLI のダウンロードおよびインストール
{: #download_install}

{{site.data.keyword.Bluemix_notm}} CLI をインストールするには、[インストーラー](#installers)を使用するか、または[シェルからインストール](#shell_install)することができます。

## インストーラーのダウンロード
{: #installers}

[{{site.data.keyword.Bluemix_notm}} CLI インストーラー (すべてのバージョン)](all_versions.html){: new_window} のページを参照して、ご使用の OS の最新インストーラーをダウンロードします。

macOS および Windows の場合は、単純にインストーラーを実行します。 

Linux の場合は、インストーラー・パッケージをダウンロードした後、それを解凍し、root 権限を使用してインストール・スクリプトを実行します。

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```
  
## shell からのインストール
{: #shell_install}


### macOS  

以下のコマンドを mac OS の端末にコピー・アンド・ペーストし、実行します。

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

以下のコマンドを Linux OS の端末にコピー・アンド・ペーストし、実行します。

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

以下のコマンドを [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window}端末コンソールにコピー・アンド・ペーストし、実行します。

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}
