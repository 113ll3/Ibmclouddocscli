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

# Gerenciando VLANs de infraestrutura clássica
{: #manage-classic-vlans}

As redes locais virtuais (VLANs) são usadas pelo {{site.data.keyword.cloud}} para isolar o tráfego
de transmissão nas redes públicas e privadas. As VLANs são designadas conforme necessário para preencher outras ofertas.

Use os comandos a seguir para gerenciar as VLANs de infraestrutura clássica.
{: shortdesc}

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
<dt>-n, --name</dt>
<dd>O nome da VLAN.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
{: codeblock}

Esse comando cria uma vlan pública localizada no data center `dal09` com 16 endereços IP e o nome é `myvlan`.

## Sl vlan cancel ibmcloud
{: #sl_vlan_cancel}

Cancelar uma VLAN:
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
{: codeblock}

Esse comando cancela a vlan com ID `12345678` sem solicitar confirmação.

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
{: codeblock}

Esse comando mostra detalhes da vlan com ID `12345678` e não a lista do servidor virtual ou do servidor de hardware.

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
{: codeblock}

Esse comando atualiza a vlan com o `ID 12345678` e dá a ela um novo nome `myvlan-rename`.

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
Esse comando lista todas as vlans na filtragem de conta atual por data center igual a `dal09`e as classifica por número de vlan.

## ibmcloud sl vlan options
{: #sl_vlan_options}

Listar todas as opções para criar a VLAN.
```
ibmcloud sl vlan options
```
{: codeblock}

**Exemplos**:
```
ibmcloud sl vlan options
```
{: codeblock}

Esse comando lista todas as opções para criar uma vlan, por exemplo, tipo de vlan, data centers, tamanho da sub-rede, roteadores, etc.
