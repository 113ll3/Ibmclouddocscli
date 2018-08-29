---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando a sub-rede de infraestrutura do {{site.data.keyword.Bluemix_notm}}

<table summary="Comandos de infraestrutura geral do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com links que trazem mais informações do comando">
<caption>Tabela 1. {{site.data.keyword.Bluemix_notm}} comandos de sub-rede de infraestrutura</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} comandos de sub-rede de infraestrutura</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[Ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[Sl subnet detail ibmcloud](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[Sl subnet list ibmcloud](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[Sl subnet lookup ibmcloud](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Cancelar uma sub-rede.
```
Ibmcloud sl subnet cancel IDENTIFIER [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl subnet cancel 12345678 -f
```
Esse comando cancela a sub-rede com ID 12345678 sem solicitar confirmação.

## Ibmcloud sl subnet create
{: #sl_subnet_create}

Inclua uma nova sub-rede em sua conta.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>Pedir endereços IPv6.</dd>
<dt>--test</dt>
<dd>Não pedir a sub-rede; obter apenas uma cota.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl subnet create public 16 567
```
Esse comando cria uma sub-rede pública com 16 endereços IP v4 e a coloca na vlan com ID 567.

## Sl subnet detail ibmcloud
{: #sl_subnet_detail}

Obter detalhes de uma sub-rede.
```
Sl subnet detail IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--no-vs</dt>
<dd>Ocultar listagem de servidor virtual.</dd>
<dt>--no-hardware</dt>
<dd>Ocultar listagem de hardware.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl subnet detail 12345678
```
Esse comando mostra informações detalhadas sobre a sub-rede com ID 12345678, incluindo informações de servidores virtuais e de hardware.

## Sl subnet list ibmcloud
{: #sl_subnet_list}

Listar todas as sub-redes em sua conta.
```
Sl subnet list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar. As opções são: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>--identifier</dt>
<dd>Filtrar pelo identificador de rede.</dd>
<dt>-t, --subnet-type</dt>
<dd>Filtrar pelo tipo de sub-rede.</dd>
<dt>--network-space</dt>
<dd>Filtrar pelo espaço de rede.</dd>
<dt>--v4, --ipv4</dt>
<dd>Exibir somente sub-redes IPv4.</dd>
<dt>--v6, --ipv6</dt>
<dd>Exibir somente sub-redes IPv6.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou as sub-redes.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Esse comando lista sub-redes IP V4 na conta atual filtrando pelo data center dal09, tipo de sub-rede PRIMARY e espaço de rede PUBLIC.

## Sl subnet lookup ibmcloud
{: #sl_subnet_lookup}

Localizar um endereço IP e exibir suas informações de sub-rede e dispositivo.
```
Ibmcloud sl subnet lookup IP_ADDRESS
```


**Exemplos**:
```
Ibmcloud sl subnet lookup 9.125.235.255
```
Esse comando localiza o registro de endereço IP com endereço 9.125.235.255 e exibe suas informações sobre a sub-rede e o dispositivo.
