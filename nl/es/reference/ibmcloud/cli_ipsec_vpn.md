---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, datacenter, encryption

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestión de túneles VPN de IPSec
{: #sl-manage-ipsec-vpn-tunnels}

El acceso VPN de {{site.data.keyword.cloud}} permite a los usuarios gestionar todos los servidores de forma remota y de forma segura a través de la red privada de {{site.data.keyword.cloud_notm}}. Una conexión VPN desde su ubicación a la red privada le ofrece la posibilidad de una gestión fuera de banda y de un rescate de servidor a través de un túnel VPN cifrado.

Utilice los mandatos siguientes para gestionar los túneles VPN de IPSec en el servicio de VPN de IPSec de la infraestructura clásica de {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Cancelar un contexto de túnel VPN de IPSec.
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--immediate</dt>
<dd>Cancelar la IPSec inmediatamente, en lugar de en el aniversario de facturación.</dd>
<dt>--reason</dt>
<dd>Una razón opcional para la cancelación.</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación.</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

Solicitar configuración de un contexto de túnel.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Listar detalles de contexto de túnel VPN de IPSec.
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Incluir recursos adicionales, las opciones son: at,is,rs,sr,ss.</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

Listar contextos de túnel VPN de IPSec.
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--order</dt>
<dd>Filtrar por ID del pedido que ha comprado la IPSEC.</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

Solicitar un túnel VPN de IPSec.
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Obligatorio. Nombre abreviado del centro de datos para la IPSEC, por ejemplo dal09.</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Añadir una nueva subred al contexto de túnel de IPSec.
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>Identificador de subred que se va a añadir, obligatorio.</dd>
<dt>-t, --subnet-type</dt>
<dd>Tipo de subred que se va a añadir, obligatorio, las opciones son: internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>Identificador de red de subred que se va a crear.</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Eliminar una subred del contexto de túnel de IPSEC.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Añadir una conversión de dirección a un túnel de IPSec.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Dirección IP estática, obligatoria.</dd>
<dt>-r, --remote-ip</dt>
<dd>Dirección IP remota, obligatoria.</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Eliminar una entrada de conversión de una IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Actualizar una conversión de dirección para una IPSec.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Dirección IP estática, obligatoria.</dd>
<dt>-r, --remote-ip</dt>
<dd>Dirección IP remota, obligatoria.</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

Actualizar propiedades de contexto de túnel.
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Nombre descriptivo.</dd>
<dt>-r, --remote-peer</dt>
<dd>Dirección IP igual remota.</dd>
<dt>-k, --preshared-key</dt>
<dd>Clave precompartida.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Autenticación de fase 1, las opciones son: MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Cifrado de fase 1, las opciones son: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Grupo diffie hellman de fase 1, las opciones son: 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Clave para la vida de fase 1, rango 120-172800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Autenticación de fase 2, las opciones son: MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Cifrado de fase 2, las opciones son: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Grupo diffie hellman de fase 2, las opciones son: 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>PFS de fase 2, rango 0-1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Clave para la vida de fase 2, rango 120-172800.</dd>
</dl>
