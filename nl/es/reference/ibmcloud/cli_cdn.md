---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, content delivery network, cdn service, cdn, classic infrastructure, ibmcloud sl cdn

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cómo trabajar con el servicio CDN
{: #sl-cdn-service}

El servicio de Red de entrega de contenido (CDN) distribuye el contenido en el lugar en el que se necesita. La primera vez que se solicita contenido, se obtiene del servidor host a la red y permanece allí para que otros usuarios puedan acceder al mismo.

Utilice los mandatos siguientes para gestionar el servicio de CDN de la infraestructura clásica de {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl cdn cancel
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

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

Detallar una cuenta CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
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

## ibmcloud sl cdn load
{: #sl_cdn_load}

Almacenar en la memoria caché uno o más archivos en todos los nodos extremos.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

Pedir una cuenta CDN.
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>Ancho de banda de CDN, si no se especifica se utilizará el precio de Pago según uso.</dd>
<dt>-s, --storage</dt>
<dd>Almacenamiento de CDN, si no se especifica se utilizará el precio de Pago según uso.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

Opciones de ancho de banda y almacenamiento para solicitar una cuenta CDN.
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
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

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Listar correlaciones de extracción de origen.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
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

## ibmcloud sl cdn purge
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
