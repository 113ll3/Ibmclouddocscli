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

# Criando, cancelando e visualizando sub-redes
{: #sl-manage-subnets}

Uma sub-rede é uma partição lógica de uma rede IP em múltiplos segmentos de rede menores. Use os comandos a seguir para gerenciar sub-redes de infraestrutura clássica do {{site.data.keyword.cloud}}.
{: shortdesc}

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
Esse comando cancela a sub-rede com o ID `12345678` sem solicitar confirmação.

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
{: codeblock}

Esse comando cria uma sub-rede pública com 16 endereços IP v4 e a coloca na vlan com o ID `567`.

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
{: codeblock}

Esse comando mostra informações detalhadas sobre a sub-rede com ID `12345678`, incluindo informações de servidores virtuais e de servidores de hardware.

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
{: codeblock}

Esse comando lista as sub-redes IP V4 na filtragem de conta atual por data center `dal09`, o tipo de sub-rede é `PRIMARY` e o espaço de rede é `PUBLIC`.

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
{: codeblock}

Esse comando localiza o registro de endereço IP com o endereço IP `9.125.235.255` e exibe as suas informações de sub-rede e de dispositivo.
