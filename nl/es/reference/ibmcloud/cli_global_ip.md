---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl globalip, globalip, global ip addresses, assign global ip

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión de IP globales
{: #sl-manage-global-ip}

Una dirección IP global es una subred secundaria estática especializada. Se le entrega como una subred /32 (en otras palabras, una dirección IP única) que se puede direccionar a cualquier otra dirección IP de su cuenta.

Utilice los mandatos siguientes para gestionar una IP global en el servicio de IP global de la infraestructura clásica de {{site.data.keyword.Bluemix}}.
{: shortdesc}

## ibmcloud sl globalip assign
{: #sl_globalip_assign}

Asignar una IP global a un direccionador de destino o dispositivo.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```

**Ejemplos**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```

Este mandato asigna la dirección IP con el ID `12345678` a un dispositivo de destino cuya dirección IP es `9.111.123.456`.

## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Cancelar una IP global.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl globalip cancel 12345678
```

Este mandato cancela la dirección IP con el ID `12345678`.

 ## ibmcloud sl globalip create
{: #sl_globalip_create}

Crear una IP global.
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--v6</dt>
<dd>Solicitar una dirección IP IPv6.</dd>
<dt>--test</dt>
<dd>Pedido de prueba.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl globalip create --v6
```

Este mandato crea una dirección IP V6.

## ibmcloud sl globalip list
{: #sl_globalip_list}

Listar todas las IP globales de su cuenta.
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--v4</dt>
<dd>Mostrar solo IPv4.</dd>
<dt>--v6</dt>
<dd>Mostrar solo IPv6.</dd>
<dt>--order</dt>
<dd>Filtrar por el ID del pedido que ha comprado esta dirección IP.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl globalip list --v4
```

Este mandato lista todas las direcciones IP V4 en la cuenta actual.

## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Desasignar una IP global de un direccionador de destino o dispositivo.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**Ejemplos**:
```
ibmcloud sl globalip unassign 12345678
```

Este mandato desasigna la dirección IP con el ID `12345678` del dispositivo de destino.
