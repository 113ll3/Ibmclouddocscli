---



copyright:

  years: 2015, 2017

lastupdated: "2017-06-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Instalación de CLI manual
{: #cli}

La interfaz de línea de mandatos de {{site.data.keyword.Bluemix}} proporciona una forma de gestionar su entorno de {{site.data.keyword.Bluemix_notm}} a través de la misma. También incluye en su instalación una interfaz de línea de mandatos de Cloud Foundry, cf, para gestionar los servicios y las aplicaciones de Cloud Foundry.
{:shortdesc}

De forma predeterminada, ambas herramientas de CLI utilizan el puerto 443. Si tiene el proxy HTTP entre las herramientas de interfaz de línea de mandatos (CLI) y el entorno de {{site.data.keyword.Bluemix_notm}}, debe configurar la variable de entorno `HTTP_PROXY` con el puerto y el URL de proxy HTTP real en el caso de que exista. Consulte [Utilización de la CLI cf con un servidor proxy HTTP ![icono de enlace externo](../icons/launch-glyph.svg)](http://docs.cloudfoundry.org/cf-cli/http-proxy.html){: new_window} para obtener más detalles.

[Descargar {{site.data.keyword.Bluemix_notm}} CLI](/docs/cli/reference/bluemix_cli/all_versions.html){: new_window} 

Si está en macOS, la forma más sencilla de empezar a trabajar con las herramientas de IBM Cloud es utilizando [IBM Cloud Application Tools 2](/docs/cli/icat.html).
{: tip}

## ![](./images/CLI_Plugin.svg) Plugins de la interfaz de línea de mandatos
{: #cliplugins notoc}

Amplíe fácilmente su interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}} con más mandatos. Para acceder
a los plugins de la interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}, consulte el
[Repositorio de plugin de la CLI ![icono de enlace externo](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window}.

### Amplíe su interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}: bx
{: #cli_bluemix_ext notoc}


Después de instalar la herramienta de interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}, el [repositorio de plugins de interfaz de línea de mandatos de ![Icono de enlace externo](../icons/launch-glyph.svg)](https://plugins.ng.bluemix.net/){: new_window} se configura de forma previa y predeterminada con un alias de repositorio `Bluemix`. Puede instalar los plugins disponibles de forma directa.

```
bluemix plugin install plugin_name -r Bluemix
```

| *{{site.data.keyword.autoscaling}} CLI* |  *IBM Bluemix Container Service*  |
|-----|-----|
| Nombre del plugin: escalado automático <br> [Ver documentos](/docs/cli/plugins/auto-scaling/index.html) |  Nombre del plugin: container-service  <br> [Ver documentos](/docs/containers/cs_cli_devtools.html) |
{: caption="Tabla 2. Plugins" caption-side="top"}

|  *Igualdad de red privada* | *Esquemas* | *VPN*  |
|-----|-----|-----|
| Nombre del plugin: private-network-peering  <br> [Ver documentos](/docs/cli/plugins/pnp/index.html) | Nombre del plugin: Schematics  <br> [Ver documentos](/docs/services/schematics/schematics_reference.html) | Nombre del plugin: VPN  <br> [Ver documentos](/docs/cli/plugins/bx_vpn/index.html) |
{: caption="Tabla 3. Plugins" caption-side="top"}

También puede añadir plugins desde otros repositorios que satisfagan la arquitectura de interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}.
1. Si desea instalar plugins de interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}} desde otro repositorio, establezca el punto final de registro del plugin:
```
bluemix plugin repo-add bluemix-other-repo [url_repo]
```
donde `url_repo` es el url https del repositorio de plugins.

2. Ejecute el mandato siguiente para instalar un plugin:
```
bluemix plugin install plugin_name -r bluemix-other-repo
```

### Interfaz de línea de mandatos extendida de Cloud Foundry: bx cf
{: #cli_cf_ext notoc}

Después de instalar la interfaz de línea de mandatos de {{site.data.keyword.Bluemix_notm}}, también se instala una interfaz de línea de mandatos de Cloud Foundry dentro del directorio de la CLI de {{site.data.keyword.Bluemix_notm}}. Ejecute los mandatos de la interfaz de línea de mandatos de Cloud Foundry mediante `bluemix cf`.

* Para instalar plugins CLI cf desde el registro de {{site.data.keyword.Bluemix_notm}}, establezca el punto final del registro de plug-ins:

```
bluemix cf add-plugin-repo bluemix-cf-repo https://plugins.ng.bluemix.net
```
{: codeblock}

* A continuación, ejecute el mandato siguiente para instalar un plugin:

```
bluemix cf install-plugin plugin_name -r bluemix-cf-repo
```
{: codeblock}

| *Consola de administración* | *VPN* |
|-----------------|-----------------|
|  Nombre del plugin: bluemix-admin <br> [Ver documentos](/docs/cli/plugins/bluemix_admin/index.html) | Nombre del plugin: VPN <br> [Ver documentos](/docs/cli/plugins/vpn/index.html) |
{: caption="Tabla 4. Plugins" caption-side="top"}


## ![](./images/Integrated_Dev_Tools.svg) Herramientas para el desarrollo integrado
{: #ide notoc}

Descargue e instale plugins para integrar sus servicios favoritos de {{site.data.keyword.Bluemix_notm}}.

| *Liberty for Java* | *MobileFirst* | *{{site.data.keyword.rules_short}}* | *API Connect* | *Eclipse Tools for Bluemix* |
|----------|----------|----------|----------|----------|
| [Plugin de Liberty Eclipse ![Icono de enlace externo](../icons/launch-glyph.svg)](https://developer.ibm.com/wasdev/downloads/liberty-profile-using-eclipse/){: new_window} | [Plugin de Eclipse ![Icono de enlace externo](../icons/launch-glyph.svg)](https://marketplace.eclipse.org/content/ibm-mobilefirst-platform-studio){: new_window} | [Plugin de Rules Designer Eclipse](../services/rules/index.html#rulov002) | [Kit de utilidades del desarrollador](/docs/services/apiconnect/creating_apis.html#install_dev_tk ) | [Plugin de Bluemix Eclipse](/docs/manageapps/eclipsetools/eclipsetools.html) |
{: caption="Tabla 5. Plugins" caption-side="top"}
