---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, manage subnet cli, classic infrastructure cli, subnet cli, ibmcloud sl subnet, subnet cli, newtork cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Creación, cancelación y visualización de subredes
{: #sl-manage-subnets}

Una subred es una partición lógica de una red de IP en varios segmentos de red más pequeños. Utilice los mandatos siguientes para gestionar las subredes de la infraestructura clásica de {{site.data.keyword.cloud}}.
{: shortdesc}

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
Este mandato cancela la subred con el ID `12345678` sin solicitar confirmación.

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
{: codeblock}

Este mandato crea una subred pública con direcciones 16 IP v4 y la coloca en la vlan con el ID `567`.

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
{: codeblock}

Este mandato muestra información detallada sobre la subred con el ID `12345678`, incluyendo información de servidores de hardware y servidores virtuales.

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
{: codeblock}

Este mandato lista subredes IP V4 de la cuenta actual, filtrando por centro de datos es `dal09`, el tipo de subred es `PRIMARY` y el espacio de red es `PUBLIC`.

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
{: codeblock}

Este mandato encuentra el registro de dirección IP con la dirección IP `9.125.235.255` y muestra la información del dispositivo y la subred.
