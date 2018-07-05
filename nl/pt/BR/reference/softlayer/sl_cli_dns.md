---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos da CLI de DNS

<table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 1. Comandos DNS de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos DNS de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_import)</td>
 <td>[Ibmcloud sl dns record-add](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list
](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/softlayer/sl_cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

### Sl dns import ibmcloud
{: #sl_dns_import}

Importar uma zona com base em um arquivo de zona BIND.
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--dry-run</dt>
<dd>Não criar registros realmente.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns import ~/ibm.com.txt
```
Esse comando importa a zona e seus registros de recurso do arquivo: ~/ibm.com.txt.

### Ibmcloud sl dns record-add
{: #sl_dns_record_add}

Incluir registro de recurso em uma zona.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL (Tempo de vida) em segundos, como: 86.400, o padrão é: 7.200.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
Esse comando inclui um registro A para a zona: ibm.com, seu host é "ftp", os dados são "127.0.0.1" e ttl é 86400 segundos.

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Atualizar registros de recurso em uma zona.
```
Ibmcloud sl dns record-edit ZONE [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--by-record</dt>
<dd>Editar pelo registro do host, como www.</dd>
<dt>--by-id</dt>
<dd>Editar um registro único por seu ID.</dd>
<dt>--data</dt>
<dd>Registrar dados, como um endereço IP.</dd>
<dt>--ttl</dt>
<dd>Valor TTL em segundos, como: 86400.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Esse comando edita registros na zona: ibm.com, cujo ID é 12345678 e configura seus dados como "127.0.0.2" e ttl como 3600.

### Ibmcloud sl dns record-list
{: #sl_dns_record_list}

Listar todos os registros de recurso em uma zona.
```
Ibmcloud sl dns record-list ZONE [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--data</dt>
<dd>Filtrar por dados do registro, como um endereço IP.</dd>
<dt>--record</dt>
<dd>Filtrar pelo registro do host, como www.</dd>
<dt>--ttl</dt>
<dd>Filtrar pelo valor TTL em segundos, como: 86400.</dd>
<dt>--type</dt>
<dd>Filtrar pelo tipo de registro, como A ou CNAME.</dd>
</dl>

**Exemplos**:
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
Esse comando lista todos os registros A na zona: ibm.com, filtrados pelo host é elasticsearch e ttl é 900 segundos.

### Ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Remover registro de recurso de uma zona.
```
Ibmcloud sl dns record-remove RECORD_ID
```


**Exemplos**:
```
Ibmcloud sl dns record-remove 12345678
```
Esse comando remove o registro de recurso com ID 12345678.

### Ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Criar uma zona.
```
ibmcloud sl dns zone-create ZONE
```


**Exemplos**:
```
ibmcloud sl dns zone-create ibm.com
```
Esse comando cria uma zona chamada ibm.com.

### Ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Excluir uma zona.
```
Ibmcloud sl dns zone-delete ZONE
```


**Exemplos**:
```
ibmcloud sl dns zone-delete ibm.com
```
Esse comando exclui uma zona chamada ibm.com.

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

Listar todas as zonas em sua conta.
```
ibmcloud sl dns zone-list
```


**Exemplos**:
```
ibmcloud sl dns zone-list
```
Esse comando lista todas as zonas na conta atual.

### Ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Imprimir registros de zona e recurso no formato BIND.
```
Ibmcloud sl dns zone-print ZONE
```


**Exemplos**:
```
ibmcloud sl dns zone-print ibm.com
```
Esse comando imprime uma zona chamada ibm.com no formato BIND.
