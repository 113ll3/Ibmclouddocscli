---

copyright:
  years: 2015, 2019
lastupdated: "2019-02-26"

keywords: stand-alone cli, install cli, uninstall cli, cli, plugin, plug-in, command line, command-line, windows powershell, linux, macos, installer

subcollection: cloud-cli

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Instalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma
{: #install-ibmcloud-cli}

La CLI de {{site.data.keyword.cloud}} proporciona la interfaz de línea de mandatos para gestionar recursos en {{site.data.keyword.cloud_notm}}. Puede seguir utilizando la CLI `cf` para iniciar sesión en
{{site.data.keyword.cloud_notm}}, pero funciona con un servicio de Cloud Foundry en {{site.data.keyword.cloud_notm}}. 

Si desea instalar tanto la CLI de {{site.data.keyword.cloud}} como otros plugins y herramientas recomendados para desarrollar aplicaciones para {{site.data.keyword.cloud_notm}}, consulte [Iniciación a la CLI de {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli).
{: tip}

Efectúe los pasos siguientes para instalar la CLI de {{site.data.keyword.cloud_notm}} autónoma:

1. Seleccione el instalador de su SO para descargarlo.

   Mac OS X de 64 bits: [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows de 64 bits: [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 de 64 bits: [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE de 64 bits (ppc64le): [instalador](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   Para versiones de 32 bits y anteriores, vaya a la página [Releases de la CLI de {{site.data.keyword.cloud_notm}}](/docs/cli/reference/ibmcloud?topic=cloud-cli-cli-releases#cli-releases) para realizar la descarga.

2. Ejecute el instalador
   * Para MacOS y Windows&trade;, ejecute el instalador.
   * Para Linux&trade;, extraiga el paquete y ejecute el script `install`

3. Establezca como destino un punto final de API e inicie sesión en {{site.data.keyword.cloud_notm}}:
   ```
   ibmcloud login
   ```
   {: codeblock}
   
Ahora, está listo para gestionar recursos de {{site.data.keyword.cloud_notm}}. Escriba `ibmcloud help` para ver las descripciones de mandatos.

Si está utilizando un ID federado, siga las instrucciones [aquí](/docs/iam?topic=iam-federated_id#federated_id) para iniciar sesión con un código de acceso de un solo uso o una clave de API.  
{: tip}

Además de los instaladores, puede tener otras opciones para instalar la CLI de {{site.data.keyword.cloud_notm}}:

* Instalar desde shell
* Descargar paquete binario e instalar en un directorio personalizado

## Instalar desde shell
{: #shell_install}

### macOS
{: #shell-install-macos}

Copie y pegue el mandato siguiente a un terminal de su SO Mac y ejecútelo:
```
curl -fsSL https://clis.cloud.ibm.com/install/osx | sh
```
{: codeblock}

### Linux
{: #shell-install-linux}

Copie y pegue el mandato siguiente a un terminal de su SO Linux&trade; y ejecútelo:
```
curl -fsSL https://clis.cloud.ibm.com/install/linux | sh
```
{: codeblock}

### Windows PowerShell
{: #shell-install-windows}

Copie y pegue el mandato siguiente en una consola de terminal de [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo") y ejecútelo:
```
iex(New-Object Net.WebClient).DownloadString('https://clis.cloud.ibm.com/install/powershell')
```
{: codeblock}

## Instalar en un directorio personalizado
{: #install-custom-dir}

Cuando se utilizan instaladores o un script de shell para instalar la CLI de {{site.data.keyword.Bluemix_notm}}, los binarios van a los directorios del sistema. Si desea especificar un directorio diferente, siga los pasos siguientes.

### Paso 1: Descargue el paquete binario basado en el sistema operativo utilizando los enlaces siguientes.
{: #step1-custom-dir}

| Plataforma | Descargas | Suma de comprobación |
|---------|----------|---------|
| macOS | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.cloud.ibm.com/download/bluemix-cli/latest/win64/archive/checksum) |

### Paso 2: Extraiga el paquete en un directorio que especifique.
{: #step2-custom-dir}

   Después de extraer el paquete, puede ver el contenido siguiente:

   Para Linux&trade; y macOS:

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
   {: codeblock}

   Para Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### Paso 3: Añadir a la variable de entorno `PATH` y habilitar el rellenado automático de shell.
{: #step3-custom-dir}

   * Añada `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` a la variable de entorno `PATH`.
   * Para obtener soporte de rellenado automático de shell (solo MacOS y Linux&trade;), consulte [esta guía](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Desinstalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma
{: #uninstall-ibmcloud-cli}

En las secciones siguientes se ofrecen detalles sobre cómo desinstalar la CLI de {{site.data.keyword.cloud_notm}} autónoma en determinadas plataformas.

### Desinstalación en Windows
{: #uninstall-cli-windows}

1. Pulse el botón `Inicio` y luego seleccione `Panel de control`.
2. En la ventana emergente, pulse `Desinstalar un programa`.
3. En la lista de aplicaciones emergente, localice `Interfaz de línea de mandatos de IBM Cloud`.
4. Pulse con el botón derecho del ratón `Interfaz de línea de mandatos de IBM Cloud`, y seleccione `Desinstalar`.
5. Se inicia el desinstalador. Siga las instrucciones para finalizar la desinstalación.

### Desinstalación en Linux y macOS
{: #uninstall-cli-linux-macos}

#### Versiones anteriores a la `0.9.0`

1. Abra un terminal y ejecute los mandatos siguientes:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`

2. Limpie los scripts de rellenado automático, si los ha configurado. Para obtener más información, consulte [Habilitación del rellenado automático para la CLI de {{site.data.keyword.cloud_notm}} (solo Linux y macOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

#### Versión `0.9.0` y posterior

1. Abra un terminal y ejecute el mandato siguiente:
  * `/usr/local/ibmcloud/bin/uninstall`
2. Limpie los scripts de rellenado automático personalizados. Para obtener más información, consulte [Habilitación del rellenado automático para la CLI de {{site.data.keyword.cloud_notm}} (solo Linux y macOS)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

## Otros enlaces para explorar más la CLI de {{site.data.keyword.cloud_notm}}
{: #other-cli-links}

* [Amplíe la CLI de {{site.data.keyword.cloud_notm}} con plugins](/docs/cli/reference/ibmcloud?topic=cloud-cli-plug-ins#plug-ins)
* [Mandatos de CLI generales (ibmcloud)](/docs/cli/reference/ibmcloud?topic=cloud-cli-ibmcloud_cli#ibmcloud_cli)

## Informar de problemas y enviar comentarios
{: #issues}

Utilice las opciones siguientes para informar de problemas o enviar nuevas solicitudes de características:
* Cree problemas en [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").
* Deje mensajes en el [canal #developer-tools de Slack de {{site.data.keyword.cloud_notm}} Tech](https://ibm-cloud-tech.slack.com){: new_window}![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo") - Solicite acceso de equipo [aquí](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg "Icono de enlace externo").
