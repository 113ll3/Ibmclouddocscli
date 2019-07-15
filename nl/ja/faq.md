---

copyright:
  years: 2019
lastupdated: "2019-06-10"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# FAQ
{: #ibm-cli-faq}

## 最新バージョンの {{site.data.keyword.cloud_notm}} CLI を使用する必要がありますか?
{: #cli-latest-version}

はい。最新バージョンを使用する必要があります。 以下のコマンドを実行して、使用しているバージョンを確認できます。

```
ibmcloud -v
```
{: codeblock}

## CLI の更新方法
{: #cli-update-version}

以下のコマンドを実行して、最新バージョンの CLI に更新します。

```
ibmcloud update
```
{: codeblock}

## 新しい CLI リリースに関する通知を受け取るにはどうすればよいですか?
{: #cli-get-notified}

はい。新しい CLI リリースが利用できるようになるときに情報を受け取れます。 [{{site.data.keyword.cloud_notm}} CLI リリース・リポジトリー](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![外部リンクのアイコン](../../../icons/launch-glyph.svg "外部リンクのアイコン") にサブスクライブします。

## {{site.data.keyword.cloud_notm}} アプリケーションのファイル構造とは何ですか?
{: #cli-file-structure}

CLI から作成または使用可能化されたアプリケーションには、`cli-config.yml` ファイル内にカプセル化されている事前構成された設定が付属しています。 `cli-config.yml` には、CLI のコマンドによって使用されるデフォルト項目が含まれています。それらは、コマンド・ラインを介して渡す値によってオーバーライドできます。

DevOps ツールチェーンにデプロイされたアプリには、`toolchain.yml` や `pipeline.yml` などのファイルも含まれていることがあります。手動でデプロイするアプリには、`manifest.yml` ファイルや Helm チャート・ファイル (例えば Cloud Foundry や Kubernetes へのデプロイメントなど) を含めることができます。

## ローカル・コンテナーはどのように使用されますか?
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI Plug-in は、アプリのビルドとテストを容易にする 2 つのコンテナーを使用します。 1 つはツール・コンテナーであり、ここには、アプリをビルドおよびテストするために必要なユーティリティーが含まれています。 このコンテナーの `Dockerfile` は、[`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) パラメーターで定義されます。 このコンテナーには特定のランタイムの開発に通常使用されるツールが含まれるため、開発コンテナーと見なすことができます。

2 つ目のコンテナーは実行コンテナーであり、クラウドにデプロイされると、アプリの実際のランタイム環境に近い環境を再現します。 このコンテナーは、例えば {{site.data.keyword.cloud_notm}} で使用するためなどにデプロイするのに適した形式になっています。 このため、アプリを開始するエントリー・ポイントが定義されています。 {{site.data.keyword.dev_cli_long}} CLI プラグインからアプリを実行することを選択すると、このコンテナーが使用されます。 このコンテナーの `Dockerfile` は、[`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) パラメーターで定義されます。

## 既存のコードをデプロイするにはどうすればよいですか?

既存のコード・ベースをデプロイするには、[デプロイメントおよびクラウド対応アセットの生成](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)を参照してください。

