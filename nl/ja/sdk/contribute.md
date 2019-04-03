---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-26"

keywords: contribute plug-in, sdk plug-in, cloud foundry cli, go environment, internationalization, ginkgo, govendor

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# SDK プラグインへの寄与
{: #contribute}

{{site.data.keyword.cloud}} CLI SDK プラグインに寄与するには、以下のガイドラインに従ってください。

## 開発環境のセットアップ
{: #dev-env}

* Cloud Foundry [CLI ](https://github.com/cloudfoundry/cli/releases){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   Cloud Foundry CLI は必須ではありませんが、端末から {{site.data.keyword.cloud_notm}} へのアクセスに役立ちます。

   Cloud Foundry CLI について詳しくは、[資料](/docs/cli?topic=cloud-cli-cf#cf)を参照してください。

* {{site.data.keyword.cloud_notm}} [CLI](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli)

   このプラグインは、{{site.data.keyword.cloud_notm}} CLI にインストールされます。 {{site.data.keyword.cloud_notm}} CLI にも、端末から {{site.data.keyword.cloud_notm}} にアクセスするのに役立つリソースが用意されています。

* Go の[開発環境 ](https://golang.org/doc/code.html){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   Go では、パッケージの場所が厳しく管理されているので、`$GOPATH` ディレクトリー構造内にソースを定義する必要があります。 必ず `$GOPATH` 変数および `$GOROOT` 変数を定義するとともに、`$GOPATH/bin` を `$PATH` 環境変数に含める必要があります。これは、(Mac OS 上で)、`~/.bash_profile` 構成ファイルを編集することによって行います。

   ```
   ### SET Go's GOPATH and GOROOT                                                                                                                   
   export GOPATH=$HOME/Development/go                                                                                                               
   export GOROOT=/usr/local/opt/go/libexec                                                                                                          
   export PATH=$PATH:$GOPATH/bin
   ```
   {: codeblock}

* 依存関係マネージャー: [govendor ](https://github.com/kardianos/govendor){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   `govendor` ツールは、Go の依存関係を作成し、管理します。 ベンダー・ディレクトリーを更新する予定がない限り、必要ありません。

   * 以下のコマンドを使用してインストールします。

      ```
      go get -u github.com/kardianos/govendor
      ```
      {: codeblock}

   * 以下のコマンドを使用して、プロジェクト・ディレクトリー上で `govendor` を初期化します。

      ```
      govendor init
      ```
      {: codeblock}

   * 以下のコマンドを使用して、`$GOPATH` からベンダー・ディレクトリーに依存関係を追加します。

      ```
      govendor add +local
      ```
      {: codeblock}

* BDD テスト・フレームワーク: [Ginkgo ](http://onsi.github.io/ginkgo/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

テスト・フレームワークは、Go 用の BDD テスト・フレームワーク Ginkgo に基づいています。 Ginkgo 用のマッチャーおよびアサーション・ライブラリーである[Gomega ](http://onsi.github.io/gomega/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")と併せて使用します。

   * 以下のコマンドを使用して `ginkgo` をインストールします。

      ```
      go get -u github.com/onsi/ginkgo/ginkgo
      ```
      {: codeblock}

   * 以下のコマンドを使用して `gomega` をインストールします。

      ```
      go get -u github.com/onsi/gomega
      ```
      {: codeblock}

   * 以下のコマンドを使用して単体テストを実行します。

      ```
      ginkgo -r
      ```
      {: codeblock}

      * コード・カバレッジを追加するには、コマンドに `-cover` を付加します。

   * コード・カバレッジの分かりやすい HTML フォームを取得するには、以下のコマンドを使用します。

      ```
      go tool -html={package}.coverprofile
      ```
      {: codeblock}

      * `.coverprofile` ファイルがあるディレクトリーに移動します。

* 国際化対応: [go-i18n ](https://github.com/nicksnyder/go-i18n){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") および [go-bindata ](https://github.com/jteeuwen/go-bindata){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

国際化対応は、Go アプリケーションを複数の言語に翻訳することをサポートするパッケージおよびコマンド・ライン・ツールである `go-i18n` に基づきます。 翻訳バンドルは、各種入力ファイルを管理しやすい GO ソース・コードに変換するコマンドである `go-bindata` で事前処理されます。

   * 以下のコマンドを使用して `go-i18n` をインストールします。

      ```
      go get -u github.com/nicksnyder/go-i18n/goi18n
      ```
      {: codeblock}

   * 以下のコマンドを使用して `go-bindata` をインストールします。

      ```
      go get -u github/com/jteeuwen/go-bindata/go-bindata
      ```
      {: codeblock}

* デバッグ: [delve ](https://github.com/derekparker/delve){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

Delve は、Go プログラミング言語用のデバッガーであり、[Visual Studio Code ](https://code.visualstudio.com/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")で使用されます。

   * 以下のコマンドを使用して `delve` をインストールします。

      ```
      go get -u github.com/derekparker/delve/cmd/dlv
      ```
      {: codeblock}

      * Mac OS では、[指示 ](http://blog.ralch.com/tutorial/golang-debug-with-delve/){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") に従って、必要な自己署名証明書を作成します。


## 必要なランタイム・ライブラリー
{: #runtime-libs}

Go は、堅固な依存関係マネージャーを提供していないので、安定度を確保するために、必要なランタイム・ライブラリーは、`vendor` ディレクトリーの下で管理され、Git リポジトリーにコミットされます。

### ランタイム依存関係
{: #runtime-dependencies}

ネストされた依存関係はリストされていません。

* [github.ibm.com/Bluemix/bluemix-cli-sdk ](https://github.ibm.com/Bluemix/bluemix-cli-sdk){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   {{site.data.keyword.cloud_notm}} CLI プラグイン SDK は、{{site.data.keyword.cloud_notm}} CLI プラグインを開発するためのインフラストラクチャーを提供します。

* [github.com/urfave/cli ](https://github.com/urfave/cli){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   このパッケージは、Go 内にコマンド・ライン・アプリをビルドするためのインフラストラクチャーを提供します。 {{site.data.keyword.cloud_notm}} CLI プラグインは、このライブラリー (github.com/codegangsta/cli) のより古いバージョンに依存します。

* [github.com/asaskevich/govalidator ](https://github.com/asaskevich/govalidator){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   このパッケージは、ストリング、ストラクチャー、およびコレクション用のバリデーターおよびサニタイザーをいくつか提供します。 独自のバリデーターを実装する代わりにこのパッケージを使用してください。

* [github.com/parnurzeal/gorequest ](https://github.com/parnurzeal/gorequest){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   このパッケージは、HTTP 要求および応答の処理を支援する簡易 HTTP クライアントを実装します。

* [github.com/briandowns/spinner ](https://github.com/briandowns/spinner){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   このパッケージは、SDK の生成などの長い操作が処理されている間にユーザーにフィードバックを提供するための CLI スピナーを実装します。

* [github.com/cloudfoundry-attic/jibber_jabber ](https://github.com/cloudfoundry-attic/jibber_jabber){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")

   このパッケージは、オペレーティング・システムの現在の言語を検出するために使用されます。

## リポジトリーの複製
{: #clone-repo}

`govendor` が動作する仕組みのため、リポジトリーは、Go の[ディレクトリー構造 ](https://golang.org/doc/code.html){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") に複製する必要があります。これは、Go のベスト・プラクティスにも従っています。

* 完全修飾パッケージ名により、内部依存関係をインポートします。

   ```
   import (
      ...
      "github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin/plugin"
   )
   ```
   {: codeblock}

* リポジトリーを複製します。

   ```
   mkdir -p $GOPATH/src/github.ibm.com/bluemix-mobile-services
   cd $GOPATH/src/github.ibm.com/bluemix-mobile-services
   git clone https://github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin.git -b compute
   ```
   {: codeblock}


## プラグインのビルド、テスト、およびインストール
{: #build-plug-in}

以下のいずれかのコマンドを選択してプラグインをビルドします。
```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
go build main.go
```
{: codeblock}

```
cd $GOPATH/src/github.ibm.com/bluemix-mobile-services/bmd-codegen-sdkgen-cli-plugin
sh bin/build.sh
```
{: codeblock}

ビルド・スクリプトは、プラグインを {{site.data.keyword.Bluemix_notm}} CLI にもインストールします。
{: note}

以下のいずれかのコマンドを選択してプラグインをテストします。
```
ginkgo -r
```
{: codeblock}

```
go test ./plugin/...
```
{: codeblock}

単体テストおよび適応範囲などを含む、統合テストを実行します。
```
sh bin/testAll.sh
```
{: codeblock}

プラグインをスタンドアロン CLI として実行します。
```
./main
```
{: codeblock}

以下のいずれかのコマンドを選択して、プラグインをインストールし、{{site.data.keyword.cloud_notm}} CLI として起動します。
```
ibmcloud plugin install main
ibmcloud help sdk
```
{: codeblock}

```
sh bin/build.sh
```
{: codeblock}
