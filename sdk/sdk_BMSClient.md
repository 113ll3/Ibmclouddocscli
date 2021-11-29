---

copyright:
  years: 2016, 2021
lastupdated: "2021-10-05"

keywords: cli, bmscclient, bmscore sdk, network request, ios, android, studio, cordova, client sdk, sdk

subcollection: cli

---


{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:external: target="_blank" .external}

# Initializing BMSClient
{: #sdk_BMSClient}

`BMSCore` provides the HTTP infrastructure that the other {{site.data.keyword.cloud}} Web and Mobile services client SDKs use to communicate with their corresponding {{site.data.keyword.cloud_notm}} services.
{: shortdesc}

## Initializing your Android app
{: #init-BMSClient-android}

You can either download and import the `BMSCore` package to your Android Studio project, or use Gradle.

1. Import the Client SDK by adding the following `import` statement at the beginning of your project file:

   ```bash
   import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
   ```
   {: codeblock}

2. Initialize the `BMSClient` SDK in your Android application by adding the initialization code in the `onCreate` method of the main activity in your Android app, or in a location that works best for your project.

   ```java
   BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Make sure that you point to your region
   ```
   {: codeblock}

   You must initialize the `BMSClient` with the `bluemixRegion` parameter. In the initializer, the `bluemixRegion` value specifies which {{site.data.keyword.cloud_notm}} deployment you are using, for example, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK`, or `BMSClient.REGION_SYDNEY`.

## Initializing your iOS app
{: #init-BMSClient-ios}

You can use [CocoaPods](https://cocoapods.org){: external} or [Carthage](https://github.com/Carthage/Carthage){: external} to get the `BMSCore` package.

1. To install `BMSCore` by using CocoaPods, add the following lines to your Podfile. If your project doesn't have a Podfile yet, use the `pod init` command.

   ```swift
   use_frameworks!

   target 'MyApp' do
     pod 'BMSCore'
   end
   ```
   {: codeblock}

   Then run the `pod install` command, and open the generated `.xcworkspace` file. To update to a newer release of `BMSCore`, use `pod update BMSCore`.

   For more information about using CocoaPods, see the [CocoaPods Guides](https://guides.cocoapods.org/using/index.html){: external}.

2. To install `BMSCore` by using Carthage, follow these [instructions](https://github.com/Carthage/Carthage#getting-started){: external}.

   1. Add the following line to your Cartfile:

      ```bash
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

   2. Run the `carthage update` command.

   3. After the build is finished, add `BMSCore.framework` to your project by following [Step 3](https://github.com/Carthage/Carthage#getting-started){: external} in the Carthage instructions.

      For apps that are built with Swift 2.3, use the `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3` command. Otherwise, use the `carthage update` command.

3. Import the `BMSCore` module.

   ```swift
   import BMSCore
   ```
   {: codeblock}

4. Initialize the `BMSClient` class by using the following code.

   Place the initialization code in the `application(_:didFinishLaunchingWithOptions:)` method of your app delegate, or in a location that works best for your project.

   ```swift
   BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Make sure that you point to your region
   ```
   {: codeblock}

   You must initialize the `BMSClient` with the **bluemixRegion** parameter. In the initializer, the **bluemixRegion** value specifies which {{site.data.keyword.cloud_notm}} deployment you're using, for example, `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom`, or `BMSClient.Region.sydney`.

## Initializing your Cordova app
{: #init-BMSClient-cordova}

1. Add the Cordova plugin by running the following command from your Cordova app root directory:

   ```bash
   cordova plugin add bms-core
   ```
   {: codeblock}

2. Initialize the `BMSClient` class in your Cordova app by adding the initialization code in the main JavaScript file, or in a location that works best for your project.

   ```bash
   BMSClient.initialize(BMSClient.REGION_US_SOUTH);
   ```
   {: codeblock}

   You must initialize the `BMSClient` with the **bluemixRegion** parameter. In the initializer, the **bluemixRegion** value specifies which {{site.data.keyword.cloud_notm}} deployment you're using, for example, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK`, or `BMSClient.REGION_SYDNEY`.

## Related Links
{: #BMSClient-rellinks notoc}

* [BMSCore Android SDK](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: external}
* [BMSCore iOS SDK](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: external}
* [BMSCore Cordova Plugin](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: external}
