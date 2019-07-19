---

copyright:
  years: 2016, 2019
lastupdated: "2019-02-26"

keywords: bmscclient, bmscore sdk, network request, ios, android, studio, cordova, client sdk, sdk, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}

# BMSClient の初期化
{: #sdk_BMSClient}

`BMSCore` は、他の {{site.data.keyword.cloud}} Web サービスおよびモバイル・サービスの Client SDK が、対応する {{site.data.keyword.cloud_notm}} サービスと通信するために使用する HTTP インフラストラクチャーを提供します。

## Android アプリケーションの初期化
{: #init-BMSClient-android}

`BMSCore` パッケージをダウンロードして Android Studio プロジェクトにインポートするか、Gradle を使用できます。

1. 以下の `import` ステートメントをプロジェクト・ファイルの先頭に追加して、Client SDK をインポートします。

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. Android アプリケーション内のメイン・アクティビティーの `onCreate` メソッド、またはプロジェクトで最適に機能するロケーションに初期化コードを追加して、Android アプリケーションで `BMSClient` SDK を初期化します。

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Make sure that you point to your region
  ```
  {: codeblock}

  **bluemixRegion** パラメーターを使用して `BMSClient` を初期化する必要があります。 初期化指定子で、**bluemixRegion** 値は、使用している {{site.data.keyword.Bluemix_notm}} デプロイメント (例えば、`BMSClient.REGION_US_SOUTH`、`BMSClient.REGION_UK`、または `BMSClient.REGION_SYDNEY`) を指定します。


## iOS アプリケーションの初期化
{: #init-BMSClient-ios}

[CocoaPods ](https://cocoapods.org){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") または [Carthage ](https://github.com/Carthage/Carthage){: new_window} ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン") を使用して、`BMSCore` パッケージを取得できます。

1. CocoaPods を使用して `BMSCore` をインストールするには、以下の行を Podfile に追加します。 プロジェクトにまだ Podfile がない場合は、`pod init` コマンドを使用します。

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  次に、`pod install` コマンドを実行し、生成された `.xcworkspace` ファイルを開きます。 `BMSCore` の新しいリリースに更新するには、`pod update BMSCore` を使用します。

  CocoaPods の使用方法について詳しくは、[CocoaPods Guides ](https://guides.cocoapods.org/using/index.html){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン") を参照してください。

2. Carthage を使用して `BMSCore` をインストールするには、以下の[説明](https://github.com/Carthage/Carthage#getting-started){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")に従ってください。

  1. 以下の行を Cartfile に追加します。

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. `carthage update` コマンドを実行します。

  3. ビルドが終了したら、Carthage の説明の[ステップ 3 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")に従って、`BMSCore.framework` をプロジェクトに追加します。

      Swift 2.3 を使用してビルドされたアプリケーションの場合、`carthage update --toolchain com.apple.dt.toolchain.Swift_2_3` コマンドを使用します。 それ以外の場合は、`carthage update` コマンドを使用してください。

3. `BMSCore` モジュールをインポートします。

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. 以下のコードを使用して、`BMSClient` クラスを初期化します。

  初期化コードを Application Delegate の `application(_:didFinishLaunchingWithOptions:)` メソッド、またはプロジェクトで最適に機能するロケーションに入れます。

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Make sure that you point to your region
  ```
  {: codeblock}

  **bluemixRegion** パラメーターを使用して `BMSClient` を初期化する必要があります。 初期化指定子で、**bluemixRegion** 値は、使用している {{site.data.keyword.Bluemix_notm}} デプロイメント (例えば、`BMSClient.Region.usSouth`、`BMSClient.Region.unitedKingdom`、または `BMSClient.Region.sydney`) を指定します。

## Cordova アプリケーションの初期化
{: #init-BMSClient-cordova}

1. Cordova アプリケーションのルート・ディレクトリーで以下のコマンドを実行し、Cordova プラグインを追加します。

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. メインの JavaScript ファイル、またはプロジェクトで最適に機能するロケーションに初期化コードを追加して、Cordova アプリケーションの `BMSClient` クラスを初期化します。

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  **bluemixRegion** パラメーターを使用して `BMSClient` を初期化する必要があります。 初期化指定子で、**bluemixRegion** 値は、使用している {{site.data.keyword.Bluemix_notm}} デプロイメント (例えば、`BMSClient.REGION_US_SOUTH`、`BMSClient.REGION_UK`、または `BMSClient.REGION_SYDNEY`) を指定します。

## 関連リンク
{: #BMSClient-rellinks notoc}

* [BMSCore Android SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")
* [BMSCore iOS SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")
* [BMSCore Cordova プラグイン ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![外部リンク・アイコン](../icons/launch-glyph.svg "外部リンク・アイコン")
