---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic infrastructure cli, vlan cli, classic vlan cli, ibmcloud sl vlan, manage virtual network cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestión de las VLAN de la infraestructura clásica
{: #manage-classic-vlans}

Las redes de área local virtual (VLAN) son utilizadas por {{site.data.keyword.cloud}} para aislar el tráfico de difusión en las redes públicas y privadas. Las VLAN se asignan a medida que se necesitan para dar servicio a otras ofertas.

Utilice los mandatos siguientes para gestionar las VLAN de la infraestructura clásica.
{: shortdesc}

## ibmcloud sl vlan create
{: #sl_vlan_create}

Crear una nueva VLAN.
```
ibmcloud sl vlan create [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>El tipo de VLAN, ya sea pública o privada.</dd>
<dt>-r, --router</dt>
<dd>El nombre de host del direccionador.</dd>
<dt>-d, --datacenter</dt>
<dd>El nombre abreviado del centro de datos.</dd>
<dt>-n, --name</dt>
<dd>El nombre de la VLAN.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
{: codeblock}

Este mandato crea una VLAN pública situada en el centro de datos `dal09` con 16 direcciones IP y con el nombre
`myvlan`.

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Cancelar una VLAN:
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vlan cancel 12345678 -f
```
{: codeblock}

Este mandato cancela la VLAN con el ID `12345678` sin solicitar confirmación.

## ibmcloud sl vlan detail
{: #sl_vlan_detail}

Obtener detalles sobre una VLAN.
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
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
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
{: codeblock}

Este mandato muestra los detalles de la VLAN con el ID `12345678`, y no la lista de servidor virtual ni servidor de hardware.

## ibmcloud sl vlan edit
{: #sl_vlan_edit}

Editar los detalles sobre una VLAN.
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-n, --name</dt>
<dd>El nombre de la VLAN.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
{: codeblock}

Este mandato actualiza la VLAN con `ID 12345678` y le da un nombre nuevo `myvlan-rename`.

## ibmcloud sl vlan list
{: #sl_vlan_list}

Listar todas las VLAN de su cuenta.
```
ibmcloud sl vlan list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--sortby</dt>
<dd>Columna para ordenar por las siguientes opciones: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar por nombre abreviado de centro de datos.</dd>
<dt>-n, --number</dt>
<dd>Filtrar por número de VLAN.</dd>
<dt>--name</dt>
<dd>Filtrar por nombre de VLAN.</dd>
<dt>--order</dt>
<dd>Filtrar por ID del pedido que ha comprado la VLAN.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
Este mandato lista todas las VLAN de la cuenta actual filtrando por centro de datos igual a `dal09`, y los ordena por número de VLAN.

## ibmcloud sl vlan options
{: #sl_vlan_options}

Listar todas las opciones para crear VLAN.
```
ibmcloud sl vlan options
```
{: codeblock}

**Ejemplos**:
```
ibmcloud sl vlan options
```
{: codeblock}

Este mandato lista todas las opciones para crear una vlan, por ejemplo, tipo de vlan, centros de datos, tamaño de subred, direccionadores, etc.
