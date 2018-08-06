---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos para gestionar CDN de la infraestructura de {{site.data.keyword.Bluemix_notm}}

 <table summary="Mandatos de infraestructura generales de {{site.data.keyword.Bluemix_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. CDN de la infraestructura de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">CDN de la infraestructura de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>

 ### ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Cancelar una cuenta CDN.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl cdn detail
{: #sl_cdn_detail}

Detallar una cuenta CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### ibmcloud sl cdn list
{: #sl_cdn_list}

Listar todas las cuentas CDN.
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--sortby</dt>
<dd>Columna por la que ordenar. Las opciones son: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filtrar por ID de pedido.</dd>
</dl>

### ibmcloud sl cdn load
{: #sl_cdn_load}

Almacenar en la memoria caché uno o más archivos en todos los nodos extremos.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### ibmcloud sl cdn order
{: #sl_cdn_order}

Pedir una cuenta CDN.
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>Ancho de banda de CDN, si no se especifica se utilizará el precio de 'Pago según uso'.</dd>
<dt>-s, --storage</dt>
<dd>Almacenamiento de CDN, si no se especifica se utilizará el precio de 'Pago según uso'.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl cdn options
{: #sl_cdn_options}

Opciones de ancho de banda y almacenamiento para solicitar una cuenta CDN.
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Crear una correlación de extracción origen.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-t, --type</dt>
<dd>El tipo de soporte para esta correlación (http, flash, wm, ...). El valor predeterminado es: http.</dd>
<dt>-c, --cname</dt>
<dd>Un CNAME opcional para adjuntar a la correlación.</dd>
</dl>

### ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Listar correlaciones de extracción de origen.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

### ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Eliminar una correlación de extracción origen.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

### ibmcloud sl cdn purge
{: #sl_cdn_purge}

Depurar archivos de memoria caché de todos los nodos extremos.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>
