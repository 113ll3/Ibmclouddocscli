---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Docker コンテナーからの {{site.data.keyword.dev_cli_notm}} の使用
{: #using-idt-from-docker}

{{site.data.keyword.dev_cli_notm}} Docker コンテナーには、{{site.data.keyword.cloud}} CLI および以下のツールが用意されています。

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
{: #idt-docker-prereq}

[{{site.data.keyword.cloud_notm}} アカウント](https://{DomainName}/login){: new_window} ![外部リンク・アイコン](../../../icons/launch-glyph.svg "外部リンク・アイコン") が必要であり、以下の手順を実行する前に、最新の安定した Docker バージョンをインストールする必要があります。

## ステップ 1. Docker Hub から Docker イメージをプルします。
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## ステップ 2. Docker コンテナーを開始します。
{: #step2-start-docker}

以下のコマンドを使用して、{{site.data.keyword.dev_cli_notm}} Docker コンテナーを開始します。

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## ステップ 3. IBMid を使用して {{site.data.keyword.cloud_notm}} にログインします。
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

資格情報が拒否された場合、統合 ID を使用している可能性があります。 詳しくは、[フェデレーテッド ID を使用したログイン](/docs/iam?topic=iam-federated_id#federated_id)を参照してください。
{: tip}

{{site.data.keyword.dev_cli_notm}} CLI Plug-in は、アプリケーションのビルドとテストを容易にする 2 つのコンテナーを使用します。 1 つはツール・コンテナーであり、ここには、アプリをビルドおよびテストするために必要なユーティリティーが含まれています。 このコンテナーの `Dockerfile` は、[`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) パラメーターで定義されます。 このコンテナーには特定のランタイムの開発に通常使用されるツールが含まれるため、開発コンテナーと見なすことができます。

2 つ目のコンテナーは実行コンテナーであり、クラウドにデプロイされた際のアプリの実際のランタイム環境に近い環境を再現します。 このコンテナーは、例えば {{site.data.keyword.cloud_notm}} で使用するためなどにデプロイするのに適した形式になっています。 このため、アプリを開始するエントリー・ポイントが定義されています。 {{site.data.keyword.dev_cli_notm}} CLI プラグインからアプリを実行することを選択すると、このコンテナーが使用されます。 このコンテナーの `Dockerfile` は、[`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters) パラメーターで定義されます。

これで、{{site.data.keyword.dev_cli_notm}} を使用して {{site.data.keyword.cloud_notm}} リソースを管理し、アプリを開発およびデプロイする準備ができました。
