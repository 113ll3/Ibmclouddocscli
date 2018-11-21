---

copyright:

  years: 2018


lastupdated: "2018-11-05"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Pedido

<table summary="Mandatos de infraestructura generales de {{site.data.keyword.BluSoftlayer_notm}} ordenados alfabéticamente que tienen enlaces que le proporcionan más información del mandato">
 <caption>Tabla 1. Pedidos de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Pedidos de infraestructura de {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl order package-locations](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_category_list)</td>
  <td>[ibmcloud sl order item-list](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_item_list)</td>
  <td>[ibmcloud sl order package-locations](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_package_locations)</td>
  <td>[ibmcloud sl order place](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_place)</td>
  <td>[ibmcloud sl order place-quote](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_place_quote)</td>
  <td>[ibmcloud sl order preset-list](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_preset_list)</td>
 </tr>
 </tbody>
</table>

## ibmcloud sl order package-locations
{: #sl_order_category_list}

Listar las categorías de un paquete
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--required</dt>
<dd>Listar solo las categorías obligatorias para el paquete</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
Este mandato muestra una lista de las categorías de servidores nativos.

## ibmcloud sl order item-list
{: #sl_order_item_list}

Listar los elementos del paquete utilizados para realizar el pedido
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--keyword</dt>
<dd>Una palabra (o serie) que se utiliza para filtrar nombres de elementos</dd>
<dt>--category</dt>
<dd>Código de categoría según el cual se filtrarán los elementos</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl order item-list CLOUD_SERVER
```
Este mandato muestra una lista todos los elementos del paquete VSI.

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

Listar centros de datos en los que se puede solicitar un paquete
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

Realizar o verificar un pedido
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--preset</dt>
<dd>El elemento preestablecido del pedido (si lo necesita el paquete)</dd>
<dt>--verify</dt>
<dd>Distintivo que indica si se debe o no únicamente verificar el pedido, no realizarlo</dd>
<dt>--billing</dt>
<dd>Tasa de facturación [hourly|monthly], [valor predeterminado: hourly]</dd>
<dt>--complex-type</dt>
<dd>El tipo completo del pedido. Suele comenzar por 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Serie JSON que indica datos adicionales que se deben enviar con el pedido</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
Este mandato solicita un VSI por hora con 4 CPU, 16 GB de RAM, 100 GB de disco SAN, Ubuntu 16.04, y 1 Gbps de enlace ascendente público y privado en dal13

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Colocar un presupuesto
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--preset</dt>
<dd>El elemento preestablecido del pedido (si lo necesita el paquete)</dd>
<dt>--verify</dt>
<dd>Distintivo que indica si se debe o no únicamente verificar el pedido, no realizarlo</dd>
<dt>--billing</dt>
<dd>Tasa de facturación [hourly|monthly], [valor predeterminado: hourly]</dd>
<dt>--complex-type</dt>
<dd>El tipo completo del pedido. Suele comenzar por 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Serie JSON que indica datos adicionales que se deben enviar con el pedido</dd>
<dt>-f, --force</dt>
<dd>Forzar la operación sin confirmación</dd>
</dl>

**Ejemplos**:
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
Este mandato solicita un presupuesto de un VSI con 4 CPU, 16 GB de RAM, 100 GB de disco SAN, Ubuntu 16.04, y 1 Gbps de enlace ascendente público y privado en dal13

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

Listar los elementos preestablecidos del paquete
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Opciones de mandato</strong>:
<dl>
<dt>--keyword</dt>
<dd>Una palabra (o serie) que se utiliza para filtrar nombres de elementos</dd>
</dl>

**Ejemplos**:
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
Este mandato muestra una lista los valores preestablecidos para servidores nativos
