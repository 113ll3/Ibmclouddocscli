---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos da CLI para gerenciamento de recursos e grupos de recursos
{: #ibmcloud_commands_resource}

<table summary="Comando ibmcloud que pode ser usado para gerenciar grupos de recursos e recursos.">
  <caption>Tabela 1. Comandos para gerenciamento de recursos e grupos de recursos</caption>
  <thead>
    <th colspan="5">Comandos para gerenciar recursos e grupos de recursos</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud grupos de recursos](ic_cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud grupo de recursos](ic_cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[resource group-create](ic_cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[Update-ibmcloud grupo de recursos](ic_cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](ic_cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](ic_cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](ic_cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance
](ic_cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](ic_cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](ic_cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](ic_cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](ic_cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](ic_cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](ic_cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](ic_cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](ic_cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[Cota de recurso ibmcloud](ic_cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[Resource service-keys ibmcloud](ic_cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[Ibmcloud recurso de serviço de chave](ic_cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[Ibmcloud resource service-key-create](ic_cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[Ibmcloud resource service-key-delete](ic_cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[Service-aliases de recursos ibmcloud](ic_cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[Resource service-alias ibmcloud](ic_cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[Ibmcloud resource service-alias-create](ic_cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[Ibmcloud resource service-alias-update](ic_cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[Ibmcloud resource service-alias-delete](ic_cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[Ibmcloud recursos de procura](ic_cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[resource tags](ic_cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[recurso de identificação](ic_cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[recurso tag-create](ic_cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[recurso tag-delete](ic_cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[recurso de identificação de conexão](ic_cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[recurso tag-detach](ic_cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[recurso tag-update](ic_cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

### ibmcloud resource groups
{: #ibmcloud_resource_groups}

Listar grupos de recursos.

```
Os grupos de recursos ibmcloud [ --default ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--default</dt>
  <dd>Obter o grupo padrão da conta atual.</dd>
</dl>

<strong>Exemplos</strong>:

Listar todos os grupos de recursos sob a conta destinada atualmente:

```
ibmcloud resource groups
```

Listar grupo padrão da conta destinada atualmente:

```
Ibmcloud --default grupos de recursos
```

### ibmcloud resource group
{: #ibmcloud_resource_group}

Mostrar detalhes de um grupo de recursos

```
ibmcloud resource group NAME [--id]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do grupo de recursos</dd>
  <dt>--id</dt>
  <dd>Mostrar somente o ID</dd>
</dl>

<strong>Exemplos</strong>:

Mostre o grupo de recursos `example-group`:

```
Ibmcloud resource group example-group
```

Mostre apenas o ID do grupo de recursos `example-group`:

```
Exemplo de grupo de recursos ibmcloud-group -- id
```

### Create-ibmcloud grupo de recursos
{: #ibmcloud_resource_group_create}

Crie um grupo de recursos

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:

<strong>Exemplos</strong>:

Criar um grupo de recursos `example-group` com a cota `free`:

```
Ibmcloud resource group-create exemplo-grupo grátis
```

### Update-ibmcloud grupo de recursos
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
Ibmcloud resource group-update example-group -n trial-group
```

Mude a cota do grupo de recursos `example-group` para `free`:

```
Ibmcloud resource group-update example-group -q free
```

### ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Listar todas as definições de cota

```
ibmcloud resource quotas
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Liste todas as definições de cota:

```
ibmcloud resource quotas
```

### Cota de recurso ibmcloud
{: #ibmcloud_resource_quota}

Mostrar detalhes de uma definição de cota

```
ibmcloud resource quota NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome da cota</dd>
</dl>

<strong>Exemplos</strong>:
mostre detalhes da cota `free`:

```
Ibmcloud recurso cota grátis
```

### Ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrar uma instância de serviço Cloudfoundry no grupo de recursos

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

### ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Listar instâncias de serviço

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Nome do serviço pertencente</dd>
  <dt>--location</dt>
  <dd>Filtrar por local</dd>
  <dt>--long</dt>
  <dd>Mostrar campos adicionais na saída</dd>
</dl>

<strong>Exemplos</strong>:

Liste instâncias de serviço do serviço `test-service`:

```
Ibmcloud resource service-instances -- service-name test-service
```

### ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostrar detalhes de uma instância de serviço

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id]
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
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes de serviço da instância `my-service-instance`:

```
Ibmcloud resource service-instance my-service-instance
``` 

### Ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Criar uma instância de serviço

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome da instância de serviço</dd>
  <dt>SERVICE_NAME ou SERVICE_ID (necessário)</dt>
  <dd>Nome ou ID do serviço</dd>
  <dt>SERVICE_PLAN_NAME ou SERVICE_PLAN_ID (necessário)</dt>
  <dd>Nome ou ID do plano de serviço</dd>
  <dt>LOCALIDADE</dt>
  <dd>Local ou ambiente de destino para criar a instância de serviço</dd>
  <dt>-t, --tags</dt>
  <dd>Tags</dd>
  <dt>-p, --parameters</dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros para criar a instância de serviço</dd>
  <dt>-d, --deployment</dt>
  <dd>Nome da implementação</dd>
</dl>

<strong>Exemplos</strong>:
crie uma instância de serviço chamada `my-service-instance` usando o plano de serviço `test-service-plan` do serviço `test-service` no local `eu-gb`:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## Ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Atualizar a instância de serviço

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [-t, --tags TAGS] [--service-plan-id SERVICE_PLAN_ID] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>Nome (obrigatório)</dt>
  <dd>Nome da instância de serviço, exclusivo com ID</dd>
  <dt>ID (obrigatório)</dt>
  <dd>ID da instância de serviço, exclusivo com NAME</dd>
  <dt>-n, --name</dt>
  <dd>Novo nome da instância de serviço</dd>
  <dt>-t, --tags</dt>
  <dd>Novas tags</dd>
  <dt>--service-plan-id</dt>
  <dd>Novo ID do plano de serviço</dd>
  <dt>-f, --force</dt>
  <dd>Forçar atualização sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:
atualize a instância de serviço `my-service-instance`, mude seu nome para `new-service-instance`:

```
Ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

### Ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Excluir instância de serviço

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
Exclua a instância de serviço do recurso `my-service-instance`:

```
Ibmcloud resource service-instance-delete my-service-instance
```

### As ligações de serviço do recurso ibmcloud
{: #ibmcloud_resource_service_bindings}

Mostrar ligações para o alias do serviço

```
Ibmcloud resource service-bindings SERVICE_ALIAS
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ALIAS (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
</dl>

<strong>Exemplos</strong>:
Mostre ligações de recursos para o alias do serviço `my-service-alias`:

```
Ibmcloud resource bindings my-service-alias
```

### ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Mostrar detalhes de uma ligação de serviços

```
Ibmcloud resource service-binding ALIAS_NAME APP_NAME [ -- id ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>APP_NAME</dt>
  <dd>Nome do aplicativo CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Exibir somente o ID. Todas as outras saídas para a ligação de serviços foram suprimidas.</dd>
</dl>

<strong>Exemplos</strong>:
mostre detalhes da ligação de serviços entre o alias do serviço `my-service-alias` e o app `my-app`:

```
Ligações de recursos ibmcloud my-service-alias my-app
```

### Ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Criar uma ligação de serviços

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ALIAS_NAME (obrigatório)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>APP_NAME</dt>
  <dd>Nome do aplicativo CloudFoundry</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nome da função de usuário</dd>
  <dt>--service-id</dt>
  <dd>Nome ou UUID do ID do serviço ao qual a função pertence</dd>
  <dt>-p, --parameter</dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros</dd>
  <dt>-f, --force</dt>
  <dd>Forçar a criação sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:
crie uma ligação de serviços entre o alias do serviço `my-service-alias` e o app `my-app` com a função `Administrator`:

```
Ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

### Ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Excluir uma ligação de serviços

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
Ibmcloud resource service-binding-delete my-service-alias my-app
```

### Resource service-keys ibmcloud
{: #ibmcloud_resource_service_keys}

Listar chaves de serviço da instância de serviço ou do alias do serviço

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ]
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
</dl>

<strong>Exemplos</strong>:
liste as chaves de serviço da instância de serviço `my-service-instance`:

```
Resource service-keys ibmcloud -- instance-name my-service-instance
```

### Ibmcloud recurso de serviço de chave
{: #ibmcloud_resource_service_key}

Mostrar detalhes de uma chave de serviço

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nome da chave</dd>
  <dt>--id</dt>
  <dd>Exibir o ID da chave de serviço</dd>
</dl>

<strong>Exemplos</strong>:
mostrar detalhes das chaves de serviço `my-service-key`:

```
Ibmcloud resource service-key my-service-key
```

### Ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Criar uma chave de serviço

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NOME</dt>
  <dd>Nome da chave</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nome da função de usuário</dd>
  <dt>--instance-id</dt>
  <dd>ID da instância de serviço</dd>
  <dt>--instance-name</dt>
  <dd>Nome da instância de serviço</dd>
  <dt>--alias-id</dt>
  <dd>ID do alias do serviço</dd>
  <dt>--alias-name</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>--service-id</dt>
  <dd>Nome ou UUID do ID do serviço ao qual a função pertence</dd>
  <dt>-p, --parameters</dt>
  <dd>Arquivo JSON ou sequência JSON de parâmetros</dd>
  <dt>-f, --force</dt>
  <dd>Forçar a criação sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:
crie uma chave de serviço chamada `my-service-key` com a função `Administrator` para a instância de serviço `my-service-instance`:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## Ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Excluir uma chave de serviço

```
Ibmcloud resource service-key-delete KEY_NAME [ -f, -- forece ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nome da chave</dd>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:
exclua a chave de serviço `my-service-key`:

```
Ibmcloud resource service-key-delete my-service-key
```

### Service-aliases de recursos ibmcloud
{: #ibmcloud_resource_service_aliases}

Listar aliases para uma instância de serviço

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID da instância de serviço pertencente.</dd>
  <dt>--instance-name</dt>
  <dd>Nome da instância de serviço pertencente.</dd>
</dl>

<strong>Exemplos</strong>:
liste os aliases de serviço para a instância de serviço `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

### Resource service-alias ibmcloud
{: #ibmcloud_resource_service_alias}

Mostrar detalhes de um alias do serviço

```
Ibmcloud resource service-alias ALIAS_NAME [ -- id ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>ALIAS_NAME (necessário)</dt>
  <dd>Nome do alias do serviço</dd>
  <dt>--id</dt>
  <dd>Exibir somente o ID do alias do serviço fornecido. Todas as outras saídas para o alias são suprimidas.</dd>
</dl>

<strong>Exemplos</strong>:
mostre os detalhes do alias do serviço `my-service-alias`:
```
Ibmcloud resource service-alias my-service-alias
```

### Ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Criar um alias de uma instância de serviço

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
crie um alias de serviço chamado `my-service-alias` da instância de serviço `my-service-instance`:
```
Ibmcloud resource service-alias-create my-service-alias -- instance-name my-service-instance
```

### Ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Atualizar um alias do serviço

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
atualize o alias do serviço `my-service-alias`, mude seu nome para `new-service-alias`:

```
Ibmcloud resource service-alias-update my-service-alias -n alias-new-service
```

### Ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Excluir um alias do serviço

```
Ibmcloud resource service-alias-delete ALIAS_NAME [ -f, -- force ]
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
excluir o alias do serviço `my-service-alias`:

```
Ibmcloud resource service-alias-delete my-service-alias
```

### Ibmcloud recursos de procura
{: #ibmcloud_resource_search}
Procurar por recursos usando a sintaxe da consulta Lucene

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-offset, --o</dt>
  <dd>Iniciando o número da posição de recursos</dd>
  <dt>-limit, --l</dt>
  <dd>Número de recursos para retorno (máximo 10.000)</dd>
</dl>

<strong>Exemplos</strong>: procurar por aplicativos do Cloud Foundry cujo nome começa com um texto
especificado:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Procurar por instâncias de serviço do Cloud Foundry do nome do serviço especificado:

```
Ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Procurar por ligações de serviço do Cloud Foundry na organização com o ID especificado:

```
Ibmcloud recurso de procura 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Procurar por espaços do Cloud Foundry com o nome especificado e localizado em uma das duas regiões
especificadas:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Procurar por recursos cujo nome contenha a palavra dev no espaço do Cloud Foundry com o ID especificado:

```            
Ibmcloud resource search 'name: * dev * AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Procurar por recursos do Resource Controller no local especificado (ou seja, na região us-south):

```
Ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Procurar por recursos ou aliases no grupo de recursos com o ID especificado:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Procurar por grupos de recursos com o nome padrão:

```
Ibmcloud resource search 'name:default AND type:resource-group'
```

Procurar por ligações de recurso para o nome do serviço especificado:

```
Ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Procurar por um recurso com o Cloud Resource Name (CRN) especificado:

```
Ibmcloud recurso de procura "crn: \" crn:v1 :staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance: \""
```

Procurar por um recurso com a tag especificada:

```
Ibmcloud recurso de procura "tags: \" mykey:myvalue \""
```

### Tags de recursos ibmcloud
{: #ibmcloud_resource_tags}

Listar todas as tags

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag tipo</dt>
  <dd>Tipo de Tag (valores suportados: usuário, restrito)</dd>
  <dt>-o, -- offset</dt>
  <dd>Iniciando o número da posição de recursos (padrão: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Número de recursos a serem retornados (máximo 10000) (padrão: 10000)</dd>
</dl>

<strong>Exemplos</strong>:

Listar todas as tags

```
Tags de recursos ibmcloud 
```

Liste todas as tags restritos

```
Tags de recursos ibmcloud -- tag tipo restrito
```

### Tag de recurso ibmcloud
{: #ibmcloud_resource_tag}

Mostrar detalhes de uma tag

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>Nome da Tag, exclusivo com -- tag-crn</dd>
  <dt>-- tag-crn (obrigatório)</dt>
  <dd>Tag CRN, exclusivo com -- tag-name</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes da tag "Ray Brown"

```
Tag de recurso ibmcloud -- tag-name "Ray Brown"
```

### Create-tag de recurso ibmcloud
{: #ibmcloud_resource_tag_create}

Crie uma tag

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>Nome de tag</dd>
  <dt>-- tag tipo</dt>
  <dd>Tipo de tag (valores suportados: user, restricted; padrão: user)</dd>
</dl>

<strong>Exemplos</strong>:

Criar uma tag de usuário com o nome think:2018

```
Create-tag de recurso ibmcloud -- tag que nome: 2018
```

Criar uma tag restrita com o nome department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Criar uma tag de usuário com o nome "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Criar uma tag restrita com o nome "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

### Delete-tag de recurso ibmcloud
{: #ibmcloud_resource_tag_delete}

Excluir uma tag

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>Nome da Tag, exclusivo com -- tag-crn</dd>
  <dt>-- tag-crn (obrigatório)</dt>
  <dd>Tag CRN, exclusivo com -- tag-name</dd>
</dl>

<strong>Exemplos</strong>:

Tag Deletag "Ray Brown"

```
Delete-tag de recurso ibmcloud -- tag-name "Ray Brown"
```

### Ibmcloud recurso de tag de conexão
{: #ibmcloud_resource_tag_attach}

Inclua uma tag para um recurso

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>Nome da Tag, exclusivo com -- tag-crn</dd>
  <dt>-- tag-crn (obrigatório)</dt>
  <dd>Tag CRN, exclusivo com -- tag-name</dd>
  <dt>-- resource-crn (obrigatório)</dt>
  <dd>Recursos CRN</dd>
</dl>

<strong>Exemplos</strong>:

Incluir a tag "Ray Brown" no recurso cujo crn é resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

### Ibmcloud recurso de identificação detach
{: #ibmcloud_resource_tag_detach}

Remover uma tag de um recurso

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>Nome da Tag, exclusivo com -- tag-crn</dd>
  <dt>-- tag-crn (obrigatório)</dt>
  <dd>Tag CRN, exclusivo com -- tag-name</dd>
  <dt>-- resource-crn (obrigatório)</dt>
  <dd>Recursos CRN</dd>
</dl>

<strong>Exemplos</strong>:

Remover a tag "Ray Brown" do recurso cujo crn é resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

### Update-tag de recurso ibmcloud
{: #ibmcloud_resource_tag_update}

Alternar a tag de usuário para a tag restrita e vice-versa

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-- tag-name (necessário)</dt>
  <dd>Nome da Tag, exclusivo com -- tag-crn</dd>
  <dt>-- tag-crn (obrigatório)</dt>
  <dd>Tag CRN, exclusivo com -- tag-name</dd>
  <dt>--tag-type (obrigatório)</dt>
  <dd>Tipo de tag</dd>
</dl>

<strong>Exemplos</strong>:

Alternar a tag "Ray Brown" para a tag restrita

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
