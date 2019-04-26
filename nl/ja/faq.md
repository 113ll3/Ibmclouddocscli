---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# よくある質問 (FAQ)
{: #ibm-cli-faq}

## {{site.data.keyword.cloud_notm}} アプリケーションのファイル構造とは何ですか?
{: #cli-file-structure}

CLI から作成または使用可能化されたアプリケーションには、`cli-config.yml` ファイル内にカプセル化されている事前構成された設定が付属しています。 `cli-config.yml` には、CLI のコマンドによって使用されるデフォルト項目が含まれています。それらは、コマンド・ラインを介して渡す値によってオーバーライドできます。

DevOps ツールチェーンにデプロイされたアプリケーションには、`toolchain.yml` や `pipeline.yml` などのファイルも含まれています。手動でデプロイするアプリケーションには、`manifest.yml` ファイルや Helm チャート・ファイル (例えば Cloud Foundry や Kubernetes へのデプロイメントなど) を含めることができます。

## ローカル・コンテナーはどのように使用されますか?
{: #cli-faq-containers}

{{site.data.keyword.dev_cli_long}} CLI Plug-in は、アプリケーションのビルドとテストを容易にする 2 つのコンテナーを使用します。 1 つはツール・コンテナーであり、ここには、アプリケーションをビルドおよびテストするために必要なユーティリティーが含まれています。 このコンテナーの `Dockerfile` は、[`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters) パラメーターで定義されます。 このコンテナーには特定のランタイムの開発に通常使用されるツールが含まれるため、開発コンテナーと見なすことができます。

2 つ目のコンテナーは実行コンテナーであり、クラウドにデプロイされると、アプリの実際のランタイム環境に近い環境を再現します。 このコンテナーは、例えば {{site.data.keyword.cloud_notm}} で使用するためなどにデプロイするのに適した形式になっています。 このため、アプリケーションを開始するエントリー・ポイントが定義されています。 {{site.data.keyword.dev_cli_long}} CLI プラグインからアプリケーションを実行することを選択すると、このコンテナーが使用されます。 このコンテナーの `Dockerfile` は、[`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) パラメーターで定義されます。

# 既存コードデプロイするには、どうすればよいですか?
既存のコードベースをデプロイするには、これらの手順を実行して[アプリを使用可能化](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli)します。

## リファレンス・ブログ、ビデオ、および資料
{: #cli-faq-reference}

### ブログ
{: #cli-blogs}

- [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### ビデオ
{: #cli-videos}

- [How to deploy to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [How to deploy existing projects to {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Create, debug, and deploy a Node.js app with the {{site.data.keyword.dev_cli_long}} CLI Plug-in and VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### 資料およびチュートリアル
- [Kubernetes への継続的デプロイメント](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [{{site.data.keyword.dev_cli_long}} CLI プラグインのトラブルシューティング](/docs/cli?topic=cloud-cli-troubleshoot)
- [{{site.data.keyword.dev_cli_long}} CLI プラグイン (ibmcloud dev) コマンド](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [{{site.data.keyword.dev_cli_long}} CLI プラグインのローカル・アプリケーションのデバッグ](/docs/cli/idt?topic=cloud-cli-local-debug)

**問題を報告したり、フィードバックを提供したりするには、[{{site.data.keyword.cloud_notm}} Tech の Slack - #developer-tools チャネル](https://ibm-cloud-tech.slack.com)を使用できます ([ここ](https://slack-invite-ibm-cloud-tech.mybluemix.net/)でチーム・アクセスを依頼できます)。**
