---

copyright:
  years: 2019
lastupdated: "2019-04-26"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# Desinstalación de la CLI de {{site.data.keyword.cloud_notm}} autónoma
{: #uninstall-ibmcloud-cli}

Siga los pasos siguientes para desinstalar la CLI de {{site.data.keyword.cloud_notm}} autónoma en determinadas plataformas.
{: shortdesc}

## Desinstalación en Windows
{: #uninstall-cli-windows}

1. Pulse el botón **Inicio** y luego seleccione **Panel de control**.
2. En la ventana emergente, pulse **Desinstalar un programa**.
3. En la lista de aplicaciones emergente, localice **Interfaz de línea de mandatos de IBM Cloud**.
4. Pulse con el botón derecho del ratón **Interfaz de línea de mandatos de IBM Cloud**, y seleccione **Desinstalar**.
5. Se inicia el desinstalador. Siga las instrucciones para finalizar la desinstalación.

## Desinstalación en Linux y macOS
{: #uninstall-cli-linux-macos}

Los pasos de desinstalación son distintos en función de la versión de la CLI que se ha instalado.

Para determinar la versión de la CLI de {{site.data.keyword.cloud_notm}}, ejecute:
```
ibmcloud -v
```
{: codeblock}

Para desinstalar versiones anteriores a `0.9.0`, ejecute los siguientes mandatos:
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

Limpie los scripts de rellenado automático, si los ha configurado. Para obtener más información, consulte [Habilitación del rellenado automático de shell para la CLI de {{site.data.keyword.cloud_notm}} (solo Linux y Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

Para desinstalar versiones `0.9.0` y posteriores, ejecute el siguiente mandato:
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

Limpie los scripts de rellenado automático personalizados. Para obtener más información, consulte [Habilitación del rellenado automático de shell para la CLI de {{site.data.keyword.cloud_notm}} (solo Linux y Mac)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).
