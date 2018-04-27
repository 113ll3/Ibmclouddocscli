---



copyright:

  years: 2015, 2018
lastupdated: "2018-04-17"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}


# {{site.data.keyword.Bluemix_notm}} CLI のダウンロードおよびインストール
{: #download_install}

インストーラーまたはシェルを使用して、CLI をダウンロードしてインストールすることができます。

## インストーラーの使用
{: #installer}

{{site.data.keyword.Bluemix_notm}} CLI をインストールするには、以下のようにします。
* [ここ](all_versions.html)に移動して、インストーラーをダウンロードします。
* macOS および Windows の場合は、インストーラーを実行します。 
* Linux の場合は、インストーラー・パッケージをダウンロードした後、それを解凍し、root 権限を使用してインストール・スクリプトを実行します。

  ```
  $ tar -xvf Bluemix_CLI.tar.gz
  $ cd Bluemix_CLI
  $ sudo ./install_bluemix_cli

  ```

## shell からのインストール
{: #shell_install}


### macOS

以下のコマンドを Mac OS の端末にコピー・アンド・ペーストし、実行します。

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
