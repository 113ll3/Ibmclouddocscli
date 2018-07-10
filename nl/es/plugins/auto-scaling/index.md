---



copyright:

  years: 2015，2018

lastupdated: "2018-06-21"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# CLI de Auto-Scaling
{: #autoscalingcli}


Puede configurar el servicio {{site.data.keyword.autoscaling}} utilizando la CLI de {{site.data.keyword.autoscaling}} para {{site.data.keyword.Bluemix_notm}}. La CLI de {{site.data.keyword.autoscaling}} admite Linux64, Win64 y OSX, y proporciona una funcionalidad similar a la que proporciona la API RESTful de escalado automático.
{: shortdesc}

Antes de empezar, instale la CLI de {{site.data.keyword.Bluemix_notm}}. Consulte [Descargar la CLI de {{site.data.keyword.Bluemix_notm}} ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/home.html){: new_window} para obtener instrucciones.

## Adición del plug-in de CLI de {{site.data.keyword.Bluemix_notm}}

Una vez instalada la CLI de {{site.data.keyword.Bluemix_notm}}, puede añadir el plugin de CLI de {{site.data.keyword.autoscaling}}.

Siga estos pasos para añadir el repositorio e instalar el plug-in:
1. Para añadir el repositorio del plugin de CLI de {{site.data.keyword.Bluemix_notm}}, ejecute el mandato siguiente:
```
ibmcloud plugin repo-add bluemix-plugin-repo https://plugins.ng.bluemix.net
```
2. Para instalar el plugin de CLI de {{site.data.keyword.autoscaling}}, ejecute el mandato siguiente:
```
ibmcloud plugin install auto-scaling -r Bluemix
```

## Adjunción de una política de escalado automático

Puede adjuntar una política de escalado automático a una app específica. Ejecute el mandato siguiente:

```
ibmcloud as policy-attach <APP_NAME> -p <policy_file>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">El nombre de la app a la que desea adjuntar una política de escalado automático.</dd>
<dt class="pt dlterm">&lt;policy_file&gt;</dt>
<dd class="pd">El nombre del archivo JSON que describe la política de escalado automático. Consulte el <a href="https://new-console.{DomainName}/apidocs/48" target="_blank">{{site.data.keyword.autoscaling}} documento de la API RESTful</a> para obtener más detalles.</dd>
</dl>


## Generación de una política de escalado automático

Puede generar una política de escalado automático si responde a las preguntas en la interfaz de línea de mandatos. Según sus respuestas, se guardará un archivo JSON que contiene la definición de la política de escalado automático, con el nombre que haya especificado. Si no especifica el nombre del archivo, el contenido de la política se mostrará directamente en la línea de mandatos sin guardarse en un archivo. Ejecute el mandato siguiente:

```
ibmcloud as policy-create
```
{: codeblock}


## Visualización de una política de escalado automático

Puede mostrar una política de escalado automático de una app. El contenido de la política se mostrará directamente en la línea de mandatos. Ejecute el mandato siguiente:

```
ibmcloud as policy-show <APP_NAME> [--json]
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">El nombre de la app para la que desea mostrar la política de escalado automático. De manera predeterminada, la estructura JSON se traduce a una serie de resultados legibles para una persona.</dd>
</dl>

**Consejo:** También puede utilizar la opción **--json** para mostrar la respuesta JSON original.


## Desconexión de una política de escalado automático

Puede eliminar una política de escalado automático de una app. Ejecute el mandato siguiente:

```
ibmcloud as policy-detach <APP_NAME>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">El nombre de la app para la que desea desconectar la política de escalado automático.</dd>
</dl>


## Habilitación o inhabilitación de una política de escalado automático

Puede habilitar o inhabilitar la política de escalado automático de una app específica. Ejecute el mandato siguiente:

```
ibmcloud as policy-enable|policy-disable <APP_NAME>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">El nombre de la app para la que desea habilitar o inhabilitar la política de auto-scaling.</dd>
</dl>


## Visualización del historial de escalado automático de una app

Puede mostrar el historial de la actividad de escalado automático de una app específica. Se muestra una tabla de historial de registros de escalado automático en la interfaz de línea de mandatos.

```
ibmcloud as history-show <APP_NAME>  [--start-date=<start_timestamp>]  [--end-date=<end_timestamp>]  [--json]
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;APP_NAME&gt;</dt>
<dd class="pd">El nombre de la app para la que desea mostrar el historial de la política de escalado automático.
<dt class="pt dlterm">&lt;start_timestamp&gt;</dt>
<dd class="pd">La indicación de fecha y hora del comienzo del rango del historial. Los formatos admitidos son `yyyy-MM-ddTHH:mm:ss+/-hhmm, yyyy-MM-ddTHH:mm:ssZ`. De manera predeterminada, la indicación de fecha y hora se define hasta 50 horas por delante de la hora actual. Consulte los <a href="https://www.w3.org/TR/NOTE-datetime" target="_blank">Formatos estándar de fecha y hora W3C</a> para obtener más detalles sobre el formato de la indicación de fecha y hora.
<dt class="pt dlterm">&lt;end_timestamp&gt;</dt>
<dd class="pd">La indicación de fecha y hora del final del rango del historial. Los formatos admitidos son `yyyy-MM-ddTHH:mm:ss+/-hhmm, yyyy-MM-ddTHH:mm:ssZ`. De manera predeterminada, la indicación de fecha y hora está definida a la hora actual. Consulte los <a href="https://www.w3.org/TR/NOTE-datetime" target="_blank">Formatos estándar de fecha y hora W3C</a> para obtener más detalles sobre el formato de la indicación de fecha y hora.
</dl>



**Consejo:** También puede utilizar la opción **--json** para mostrar la respuesta JSON original.

# rellinks
{: rellinks}
## general
{: general}
* [{{site.data.keyword.autoscaling}} servicio](/docs/services/Auto-Scaling/index.html)
* [CLI de {{site.data.keyword.Bluemix_notm}} ![Icono de enlace externo](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/home.html){: new_window}
* [Formatos estándar de fecha y hora W3C ![icono de enlace externo](../../../icons/launch-glyph.svg)](https://www.w3.org/TR/NOTE-datetime){: new_window}
