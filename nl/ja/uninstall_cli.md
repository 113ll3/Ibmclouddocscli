---

copyright:
  years: 2019
lastupdated: "2019-08-05"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# スタンドアロン {{site.data.keyword.cloud_notm}} CLI のアンインストール
{: #uninstall-ibmcloud-cli}

特定のプラットフォームでスタンドアロンの {{site.data.keyword.cloud_notm}} CLI をアンインストールするには、以下の手順を実行します。
{: shortdesc}

## Windows でのアンインストール
{: #uninstall-cli-windows}

1. **「スタート」**ボタンをクリックし、**「コントロール パネル」**を選択します。
2. ポップアップ・ウィンドウで、**「プログラムのアンインストール」**をクリックします。
3. ポップアップしたアプリケーション・リストで、**「IBM Cloud コマンド・ライン・インターフェース」**を見つけます。
4. **「IBM Cloud コマンド・ライン・インターフェース」**を右クリックして、**「アンインストール」**を選択します。
5. アンインストーラーが開始します。 指示に従ってアンインストールを完了します。

## Linux および MacOS でのアンインストール
{: #uninstall-cli-linux-macos}

アンインストール手順は、インストールされている CLI のバージョンによって異なります。

ご使用の {{site.data.keyword.cloud_notm}} CLI のバージョンを判別するには、次のコマンドを実行します。
```
ibmcloud -v
```
{: codeblock}

`0.9.0` よりも前のバージョンをアンインストールするには、次の一連のコマンドを実行します。
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

オートコンプリート機能スクリプトを構成した場合は、それをクリーンアップします。 詳しくは、[{{site.data.keyword.cloud_notm}} CLI の shell オートコンプリート機能の有効化 (Linux および Mac のみ)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete) を参照してください。

バージョン `0.9.0` 以降をアンインストールするには、次のコマンドを実行します。
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

カスタム・オートコンプリート機能スクリプトがあれば、それをクリーンアップします。 詳しくは、[{{site.data.keyword.cloud_notm}} CLI の shell オートコンプリート機能の有効化 (Linux および Mac のみ)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete) を参照してください。
