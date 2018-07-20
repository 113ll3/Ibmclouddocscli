---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-09"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# スタンドアロン {{site.data.keyword.Bluemix_notm}} CLI のインストール
{: #install_use}

{{site.data.keyword.Bluemix_notm}} CLI は、{{site.data.keyword.Bluemix_notm}} でアプリケーション、コンテナー、インフラストラクチャー、サービス、およびその他のリソースを管理するためのコマンド・ライン・インターフェースを提供します。

{{site.data.keyword.Bluemix}} CLI と、{{site.data.keyword.Bluemix_notm}} 用のアプリケーションを開発するための推奨されるその他のプラグインおよびツールの両方をインストールする場合は、[ここ](/docs/cli/index.html)で説明されている方法に従ってください。
{: tip}

スタンドアロン {{site.data.keyword.Bluemix_notm}} CLI をインストールするには、次の手順を実行します。

1. ダウンロードするための、ご使用の OS のインストーラーを選択します。

   Mac OS X 64 ビット: [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 ビット: [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 ビット: [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 ビット (ppc64le): [インストーラー](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **32 ビットのリリースと以前のバージョンについては、[ここ](all_versions.html)を参照してください。

1. インストーラーを実行します。
   * macOS および Windows の場合は、単純にインストーラーを実行します。
   * Linux の場合は、パッケージを解凍し、`install_bluemix_cli` スクリプトを実行します。

1. API エンドポイントをターゲットに指定し、{{site.data.keyword.Bluemix_notm}} にログインします。

  ![例](example.gif){: gif}

これで、{{site.data.keyword.Bluemix_notm}} リソースを管理する準備ができました。 コマンド説明を表示するには、`ibmcloud help` と入力します。

フェデレーテッド ID を使用する場合は、[ここ](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id)で説明する手順に従って、ワンタイム・パスコードまたは API キーを使用してログインします。  
{: tip}

## {{site.data.keyword.Bluemix_notm}} CLI をインストールするその他のオプション
{: #more_options_install}


[インストーラー](install_use_cli.html#getting_started)に加えて、シェルを使って CLI をダウンロードおよびインストールすることもできます。 


### シェルからのインストール
{: #shell_install}


### MacOS

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

以下のコマンドを [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} 端末コンソールにコピー・アンド・ペーストし、実行します。

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## {{site.data.keyword.Bluemix_notm}} CLI をさらに探索するためのその他のリンク

* [プラグインを使用した {{site.data.keyword.Bluemix_notm}} CLI 機能の拡張](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [一般的な {{site.data.keyword.Bluemix_notm}} CLI コマンド使用法](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [一般的な {{site.data.keyword.Bluemix_notm}} (ibmcloud sl) コマンド使用法](/docs/cli/reference/softlayer/index.html)


## 問題の報告とフィードバックの送信
{: #issues}

問題を報告したり新しいフィーチャーの要求を送信したりするには、以下のオプションを使用してください。
 * [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg) で問題を作成する
 * [Slack channel](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg) にメッセージを残す
