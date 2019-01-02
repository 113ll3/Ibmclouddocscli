---

copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# Jetbrains IDE 用 IBM Cloud Developer Tools
{: #ibm-dev-tools-for-jetbrains}

{{site.data.keyword.Bluemix}} Developer Tools の Jetbrains IDE 用拡張機能には、`IntelliJ`、`WebStorm`、`Android Studio` などが含まれ、IDE 内から {{site.data.keyword.dev_cli_notm}} CLI コマンドに直接アクセスするための新しいメニュー項目が用意されています。 これにより、アプリのデプロイメント、{{site.data.keyword.Bluemix_notm}} 上でのアプリの開始/停止/再始動、リモート・アプリ・ログの表示など、Docker と CloudFoundry の両方のワークフローで、エディターのコンテキストを離れることなく、`ibmcloud dev` コマンドのサブセットに素早くアクセスすることができます。
{:shortdesc}

![WebStorm IDE 内で実行される IBM Cloud Developer Tools の画面キャプチャー。](jetbrains.png "WebStorm IDE 内で実行される {{site.data.keyword.Bluemix_notm}} Developer Tools のメニューの例")

## 従属関係
{: #dependencies}

{{site.data.keyword.Bluemix_notm}} Developer Tools の Jetbrains ベースの IDE の拡張機能を使用するには、さらに [{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli/index.html#overview) がシステムにインストールされている必要があります。

## インストール
{: #installation}

{{site.data.keyword.Bluemix_notm}} Developer Tools の Jetbrains IDE 用の拡張機能をインストールする最も簡単な方法は、[{{site.data.keyword.Bluemix_notm}} Developer Tools Github リポジトリーの jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") ページにアクセスし、そこにある説明に従うことです。

## 使用量
{: #usage}

開始するにあたって、既存のサーバー・サイド・アプリを使用し、そのアプリを {{site.data.keyword.Bluemix_notm}} 対応にすることも、{{site.data.keyword.dev_cli_notm}} CLI を使用してスターター・キットから新規アプリを作成することもできます (ibmcloud dev create)。 アプリのプロジェクトが準備できたら、それを JetBrains IDE で開きます。

汎用のサーバー・サイド・アプリがある場合、「ツール」>「IBM Cloud Developer Tools」>「アプリを IBM Cloud 対応にする (Enable app for IBM Cloud)」を選択します。 これは、必要なすべてのファイルの有無を検査し、欠落しているファイルがあれば追加します。これにより、アプリをローカル側でビルドでき、Cloud Foundry アプリを使用して {{site.data.keyword.Bluemix_notm}} に、または Kubernetes クラスターにデプロイすることができます。

{{site.data.keyword.Bluemix_notm}} 開発者ツール・メニューから基本の build/run/deploy アクションを使用して、クラウド・ネイティブ・アプリを開発します。 メニューにないアクションを実行する必要がある場合は、単に「端末」タブを開いて、必要なコマンドを手動で入力します。
