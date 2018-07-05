---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos da CLI de imagem

<table summary="Comandos gerais de infraestrutura {{site.data.keyword.BluSoftlayer_notm}} em ordem alfabética que possuem links que levam você para mais informações sobre o comando">
<caption>Tabela 1. Comandos de imagem de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandos de imagem de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>
 
 ### Sl image delete ibmcloud
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

### Sl image detail ibmcloud
{: #sl_image_detail}

Obter detalhes para uma imagem.
```
Sl image detail IDENTIFIER ibmcloud
```
**Exemplos**:
```
 Ibmcloud sl image detail 12345678
```
Esse comando obtém detalhes para a imagem com ID 12345678.

### Sl image edit ibmcloud
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

### Sl image list ibmcloud
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
