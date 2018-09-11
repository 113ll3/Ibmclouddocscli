---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} Infra-estrutura IP Global

Use os comandos a seguir para gerenciar um IP global no serviço IP global de infraestrutura do {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

<table summary="Comandos de IP global de infraestrutura do {{site.data.keyword.Bluemix_notm}} ordenados alfabeticamente com os links para as informações adicionais do comando">
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_assign)</td>
  <td>[Sl globalip cancel ibmcloud](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[Ibmcloud sl globalip create](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_create)</td>
 <td>[Sl globalip list ibmcloud](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_list)</td>
 <td>[Sl globalip unassign ibmcloud](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl globalip assign
{: #sl_globalip_assign}

Designar um IP global a um roteador ou dispositivo de destino.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Exemplos**:
```
Ibmcloud sl globalip assign 12345678 9.111.123.456
```
Esse comando designa um endereço IP com ID 12345678 a um dispositivo de destino cujo endereço IP é 9.111.123.456.

## Sl globalip cancel ibmcloud
{: #sl_globalip_cancel}

Cancelar um IP global.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Ibmcloud sl globalip cancel 12345678
```
Esse comando cancela o endereço IP com ID 12345678.

 ## Ibmcloud sl globalip create
{: #sl_globalip_create}

Criar um IP global.
```
Ibmcloud sl globalip create [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--v6</dt>
<dd>Pedir um endereço IP IPv6.</dd>
<dt>--test</dt>
<dd>Testar a ordem.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

**Exemplos**:
```
Sl globalip create ibmcloud -- v6
```
Esse comando cria um endereço IP V6.

## Sl globalip list ibmcloud
{: #sl_globalip_list}

Listar todos os IPs globais em sua conta.
```
Sl globalip list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--v4</dt>
<dd>Exibir apenas o Protocolo da Internet versão 4.</dd>
<dt>--v6</dt>
<dd>Exibir apenas o Protocolo da Internet versão 6.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem que comprou esse endereço IP.</dd>
</dl>

**Exemplos**:
```
Sl globalip list ibmcloud -- v4
```
Esse comando lista todos os endereços IP V4 na conta atual.

## Sl globalip unassign ibmcloud
{: #sl_globalip_unassign}

Remover designação de um IP global de um roteador ou dispositivo de destino.
```
Ibmcloud sl globalip unassign IDENTIFIER
```


**Exemplos**:
```
Ibmcloud sl globalip unassign 12345678
```
Esse comando remove a designação do endereço IP com ID 12345678 do dispositivo de destino.
