---

copyright:
  years: 2016, 2019
lastupdated: "2019-05-21"

keywords: cli, bmscclient, bmscore sdk, network request, ios, android, studio, cordova, client sdk, sdk, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}

# 初始化 BMSClient
{: #sdk_BMSClient}

`BMSCore` 提供的 HTTP 基础架构可供其他 {{site.data.keyword.cloud}} Web 和 Mobile 服务客户机 SDK 用于与其对应的 {{site.data.keyword.cloud_notm}} 服务进行通信。

## 初始化 Android 应用程序
{: #init-BMSClient-android}

可以下载 `BMSCore` 软件包，并将其导入到 Android Studio 项目中，也可以使用 Gradle。

1. 通过在项目文件的开头添加以下 `import` 语句来导入客户机 SDK：

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. 通过在 Android 应用程序的主活动的 `onCreate` 方法中添加初始化代码，或者在最适合您项目的位置中添加初始化代码，从而初始化 Android 应用程序中的 `BMSClient` SDK。

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // 确保指向您的区域
  ```
  {: codeblock}

  必须使用 **bluemixRegion** 参数来初始化 `BMSClient`。在初始化程序中，**bluemixRegion** 值指定您使用的 {{site.data.keyword.Bluemix_notm}} 部署，例如 `BMSClient.REGION_US_SOUTH`、`BMSClient.REGION_UK` 或 `BMSClient.REGION_SYDNEY`。


## 初始化 iOS 应用程序
{: #init-BMSClient-ios}

您可以使用 [CocoaPods ](https://cocoapods.org){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 或 [Carthage ](https://github.com/Carthage/Carthage){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标") 来获取 `BMSCore` 软件包。

1. 要使用 CocoaPods 来安装 `BMSCore`，请向 Podfile 添加以下行。如果您的项目还没有 Podfile，请使用 `pod init` 命令。

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  然后，运行 `pod install` 命令，并打开生成的 `.xcworkspace` 文件。要更新到 `BMSCore` 的更新发行版，请使用 `pod update BMSCore`。

  有关使用 CocoaPods 的更多信息，请参阅 [CocoaPods 指南 ](https://guides.cocoapods.org/using/index.html){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。

2. 要使用 Carthage 来安装 `BMSCore`，请遵循以下[指示信息 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")。

  1. 向 Cartfile 添加以下行：

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. 运行 `carthage update` 命令。

  3. 构建完成后，通过遵循 Carthage 指示信息中的[步骤 3 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")，将 `BMSCore.framework` 添加到项目。

      对于使用 Swift 2.3 构建的应用程序，请使用 `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3` 命令。对于其他情况，请使用 `carthage update` 命令。

3. 导入 `BMSCore` 模块。

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. 使用以下代码来初始化 `BMSClient` 类。

  将初始化代码放入应用程序代理的 `application(_:didFinishLaunchingWithOptions:)` 方法中，或放入最适合您项目的位置。

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // 确保指向您的区域
  ```
  {: codeblock}

  必须使用 **bluemixRegion** 参数来初始化 `BMSClient`。在初始化程序中，**bluemixRegion** 值指定您使用的 {{site.data.keyword.Bluemix_notm}} 部署，例如 `BMSClient.Region.usSouth`、`BMSClient.Region.unitedKingdom` 或 `BMSClient.Region.sydney`。

## 初始化 Cordova 应用程序
{: #init-BMSClient-cordova}

1. 通过从 Cordova 应用程序根目录运行以下命令来添加 Cordova 插件：

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. 通过在主 JavaScript 文件中添加初始化代码，或在最适合您项目的位置中添加初始化代码，从而初始化 Cordova 应用程序中的 `BMSClient` 类。

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  必须使用 **bluemixRegion** 参数来初始化 `BMSClient`。在初始化程序中，**bluemixRegion** 值指定您使用的 {{site.data.keyword.Bluemix_notm}} 部署，例如 `BMSClient.REGION_US_SOUTH`、`BMSClient.REGION_UK` 或 `BMSClient.REGION_SYDNEY`。

## 相关链接
{: #BMSClient-rellinks notoc}

* [BMSCore Android SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")
* [BMSCore iOS SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")
* [BMSCore Cordova Plugin ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")
