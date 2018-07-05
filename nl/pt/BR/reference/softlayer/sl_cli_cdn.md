---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos da CLI do CDN

 <table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 1. CDN de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">CDN de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_list)</td>
  <td>[Sl cdn load ibmcloud](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options
](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>
 
 ### Sl cdn cancel ibmcloud
{: #sl_cdn_cancel}

Cancelar uma conta do CDN.
```
Ibmcloud sl cdn cancel ACCOUNT_ID [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### Sl cdn detail ibmcloud
{: #sl_cdn_detail}

Detalhar uma Conta do CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### Sl cdn list ibmcloud
{: #sl_cdn_list}

Listar todas as contas do CDN.
```
Sl cdn list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Coluna pela qual classificar, as opções são: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filtrar pelo ID da ordem.</dd>
</dl>

### Sl cdn load ibmcloud
{: #sl_cdn_load}

Armazenar em cache um ou mais arquivos em todos os nós da borda.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### Ordem ibmcloud sl cdn
{: #sl_cdn_order}

Pedir uma conta do CDN.
```
Sl cdn order ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>Largura da banda do CDN, o preço 'Pagamento por uso' será usado, se não especificado.</dd>
<dt>-s, --storage</dt>
<dd>Armazenamento do CDN, o preço 'Pagamento por uso' será usado, se não especificado.</dd>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### ibmcloud sl cdn options
{: #sl_cdn_options}

Opções de largura da banda e de armazenamento para pedir a conta do CDN.
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Criar um mapeamento pull de origem.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-t, --type</dt>
<dd>O tipo de mídia para esse mapeamento (http, flash, wm...), o padrão é: http.</dd>
<dt>-c, --cname</dt>
<dd>Um CNAME opcional para anexar ao mapeamento.</dd>
</dl>

### Ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Listar mapeamentos pull de origem.
```
Ibmcloud sl cdn origin-list ACCOUNT_ID
```

### Ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Remover um mapeamento pull de origem.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>

### Sl cdn purge ibmcloud
{: #sl_cdn_purge}

Limpar arquivos em cache de todos os nós da borda.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forçar a operação sem confirmação.</dd>
</dl>
