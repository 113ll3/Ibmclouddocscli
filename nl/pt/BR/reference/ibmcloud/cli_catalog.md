---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-19"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Procurando e gerenciando ofertas de catálogo
{: #ibmcloud_catalog}

Use os comandos a seguir para gerenciar as entradas do catálogo, modelos de consulta, tempos de execução e geolocalizações de data centers do {{site.data.keyword.cloud}}.
{: shortdesc}
  
## Ibmcloud de procura de catálogo
{: #ibmcloud_catalog_search}

Entradas no catálogo de procura:
```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Especificar a região geográfica na qual procurar. Atualmente, somente "us-south" e "united-kingdom" são suportados</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrar por meio do tipo de recursos. Atualmente, somente "service-cf", "iaas", "tempo de execução", "modelo" e "painel" são suportados</dd>
  <dt>-p, --price</dt>
  <dd>Filtrar pelo preço. Atualmente, somente "grátis", "pré-pago", "ibmcloud-subscription" são suportados</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrar pela tag.</dd>
  <dt>--sort-by</dt>
  <dd>Propriedade pela qual classificar</dd>
  <dt>--col</dt>
  <dd>Especificar colunas adicionais para a tabela. Atualmente, "group", "provider", e "tags"</dd>
  <dt>--reverse</dt>
  <dd>Se a ordem de classificação deve ser revertida</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especificar TYPE de saída, somente JSON é suportado agora. Essa opção é exclusiva com '--id'.</dd>
  <dt>--csv</dt>
  <dd>Arquivo CSV de saída</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Procure o serviço `Automation test`:
```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Obter uma entrada no catálogo:
```
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--children</dt>
  <dd>Obter todos os filhos da entrada no catálogo</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especificar TYPE de saída, somente JSON é suportado agora.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Obtenha a entrada com ID `a0ef1-d3b4j0`:
```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}

Criar uma entrada no catálogo (somente administrador do catálogo de uma conta):
```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>ID-pai do objeto</dd>
  <dt>-c</dt>
  <dd>Objeto JSON válido contendo parâmetros de configuração específicos do catálogo, fornecido sequencialmente ou em um arquivo. Para obter uma lista de parâmetros de configuração suportados, veja a documentação para a entrada no catálogo específica.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Criar o recurso do arquivo JSON com o ID pai `a0ef1-d3b4j0`:
```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}

Atualize uma entrada no catálogo existente (administrador de catálogo ou editor de uma conta apenas):
```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-c</dt>
  <dd>Objeto JSON válido contendo parâmetros de configuração específicos do catálogo, fornecido sequencialmente ou em um arquivo. Para obter uma lista de parâmetros de configuração suportados, veja a documentação para a entrada no catálogo específica.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Atualizar o recurso `j402-dnf1i` do arquivo JSON:
```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Excluir uma entrada no catálogo (somente administrador do catálogo de uma conta)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Excluir o recurso `j402-dnf1i`:
```
ibmcloud catalog delete `j402-dnf1i`
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

Obter a visibilidade de uma entrada no catálogo (administrador do catálogo de uma conta somente)
```
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-json</dt>
  <dd>Resposta JSON original da saída</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especificar TYPE de saída, somente JSON é suportado agora.</dd>
  <dt>-global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Obtenha visibilidade do recurso `j402-dnf1i` no escopo global:
```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}

Atualize a visibilidade de uma entrada no catálogo existente (administrador de catálogo de uma conta apenas):
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Incluindo uma conta (ou lista de contas separadas por vírgula) na lista de inclusões, concedendo visibilidade para a entrada. GUIDs de e-mail ou conta são aceitáveis.</dd>
  <dt>--includes-remove</dt>
  <dd>Removendo uma conta (ou lista de contas separadas por vírgula) da lista de inclusões, revogando visibilidade para a entrada. GUIDs de e-mail ou conta são aceitáveis.</dd>  
  <dt>--excludes-add</dt>
  <dd>Incluindo uma conta (ou lista de contas separadas por vírgula) na lista de exclusões. GUIDs de e-mail ou conta são aceitáveis.</dd>
  <dt>--excludes-remove</dt>
  <dd>Removendo uma conta (ou lista de contas separadas por vírgula) da lista de exclusões, revogando visibilidade para a entrada. Se a conta foi configurada por administradores globais, os administradores de conta não poderão remover a conta. GUIDs de e-mail ou conta são aceitáveis.</dd>
  <dt>--owner</dt>
  <dd>Mudando o proprietário de um objeto. GUIDs de e-mail ou conta são aceitáveis.</dd>
  <dt>--restrict</dt>
  <dd>Mudando a restrição do objeto de visibilidade para 'Privado'.</dd>
  <dt>--unrestrict</dt>
  <dd>Mudando a restrição do objeto de visibilidade para 'Público'.</dd>  
  <dt>-c</dt>
  <dd>Objeto JSON válido contendo parâmetros de configuração específicos do catálogo, fornecido sequencialmente ou em um arquivo. Para obter uma lista de parâmetros de configuração suportados, veja a documentação para a entrada no catálogo específica.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Configure a visibilidade do recurso `j402-dnf1i` no arquivo JSON:
```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}

