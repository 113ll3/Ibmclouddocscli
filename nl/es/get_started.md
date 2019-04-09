---



copyright:

  years: 2015, 2019
lastupdated: "2019-01-03"

---


{:shortdesc: .shortdesc}
{:gif: data-image-type='gif'}
{:new_window: target="_blank"}
{:tip: .tip}



# Iniciación a la CLI de {{site.data.keyword.Bluemix_notm}}
{: #getting-started}

Se recomienda instalar la CLI de {{site.data.keyword.Bluemix_notm}} y todas las dependencias recomendadas utilizando el método que se describe [aquí.](/docs/cli/index.html)
{: tip}


La CLI de {{site.data.keyword.Bluemix_notm}} proporciona la interfaz de línea de mandatos para gestionar aplicaciones, contenedores, infraestructuras, servicios y otros recursos de {{site.data.keyword.Bluemix_notm}}.


Para empezar solo con la CLI de {{site.data.keyword.Bluemix_notm}}:

1. Seleccione el instalador de su SO para descargar

   Mac OS X de 64 bits: [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows de 64 bits: [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 de 64 bits: [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE de 64 bits (ppc64le): [instalador](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **Los releases de 32 bits y versiones anteriores se pueden encontrar [aquí](/docs/cli/reference/ibmcloud/all_versions.html)

1. Ejecute el instalador
   * Para macOS y Windows, ejecute el instalador.
   * Para Linux, extraiga el paquete y ejecute el script `install_bluemix_cli`

1. Establezca como destino un punto final de API e inicie sesión en {{site.data.keyword.Bluemix_notm}}

  ![Ejemplo](example.gif){: gif}

Ahora está listo para gestionar recursos de {{site.data.keyword.Bluemix_notm}}. Escriba `ibmcloud help` para ver las descripciones de mandatos.

Si está utilizando un ID federado, siga las instrucciones [aquí](/docs/iam/login_fedid.html#federated_id) para iniciar sesión con un código de acceso de un solo uso o una clave de API.
{: tip}

## Otros enlaces para explorar más la CLI de {{site.data.keyword.Bluemix_notm}}

* [Más opciones para descargar e instalar la CLI de {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud/download_cli.html)
* [Extend {{site.data.keyword.Bluemix_notm}} Prestaciones de la CLI con plug-ins](/docs/cli/reference/ibmcloud/extend_cli.html)
* [Todas las versiones de la CLI de {{site.data.keyword.Bluemix_notm}} y las notas de release](/docs/cli/reference/ibmcloud/all_versions.html)
* [Documento sobre el {{site.data.keyword.Bluemix_notm}}uso de mandatos de CLI](/docs/cli/reference/ibmcloud/bx_cli.html)


## Informar de problemas y enviar comentarios
{: #issues}

Utilice las opciones siguientes para informar de problemas o enviar nuevas solicitudes de características:
 * Crear problemas en [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg)
 * Dejar mensajes en el [canal de Slack](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Icono de enlace externo](../../../icons/launch-glyph.svg)
