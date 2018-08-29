---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión de subredes de la infraestructura de {{site.data.keyword.Bluemix_notm}}

<table summary="Mandatos de infraestructura generales de {{site.data.keyword.Bluemix_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. Mandatos subnet de la infraestructura de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Mandatos subnet de la infraestructura de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Cancelar una subred.
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl subnet cancel 12345678 -f
```
Este mandato cancela la subred con el ID 12345678 sin solicitar confirmación.

## ibmcloud sl subnet create
{: #sl_subnet_create}

Añadir una nueva subred a su cuenta.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>Solicitar direcciones IPv6.</dd>
<dt>--test</dt>
<dd>No realizar el pedido de la subred; solo obtener un presupuesto.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl subnet create public 16 567
```
Este mandato crea una subred pública con direcciones 16 IP v4 y la coloca en la vlan con el ID 567.

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

Obtener detalles de una subred.
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--no-vs</dt>
<dd>Ocultar lista de servidores virtuales.</dd>
<dt>--no-hardware</dt>
<dd>Ocultar lista de hardware.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl subnet detail 12345678
```
Este mandato muestra información detallada sobre la subred con el ID 12345678, incluyendo información de servidores de hardware y servidores virtuales.

## ibmcloud sl subnet list
{: #sl_subnet_list}

Listar todas las subredes de su cuenta.
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--sortby</dt>
<dd>Columna para ordenar por. Las opciones son: id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por nombre abreviado de centro de datos.</dd>
<dt>--identifier</dt>
<dd>Filtrar por identificador de red.</dd>
<dt>-t, --subnet-type</dt>
<dd>Filtrar por tipo de subred.</dd>
<dt>--network-space</dt>
<dd>Filtrar por espacio de red.</dd>
<dt>--v4, --ipv4</dt>
<dd>Mostrar solo subredes IPv4.</dd>
<dt>--v6, --ipv6</dt>
<dd>Mostrar solo subredes IPv6.</dd>
<dt>--order</dt>
<dd>Filtrar por el ID del pedido que ha comprado las subredes.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Este mandato lista subredes IP V4 de la cuenta actual, filtrando por centro de datos es dal09, el tipo de subred es PRIMARY y el espacio de red es PUBLIC.

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

Buscar una dirección IP y visualizar su información de dispositivos y subredes.
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**Ejemplos**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
Este mandato encuentra el registro de dirección IP con la dirección 9.125.235.255 y muestra la información del dispositivo y la subred.
