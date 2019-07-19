---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, plugin, plug-in, command line, command-line, windows powershell, linux, macos, installer

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# スタンドアロン {{site.data.keyword.cloud_notm}} CLI のインストール
{: #install-ibmcloud-cli}

{{site.data.keyword.cloud}} CLI は、{{site.data.keyword.cloud_notm}} のリソースを管理するためのコマンド・ライン・インターフェースを提供します。 引き続き `cf` CLI を使用して {{site.data.keyword.cloud_notm}} にログインすることもできますが、それは {{site.data.keyword.cloud_notm}} 内の Cloud Foundry サービスで動作します。 

{{site.data.keyword.cloud}} CLI と、{{site.data.keyword.cloud_notm}} 用のアプリケーションを開発するための推奨されるその他のプラグインおよびツールの両方をインストールする場合は、[{{site.data.keyword.cloud_notm}} CLI の概説](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)を参照してください。
{: tip}

スタンドアロン {{site.data.keyword.cloud_notm}} CLI をインストールするには、次の手順を実行します。

1. ダウンロードするための、ご使用の OS のインストーラーを選択します。

   Mac OS X 64 ビット: [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 ビット: [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 ビット: [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 ビット (ppc64le): [インストーラー](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   32 ビットのバージョンおよび古いバージョンの場合、[{{site.data.keyword.cloud_notm}} CLI リリース](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases)のページに移動してダウンロードしてください。

2. インストーラーを実行します。
   * MacOS および Windows&trade; の場合は、インストーラーを実行します。
   * Linux&trade; の場合は、パッケージを解凍し、`install` スクリプトを実行します。

3. API エンドポイントをターゲットに指定し、{{site.data.keyword.cloud_notm}} にログインします。
   ```
   ibmcloud login
   ```
   {: codeblock}
   
これで、{{site.data.keyword.cloud_notm}} リソースを管理する準備ができました。 コマンド説明を表示するには、`ibmcloud help` と入力します。

フェデレーテッド ID を使用する場合は、[ここ](/docs/iam?topic=iam-federated_id#federated_id)で説明する手順に従って、ワンタイム・パスコードまたは API キーを使用してログインします。  
{: tip}

インストーラー以外にも、{{site.data.keyword.cloud_notm}} CLI をインストールするためのオプションがあります。

* shell からのインストール
* バイナリー・パッケージをダウンロードしてカスタム・ディレクトリーへインストール

## shell からのインストール
{: #shell_install}

### macOS
{: #shell-install-macos}

以下のコマンドを Mac OS の端末にコピー・アンド・ペーストし、実行します。
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

以下のコマンドを Linux&trade; OS の端末にコピー・アンド・ペーストし、実行します。
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

以下のコマンドを [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") 端末コンソールにコピー・アンド・ペーストし、実行します。
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## カスタム・ディレクトリーへのインストール
{: #install-custom-dir}

インストーラーまたは shell スクリプトを使用して {{site.data.keyword.Bluemix_notm}} CLI をインストールすると、バイナリーがシステム・ディレクトリーに移動します。 別のディレクトリーを指定する場合は、以下の手順を実行します。

### ステップ 1: 使用している OS に基づいたバイナリー・パッケージを、以下のリンクを使用してダウンロードします。
{: #step1-custom-dir}

| プラットフォーム | ダウンロード | チェックサム |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### ステップ 2: 指定したディレクトリーにパッケージを解凍します。
{: #step2-custom-dir}

   パッケージを解凍すると、以下のコンテンツを確認できます。

   Linux&trade; および MacOS の場合:

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

   Windows

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

### ステップ 3: `PATH` 環境変数に追加し、shell オートコンプリート機能を有効にします。
{: #step3-custom-dir}

   * `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` を `PATH` 環境変数に追加します。
   * shell オートコンプリート機能サポート (MacOS および Linux&trade; のみ) については、[このガイド](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)を参照してください。

## スタンドアロン {{site.data.keyword.cloud_notm}} CLI のアンインストール
{: #uninstall-ibmcloud-cli}

以下のセクションでは、特定のプラットフォームでスタンドアロンの {{site.data.keyword.cloud_notm}} CLI をアンインストールする方法を詳しく説明します。

### Windows でのアンインストール
{: #uninstall-cli-windows}

1. `「スタート」`ボタンをクリックし、`「コントロール パネル」`を選択します。
2. ポップアップ・ウィンドウで、`「プログラムのアンインストール」`をクリックします。
3. ポップアップしたアプリケーション・リストで、`「IBM Cloud コマンド・ライン・インターフェース」`を見つけます。
4. `「IBM Cloud コマンド・ライン・インターフェース」`を右クリックして、`「アンインストール」`を選択します。
5. アンインストーラーが開始します。 指示に従ってアンインストールを完了します。

### Linux および MacOS でのアンインストール
{: #uninstall-cli-linux-macos}

#### `0.9.0` よりも前のバージョン

1. 端末を開き、以下のコマンドを実行します。
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. オートコンプリート機能スクリプトを構成した場合は、それをクリーンアップします。 詳しくは、『[{{site.data.keyword.cloud_notm}} CLI の shell オートコンプリート機能の有効化 (Linux および MacOS のみ)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)』を参照してください。

#### バージョン `0.9.0` 以降

1. 端末を開き、次のコマンドを実行します。
  * `/usr/local/ibmcloud/bin/uninstall`
2. カスタム・オートコンプリート機能スクリプトがあれば、それをクリーンアップします。 詳しくは、『[{{site.data.keyword.cloud_notm}} CLI の shell オートコンプリート機能の有効化 (Linux および MacOS のみ)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete)』を参照してください。

## {{site.data.keyword.cloud_notm}} CLI をさらに探索するためのその他のリンク
{: #other-cli-links}

* [プラグインによる {{site.data.keyword.cloud_notm}} CLI の拡張](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [汎用 CLI (ibmcloud) コマンド](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## 問題の報告とフィードバックの送信
{: #issues}

問題を報告したり新しいフィーチャーの要求を送信したりするには、以下のオプションを使用してください。
* [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") で問題を作成する。
* [{{site.data.keyword.cloud_notm}} Tech の Slack - #developer-tools チャネル](https://ibm-cloud-tech.slack.com){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") にメッセージを残す。- [ここ](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") でチーム・アクセスを要求。
