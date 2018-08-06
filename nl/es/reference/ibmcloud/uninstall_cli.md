---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Desinstalar la CLI de {{site.data.keyword.Bluemix_notm}}

Consulte las secciones siguientes para obtener instrucciones sobre cómo desinstalar {{site.data.keyword.Bluemix_notm}} en plataformas específicas.

## Desinstalar en Windows

* Pulse el botón `Inicio` y, a continuación, seleccione `Panel de control`
* En la ventana emergente, pulse `Desinstalar un programa`
* En la lista de aplicaciones emergente, localice `Interfaz de línea de mandatos de IBM Cloud`
* Pulse con el botón derecho del ratón `Interfaz de línea de mandatos de IBM Cloud`, y seleccione `Desinstalar`
* Se iniciará el desinstalador. Siga las instrucciones para finalizar la desinstalación.

## Desinstalar en Linux/macOS

### Antes de la versión `0.9.0`

* Abra un terminal, y ejecute los mandatos siguientes
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* Limpie los scripts de rellenado automático, si los ha configurado. Para obtener más detalles, consulte [Habilitar el rellenado automático de la CLI](enable_cli_autocompletion.html).

### Versión `0.9.0` y posterior

* Abra un terminal, y ejecute el mandato siguiente
  * `/usr/local/ibmcloud/uninstall`
* Limpie los scripts de rellenado automático, si los ha configurado. Para obtener más detalles, consulte [Habilitar el rellenado automático de la CLI](enable_cli_autocompletion.html).
