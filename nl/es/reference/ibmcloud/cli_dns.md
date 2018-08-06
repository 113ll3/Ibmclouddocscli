---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Mandatos para gestionar DNS de la infraestructura de {{site.data.keyword.Bluemix_notm}}

<table summary="Mandatos de infraestructura generales de {{site.data.keyword.Bluemix_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
<caption>Tabla 1. Mandatos DNS de la infraestructura de {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Mandatos DNS de la infraestructura de {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

### ibmcloud sl dns import
{: #sl_dns_import}

Importar una zona basada en un archivo de zona BIND.
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--dry-run</dt>
<dd>No crear realmente los registros.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl dns import ~/ibm.com.txt
```
Este mandato importa la zona y los registros de recursos del archivo : ~/ibm.com.txt.

### ibmcloud sl dns record-add
{: #sl_dns_record_add}

Añadir registro de recurso en una zona.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL (Time-To-Live) en segundos, como por ejemplo: 86400. El valor predeterminado es: 7200.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
Este mandato añade un registro A a la zona: ibm.com, su host es "ftp", los datos son "127.0.0.1" y el ttl es 86400 segundos.

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Actualizar los registros de recursos en una zona.
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--by-record</dt>
<dd>Editar por registro de host, como www.</dd>
<dt>--by-id</dt>
<dd>Editar un registro único por su ID.</dd>
<dt>--data</dt>
<dd>Registrar datos, como una dirección IP.</dd>
<dt>--ttl</dt>
<dd>Valor de TTL en segundos, como: 86400.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Este mandato edita registros de la zona: ibm.com, cuyo ID es 12345678, y establece sus datos en "127.0.0.2" y el ttl a 3600.

### ibmcloud sl dns record-list
{: #sl_dns_record_list}

Listar todos los registros de recursos en una zona.
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--data</dt>
<dd>Filtrar por datos de registro, como una dirección IP.</dd>
<dt>--record</dt>
<dd>Filtrar por registro de host, como por ejemplo www.</dd>
<dt>--ttl</dt>
<dd>Filtrar por valor de TTL en segundos, como 86400.</dd>
<dt>--type</dt>
<dd>Filtrar por tipo de registro, como A o CNAME.</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
Este mandato lista todos los registros A de la zona: ibm.com,filtrados por host es elasticsearch y el ttl es 900 segundos.

### ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Eliminar registro de recurso de una zona.
```
ibmcloud sl dns record-remove RECORD_ID
```


**Ejemplos**:
```
ibmcloud sl dns record-remove 12345678
```
Este mandato elimina el registro de recurso con el ID 12345678.

### ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Crear una zona.
```
ibmcloud sl dns zone-create ZONE
```


**Ejemplos**:
```
ibmcloud sl dns zone-create ibm.com
```
Este mandato crea una zona denominada ibm.com.

### ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Suprimir una zona.
```
ibmcloud sl dns zone-delete ZONE
```


**Ejemplos**:
```
ibmcloud sl dns zone-delete ibm.com
```
Este mandato suprime una zona denominada ibm.com.

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

Listar todas las zonas de su cuenta.
```
ibmcloud sl dns zone-list
```


**Ejemplos**:
```
ibmcloud sl dns zone-list
```
Este mandato lista todas las zonas en la cuenta actual.

### ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Imprimir registros del recurso y zona en formato BIND.
```
ibmcloud sl dns zone-print ZONE
```


**Ejemplos**:
```
ibmcloud sl dns zone-print ibm.com
```
Este mandato imprime la zona denominada ibm.com en formato BIND.
