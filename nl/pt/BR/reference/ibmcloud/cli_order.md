---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, orders, quotes, ibmcloud sl order, item-list, package-locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando pedidos e cotações de infraestrutura clássica
{: #sl-manage-classic-orders}

Use os comandos a seguir para gerenciar pedidos e cotações em sua infraestrutura clássica.

## ibmcloud sl order package-locations
{: #sl_order_category_list}

Listar as categorias de um pacote
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>Opções de comando</strong>:
<dl>
<dt>--required</dt>
<dd>Listar somente as categorias requeridas para o pacote</dd>
</dl>

**Exemplos**:
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
Esse comando lista as categorias de servidores Bare Metal.

## ibmcloud sl order item-list
{: #sl_order_item_list}

Listar itens de pacote usados para pedir
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Opções de comando</strong>:
<dl>
<dt>--keyword</dt>
<dd>Uma palavra (ou sequência) usada para filtrar nomes de itens</dd>
<dt>--category</dt>
<dd>Código de categoria para filtrar itens</dd>
</dl>

**Exemplos**:
```
ibmcloud sl order item-list CLOUD_SERVER
```
Este comando lista todos os itens no pacote VSI.

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

Listar data centers nos quais um pacote pode ser pedido
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

Fazer ou verificar um pedido
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--preset</dt>
<dd>A pré-configuração do pedido (se requerido pelo pacote)</dd>
<dt>--verify</dt>
<dd>Sinalização denotando se o pedido deve ou não ser somente verificado, não feito</dd>
<dt>--billing</dt>
<dd>Taxa de faturamento [de hora em hora|mensalmente], [padrão: de hora em hora]</dd>
<dt>--complex-type</dt>
<dd>O tipo complexo do pedido. Geralmente inicia com 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Sequência JSON denotando dados extras que precisam ser enviados com o pedido</dd>
<dt>-f, --force</dt>
<dd>Forçar operação sem confirmação</dd>
</dl>

**Exemplos**:
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
Esse comando pede um VSI por hora com 4 CPU, 16 GB de RAM, 100 GB de disco SAN, Ubuntu 16.04 e 1 Gbps de uplink público e privado no dal13

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Fazer uma cotação
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--preset</dt>
<dd>A pré-configuração do pedido (se requerido pelo pacote)</dd>
<dt>--verify</dt>
<dd>Sinalização denotando se o pedido deve ou não ser somente verificado, não feito</dd>
<dt>--billing</dt>
<dd>Taxa de faturamento [de hora em hora|mensalmente], [padrão: de hora em hora]</dd>
<dt>--complex-type</dt>
<dd>O tipo complexo do pedido. Geralmente inicia com 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Sequência JSON denotando dados extras que precisam ser enviados com o pedido</dd>
<dt>-f, --force</dt>
<dd>Forçar operação sem confirmação</dd>
</dl>

**Exemplos**:
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
Esse comando solicita uma cotação de VSI com 4 CPU, 16 GB de RAM, 100 GB de disco SAN, Ubuntu 16.04 e 1 Gbps de uplink público e privado no dal13

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

Listar pré-configurações do pacote
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Opções de comando</strong>:
<dl>
<dt>--keyword</dt>
<dd>Uma palavra (ou sequência) usada para filtrar nomes de itens</dd>
</dl>

**Exemplos**:
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
Esse comando lista as pré-configurações para servidores Bare Metal
