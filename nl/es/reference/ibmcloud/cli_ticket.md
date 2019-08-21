---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestión de incidencias de la infraestructura clásica
{: #manage-sl-tickets}

Utilice los mandatos siguientes para gestionar las incidencias de la infraestructura clásica de {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

Para adjuntar dispositivos a una incidencia:
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--hardware</dt>
<dd>El identificador del hardware a adjuntar.</dd>
<dt>--virtual</dt>
<dd>El identificar de un servidor virtual a adjuntar.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

Para crear una incidencia de soporte:
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--attachment</dt>
<dd>Número de ID del objeto inicial a adjuntar a la incidencia.</dd>
<dt>--rootpwd</dt>
<dd>Contraseña raíz asociada con el ID de dispositivo adjunto.</dd>
<dt>--subject-id</dt>
<dd>Obligatorio. ID del asunto que se va a utilizar para la incidencia; emita `ibmcloudsl ticket subjects` para obtener la lista.</dd>
<dt>--title</dt>
<dd>Obligatorio. El título de la incidencia.</dd>
<dt>--body</dt>
<dd>Cuerpo de la incidencia.</dd>
<dt>--priority</dt>
<dd>Prioridad de la incidencia [1|2|3|4], entre 1 (Crítica) a 4 (Impacto mínimo). Solo es configurable con el soporte avanzado y premium. Consulte https://www.ibm.com/cloud/support.</dd>
<dt>--attachment-type</dt>
<dd>Especifica el tipo de adjunto: hardware o virtual. El valor predeterminado es hardware.</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

Para quitar dispositivos de una incidencia:
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--hardware</dt>
<dd>El identificador del hardware que se va a quitar.</dd>
<dt>--virtual</dt>
<dd>El identificar del servidor virtual que se va a quitar.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

Para ver los detalles de la incidencia:
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--count</dt>
<dd>Número de actualizaciones.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

Para mostrar la lista de incidencias:
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--open</dt>
<dd>Mostrar solo las incidencias abiertas.</dd>
<dt>--closed</dt>
<dd>Mostrar solo las incidencias cerradas.</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

Para ver una lista de ID de asunto para la creación de incidencias:
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

Para ver información de resumen sobre las incidencias:
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

Para añadir una actualización a una incidencia existente:
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**Ejemplos**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

Para añadir un archivo adjunto a una incidencia existente:
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--name</dt>
<dd>El nombre del archivo adjunto que aparece en la incidencia.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

