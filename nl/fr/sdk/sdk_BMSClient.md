---

copyright:
  years: 2016, 2017
lastupdated: "2018-03-16"

---
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}

# Initialisation de BMSClient
{: #sdk_BMSClient}

`BMSCore` fournit l'infrastructure HTTP que les autres SDK de client des services Web et mobiles {{site.data.keyword.Bluemix}} utilisent pour communiquer avec leurs services {{site.data.keyword.Bluemix_notm}} correspondants.


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

  ```Java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Make sure that you point to your region
  ```
  {: codeblock}

  Vous devez initialiser `BMSClient` avec le paramètre **bluemixRegion**. Dans l'initialiseur, la valeur **bluemixRegion** spécifie le déploiement {{site.data.keyword.Bluemix_notm}} que vous utilisez, par exemple, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` ou `BMSClient.REGION_SYDNEY`.


## Initialisation de votre application iOS
{: #init-BMSClient-ios}

Vous pouvez utiliser [CocoaPods](https://cocoapods.org){: new_window} ou [Carthage](https://github.com/Carthage/Carthage){: new_window} pour obtenir le package `BMSCore`.

1. Pour installer `BMSCore` à l'aide de CocoaPods, ajoutez les lignes ci-après à votre fichier Pod. Si votre projet ne comporte pas de fichier Pod, utilisez la commande `pod init`.

  ```Swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  Exécutez ensuite la commande `pod install` et ouvrez le fichier `.xcworkspace` généré. Pour effectuer une mise à jour vers une édition plus récente de `BMSCore`, utilisez `pod update BMSCore`.

  Pour plus d'informations sur l'utilisation de CocoaPods, voir les [guides CocoaPods![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://guides.cocoapods.org/using/index.html){: new_window}.

2. Pour installer `BMSCore` en utilisant Carthage, suivez ces [instructions ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/Carthage/Carthage#getting-started){: new_window}.

  1. Ajoutez la ligne suivante à votre fichier Cartfile :

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. Exécutez la commande `carthage update`.

  3. Une fois la génération terminée, ajoutez `BMSCore.framework` à votre projet en suivant l'[étape 3 ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://github.com/Carthage/Carthage#getting-started) des instructions Carthage.

      Pour les applications générées avec Swift 2.3, utilisez la commande `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3`. Sinon, utilisez la commande `carthage update`.

3. Importez le module.

  ```Swift
  import BMSCore
  ```
  {: codeblock}

4. Initialisez la classe `BMSClient` à l'aide du code suivant :

  Placez le code d'initialisation dans la méthode `application(_:didFinishLaunchingWithOptions:)` de votre délégué d'application ou dans un endroit particulièrement approprié pour votre projet.

  ```Swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Make sure that you point to your region
  ```
  {: codeblock}

  Vous devez initialiser `BMSClient` avec le paramètre **bluemixRegion**. Dans l'initialiseur, la valeur **bluemixRegion** spécifie le déploiement {{site.data.keyword.Bluemix_notm}} que vous utilisez, par exemple, `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom` ou `BMSClient.Region.sydney`.


## Initialisation de votre application Cordova
{: #init-BMSClient-cordova}

1. Ajoutez le plug-in Cordova en exécutant la commande suivante depuis le répertoire racine de votre application Cordova :

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

  Vous devez initialiser `BMSClient` avec le paramètre **bluemixRegion**. Dans l'initialiseur, la valeur **bluemixRegion** spécifie le déploiement {{site.data.keyword.Bluemix_notm}} que vous utilisez, par exemple, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` ou `BMSClient.REGION_SYDNEY`.


# Liens connexes
{: #rellinks notoc}

## Liens connexes
{: #general notoc}

* [SDK BMSCore pour Android](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window}
* [SDK BMSCore pour iOS](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window}
* [Plug-in BMSCore pour Cordova](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window}
