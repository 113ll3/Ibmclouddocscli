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

# 起始設定 BMSClient
{: #sdk_BMSClient}

`BMSCore` 提供 HTTP 基礎架構，而其他 {{site.data.keyword.cloud}} Web 及行動服務用戶端 SDK 用來與其對應 {{site.data.keyword.cloud_notm}} 服務通訊。

## 起始設定 Android 應用程式
{: #init-BMSClient-android}

您可以下載 `BMSCore` 套件並將其匯入至 Android Studio 專案，或使用 Gradle。

1. 在專案檔開頭新增下列 `import` 陳述式，以匯入「用戶端 SDK」：

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. 在 Android 應用程式中主要活動的 `onCreate` 方法中或在最適合您專案的位置中新增起始設定碼，以在 Android 應用程式中起始設定 `BMSClient` SDK。

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Make sure that you point to your region
  ```
  {: codeblock}

  您必須起始設定具有 **bluemixRegion** 參數的 `BMSClient`。在起始設定程式中，**bluemixRegion** 值指定您要使用的 {{site.data.keyword.Bluemix_notm}} 部署，例如，`BMSClient.REGION_US_SOUTH`、`BMSClient.REGION_UK` 或 `BMSClient.REGION_SYDNEY`。


## 起始設定 iOS 應用程式
{: #init-BMSClient-ios}

您可以使用 [CocoaPods ](https://cocoapods.org){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 或 [Carthage ](https://github.com/Carthage/Carthage){: new_window} ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示") 來取得 `BMSCore` 套件。

1. 若要使用 CocoaPods 來安裝 `BMSCore`，請在 Podfile 中新增下列數行。如果您的專案還沒有 Podfile，請使用 `pod init` 指令。

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  接著執行 `pod install` 指令，然後開啟所產生的 `.xcworkspace` 檔案。若要更新為較新版的 `BMSCore`，請使用 `pod update BMSCore`。

  如需使用 CocoaPods 的相關資訊，請參閱 [CocoaPods 手冊 ](https://guides.cocoapods.org/using/index.html){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

2. 若要使用 Carthage 安裝 `BMSCore`，請遵循下列[指示 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")。

  1. 將下行新增至 Cartfile：

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. 執行 `carthage update` 指令。

  3. 在建置完成之後，請遵循 Carthage 指示中的[步驟 3 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")，以將 `BMSCore.framework` 新增至專案。

      針對使用 Swift 2.3 所建置的應用程式，請使用 `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3` 指令。否則，請使用 `carthage update` 指令。

3. 匯入 `BMSCore` 模組。

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. 使用下列程式碼，起始設定 `BMSClient` 類別。

  請將起始設定碼放入應用程式委派的 `application(_:didFinishLaunchingWithOptions:)` 方法中，或最適合您專案的位置中。

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Make sure that you point to your region
  ```
  {: codeblock}

  您必須起始設定具有 **bluemixRegion** 參數的 `BMSClient`。在起始設定程式中，**bluemixRegion** 值指定您要使用的 {{site.data.keyword.Bluemix_notm}} 部署，例如，`BMSClient.Region.usSouth`、`BMSClient.Region.unitedKingdom` 或 `BMSClient.Region.sydney`。

## 起始設定 Cordova 應用程式
{: #init-BMSClient-cordova}

1. 從您的 Cordova 應用程式根目錄，執行下列指令以新增 Cordova 外掛程式：

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. 在主要 JavaScript 檔案或在最適合您專案的位置中新增起始設定碼，以在 Cordova 應用程式中起始設定 `BMSClient` 類別。

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  您必須起始設定具有 **bluemixRegion** 參數的 `BMSClient`。在起始設定程式中，**bluemixRegion** 值指定您要使用的 {{site.data.keyword.Bluemix_notm}} 部署，例如，`BMSClient.REGION_US_SOUTH`、`BMSClient.REGION_UK` 或 `BMSClient.REGION_SYDNEY`。

## 相關鏈結
{: #BMSClient-rellinks notoc}

* [BMSCore Android SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")
* [BMSCore iOS SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")
* [BMSCore Cordova 外掛程式 ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![外部鏈結圖示](../icons/launch-glyph.svg "外部鏈結圖示")
