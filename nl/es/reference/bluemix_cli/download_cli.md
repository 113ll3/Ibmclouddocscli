---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-27"

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

   **Los releases de 32 bits y versiones anteriores se pueden encontrar [aquí](all_versions.html)

1. Ejecute el instalador
   * Para macOS y Windows, simplemente ejecute el instalador.
   * Para Linux, extraiga el paquete y ejecute el script `install_bluemix_cli`

1. Establezca como destino un punto final de API e inicie sesión en {{site.data.keyword.Bluemix_notm}}

  ![Ejemplo](example.gif){: gif}

Ahora está listo para gestionar recursos de {{site.data.keyword.Bluemix_notm}}. Escriba `ibmcloud help` para ver las descripciones de mandatos.

Si está utilizando un ID federado, siga las instrucciones [aquí](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) para iniciar sesión con un código de acceso de una sola vez o una clave de API.  
{: tip}

## Más opciones para instalar la CLI de {{site.data.keyword.Bluemix_notm}}
{: #more_options_install}


Además del [instalador](install_use_cli.html#getting_started), también puede utilizar el shell para descargar e instalar la CLI. 


### Instalar desde el shell
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

## Otros enlaces para explorar más la CLI de {{site.data.keyword.Bluemix_notm}}

* [Amplíe las prestaciones de la CLI de {{site.data.keyword.Bluemix_notm}} con plugins](extend_cli.html)
* [Documento sobre el {{site.data.keyword.Bluemix_notm}}uso de mandatos de CLI](ic_cli_cmds.html)


## Informar de problemas y enviar comentarios
{: #issues}

Utilice las opciones siguientes para informar de problemas o enviar nuevas solicitudes de características:
 * Crear problemas en [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg)
 * Dejar mensajes en el [canal de Slack](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg)