Listar ofertas de serviços no mercado de trabalho:
```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Mostrar serviços do Cloud Foundry somente</dd>
  <dt>--rc</dt>
  <dd>Mostrar serviços compatíveis com RC somente</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Mostre ofertas de serviço no escopo global:
```
ibmcloud catalog service-marketplace --global
```
{: codeblock}

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualize os modelos no {{site.data.keyword.cloud_notm}}.
```
ibmcloud catalog templates [-d] [--output json]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>-d (opcional)</dt>
   <dd>Se a opção <i>-d</i> for especificada, a descrição de cada modelo também será exibida. Caso contrário, somente o ID e o nome de cada modelo serão mostrados.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
   </dl>

## Modelo do catálogo ibmcloud
{: #ibmcloud_catalog_template}

Visualize as informações detalhadas de um modelo de modelo especificado.
```
ibmcloud catalog template TEMPLATE_ID [--output json]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>TEMPLATE_ID (necessário)</dt>
   <dd>O ID do modelo de modelo. Use <i>ibmcloud templates</i> para visualizar os IDs de todos os modelos.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
   </dl>


<strong>Exemplos</strong>:

Visualize detalhes do modelo `mobileBackendStarter`:
```
ibmcloud catalog template mobileBackendStarter
```
{: codeblock}

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crie um aplicativo cf que seja baseado no modelo especificado com a URL e descrição especificadas. Por padrão, o novo app é iniciado automaticamente.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
   <dl>
   <dt>TEMPLATE_ID (necessário)</dt>
   <dd>O modelo no qual o aplicativo é baseado durante a criação. Use <i>ibmcloud templates</i> para ver o ID de todos os modelos.</dd>
   <dt>CF_APP_NAME (necessário)</dt>
   <dd>O nome do aplicativo cf a ser criado.</dd>
   <dt>-n<i>HOSTNAME</i></dt>
   <dd>O nome do host do aplicativo CF. Se não especificada, a rota será configurada pelo {{site.data.keyword.cloud_notm}} automaticamente com base no nome do app e domínio padrão.</dd>
   <dt>-d<i>DOMAINNAME</i></dt>
   <dd>O domínio do aplicativo CF. Se não especificada, a rota será configurada pelo {{site.data.keyword.cloud_notm}} automaticamente com base no nome do app e domínio padrão.</dd>
   <dt>--desc <i>DESCRIPTION</i> (opcional)</dt>
   <dd>Descrição do aplicativo.</dd>
   <dt>--no-start (opcional)</dt>
   <dd>Não iniciar o aplicativo automaticamente após a criação. Se não especificado, o aplicativo será iniciado automaticamente após a criação.</dd>
   </dl>


<strong>Exemplos</strong>:

Crie um app `cf` denominado `my-app` com base em um modelo `javaHelloWorld`:
```
ibmcloud catalog template-run javaHelloWorld my-app
```
{: codeblock}

Crie um app `my-ruby-app` com base no modelo `rubyHelloWorld` com uma descrição:
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```
{: codeblock}

Crie um app `my-python-app` com base no modelo `pythonHelloWorld` sem início automático:
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```
{: codeblock}

## Locais do catálogo ibmcloud
{: #ibmcloud_catalog_locations}

Obter um subconjunto de opção das regiões em sua opção de formato.
```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>Opções de comando</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Especificar geografia por ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Obter uma lista de entradas para o tipo especificado.</dd>
  <dt>--col</dt>
  <dd>Especificar colunas adicionais para a tabela. Atualmente, "group", "provider" e "tags".</dd>
  <dt>--output TYPE (opcional)</dt>
  <dd>--output value  Especificar TYPE de saída, somente JSON é suportado agora. Essa opção é exclusiva com '--id'.</dd>
  <dt>--global</dt>
  <dd>Operar em um escopo global.</dd>
  <dt>--csv</dt>
  <dd>Arquivo CSV de saída</dd>
</dl>

## Execução de catálogo ibmcloud
{: #ibmcloud_catalog_runtime}

Visualizar os detalhes de um tempo de execução. Esse comando está disponível somente para a nuvem pública.
```
ibmcloud catalog runtime RUNTIME_ID [--output json]
```

<strong>Opções de comando</strong>:
<dl>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes do tempo de execução "nodejsHelloWorld":
```
catalog runtime nodejsHelloWorld
```
{: codeblock}

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Listar todos os tempos de execução. Esse comando está disponível somente para a nuvem pública.
```
ibmcloud catalog runtimes [-d] [--output json]
```

<strong>Opções de comando</strong>:

<dl>
  <dt>-d</dt>
  <dd>Mostrar a descrição de cada tempo de execução</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Listar todos os tempos de execução juntamente com suas descrições:
```
ibmcloud catalog runtimes -d
```
{: codeblock}
