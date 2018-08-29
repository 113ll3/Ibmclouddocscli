---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando a  {{site.data.keyword.Bluemix_notm}}  VLAN de infraestrutura

<table summary="Comandos de infraestrutura geral do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com links que trazem mais informações do comando">

<caption>Tabela 1. {{site.data.keyword.Bluemix_notm}}  comandos de VLAN de infraestrutura</caption>

 <thead>
 <th colspan="6">Comandos da VLAN de infraestrutura {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[Ibmcloud sl vlan create](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_create)</td>
 <td>[Sl vlan cancel ibmcloud](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_cancel)</td>
 <td>[Sl vlan detail ibmcloud](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_detail)</td>
 <td>[Sl vlan edit ibmcloud](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_edit)</td>
 <td>[Sl vlan list ibmcloud](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options
](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

 ## Ibmcloud sl vlan create
{: #sl_vlan_create}

Criar uma nova VLAN.
```
Sl vlan create ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>O tipo da VLAN, público ou privado.</dd>
<dt>-r, --router</dt>
<dd>O nome do host do roteador.</dd>
<dt>-d, --datacenter</dt>
<dd>O nome abreviado do data center.</dd>
<dt>-s, --size</dt>
<dd>O tamanho das sub-redes, as opções são: 8 (5 IPs utilizáveis) ou 16 (13 IPs utilizáveis) ou 32 (29 IPs utilizáveis).</dd>
<dt>-n, --name</dt>
<dd>O nome da VLAN.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Esse comando cria uma vlan pública localizada no data center dal09 com 16 endereços IP e o nome é myvlan.

## Sl vlan cancel ibmcloud
{: #sl_vlan_cancel}

Cancelar uma VLAN.
```
Sl vlan cancel IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl vlan cancel 12345678 -f
```
Esse comando cancela a vlan com ID 12345678 sem solicitar confirmação.

## Sl vlan detail ibmcloud
{: #sl_vlan_detail}

Obter detalhes sobre uma VLAN.
```
Sl vlan detail IDENTIFIER ibmcloud [ OPTIONS ]
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
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
Esse comando mostra detalhes da vlan com ID 12345678 e não lista o servidor virtual ou o servidor de hardware.

## Sl vlan edit ibmcloud
{: #sl_vlan_edit}

Editar os detalhes sobre uma VLAN.
```
Sl vlan edit IDENTIFIER ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>O nome da VLAN.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
Esse comando atualiza a vlan com ID 12345678 e fornece um novo nome a ela "myvlan-rename".

## Sl vlan list ibmcloud
{: #sl_vlan_list}

Listar todas as VLANs em sua conta.
```
Sl vlan list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtrar pelo nome abreviado do data center.</dd>
<dt>-n, --number</dt>
<dd>Filtrar pelo número da VLAN.</dd>
<dt>--name</dt>
<dd>Filtrar pelo nome da VLAN.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou a VLAN.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
Esse comando lista todas as vlans na conta atual, a filtragem por data center é igual a dal09 e a classificação é pelo número da vlan.

## ibmcloud sl vlan options
{: #sl_vlan_options}

Listar todas as opções para criar a VLAN.
```
ibmcloud sl vlan options
```


**Exemplos**:
```
ibmcloud sl vlan options
```
Esse comando lista todas as opções para criar uma vlan, por exemplo, tipo de vlan, data centers, tamanho da sub-rede, roteadores, etc.
