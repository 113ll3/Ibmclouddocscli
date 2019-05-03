---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: content delivery network, cdn service, cdn, classic infrastructure, ibmcloud sl cdn

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Trabalhando com o serviço CDN
{: #sl-cdn-service}

O serviço do Content Delivery Network (CDN) distribui conteúdo no local em que ele é necessário. Na primeira vez em que o
conteúdo é solicitado, ele é retirado do servidor host para a rede e permanece lá para que outros usuários o acessem.

Use os comandos a seguir para gerenciar o serviço CDN da infraestrutura clássica do {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## Sl cdn cancel ibmcloud
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

## Sl cdn detail ibmcloud
{: #sl_cdn_detail}

Detalhar uma Conta do CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## Sl cdn list ibmcloud
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

## Sl cdn load ibmcloud
{: #sl_cdn_load}

Armazenar em cache um ou mais arquivos em todos os nós da borda.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## Ordem ibmcloud sl cdn
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

## ibmcloud sl cdn options
{: #sl_cdn_options}

Opções de largura da banda e de armazenamento para pedir a conta do CDN.
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
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

## Ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Listar mapeamentos pull de origem.
```
Ibmcloud sl cdn origin-list ACCOUNT_ID
```

## Ibmcloud sl cdn origin-remove
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

## Sl cdn purge ibmcloud
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
