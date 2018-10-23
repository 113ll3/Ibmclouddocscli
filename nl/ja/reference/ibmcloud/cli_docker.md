---

copyright:

  years: 2018
lastupdated: "2018-10-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Docker コンテナーからの {{site.data.keyword.dev_cli_notm}} の使用

{{site.data.keyword.dev_cli_notm}} Docker コンテナーには、{{site.data.keyword.Bluemix}} CLI および以下のツールが用意されています。

* `Git`
* `Helm`
* `kubectl`
* `curl`
* {{site.data.keyword.dev_cli_notm}} プラグイン
* {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}} プラグイン
* {{site.data.keyword.registrylong_notm}} プラグイン
* {{site.data.keyword.containerlong_notm}} プラグイン
* `sdk-gen` プラグイン

## 始める前に
{: #prereq}

[{{site.data.keyword.Bluemix_notm}} アカウント](https://console.bluemix.net/){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") が必要であり、以下の手順を実行する前に、最新の安定した Docker バージョンをインストールする必要があります。

## ステップ 1. Docker Hub から Docker イメージをプルします。
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## ステップ 2. Docker コンテナーを開始します。
{: #step2}

以下のコマンドを使用して、{{site.data.keyword.dev_cli_notm}} Docker コンテナーを開始します。

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## ステップ 3. IBM ID を使用して {{site.data.keyword.Bluemix_notm}} にログインします。
{: #step3}

```
ibmcloud login
```
{: codeblock}


資格情報が拒否された場合、統合 ID を使用している可能性があります。 詳しくは、[フェデレーテッド ID を使用したログイン](/docs/iam/login_fedid.html#federated_id)を参照してください。
{: tip}

これで、{{site.data.keyword.dev_cli_notm}} を使用して {{site.data.keyword.Bluemix_notm}} リソースを管理し、アプリケーションを開発およびデプロイする準備ができました。
