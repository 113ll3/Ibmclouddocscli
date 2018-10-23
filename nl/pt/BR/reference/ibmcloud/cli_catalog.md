---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Catálogo
{: #ibmcloud_catalog}

Use os comandos a seguir para gerenciar as entradas do catálogo, os modelos de
consulta, os tempos de execução e as localizações geográficas dos data centers do {{site.data.keyword.Bluemix}}.
{: shortdesc}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar o catálogo do {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_catalog.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_catalog.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_catalog.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_catalog.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_catalog.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_catalog.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_catalog.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_catalog.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_catalog.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_catalog.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_catalog.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_catalog.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_catalog.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_catalog.html#ibmcloud_catalog_runtimes)</td>
</tr>
 </tbody>
 </table>
  
  ## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Procurar entradas no catálogo

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Especificar a região geográfica na qual procurar. Atualmente, apenas "us-south" e "united-kingdom" são suportados</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrar pelo tipo de recursos. Atualmente, apenas "service-cf", "iaas", "runtime", "template" e "dashboard" são suportados</dd>
  <dt>-p, --price</dt>
  <dd>Filtrar pelo preço. Atualmente, apenas "free", "paygo", "bluemix-subscription" são suportados</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrar pela tag.</dd>
  <dt>--sort-by</dt>
  <dd>Propriedade pela qual classificar</dd>
  <dt>--col</dt>
  <dd>Especificar colunas adicionais para a tabela. Atualmente "grupo", "provedor" e "tags"</dd>
  <dt>--reverse</dt>
  <dd>Se a ordem de classificação deve ser revertida</dd>
  <dt>--json</dt>
  <dd>Resposta JSON original da saída</dd>
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

Obter uma entrada no catálogo

```
ibmcloud catalog entry ID [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--children</dt>
  <dd>Obter todos os filhos da entrada no catálogo</dd>
  <dt>--json</dt>
  <dd>Resposta JSON original da saída</dd>
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
Criar uma nova entrada no catálogo (administrador do catálogo de uma conta somente)

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

Crie o recurso do arquivo JSON com o ID pai `a0ef1-d3b4j0`:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Atualizar uma entrada no catálogo existente (administrador do catálogo ou editor de uma conta somente)

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

Atualize o recurso `j402-dnf1i` do arquivo JSON:

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

Exclua o recurso `j402-dnf1i`:

```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Obter a visibilidade de uma entrada no catálogo (administrador do catálogo de uma conta somente)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-json</dt>
  <dd>Resposta JSON original da saída</dd>
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
Atualizar a visibilidade de uma entrada no catálogo existente (administrador do catálogo de uma conta somente)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Incluindo uma conta (ou lista de contas separadas por vírgula) para a lista de inclusões, concedendo visibilidade para a entrada. GUIDs de e-mail ou conta são aceitáveis</dd>
  <dt>--includes-remove</dt>
  <dd>Removendo uma conta (ou lista de contas separadas por vírgula) da lista de inclusões, revogando a visibilidade para a entrada. GUIDs de e-mail ou conta são aceitáveis</dd>  
  <dt>--excludes-add</dt>
  <dd>Incluindo uma conta (ou lista de contas separadas por vírgula) para a lista de exclusões. GUIDs de e-mail ou conta são aceitáveis</dd>
  <dt>--excludes-remove</dt>
  <dd>Removendo uma conta (ou lista de contas separadas por vírgula) da lista de exclusões, revogando a visibilidade para a entrada. Se a conta foi configurada por administradores globais, os administradores de contas não poderão remover a conta. Os GUIDs de e-mail e conta são aceitáveis</dd>
  <dt>--owner</dt>
  <dd>Mudando o proprietário de um objeto. GUIDs de e-mail ou conta são aceitáveis.</dd>
  <dt>--restrict</dt>
  <dd>Mudando a restrição do objeto de visibilidade para 'Privado'</dd>
  <dt>--unrestrict</dt>
  <dd>Mudando a restrição do objeto de visibilidade para 'Público'</dd>  
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
Listar ofertas de serviços no mercado de trabalho

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

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualize os modelos de modelo no {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>-d (opcional)</dt>
   <dd>Se a opção <i>-d</i> for especificada, a descrição de cada modelo também será exibida. Caso contrário, somente o ID e o nome de cada modelo serão mostrados.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Visualize as informações detalhadas de um modelo de modelo especificado.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>TEMPLATE_ID (necessário)</dt>
   <dd>O ID do modelo de modelo. Use <i>ibmcloud templates</i> para visualizar os IDs de todos os modelos.</dd>
   </dl>


<strong>Exemplos</strong>:

Visualize detalhes do modelo `mobileBackendStarter`:

```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crie um aplicativo cf que seja baseado no modelo especificado com a URL e descrição especificadas. Por padrão, o novo app é iniciado automaticamente.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
   <dl>
   <dt>TEMPLATE_ID (necessário)</dt>
   <dd>O modelo no qual o aplicativo será baseado quando for criado. Use <i>ibmcloud templates</i> para ver o ID de todos os modelos.</dd>
   <dt>CF_APP_NAME (necessário)</dt>
   <dd>O nome do aplicativo cf a ser criado.</dd>
   <dt>-u <i>URL</i> (opcional)</dt>
   <dd>A rota do aplicativo. Se não especificada, a rota será configurada pelo {{site.data.keyword.Bluemix_notm}} automaticamente com base no nome do app e domínio padrão.</dd>
   <dt>-d <i>DESCRIPTION</i> (opcional)</dt>
   <dd>Descrição do aplicativo.</dd>
   <dt>--no-start (opcional)</dt>
   <dd>Não inicie o aplicativo automaticamente após ele ser criado. Se não especificado, o aplicativo será iniciado automaticamente após ser criado.</dd>
   </dl>


<strong>Exemplos</strong>:

Crie um aplicativo cf `my-app` baseado no modelo `javaHelloWorld`:

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Crie um aplicativo `my-ruby-app` baseado no modelo `rubyHelloWorld`
com a rota `myrubyapp.chinabluemix.net` e a descrição `My first ruby app on
{{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Crie um aplicativo `my-python-app` baseado no modelo `pythonHelloWorld` sem início automático:

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## Locais do catálogo ibmcloud
{: #ibmcloud_catalog_locations}

Obter um subconjunto de opção das regiões em sua opção de formato.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Opções de comando</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Especificar geografia por ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Obter uma lista de entradas para o tipo especificado.</dd>
  <dt>--col</dt>
  <dd>Especificar colunas adicionais para a tabela. Atualmente "grupo", "provedor" e "tags".</dd>
  <dt>--json</dt>
  <dd>Saída da resposta JSON original.</dd>
  <dt>--global</dt>
  <dd>Operar em um escopo global.</dd>
  <dt>--csv</dt>
  <dd>Arquivo CSV de saída</dd>
</dl>

## Execução de catálogo ibmcloud
{: #ibmcloud_catalog_runtime}

Visualizar os detalhes de um tempo de execução. Esse comando está disponível somente para a nuvem pública.

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Exemplos</strong>:

Mostrar detalhes do tempo de execução "nodejsHelloWorld":

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Listar todos os tempos de execução. Esse comando está disponível somente para a nuvem pública.

```
ibmcloud catalog runtimes [-d]
```

<strong>Opções de comando</strong>:

<dl>
  <dt>-d</dt>
  <dd>Mostrar a descrição de cada tempo de execução</dd>
</dl>

<strong>Exemplos</strong>:

Listar todos os tempos de execução juntamente com suas descrições:

```
ibmcloud catalog runtimes -d
```
