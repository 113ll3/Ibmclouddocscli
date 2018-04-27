---
copyright:

  years: 2018

lastupdated: "2018-04-17"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}} CLI のセットアップ
{: #add-cli}

{{site.data.keyword.dev_cli_short}} CLI は、コマンド・ラインを使用して Web アプリケーション、モバイル・アプリケーション、およびマイクロサービス・アプリケーションをエンドツーエンドで開発することを希望する開発者に向けた、アプリケーションを作成、開発、およびデプロイするためのコマンド・ライン・アプローチです。
{: shortdesc}

## 前提条件
{: #prereq}

[{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net) に登録します。

*  Microsoft Windows&trade; を使用する場合、Windows 10 以降を使用する必要があります。

* Docker の Stable チャネル (安定版) を使用する必要があり、バージョン 1.13.1 以上が必要です。

## インストール
{: #installation}

ツールをインストールするには、関連するコマンドを実行して、インストーラーを起動します。これにより、IBM Cloud CLI、Kubernetes、Helm、Docker などの依存関係もインストールされます。 インストールするには、以下のインストール・ステップを使用します。

**Mac および Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* 注: 右クリックして「管理者として実行」を選択することにより、Windows PowerShell を開きます。

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

以下のコマンドを実行して、プラグインが正常にインストールされたことを確認します。  

```
bx dev
```
{: codeblock}

## 環境の構成
{: #configure-environment}

1. ご使用の [{{site.data.keyword.Bluemix_notm}} 地域](/docs/overview/cf.html#ov_intro_reg)の API エンドポイントに接続します。 例えば、{{site.data.keyword.Bluemix_notm}} 米国南部地域に接続するには、以下のコマンドを入力します。

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. IBM ID を使用して {{site.data.keyword.Bluemix_notm}} にログインします。

	```
	bx login
	```
	{: codeblock}

	**注:** 資格情報が拒否された場合、統合 ID を使用している可能性があります。 統合 ID を使用して認証を受けるには、以下のステップに従ってください。

	1. [{{site.data.keyword.iamshort}} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://www.bluemix.net/iam/#/apikeys){: new_window} にログインします。
	2. **「API キーの作成」**を選択します。
		* API キーの名前と説明を入力します。
	3. API キーをダウンロードします。
	4. ファイルを開き、`apiKey` フィールドから値をコピーします。
	5. 以下のコマンドを使用してログインします。

		```
		bx login --apikey <value>
		```
		{: codeblock}

3. 以下のように、組織とスペースを設定します。

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## 詳細はこちら
{: #learn}

これで、{{site.data.keyword.dev_cli_short}} CLI のインストールが完了したので、この便利なツールを有効に利用する方法について学習できます。
- [IDT CLI の概説](index.html)
- [IDT (bx dev) コマンド](commands.html)
- [VS Code 用の Developer Tools](vscode.html)
- [Jetbrains IDE 用 Developer Tools](jetbrains.html)

{{site.data.keyword.dev_cli_short}} CLI を使用してクラウド・ネイティブ・アプリを作成する方法を示した[チュートリアル](/docs/apps/tutorials/tutorial_bff.html)を確認してください。

## 追加の資料
{: #learn-more}

IBM Developer Tools CLI を使用してクラウド・ネイティブ・アプリを開発するときは、以下の資料が役立ちます。

- [IBM Cloud Developer Tools メイン・ランディング・ページ](https://www.ibm.com/cloud/cli) - IDT CLI のメイン製品ページ
- [IBM Developer Tools インストーラー](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - 詳細なインストール指示を含むパブリック GitHub リポジトリー
- [IBM Cloud App Service](https://console.bluemix.net/developer/appservice) - クラウド・ネイティブ・アプリを作成および管理するときに、IDT ツールのガイドとなる IBM Cloud コンソール・ページ
- [IBM Cloud Tech の Slack - #developer-tools チャネル](https://ibm-cloud-tech.slack.com) - IDT ツールに関する議論、回答の入手、アイデアの提案など
	- [ここからチームにアクセスを申請できます。](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**言語に焦点を置いた資料**

- [IBM Cloud 上の Node.js](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**ブログおよびチュートリアル**

- [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
