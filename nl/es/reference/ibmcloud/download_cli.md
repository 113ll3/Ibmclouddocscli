---



copyright:

  years: 2015, 2018
lastupdated: "2018-08-09"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Instalación de la CLI de {{site.data.keyword.Bluemix_notm}} autónoma
{: #install_use}

La CLI de {{site.data.keyword.Bluemix_notm}} proporciona la interfaz de línea de mandatos para gestionar aplicaciones, contenedores, infraestructuras, servicios y otros recursos de {{site.data.keyword.Bluemix_notm}}.

Si desea instalar tanto la CLI de {{site.data.keyword.Bluemix}} como otros plug-ins y herramientas recomendados para el desarrollo de aplicaciones de {{site.data.keyword.Bluemix_notm}}, siga el método descrito [aquí](/docs/cli/index.html).
{: tip}

Efectúe los pasos siguientes para instalar la CLI de {{site.data.keyword.Bluemix_notm}} autónoma:

1. Seleccione el instalador de su SO para descargar

   Mac OS X de 64 bits: [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows de 64 bits: [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 de 64 bits: [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE de 64 bits (ppc64le): [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

1. Ejecute el instalador
   * Para macOS y Windows, simplemente ejecute el instalador.
   * Para Linux, extraiga el paquete y ejecute el script `install_bluemix_cli`

1. Establezca como destino un punto final de API e inicie sesión en {{site.data.keyword.Bluemix_notm}}

   ```
   ibmcloud login
   ```
   {: codeblock}
   
Ahora está listo para gestionar recursos de {{site.data.keyword.Bluemix_notm}}. Escriba `ibmcloud help` para ver las descripciones de mandatos.

Si está utilizando un ID federado, siga las instrucciones [aquí](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) para iniciar sesión con un código de acceso de una sola vez o una clave de API.  
{: tip}

Además de los instaladores, puede tener otras opciones para instalar la CLI de {{site.data.keyword.Bluemix_notm}}:

* Instalar desde shell
* Descargar paquete binario e instalar en un directorio personalizado

## Instalar desde shell
{: #shell_install}

### MacOS

Copie y pegue el mandato siguiente a un terminal de su SO Mac y ejecútelo:

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copie y pegue el mandato siguiente a un terminal de su SO Linux y ejecútelo:

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copie y pegue el mandato siguiente a una consola de terminal de [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} y ejecútelo:

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Instalar en un directorio personalizado

Cuando se utilizan instaladores o un script de shell para instalar la CLI de {{site.data.keyword.Bluemix_notm}}, los binarios irán a los directorios del sistema. Si desea especificar un directorio diferente, siga los pasos siguientes.

### Paso 1: Descargue el paquete binario basado en el sistema operativo utilizando los enlaces siguientes.

| Plataforma | Descargas | Suma de comprobación |
|---------|----------|---------|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### Paso 2: Extraiga el paquete en un directorio que especifique.

   Después de extraer el paquete, el contenido tendrá un aspecto parecido al siguiente:

   Para Linux y MacOS

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

   * Añada `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` a la variable de entorno `PATH`.
   * Para obtener soporte de rellenado automático de shell (solo MacOS y Linux), consulte [esta guía](enable_cli_autocompletion.html).
   
## Desinstalación de la CLI de {{site.data.keyword.Bluemix_notm}} autónoma

Las secciones siguientes proporcionan detalles sobre cómo desinstalar la CLI de {{site.data.keyword.Bluemix_notm}} autónoma en plataformas específicas.

### Desinstalación en Windows

1. Pulse el botón `Inicio` y, a continuación, seleccione `Panel de control`.
2. En la ventana emergente, pulse `Desinstalar un programa`.
3. En la lista de aplicaciones emergente, localice `Interfaz de línea de mandatos de IBM Cloud`.
4. Pulse con el botón derecho del ratón `Interfaz de línea de mandatos de IBM Cloud`, y seleccione `Desinstalar`.
5. Se iniciará el desinstalador. Siga las instrucciones para finalizar la desinstalación.

### Desinstalación en Linux/macOS

#### Antes de la versión `0.9.0`

1. Abra un terminal, y ejecute los mandatos siguientes:
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
2. Limpie los scripts de rellenado automático, si los ha configurado. Para obtener más detalles, consulte [Habilitar el rellenado automático de la CLI](enable_cli_autocompletion.html).

#### Versión `0.9.0` y posterior

1. Abra un terminal, y ejecute el mandato siguiente:
  * `/usr/local/ibmcloud/uninstall`
2. Limpie los scripts de rellenado automático, si los ha configurado. Para obtener más detalles, consulte [Habilitar el rellenado automático de la CLI](enable_cli_autocompletion.html).


## Otros enlaces para explorar más la CLI de {{site.data.keyword.Bluemix_notm}}

* [Amplíe las prestaciones de la CLI de {{site.data.keyword.Bluemix_notm}} con plugins](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [Uso general de mandatos de CLI de {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [Uso general de mandatos de {{site.data.keyword.Bluemix_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html)

## Informar de problemas y enviar comentarios
{: #issues}

Utilice las opciones siguientes para informar de problemas o enviar nuevas solicitudes de características:
 * Cree problemas en [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg).
 * Deje los mensajes en el [IBM Cloud Tech's Slack - canal #developer-tools](https://ibm-cloud-tech.slack.com) - Solicitar acceso de equipo [aquí](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg).
