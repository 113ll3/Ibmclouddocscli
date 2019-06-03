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

# Inicialización de BMSClient
{: #sdk_BMSClient}

`BMSCore` proporciona la infraestructura HTTP que utilizan los otros SDK de cliente de servicios de web y móviles de {{site.data.keyword.cloud}} con sus correspondientes servicios de {{site.data.keyword.cloud_notm}}.

## Inicialización de la app Android
{: #init-BMSClient-android}

Puede descargar e importar el paquete `BMSCore` en su proyecto Android Studio o puede utilizar Gradle.

1. Importe el SDK de cliente añadiendo la siguiente sentencia `import` al principio del archivo del proyecto:

  ```
  import com.ibm.mobilefirstplatform.clientsdk.android.core.api.*;
  ```
  {: codeblock}

2. Inicialice el SDK `BMSClient` en la aplicación Android añadiendo el código de inicialización del método `onCreate` de la actividad principal a la app Android o en la ubicación que mejor se ajuste a su proyecto.

  ```java
  BMSClient.getInstance().initialize(getApplicationContext(), BMSClient.REGION_US_SOUTH); // Asegúrese de que apunte a su región
  ```
  {: codeblock}

  Debe inicializar `BMSClient` con el parámetro **bluemixRegion**. En el inicializador, el valor **bluemixRegion** especifica el despliegue de {{site.data.keyword.Bluemix_notm}} que está utilizando, por ejemplo `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` o `BMSClient.REGION_SYDNEY`.


## Inicialización de la app iOS
{: #init-BMSClient-ios}

Puede utilizar [CocoaPods](https://cocoapods.org){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") o [Carthage](https://github.com/Carthage/Carthage){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") para obtener el paquete `BMSCore`.

1. Para instalar `BMSCore` mediante CocoaPods, añada las siguientes líneas a Podfile. Si el proyecto no tiene todavía un Podfile, utilice el mandato `pod init`.

  ```swift
  use_frameworks!

  target 'MyApp' do
    pod 'BMSCore'
  end
  ```
  {: codeblock}

  A continuación, ejecute el mandato `pod install` y abra el archivo `.xcworkspace` generado. Para actualizar a un release posterior de `BMSCore`, utilice `pod update BMSCore`.

  Para obtener más información sobre cómo utilizar CocoaPods, consulte las [Guías de CocoaPods](https://guides.cocoapods.org/using/index.html){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").

2. Para instalar `BMSCore` mediante Carthage, siga estas [instrucciones](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo").

  1. Añada la siguiente línea a Cartfile:

      ```
      github "ibm-bluemix-mobile-services/bms-clientsdk-swift-core"
      ```
      {: codeblock}

  2. Ejecute el mandato `carthage update`.

  3. Una vez finalizada la compilación, añada `BMSCore.framework` al proyecto siguiendo el [Paso 3](https://github.com/Carthage/Carthage#getting-started){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo") en las instrucciones de Carthage.

      Para apps compiladas con Swift 2.3, utilice el mandato `carthage update --toolchain com.apple.dt.toolchain.Swift_2_3`. De lo contrario, utilice el mandato `carthage update`.

3. Importe el módulo `BMSCore`.

  ```swift
  import BMSCore
  ```
  {: codeblock}

4. Inicialice la clase `BMSClient` utilizando el código siguiente.

  Coloque el código de inicialización en el método `application(_:didFinishLaunchingWithOptions:)` de delegado de la app o en la ubicación que mejor se ajuste a su proyecto.

  ```swift
  BMSClient.sharedInstance.initialize(bluemixRegion: BMSClient.Region.usSouth) // Asegúrese de que apunte a su región
  ```
  {: codeblock}

  Debe inicializar `BMSClient` con el parámetro **bluemixRegion**. En el inicializador, el valor **bluemixRegion** especifica el despliegue de {{site.data.keyword.Bluemix_notm}} que está utilizando, por ejemplo `BMSClient.Region.usSouth`, `BMSClient.Region.unitedKingdom` o `BMSClient.Region.sydney`.

## Inicialización de la app Cordova
{: #init-BMSClient-cordova}

1. Añada el plugin Cordova ejecutando el mandato siguiente desde el directorio raíz de la app Cordova:

  ```
  cordova plugin add bms-core
  ```
  {: codeblock}

2. Inicialice la clase `BMSClient` en la app Cordova añadiendo el código de inicialización en el archivo principal de JavaScript o en la ubicación que mejor se ajuste al proyecto.

  ```
  BMSClient.initialize(BMSClient.REGION_US_SOUTH);
  ```
  {: codeblock}

  Debe inicializar `BMSClient` con el parámetro **bluemixRegion**. En el inicializador, el valor **bluemixRegion** especifica el despliegue de {{site.data.keyword.Bluemix_notm}} que está utilizando, por ejemplo `BMSClient.REGION_US_SOUTH`, `BMSClient.REGION_UK` o `BMSClient.REGION_SYDNEY`.

## Enlaces relacionados
{: #BMSClient-rellinks notoc}

* [SDK BMSCore Android](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-android-core){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")
* [SDK BMSCore iOS](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-swift-core){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")
* [Plugin BMSCore Cordova](https://github.com/ibm-bluemix-mobile-services/bms-clientsdk-cordova-plugin-core){: new_window} ![Icono de enlace externo](../../icons/launch-glyph.svg "Icono de enlace externo")
