---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl image, manage compute images, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Criando, editando e excluindo imagens de cálculo
{: #sl-manage-compute-images}

Use os comandos a seguir para gerenciar as imagens de cálculo do {{site.data.keyword.cloud}}.
{: shortdesc}

## Sl image delete ibmcloud
{: #sl_image_delete}

Excluir uma imagem.
```
Sl image delete IDENTIFIER ibmcloud
```

**Exemplos**:
```
Ibmcloud sl image delete 12345678
```

Esse comando exclui a imagem com ID `12345678`.

## Sl image detail ibmcloud
{: #sl_image_detail}

Obter detalhes para uma imagem.
```
Sl image detail IDENTIFIER ibmcloud
```

**Exemplos**:
```
 Ibmcloud sl image detail 12345678
```

Esse comando obtém detalhes para a imagem com ID `12345678`.

## Sl image edit ibmcloud
{: #sl_image_edit}

Editar detalhes de uma imagem.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--name</dt>
<dd>Nome da imagem.</dd>
<dt>--note</dt>
<dd>Nota adicional para a imagem.</dd>
<dt>--tag</dt>
<dd>Tags para a imagem.</dd>
</dl>

*Exemplos**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```

Esse comando edita a imagem com o ID `12345678` e configura seu nome para `ubuntu16`, a nota para `testing` e a tag para `staging`.

## Sl image list ibmcloud
{: #sl_image_list}

Listar todas as imagens em sua conta.
```
Sl image list ibmcloud [ OPTIONS ]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--name</dt>
<dd>Filtrar no nome da imagem.</dd>
<dt>--public</dt>
<dd>Exibir somente imagens públicas.</dd>
<dt>--private</dt>
<dd>Exibir somente imagens privadas.</dd>
</dl>
