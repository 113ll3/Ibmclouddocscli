---

copyright:
  years: 2016, 2019
lastupdated: "2019-06-10"

keywords: cli, bmscclient, bmscore sdk, network request, ios, android, studio, cordova, client sdk, sdk, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}

# Initialisation de BMSClient
{: #sdk_BMSClient}

`BMSCore` fournit l'infrastructure HTTP que les autres SDK de client des services Web et mobiles {{site.data.keyword.cloud}} utilisent pour communiquer avec leurs services {{site.data.keyword.cloud_notm}} correspondants.

## Initialisation de votre application Android
{: #init-BMSClient-android}

Vous pouvez soit télécharger et importer le package `BMSCore` dans votre projet Android Studio, soit utiliser Gradle.

1. Importez le SDK de client en ajoutant l'instruction `import` suivante au début de votre fichier de projet :

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. Initialisez le SDK `BMSClient` dans votre application Android en ajoutant le code d'initialisation dans la méthode
`onCreate` de l'activité principale dans votre application Android ou à l'emplacement le plus approprié pour votre projet.

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Make sure that you point to your region
  ```
  {: codeblock}

  Vous devez initialiser `BMSClient` avec le paramètre `bluemixRegion`. Dans l'initialiseur, la valeur `bluemixRegion` spécifie le déploiement {{site.data.keyword.cloud_notm}} que vous utilisez, par exemple, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` ou `BMSClient.REGION_SYDNEY`.

## Initialisation de votre application iOS
{: #init-BMSClient-ios}

Vous pouvez utiliser [CocoaPods ](https://cocoapods.org){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") ou [Carthage ](https://github.com/Carthage/Carthage){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") pour vous procurer le package `BMSCore`.

1. Pour installer `BMSCore` à l'aide de CocoaPods, ajoutez les lignes ci-après à votre fichier Pod. Si votre projet n'a pas encore de fichier Pod, utilisez la commande `pod init`.

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  Exécutez ensuite la commande `pod install` et ouvrez le fichier `.xcworkspace` généré. Pour effectuer une mise à jour vers une édition plus récente de `BMSCore`, utilisez `pod update BMSCore`.

  Pour plus d'informations sur l'utilisation de CocoaPods, voir les [guides CocoaPods](https://guides.cocoapods.org/using/index.html){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").

2. Pour installer `BMSCore` en utilisant Carthage, suivez ces [instructions ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").

  1. Ajoutez la ligne suivante à votre fichier Cartfile :

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. Exécutez la commande `carthage update`.

  3. Une fois la génération terminée, ajoutez `BMSCore.framework` à votre projet en suivant l'[étape 3 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") des instructions Carthage.

      Pour les applications générées avec Swift 2.3, utilisez la commande `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3`. Sinon, utilisez la commande `carthage update`.

3. Importez le module `BMSCore`.

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. Initialisez la classe `BMSClient` à l'aide du code suivant.

  Placez le code d'initialisation dans la méthode `application(_:didFinishLaunchingWithOptions:)` de votre délégué d'application ou dans un endroit particulièrement approprié pour votre projet.

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Make sure that you point to your region
  ```
  {: codeblock}

  Vous devez initialiser `BMSClient` avec le paramètre **bluemixRegion**. Dans l'initialiseur, la valeur **bluemixRegion** spécifie le déploiement {{site.data.keyword.cloud_notm}} que vous utilisez (par exemple, `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom` ou `BMSClient.Region.sydney`).

## Initialisation de votre application Cordova
{: #init-BMSClient-cordova}

1. Ajoutez le plugin Cordova en exécutant la commande suivante depuis le répertoire racine de votre application Cordova :

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. Initialisez la classe `BMSClient` dans votre application Cordova en ajoutant le code d'initialisation
dans le fichier JavaScript principal ou à l'emplacement le plus approprié pour votre projet.

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  Vous devez initialiser `BMSClient` avec le paramètre **bluemixRegion**. Dans l'initialiseur, la valeur **bluemixRegion** spécifie le déploiement {{site.data.keyword.cloud_notm}} que vous utilisez (par exemple, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` ou `BMSClient.REGION_SYDNEY`).

## Liens connexes
{: #BMSClient-rellinks notoc}

* [BMSCore Android SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
* [BMSCore iOS SDK ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
* [BMSCore Cordova Plugin ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
