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

# BMSClient initialisieren
{: #sdk_BMSClient}

`BMSCore` stellt die HTTP-Infrastruktur bereit, die die anderen Client-SDKs für {{site.data.keyword.cloud}} Web- und Mobile-Services für die Kommunikation mit den entsprechenden {{site.data.keyword.cloud_notm}}-Services verwenden.

## Android-App initialisieren
{: #init-BMSClient-android}

Sie können entweder das `BMSCore`-Paket herunterladen und in Ihr Android Studio-Projekt importieren oder Sie können Gradle verwenden.

1. Importieren Sie das Client-SDK, indem Sie die folgende `import`-Anweisung am Anfang Ihrer Projektdatei hinzufügen:

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. Initialisieren Sie das `BMSClient`-SDK in Ihrer Android-App, indem Sie den Initialisierungscode in der Methode `onCreate` der Hauptaktivität in Ihrer Android-App hinzufügen oder an einer anderen Stelle, die für Ihr Projekt sinnvoll ist.

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Stellen Sie sicher, dass Sie auf Ihre Region zeigen.
  ```
  {: codeblock}

  Sie müssen den `BMSClient` mit dem Parameter **bluemixRegion** initialisieren. Im Initialisierungsoperator gibt der Wert **bluemixRegion** an, welche {{site.data.keyword.Bluemix_notm}}-Bereitstellung verwendet wird, z. B. `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` oder `BMSClient.REGION_SYDNEY`.


## iOS-App initialisieren
{: #init-BMSClient-ios}

Sie können [CocoaPods ](https://cocoapods.org){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") oder [Carthage ](https://github.com/Carthage/Carthage){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") verwenden, um das `BMSCore`-Paket abzurufen.

1. Fügen Sie die folgenden Zeilen zu Ihrer POD-Datei hinzu, um `BMSCore` mithilfe von CocoaPods zu installieren. Wenn für Ihr Projekt noch keine POD-Datei vorhanden ist, verwenden Sie den Befehl `pod init`.

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  Führen Sie dann den Befehl `pod install` aus und öffnen Sie die generierte Datei `.xcworkspace`. Verwenden Sie zum Aktualisieren auf ein neueres Release von `BMSCore` den Befehl `pod update BMSCore`.

  Weitere Informationen zur Verwendung von CocoaPods finden Sie in den [CocoaPods-Handbüchern ](https://guides.cocoapods.org/using/index.html){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link").

2. Befolgen Sie diese [Anweisungen ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link"), um `BMSCore` mithilfe von Carthage zu installieren.

  1. Fügen Sie die folgende Zeile zu Ihrer Cart-Datei hinzu:

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. Führen Sie den Befehl `carthage update` aus.

  3. Nachdem der Build fertig gestellt ist, fügen Sie `BMSCore.framework` zu Ihrem Projekt hinzu, indem Sie [Schritt 3 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link") in den Carthage-Anweisungen ausführen.

      Verwenden Sie für Apps, die mit Swift 2.3 erstellt wurden, den Befehl `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3`. Verwenden Sie andernfalls den Befehl `carthage update`.

3. Importieren Sie das Modul `BMSCore`.

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. Initialisieren Sie die Klasse `BMSClient` unter Verwendung des folgenden Codes.

  Platzieren Sie den Initialisierungscode in der Methode `application(_:didFinishLaunchingWithOptions:)` Ihres App-Delegierten oder an einer anderen Stelle, die für Ihr Projekt sinnvoll ist.

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Stellen Sie sicher, dass Sie auf Ihre Region zeigen.
  ```
  {: codeblock}

  Sie müssen den `BMSClient` mit dem Parameter **bluemixRegion** initialisieren. Im Initialisierungsoperator gibt der Wert **bluemixRegion** an, welche {{site.data.keyword.Bluemix_notm}}-Bereitstellung Sie verwenden (z. B. `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom` oder `BMSClient.Region.sydney`).

## Cordova-App initialisieren
{: #init-BMSClient-cordova}

1. Fügen Sie das Cordova-Plug-in hinzu, indem Sie den folgenden Befehl im Stammverzeichnis Ihrer Cordova-App ausführen:

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. Initialisieren Sie die Klasse `BMSClient` in Ihrer Cordova-App, indem Sie den Initialisierungscode in der JavaScript-Hauptdatei hinzufügen oder an einer anderen Stelle, die für Ihr Projekt sinnvoll ist.

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  Sie müssen den `BMSClient` mit dem Parameter **bluemixRegion** initialisieren. Im Initialisierungsoperator gibt der Wert **bluemixRegion** an, welche {{site.data.keyword.Bluemix_notm}}-Bereitstellung Sie verwenden (z. B. `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` oder `BMSClient.REGION_SYDNEY`).

## Zugehörige Links
{: #BMSClient-rellinks notoc}

* [BMSCore Android SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
* [BMSCore iOS SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
* [BMSCore Cordova Plugin ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")
