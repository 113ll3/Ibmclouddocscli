---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión de la imagen de la infraestructura de {{site.data.keyword.Bluemix_notm}}

<table summary="Mandatos de infraestructura generales de {{site.data.keyword.Bluemix_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. Mandatos image de la infraestructura de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Mandatos image de la infraestructura de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl image delete
{: #sl_image_delete}

Suprimir una imagen.
```
ibmcloud sl image delete IDENTIFIER
```
**Ejemplos**:
```
   ibmcloud sl image delete 12345678
```
Este mandato suprime la imagen con el ID `12345678`.

## ibmcloud sl image detail
{: #sl_image_detail}

Obtener detalles para una imagen.
```
ibmcloud sl image detail IDENTIFIER
```
**Ejemplos**:
```
 ibmcloud sl image detail 12345678
```
Este mandato obtiene los detalles para la imagen con el ID 12345678.

## ibmcloud sl image edit
{: #sl_image_edit}

Editar los detalles de una imagen.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--name</dt>
<dd>Nombre de la imagen.</dd>
<dt>--note</dt>
<dd>Nota adicional para la imagen.</dd>
<dt>--tag</dt>
<dd>Etiquetas para la imagen.</dd>
</dl>

*Ejemplos**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Este mandato edita la imagen con el ID `12345678` y establece el nombre en `ubuntu16`, la nota en `testing` y la etiqueta en `staging`.

## ibmcloud sl image list
{: #sl_image_list}

Listar todas las imágenes de su cuenta.
```
ibmcloud sl image list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--name</dt>
<dd>Filtrar en el nombre de imagen.</dd>
<dt>--public</dt>
<dd>Mostrar solo imágenes públicas.</dd>
<dt>--private</dt>
<dd>Mostrar solo imágenes privadas.</dd>
</dl>
