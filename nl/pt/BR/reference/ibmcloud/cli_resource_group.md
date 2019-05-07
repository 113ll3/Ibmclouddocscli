---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-22"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Trabalhando com recursos e grupos de recursos
{: #ibmcloud_commands_resource}

Um grupo de recursos é uma maneira para organizar os recursos da conta em agrupamentos customizáveis. Use os comandos a seguir para gerenciar os recursos do {{site.data.keyword.cloud}} em um grupo de recursos.
{: shortdesc}

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Listar grupos de recursos.
```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--default</dt>
  <dd>Obter o grupo padrão da conta atual.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Listar todos os grupos de recursos sob a conta destinada atualmente:
```
ibmcloud resource groups
```
{: codeblock}

Listar grupo padrão da conta destinada atualmente:
```
ibmcloud resource groups --default
```
{: codeblock}

## ibmcloud resource group
{: #ibmcloud_resource_group}

Mostrar detalhes de um grupo de recursos
```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--id</dt>
  <dd>Mostrar somente o ID</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Mostre o grupo de recursos `example-group`:
```
ibmcloud resource group example-group
```
{: codeblock}

Mostre apenas o ID do grupo de recursos `example-group`:
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Crie um grupo de recursos:
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do grupo de recursos</dd>
</dl>

<strong>Exemplos</strong>:

Crie um grupo de recursos  ` exemplo-group `:
```
ibmcloud resource group-create example-group
```
{: codeblock}

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Atualizar um grupo de recursos existente
```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do grupo de recursos de destino</dd>
  <dt>-n, --name</dt>
  <dd>Novo nome do grupo de recursos</dd>
  <dt>-q, --quota</dt>
  <dd>Nome da nova definição de cota</dd>
  <dt>-f</dt>
  <dd>Forçar atualização sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Renomeie o grupo de recursos `example-group` para `trial-group`:
```
ibmcloud resource group-update example-group -n trial-group
```
{: codeblock}

Mude a cota do grupo de recursos `example-group` para `free`:
```
ibmcloud resource group-update example-group -q free
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Listar todas as definições de cota.
```
ibmcloud resource quotas
```
{: codeblock}

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Liste todas as definições de cota:
```
ibmcloud resource quotas
```
{: codeblock}

## Cota de recurso ibmcloud
{: #ibmcloud_resource_quota}

Mostrar detalhes de uma definição de cota.
```
ibmcloud resource quota NAME
```
{: codeblock}

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome da cota</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes da cota  ` free `:
```
ibmcloud resource quota free
```
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrar uma instância de serviço do Cloud Foundry para o grupo de recursos
```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Pré-requisitos</strong>: Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_INSTANCE_NAME ou SERVICE_INSTANCE_ID (obrigatório)</dt>
  <dd>Nome ou ID da instância de serviço</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome do grupo de recursos. Essa opção é exclusiva com '--resource-group-id'. Se nenhum deles for especificado, assumirão o padrão para o grupo de recursos de destino atual.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID do grupo de recursos. Essa opção é exclusiva com '--resource-group-name'. Se nenhum deles for especificado, assumirão o padrão para o grupo de recursos de destino atual.</dd>
  <dt>-f, --force</dt>
  <dd>Migrar sem confirmação</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Listar instâncias de serviço.
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>Nome do serviço pertencente</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>Filtrar por local</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>Tipo de instâncias. O tipo `service_instance` é usado, se não especificado; usar all para listar todos os tipos de instâncias.</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--long</dt>
  <dd>Mostrar campos adicionais na saída</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora. </dd>
</dl>

<strong>Exemplos</strong>:

Liste instâncias de serviço do serviço `test-service`:
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostrar detalhes de uma instância de serviço.

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (obrigatório), exclusivo com ID</dt>
  <dd>Nome da instância de serviço</dd>
  <dt>ID (obrigatório), exclusivo com NAME</dt>
  <dd>ID da instância de serviço</dd>
  <dt>--location</dt>
  <dd>Filtrar por local</dd>
  <dt>--id</dt>
  <dd>Exibir o ID da instância de serviço</dd>
  <dt>--output</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Essa opção é exclusiva com '--id'.</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes de serviço da instância `my-service-instance`:
```
ibmcloud resource service-instance my-service-instance
```
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Crie uma instância de serviço.
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome da instância de serviço</dd>
  <dt>SERVICE_NAME ou SERVICE_ID (necessário)</dt>
  <dd>Nome ou ID do serviço. Para listar ofertas de serviços, use o comando `ibmcloud catalog service-marketplace`[](/docs/cli/reference/ibmcloud/cli_catalog.html#ibmcloud_catalog_service_marketplace).</dd>
  <dt>SERVICE_PLAN_NAME ou SERVICE_PLAN_ID (necessário)</dt>
  <dd>Nome ou ID do plano de serviço</dd>
  <dt>LOCATION (necessário)</dt>
  <dd>Local ou ambiente de destino para criar a instância de serviço</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>Nome da implementação</dd>
  <dt>-p, --parameters <i>@JSONFILE ou JSON_STRING</i></dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros para criar a instância de serviço</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Tipos de terminais em serviço</dd>
</dl>

<strong>Exemplos</strong>:

Crie uma instância de serviço que seja denominada `my-service-instance` usando o plano de serviço `test-service-plan` do serviço `test-service` no local `eu-gb`:
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Atualizar instância de serviço.
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>Nome (obrigatório)</dt>
  <dd>Nome da instância de serviço, exclusivo com ID</dd>
  <dt>ID (obrigatório)</dt>
  <dd>ID da instância de serviço, exclusivo com NAME</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>Novo nome da instância de serviço</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>Novo ID do plano de serviço</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros para criar a instância de serviço</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Tipos de terminais em serviço</dd>
  <dt>-f, --force</dt>
  <dd>Forçar atualização sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Atualize a instância de serviço `my-service-instance`, mude o seu nome para `new-service-instance`:
```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Excluir instância de serviço.
```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>Nome (obrigatório)</dt>
  <dd>Nome da instância de serviço, exclusivo com ID</dd>
  <dt>ID (obrigatório)</dt>
  <dd>ID da instância de serviço, exclusivo com NAME</dd>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
  <dt>--recursive</dt>
  <dd>Excluir todos os recursos pertencentes</dd>
</dl>

<strong>Exemplos</strong>:

Excluir instância de serviço de recurso-instância  ` my-service-instance `:
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## As ligações de serviço do recurso ibmcloud
{: #ibmcloud_resource_service_bindings}

Mostrar ligações para o alias de serviço.
```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ALIAS (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Mostre ligações de recursos para o alias de serviço `my-service-alias`:
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Mostre detalhes de uma ligação de serviços.
```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>APP_NAME</dt>
  <dd>Nome do aplicativo CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Exibir somente o ID. Todas as outras saídas para a ligação de serviços foram suprimidas. Essa opção é exclusiva com '-- output'.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora. Essa opção é exclusiva com '--id'.</dd>
</dl>

<strong>Exemplos</strong>:

Mostre detalhes da ligação de serviços entre o alias de serviço `my-service-alias` e o app `my-app`:
```
ibmcloud resource bindings my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Crie uma ligação de serviços.
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (obrigatório)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>APP_NAME (necessário)</dt>
  <dd>Nome do aplicativo CloudFoundry</dd>
  <dt>ROLE_NAME (necessário)</dt>
  <dd>Nome da função de usuário</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Nome ou UUID do ID de serviço ao qual a função pertence</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Tipo do terminal em serviço</dd>
  <dt>-f, --force</dt>
  <dd>Forçar a criação sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Crie uma ligação de serviços entre o alias de serviço `my-service-alias` e o app `my-app` com a função `Administrator`:
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Excluir uma ligação de serviço.
```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (obrigatório)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>APP_NAME</dt>
  <dd>Nome do aplicativo CloudFoundry</dd>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:
Exclua a ligação de serviços entre o alias do serviço `my-service-alias` e o app `my-app`:
```
ibmcloud resource service-binding-delete my-service-alias my-app
```
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Liste chaves de serviço da instância de serviço ou do alias de serviço.
```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID da instância de serviço</dd>
  <dt>--instance-name</dt>
  <dd>Nome da instância de serviço</dd>
  <dt>--alias-id</dt>
  <dd>ID do alias do serviço</dd>
  <dt>--alias-name</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Liste chaves de serviço da instância de serviço `my-service-instance`:
```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Exibe os detalhes de qualquer número de chaves de serviço, em que os primeiros *n* caracteres do nome
da chave de serviço correspondem ao KEY_NAME fornecido.
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NOME</dt>
  <dd>Nome da chave</dd>
  <dt>ID</dt>
  <dd>ID da chave</dd>
  <dt>-g</dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--id</dt>
  <dd>Exibir o ID da chave de serviço. Essa opção é exclusiva com '-- output'.</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Essa opção é exclusiva com '--id'.</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes das chaves de serviço  ` my-service-key `:
```
Ibmcloud resource service-key my-service-key
```
<strong>Exemplos</strong>:
mostre detalhes da chave de serviço com ID `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79`:

```
ibmcloud resource service-key crn:v1 :bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba711589 :cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key: 9057f12e-fbf5-421d-8865-76442221722217217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Crie uma chave de serviço.
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome da chave</dd>
  <dt>ROLE_NAME (necessário)</dt>
  <dd>Nome da função de usuário</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>ID da instância de serviço</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>Nome da instância de serviço</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>ID do alias do serviço</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>Nome do alias do serviço</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Nome ou UUID do ID de serviço ao qual a função pertence</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Tipo do terminal em serviço</dd>
  <dt>-f, --force</dt>
  <dd>Forçar a criação sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Crie uma chave de serviço denominada `my-service-key` com a função `Administrator` para a instância de serviço `my-service-instance`:
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Atualizar uma chave de serviço.
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME | ID</dt>
  <dd>Nome ou ID da chave</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>Novo nome da chave</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>ID do grupo de recursos ao qual a chave pertence</dd>
  <dt>-f, --force</dt>
  <dd>Forçar atualização sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Atualize uma chave de serviço denominada `my-service-key`, dê a ela um novo nome `my-service-key-2`:
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Excluir uma chave de serviço.
```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>Nome da chave ou o ID da chave</dd>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Excluir a chave de serviço `my-service-key`:
```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Listar aliases para uma instância de serviço.
```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID da instância de serviço pertencente.</dd>
  <dt>--instance-name</dt>
  <dd>Nome da instância de serviço pertencente.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora.</dd>
</dl>

<strong>Exemplos</strong>:

Liste aliases de serviço para a instância de serviço `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Mostrar detalhes de um alias de serviço.
```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>--id</dt>
  <dd>Exibir somente o ID do alias do serviço fornecido. Todas as outras saídas para o alias são suprimidas. Essa opção é exclusiva com '-- output'.</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>--output value  Especificar o formato de saída, somente JSON é suportado agora. Essa opção é exclusiva com '--id'.</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes do alias de serviço  ` my-service-alias `:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Crie um alias de uma instância de serviço.
```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>--instance-id</dt>
  <dd>ID da instância de serviço pertencente.</dd>
  <dt>--instance-name</dt>
  <dd>Nome da instância de serviço pertencente.</dd>
  <dt>-s</dt>
  <dd>Nome do espaço em que o alias foi criado. O padrão é o espaço atual.</dd>
  <dt>-t, --tags</dt>
  <dd>Lista de marcações.</dd>
  <dt>-p, --parameters</dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros.</dd>
</dl>

<strong>Exemplos</strong>:

Crie um alias de serviço denominado `my-service-alias` da instância de serviço `my-service-instance`:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Atualize um alias de serviço.
```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>-n, --name</dt>
  <dd>Novo nome do alias do serviço.</dd>
  <dt>-t, --tags</dt>
  <dd>Lista de marcações.</dd>
  <dt>-p, --parameters</dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros.</dd>
  <dt>-f, --force</dt>
  <dd>Forçar atualização sem confirmação do usuário.</dd>
</dl>

<strong>Exemplos</strong>:

Atualize o alias de serviço `my-service-alias`, mude o seu nome para `new-service-alias`:
```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Excluir um alias de serviço.
```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Excluir alias de serviço  ` my-service-alias `:
```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}

Procure recursos usando a sintaxe de consulta do Lucene.
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Iniciando o número da posição de recursos</dd>
  <dt>-l, -limit</dt>
  <dd>Número de recursos para retorno (máximo 10.000)</dd>
  <dt>-s, -- sort-por</dt>
  <dd>Propriedade a classificar por. Entradas aceitas são `name`, `family`,
`region`, `type` e `crn`.</dd>
  <dt>-p, -- provider</dt>
  <dd>Exibir os recursos da infraestrutura clássica. O único valor permitido é: classic-infrastructure</dd>
</dl>

<strong>Atributos procuráveis</strong>:
é possível procurar os atributos a seguir:

<dl>
  <dt>Nome</dt>
  <dd>O nome definido pelo usuário do recurso.</dd>
  <dt>região</dt>
  <dd>A localização geográfica na qual o recurso é provisionado. Por exemplo: us-south, us-east, au-syd, eu-gb, eu-de e jp-tok.</dd>
  <dt>nome_do_serviço</dt>
  <dd>O nome do serviço como aparece na coluna Nome da saída de 'ibmcloud catalog service-marketplace'.</dd>
  <dt>família</dt>
  <dd>O componente de nuvem ao qual seu recurso pertence. Os valores permitidos são cloud_foundry, containers, resource_controller, vmware ou ims.</dd>
  <dt>organization_id</dt>
  <dd>O GUID da organização do Cloud Foundry.</dd>
  <dt>doc.space_id</dt>
  <dd>O GUID do espaço do Cloud Foundry.</dd>
  <dt>doc.resource_group_id</dt>
  <dd>O ID do grupo de recursos.</dd>
  <dt>type</dt>
  <dd>O tipo de recurso. Os valores permitidos são k8-cluster, cf-service-instance, cf-user-provided-service-instance, cf-organization, cf-service-binding, cf-space, cf-application, resource-instance, resource-alias, resource-binding, resource-group, vmware-solutions, cloud-objects-storage-infrastructure, block-storage, file-storage, cloud-backup.</dd>
  <dt>creation_date</dt>
  <dd>A data na qual o recurso é criado.</dd>
  <dt>modification_date</dt>
  <dd>A data da última modificação do recurso. Ele está no formato yyyy-mm-ddThh:mm:ssZ </dd>
  <dt>_objectType</dt>
  <dd>O tipo do recurso de infraestrutura clássica. Os valores permitidos são SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall e SoftLayer_Virtual_Guest. </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>A tag anexada a um recurso. Use tagReferences.tag.name ao procurar tags anexadas aos recursos de infraestrutura clássica </dd> 
</dl>

<strong>Exemplos</strong>:

Procure aplicativos do Cloud Foundry cujo nome inicia com um texto especificado:
```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Procurar por instâncias de serviço do Cloud Foundry do nome do serviço especificado:
```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Procurar por ligações de serviço do Cloud Foundry na organização com o ID especificado:
```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Procurar por espaços do Cloud Foundry com o nome especificado e localizado em uma das duas regiões
especificadas:
```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Procurar por recursos cujo nome contenha a palavra dev no espaço do Cloud Foundry com o ID especificado:
```
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Procurar por recursos do Resource Controller no local especificado (ou seja, na região us-south):
```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Procurar por recursos ou aliases no grupo de recursos com o ID especificado:
```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Procurar por grupos de recursos com o nome padrão:
```
ibmcloud resource search 'name:default AND type:resource-group'
```

Procurar por ligações de recurso para o nome do serviço especificado:
```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Procurar por um recurso com o Cloud Resource Name (CRN) especificado:
```
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Procurar por um recurso com a tag especificada:
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

Procure o recurso de Guest virtual de infraestrutura clássica com o ID especificado (somente com infraestrutura clássica -p):
```
ibmcloud resource search 'id:12345678 _objectType:SoftLayer_Virtual_Guest'
```
{: codeblock}

Procure o recurso de Hardware de infraestrutura clássica com o nome de tag especificado (somente com infraestrutura clássica -p):
```
ibmcloud resource search 'tagReferences.tag.name:name _objectType: SoftLayer_Hardware'
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Liste todas as tags em sua conta de faturamento

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Número da posição de tag inicial</dd>
  <dt>-l, -limit</dt>
  <dd>Número de tags a serem retornadas (máximo 1.000, padrão 100)</dd>
  <dt>-p; --provider</dt> 
  <dd>Especifique a infraestrutura clássica ao procurar tags de infraestrutura clássica</dd>
  <dt>-d, --details</dt>
  <dd>Mostrar o número de recursos identificados.</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Conecte uma ou mais tags a um recurso:
```
ibmcloud resource tag-attach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>--tag-names (necessários)</dt>
  <dd>Lista separada por vírgulas de nomes de tag</dd>
  <dt>--resource-id</dt>
  <dd>O CRN do recurso ao qual as tags serão anexadas; para os recursos de infraestrutura clássica, ele é o ID do recurso. É possível obter o CRN ou o ID do recurso usando o comando 'ibmcloud resource search'.</dd>
  <dt>--resource-type</dt>
  <dd>O tipo de recurso de infraestrutura clássica ao qual as tags serão anexadas; esse parâmetro será necessário se estiver anexando uma tag a um recurso de infraestrutura clássica. Os valores possíveis para --resource-type são: SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall e SoftLayer_Virtual_Guest. </dd>
</dl>

<strong>Exemplos</strong>:

* Para anexar a tag `MyTag` a um cluster Kubernetes denominado `MyCluster`, primeiro procure pelo CRN do cluster que você gostaria de identificar:
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  Tome nota do CRN, que é uma sequência semelhante ao exemplo a seguir: 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  Para anexar a tag, execute o comando a seguir:
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* Para anexar a tag `MyTag` a um guest virtual de infraestrutura clássica denominado `MyVM`, primeiro procure o ID do guest virtual que você gostaria de identificar:
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  Anote o ID, que é uma sequência semelhante a `48373549`.

  Para anexar a tag, execute o comando a seguir:
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Desconectando uma ou mais tags de um recurso:
```
ibmcloud resource tag-detach --tag-names TAG_NAMES --resource-id RESOURCE_ID [--resource-type RESOURCE_TYPE]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>--tag-names (necessários)</dt>
  <dd>Lista separada por vírgulas de nomes de tag</dd>
  <dt>--resource-id</dt>
  <dd>O CRN do recurso do qual as tags serão desconectadas; para recursos de infraestrutura clássica, ele é o ID do recurso. É possível obter o CRN ou o ID do recurso usando o comando 'ibmcloud resource search'.</dd>
  <dt>--resource-type</dt>
  <dd>O tipo de recurso de infraestrutura clássica por meio do qual as tags serão desconectadas; esse parâmetro será necessário se estiver anexando uma tag a um recurso de infraestrutura clássica. Os valores possíveis para --resource-type são: SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall e SoftLayer_Virtual_Guest. </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Excluindo uma tag:
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>O nome da tag a ser excluída.</dd>
  <dt>-p; --provider</dt> 
  <dd>Especifique a infraestrutura clássica ao excluir uma tag de infraestrutura clássica</dd>
</dl>

Uma tag poderá ser excluída apenas se ela não estiver anexada a nenhum recurso.
