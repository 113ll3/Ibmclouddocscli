---

copyright:

  years: 2018


lastupdated: "2018-07-26"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos para gerenciar configurações de catálogo, de plug-ins e de faturamento
{: #ibmcloud_commands_settings}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar o catálogo, os plug-ins, o faturamento e as configurações de segurança do {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabela 1. Comandos para gerenciar as configurações de catálogo, plug-ins, faturamento e segurança do {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar o catálogo, os plug-ins, o faturamento e as configurações de segurança do {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud entrada no catálogo](cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[Update-ibmcloud entrada no catálogo](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catálogo de modelos](cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catálogo locais](cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catálogo de execução](cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[Ibmcloud tempos no catálogo](cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[Ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[Uso de conta de cobrança ibmcloud](cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[Ibmcloud billing resource-group-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[Ibmcloud billing resource-instances-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ### Ibmcloud de procura de catálogo
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

### ibmcloud catalog entry
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
Ibmcloud entrada no catálogo 'a0ef1-d3b4j0'
```

### Create-ibmcloud entrada no catálogo
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
  <dd>Objeto JSON válido contendo parâmetros de configuração específicos do catálogo, fornecido sequencialmente ou em um arquivo. Para obter uma lista de parâmetros de configuração suportados, consulte a documentação para a entrada no catálogo específica.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Crie o recurso do arquivo JSON com o ID pai `a0ef1-d3b4j0`:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

### Update-ibmcloud entrada no catálogo
{: #ibmcloud_catalog_entry_update}
Atualizar uma entrada no catálogo existente (administrador do catálogo ou editor de uma conta somente)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-c</dt>
  <dd>Objeto JSON válido contendo parâmetros de configuração específicos do catálogo, fornecido sequencialmente ou em um arquivo. Para obter uma lista de parâmetros de configuração suportados, consulte a documentação para a entrada no catálogo específica.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Atualize o recurso `j402-dnf1i` do arquivo JSON:

```
Ibmcloud catalog entry-update 'j402-dnf1i' -c
```

### Delete-entrada no catálogo ibmcloud
{: #ibmcloud_catalog_entry_delete}
Excluir uma entrada no catálogo (somente administrador do catálogo de uma conta)
```
Ibmcloud catalog entry-delete ID [ -- global ]
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
Ibmcloud catalog delete 'j402-dnf1i'
```

### Catalog entry-visibility ibmcloud
{: #ibmcloud_catalog_entry_visibility}
Obter a visibilidade de uma entrada no catálogo (administrador do catálogo de uma conta somente)

```
Ibmcloud catalog entry-visibility ID [ -- global ]
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
Ibmcloud catalog entry-visibility 'j402-dnf1i' -- global
```

### Ibmcloud catalog entry-visibility-set
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
  <dd>Objeto JSON válido contendo parâmetros de configuração específicos do catálogo, fornecido sequencialmente ou em um arquivo. Para obter uma lista de parâmetros de configuração suportados, consulte a documentação para a entrada no catálogo específica.</dd>
  <dt>--global</dt>
  <dd>Operar no escopo global</dd>
</dl>

<strong>Exemplos</strong>:

Configure a visibilidade do recurso `j402-dnf1i` no arquivo JSON:

```
Ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c
```

### Catalog service-marketplace ibmcloud
{: #ibmcloud_catalog_service_marketplace}
Listar ofertas de serviços no mercado de trabalho

```
Ibmcloud catalog service-marketplace [ -- cf ] [ -- rc ] [ -- global ]
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
Ibmcloud catalog service-marketplace -- global
```

### ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualize os modelos de modelo no {{site.data.keyword.Bluemix_notm}}.

```
Modelos do catálogo ibmcloud [ -d ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>-d (opcional)</dt>
   <dd>Se a opção <i>-d</i> for especificada, a descrição de cada modelo também será exibida. Caso contrário, somente o ID e o nome de cada modelo serão mostrados.</dd>
   </dl>

### Modelo do catálogo ibmcloud
{: #ibmcloud_catalog_template}

Visualize as informações detalhadas de um modelo de modelo especificado.

```
Modelo do catálogo ibmcloud TEMPLATE_ID
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
Catalog template ibmcloud
```

### Catalog template-run ibmcloud
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
Ibmcloud catalog template-run javaHelloWorld my-app
```

Crie um aplicativo `my-ruby-app` baseado no modelo `rubyHelloWorld`
com a rota `myrubyapp.chinabluemix.net` e a descrição `My first ruby app on
{{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Crie um aplicativo `my-python-app` baseado no modelo `pythonHelloWorld` sem início automático:

```
Ibmcloud catalog template-run pythonHelloWorld my-python-app -- no-start
```

### Locais do catálogo ibmcloud
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

### Execução de catálogo ibmcloud
{: #ibmcloud_catalog_runtime}

Visualizar os detalhes de um tempo de execução. Esse comando está disponível somente para a nuvem pública.

```
Catalog runtime RUNTIME_ID ibmcloud
```

<strong>Exemplos</strong>:

Mostrar detalhes do tempo de execução "nodejsHelloWorld":

```
catalog runtime nodejsHelloWorld
```

### Ibmcloud tempos no catálogo
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
Ibmcloud de catálogo runtimes -d
```

### Uso de conta de cobrança ibmcloud
{: #ibmcloud_billing_account_usage}

Mostrar o uso mensal da conta atual (somente administrador de conta)

```
Uso de conta de cobrança ibmcloud [-d YYYY-MM ] [ -- json ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>--json (opcional)</dt>
  <dd>Exibir o resultado de uso em formato JSON.</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar o relatório de uso e de custo da conta atual em 06/2016:

```
Ibmcloud billing account-usage -d 2016-06
```

### Billing org-usage ibmcloud
{: #ibmcloud_billing_org_usage}

Mostrar o uso mensal para uma organização (somente administrador da conta ou gerenciador de faturamento da
organização)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>ORG_NAME (necessário)</dt>
  <dd>Nome da organização.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>--json (opcional)</dt>
  <dd>Exibir o resultado de uso em formato JSON.</dd>
</dl>

### Ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostrar o uso mensal para um grupo de recursos (somente administrador de conta ou administrador de
grupo de recursos)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>GROUP_NAME (obrigatório)</dt>
  <dd>Nome do grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para o mês e a data especificados usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>--json (opcional)</dt>
  <dd>Exibir o resultado de uso em formato JSON.</dd>
</dl>

### Ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostrar o uso mensal das instâncias de recursos sob a conta atual.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
  <dt>-o ORG_NAME (opcional)</dt>
  <dd>Filtrar instâncias por organização.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filtrar instância por grupo de recursos.</dd>
  <dt>-d MONTH_DATE (opcional)</dt>
  <dd>Exibir dados para mês e data especificada usando o formato AAAA-MM. Se não especificado, o uso do mês atual será mostrado.</dd>
  <dt>--json (opcional)</dt>
  <dd>Exibir o resultado de uso em formato JSON.</dd>
</dl>

### ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Listar todos os repositórios de plug-in que estão registrados na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Pré-requisitos</strong>: Nenhum

### Plugin repo-add ibmcloud
{: #ibmcloud_plugin_repo_add}

Incluir um novo repositório de plug-in na CLI do {{site.data.keyword.Bluemix_notm}}.

```
Ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>REPO_NAME (necessário)</dt>
   <dd>O nome do repositório a ser incluído. É possível definir seu próprio nome para cada repositório.</dd>
   <dt>REPO_URL (necessário)</dt>
   <dd>A URL do repositório a ser incluído. A URL do repositório deve conter o protocolo (por exemplo, http://plugins.ng.bluemix.net em vez de plugins.ng.bluemix.net). http://plugins.ng.bluemix.net é o repositório de plug-in oficial da CLI do {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Exemplos</strong>:

Incluir o repositório de plug-in oficial da CLI do {{site.data.keyword.Bluemix_notm}} como `bluemix-repo`:

```
Ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

### Plugin repo-remove ibmcloud
{: #ibmcloud_plugin_repo_remove}

Remover um repositório de plug-in da CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>REPO_NAME (necessário)</dt>
   <dd>O nome do repositório a ser removido.</dd>
   </dl>

<strong>Exemplos</strong>:

Remova o repositório `bluemix-repo` da CLI do {{site.data.keyword.Bluemix_notm}}:

```
Ibmcloud plugin repo-remove bluemix-repo
```

### ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Listar todos os plug-ins disponíveis em todos os repositórios incluídos ou em um repositório específico.

```
Ibmcloud plugin repo-plugins [-r REPO_NAME ]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>Liste somente os plug-ins no repositório especificado.</dd>
   </dl>

<strong>Exemplos</strong>:

Liste todos os plug-ins em todos os repositórios incluídos:

```
ibmcloud plugin repo-plugins
```

Listar todos os plug-ins no repositório `bluemix-repo`:

```
Ibmcloud plugin repo-plugins -r bluemix-repo
```

### Plugin ibmcloud
{: #ibmcloud_plugin_repo_plugin}

Mostrar os detalhes de um plug-in no repositório.

```
Plugin ibmcloud PLUGIN_NAME [-r REPO_NAME ]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>O nome do repositório. Se nenhum repositório for especificado, o comando usará o plug-in padrão repository.å</dd>
   </dl>

<strong>Exemplos</strong>:

Listar detalhes do plug-in "IBM-Containers" no repositório "sample-repo":

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Listar detalhes do plug-in "IBM-Containers" no repositório padrão

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

### ibmcloud plugin list
{: #ibmcloud_plugin_list}

Listar todos os plug-ins instalados na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Pré-requisitos</strong>: Nenhum

### Ibmcloud plugin show
{: #ibmcloud_plugin_show}

Mostrar detalhes de um plug-in instalado.

```
Ibmcloud plugin show PLUGIN-NAME
```

<strong>Pré-requisitos</strong>: Nenhum

### Plugin install ibmcloud
{: #ibmcloud_plugin_install}

Instalar a versão específica de plug-in na CLI do {{site.data.keyword.Bluemix_notm}} por meio do caminho ou do repositório especificado.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Se nenhum repositório for especificado, o comando usará o repositório de plug-in padrão 'Bluemix'.
Se nenhuma versão for especificada, o comando selecionará a versão mais recente disponível para instalação.

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (obrigatório)</dt>
   <dd>Se -r <i>REPO_NAME</i> não for especificado, o plug-in será instalado por meio do caminho local ou da URL remota especificada.</dd>
   <dt>-r <i>REPO_NAME</i> (opcional)</dt>
   <dd>O nome do repositório no qual o binário do plug-in está localizado. Se nenhum repositório for especificado, o comando usará o repositório de plug-in padrão 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (opcional)</dt>
   <dd>A versão do plug-in a ser instalado. Se não fornecida, a versão mais recente do plug-in será instalada. Essa opção é válida somente quando você instala o plug-in por meio do repositório.</dd>
   <dt>-f </dt>
   <dd>Forçar instalação do plug-in sem confirmação.</dd>
    </dl>


A CLI do {{site.data.keyword.Bluemix_notm}} tem o nome oficial do repositório de
`Bluemix`.

<strong>Exemplos</strong>:

Instalar um plug-in por meio do arquivo local:

```
ibmcloud plugin install /downloads/new_plugin
```

Instalar um plug-in por meio da URL remota:

```
Ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Instalar o plug-in 'container-service' da versão mais recente por meio do repositório 'Bluemix':

```
Ibmcloud plugin install container-service -r Bluemix
```

ou apenas:

```
Ibmcloud plugin install container-service
```

Instalar o plug-in 'container-service' com a versão '0.1.425' por meio do repositório de plug-in oficial:

```
Ibmcloud plugin install container-service -v 0.1.425
```

### ibmcloud plugin update
{: #ibmcloud_plugin_update}

Fazer upgrade do plug-in por meio de um repositório.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Se nenhum repositório for especificado, o comando usará o repositório de plug-in padrão 'Bluemix'.
Se nenhuma versão for especificada, o comando selecionará a versão mais recente disponível para instalação.

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nome do plug-in a ser atualizado. Se não especificado, o comando verificará os upgrades de todos os plug-ins instalados.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>O nome do repositório no qual o binário do plug-in está localizado. Se não especificado, o comando usará
o repositório de plug-in padrão 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (opcional)</dt>
 <dd>A versão para a qual o plug-in será atualizado. Se não fornecida, atualize o plug-in para a versão mais recente disponível.</dd>
 <dt>--all</dt>
 <dd>Atualizar todos os plug-ins disponíveis</dd>
</dl>

<strong>Exemplos</strong>:

Procurar por todos os upgrades disponíveis no repositório de plug-in oficial 'Bluemix':

```
Ibmcloud plugin update -r Bluemix
```

ou apenas:

```
ibmcloud plugin update
```

Plug-in de upgrade 'container-service' no repositório de plug-in oficial para o mais recente:

```
Ibmcloud plugin update container-service
```

Atualizar o plug-in 'container-service' no repositório de plug-in oficial para a versão '0.1.440':

```
Ibmcloud plugin update container-service -v 0.1.440
```

### Ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Desinstalar o plug-in especificado da CLI do {{site.data.keyword.Bluemix_notm}}.

```
Plugin uninstall ibmcloud
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>PLUGIN_NAME (necessário)</dt>
   <dd>O nome do plug-in a ser desinstalado.</dd>
    </dl>

<strong>Exemplos</strong>:

Desinstalar o plug-in 'container-service' que foi instalado anteriormente:

```
Ibmcloud plugin uninstall container-service
```
