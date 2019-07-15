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

# Inicializando o BMSClient
{: #sdk_BMSClient}

O `BMSCore` fornece a infraestrutura de HTTP que os outros SDKs do cliente de serviços da web e móveis do {{site.data.keyword.cloud}} usam para se comunicar com seus serviços correspondentes do {{site.data.keyword.cloud_notm}}.

## Inicializando seu app Android
{: #init-BMSClient-android}

É possível fazer download e importar o pacote `BMSCore` para seu projeto Android Studio ou usar o Gradle.

1. Importe o Client SDK incluindo a instrução `import` a seguir no início do seu arquivo de projeto:

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. Inicialize o SDK do `BMSClient` no aplicativo Android incluindo o código de inicialização no método `onCreate` da atividade principal no app Android ou em um local que funcione melhor para seu projeto.

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Make sure that you point to your region
  ```
  {: codeblock}

  Deve-se inicializar o `BMSClient` com o parâmetro `bluemixRegion`. No inicializador, o valor `bluemixRegion` especifica qual implementação do {{site.data.keyword.cloud_notm}} está sendo usada, por exemplo, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` ou `BMSClient.REGION_SYDNEY`.

## Inicializando seu app iOS
{: #init-BMSClient-ios}

É possível usar o [CocoaPods ](https://cocoapods.org){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") ou o [Carthage ](https://github.com/Carthage/Carthage){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") para obter o pacote `BMSCore`.

1. Para instalar o `BMSCore` usando CocoaPods, inclua as linhas a seguir em seu arquivo pod. Se o seu projeto ainda não tiver um Podfile, use o comando `pod init`.

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  Em seguida, execute o comando `pod install` e abra o arquivo `.xcworkspace` gerado. Para atualizar para uma liberação mais recente do `BMSCore`, use `pod update BMSCore`.

  Para obter mais informações sobre como usar o CocoaPods, consulte os Guias do [CocoaPods ](https://guides.cocoapods.org/using/index.html){: new_window} ![Ícone de linkexterno](../../icons/launch-glyph.svg "Ícone de link externo").


2. Para instalar o `BMSCore` usando o Carthage, siga estas [instruções ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").

  1. Inclua a linha a seguir em seu Cartfile:

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. Execute o comando `carthage update`.

  3. Após concluir a construção, inclua `BMSCore.framework` em seu projeto, seguindo a [Etapa 3 ](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") nas instruções do Carthage.

      Para apps construídos com o Swift 2.3, use o comando `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3`. Caso contrário, use o comando `carthage update`.

3. Importe o módulo `BMSCore`.

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. Inicialize a classe `BMSClient` usando o código a seguir.

  Coloque o código de inicialização no método `application(_:didFinishLaunchingWithOptions:)` de seu app delegado ou em um local que funcione melhor para seu projeto.

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Make sure that you point to your region
  ```
  {: codeblock}

  Deve-se inicializar o `BMSClient` com o parâmetro **bluemixRegion**. No inicializador, o valor **bluemixRegion** especifica qual implementação do {{site.data.keyword.cloud_notm}} você está usando, por exemplo, `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom` ou `BMSClient.Region.sydney`.

## Inicializando seu app Cordova
{: #init-BMSClient-cordova}

1. Inclua o plug-in Cordova executando o comando a seguir por meio do diretório-raiz do app Cordova:

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. Inicialize a classe `BMSClient` em seu app Cordova incluindo o código de inicialização no arquivo JavaScript principal ou em um local que funcione melhor para seu projeto.

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  Deve-se inicializar o `BMSClient` com o parâmetro **bluemixRegion**. No inicializador, o valor **bluemixRegion** especifica qual implementação do {{site.data.keyword.cloud_notm}} você está usando, por exemplo, `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` ou `BMSClient.REGION_SYDNEY`.

## Links Relacionados
{: #BMSClient-rellinks notoc}

* [SDK do Android do BMSCore](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
* [SDK do iOS do BMSCore](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
* [Plug-in do Cordova BMSCore ](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
