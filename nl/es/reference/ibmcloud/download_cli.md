---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-10"

keywords: stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}
{:tip: .tip}

# Instalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma
{: #install-ibmcloud-cli}

La CLI de {{site.data.keyword.cloud}} proporciona la interfaz de línea de mandatos para gestionar recursos en {{site.data.keyword.cloud_notm}}. Puede seguir utilizando la CLI `cf` para iniciar sesión en
{{site.data.keyword.cloud_notm}}, pero funciona con un servicio de Cloud Foundry en {{site.data.keyword.cloud_notm}}. 

Si desea instalar la CLI de {{site.data.keyword.cloud}} más reciente y otros plugins y herramientas recomendados para desarrollar aplicaciones para {{site.data.keyword.cloud_notm}}, consulte [Iniciación a la CLI de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-getting-started).
{: tip}

## Antes de empezar
{: #before-download-cli}

Si necesita utilizar una versión de 32 bits, o una versión anterior que no sea la última para entornos {{site.data.keyword.cloud_notm}} dedicados, consulte [Releases de la CLI de {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window}![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").

## Instalación con un instalador
{: #ibmcloud-cli-installer}

Siga los pasos siguientes para instalar la CLI de {{site.data.keyword.cloud_notm}} autónoma más reciente:

1. Utilice un navegador para acceder al repositorio oficial de GitHub [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) y **seleccione** el instalador de su sistema operativo para comenzar la descarga. Se admiten los siguientes sistemas operativos: macOS X 64-bit, Windows&trade; 64-bit, Linux&trade; x86 64-bit y Linux&trade; LE 64-bit (ppc64le).

2. Ejecute el instalador:
  * Para Mac y Windows&trade;, ejecute el instalador.
  * Para Linux&trade;, extraiga el paquete y ejecute el script `install`.

3. Inicie una sesión en {{site.data.keyword.cloud_notm}}:
  ```
  ibmcloud login
  ```
  {: codeblock}
   
  Ahora, está listo para gestionar recursos de {{site.data.keyword.cloud_notm}}. Escriba `ibmcloud help` para ver las descripciones de mandatos.

  Si utiliza un ID federado, [inicie una sesión con un código de acceso de uso único o con una clave de API](/docs/iam?topic=iam-federated_id).
  {: tip}

## Instalación desde el shell
{: #shell_install}

Para instalar la CLI más reciente para el sistema operativo desde el shell manualmente, utilice el mandato siguiente para el sistema operativo:

* Para **Mac**, copie y pegue el mandato siguiente en un terminal y ejecútelo:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
  ```
  {: codeblock}

* Para **Linux&trade;**, copie y pegue el mandato siguiente en un terminal y ejecútelo:
  ```
  curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
  ```
  {: codeblock}

* Para **Windows&trade;**, copie y pegue el siguiente mandato en una consola de terminal de [Windows&trade; PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo") y ejecútelo:
  ```
  iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
  ```
  {: codeblock}

## Instalación en un directorio personalizado
{: #install-custom-dir}

Cuando se utilizan instaladores o un script de shell para instalar la CLI de {{site.data.keyword.cloud_notm}}, se instala en los directorios del sistema. Si desea especificar un directorio diferente, siga los pasos siguientes.

1. Utilice un navegador para acceder al repositorio oficial de GitHub [`ibm-cloud-cli-releases`](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/) y **seleccione** el archivo binario correspondiente a su plataforma para comenzar la descarga. Se admiten las siguientes plataformas: macOS, linux32, linux64, ppc64le, win32 y win64.

2. Extraiga el paquete en un directorio que especifique.

   Verá el siguiente contenido extraído:

   Para Linux &trade; y Mac:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: screen}

   Para Windows&trade;:
   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: screen}

3. Añada a la variable de entorno `PATH` y habilite el rellenado automático de shell.
  * Añada `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` a la variable de entorno `PATH`.
  * Para obtener soporte de rellenado automático de shell (solo Mac y Linux&trade;), consulte [Habilitación del rellenado automático de shell para la CLI de IBM Cloud](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Actualización de la CLI de {{site.data.keyword.cloud_notm}}
{: #update-ibmcloud-cli}

Debe utilizar la versión más reciente de la CLI. Si no está utilizando la versión más reciente, ejecute el mandato siguiente para actualizar la CLI:

```
ibmcloud update
```
{: codeblock}

Para determinar la versión de la CLI de {{site.data.keyword.cloud_notm}}, ejecute el siguiente mandato:
```
ibmcloud -v
```
{: codeblock}

Si está ejecutando el release actual, se visualiza la salida siguiente:
```
Checking for updates...
No update required. Your CLI is already up-to-date.
```
{: screen}

Para que se le envíe notificaciones sobre nuevos releases de la CLI de {{site.data.keyword.cloud_notm}}, suscríbase al [Repositorio de releases de CLI de {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").
