---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.dev_cli_notm}} 概要
{: #overview}

{{site.data.keyword.dev_cli_notm}} は、コマンド・ラインを使用して Web アプリケーション、モバイル・アプリケーション、およびマイクロサービス・アプリケーションをエンドツーエンドで開発することを希望する開発者に向けた、アプリケーションを作成、開発、およびデプロイするためのコマンド・ライン・アプローチです。 以下のいずれかのスクリプトを実行することによって、推奨ツール・セットの使用を素早く開始できます。
{: shortdesc}

## {{site.data.keyword.dev_cli_notm}} の前提条件
{: #prereq}

[{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration) に登録します。

* Microsoft Windows&trade; を使用する場合、Windows 10 以降を使用する必要があります。

* Docker の Stable チャネル (安定版) を使用する必要があり、バージョン 1.13.1 以上が必要です。

## {{site.data.keyword.dev_cli_notm}} のインストール方法
{: #installation}

ツール・セットをインストールするには、関連するコマンドを実行して、インストーラーを起動します。 これにより、{{site.data.keyword.Bluemix_notm}} 開発用の推奨されるツールである、`Homebrew` (Mac のみ)、`Git`、`Docker`、`Helm`、`kubectl`、`curl`、{{site.data.keyword.Bluemix_notm}} CLI、{{site.data.keyword.dev_cli_notm}} プラグイン、Cloud Functions プラグイン、Container Registry プラグイン、Container Service プラグイン、および `sdk-gen` プラグインがインストールされます (まだインストールされていない場合)。

**Mac および Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* 注: PowerShell アイコンを右クリックして「管理者として実行」を選択することによって、Windows PowerShell を開きます。

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

## インストールの検証
インストールを検査するには、次の `help` コマンドを実行します。

```
ibmcloud dev help
```
{: codeblock}

インストールが成功していた場合、出力には、使用方法の説明、現行バージョン、およびサポートされるコマンドがリストされます。


## {{site.data.keyword.dev_cli_notm}} をさらに探索するためのその他のリンク

- [セットアップ詳細](/docs/cli/idt/setting_up_idt.html)
- [使用法](/docs/cli/idt/index.html)
- [コマンド](/docs/cli/idt/commands.html)
- [CLI プラグイン](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [VSCode IDE 用拡張機能](/docs/cli/idt/vscode.html)
- [IBM Cloud CLI の手動インストール](/docs/cli/reference/bluemix_cli/get_started.html)
- [Report issues on GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [IBM Cloud Tech の Slack - #developer-tools チャネル](https://ibm-cloud-tech.slack.com) - [ここ](https://slack-invite-ibm-cloud-tech.mybluemix.net/)でチーム・アクセスを要求
