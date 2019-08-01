---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando a empresa, grupos de contas e contas
{: #ibmcloud_enterprise}

Use os comandos a seguir para gerenciar a empresa, grupos de contas e contas.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

Criar uma empresa.
```
ibmcloud enterprise create NAME [-d, --domain DOMAIN_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da empresa.</dd>
<dt>-d, --domain DOMAIN_NAME (opcional)</dt>
<dd>Nome de domínio.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (opcional)</dt>
<dd>O ID de usuário do contato principal da empresa.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

Atualizar informações da empresa.
```
ibmcloud enterprise update (-n, --name NEW_NAME) [-f, --force] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>-f, -- force (opcional)</dt>
<dd>Atualizar sem confirmação.</dd>
<dt>-n, --name NEW_NAME (necessário)</dt>
<dd>Novo nome da empresa.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

Exibir detalhes da empresa.
```
ibmcloud enterprise show [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

Criar um grupo de contas.
```
ibmcloud enterprise account-group-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--primary-contact-id PRIMARY_CONTACT_USER_ID] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>NAME (necessário)</dt>
<dd>Nome do grupo de contas.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional)</dt>
<dd>Nome do grupo de contas pai. Se omitido, o pai será a empresa atual.</dd>
<dt>--primary-contact-id PRIMARY_CONTACT_USER_ID (opcional)</dt>
<dd>O ID de usuário do contato principal do grupo de contas.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

Atualizar um grupo de contas.
```
ibmcloud enterprise account-group-update (-n, --name NAME | --id ID) (--new-name NEW_NAME) [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--id ID (necessário)</dt>
<dd>ID do grupo de contas de destino. Essa opção é exclusiva com `-n, --name`.</dd>
<dt>-n, --name NAME (necessário)</dt>
<dd>Nome do grupo de contas de destino. Essa opção é exclusiva com `--id`.</dd>
<dt>--new-name NEW_NAME (necessário)</dt>
<dd>Novo nome do grupo de contas de destino.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

Exibir detalhes do grupo de contas.
```
ibmcloud enterprise account-group (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--id ID (necessário)</dt>
<dd>ID do grupo de contas. Essa opção é exclusiva com `-n, --name`.</dd>
<dt>-n, --name NAME (necessário)</dt>
<dd>Nome do grupo de contas. Essa opção é exclusiva com `--id`.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

Listar grupos de contas.
```
ibmcloud enterprise account-groups [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional)</dt>
<dd>Nome do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (opcional)</dt>
<dd>ID do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group`.</dd>
<dt>--recursive (opcional)</dt>
<dd>Mostrar grupos de contas descendentes.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

Crie uma conta.
```
ibmcloud enterprise account-create NAME [--parent-account-group ACCOUNT_GROUP_NAME] [--owner USER_ID] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>NAME (necessário)</dt>
<dd>Nome do grupo de contas.</dd>
<dt>--owner USER_ID (opcional)</dt>
<dd>ID do usuário do grupo de contas.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional).</dt>
<dd>Nome do grupo de contas pai. Se omitido, o pai será a empresa atual.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

Mover uma conta sob pai diferente.
```
ibmcloud enterprise account-move (-n, --name NAME | --id ID) (--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID | --parent-enterprise)
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--id ID (necessário)</dt>
<dd>ID da conta de destino. Essa opção é exclusiva com `-n, --name`.</dd>
<dt>-n, --name NAME (necessário)</dt>
<dd>Nome da conta de destino. Essa opção é exclusiva com `--id`.</dd>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (necessário)</dt>
<dd>Nome do grupo de contas pai. Esta opção é exclusiva com `--parent-account-group-id` e `--parent-enterprise`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (necessário)</dt>
<dd>ID do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group` e `--parent-enterprise`.</dd>
<dt>--parent-enterprise (necessário)</dt>
<dd>Configurar a empresa como o pai. Essa opção é exclusiva com `--parent-account-group` e `--parent-account-group-id`.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

Exibir detalhes de uma conta.
```
ibmcloud enterprise account-show (-n, --name NAME | --id ID) [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--id ID (necessário)</dt>
<dd>ID da conta. Essa opção é exclusiva com `-n, --name`.</dd>
<dt>-n, --name NAME (necessário)</dt>
<dd>Nome da conta. Essa opção é exclusiva com `--id`.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

Listar contas.
```
ibmcloud enterprise accounts [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID] [--recursive] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--parent-account-group ACCOUNT_GROUP_NAME (opcional)</dt>
<dd>Nome do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ACCOUNT_GROUP_ID (opcional)</dt>
<dd>ID do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group`.</dd>
<dt>--recursive (opcional)</dt>
<dd>Mostrar contas descendentes.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifique o formato de saída; somente 'JSON' é suportado.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

Importar uma conta independente.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group ACCOUNT_GROUP_NAME | --parent-account-group-id ACCOUNT_GROUP_ID]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

<dl>
<dt>--account-id</dt>
<dd>ID da conta de origem.</dd>
<dt>--parent-account-group PARENT_ACCOUNT_GROUP (opcional)</dt>
<dd>Nome do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id PARENT_ACCOUNT_GROUP_ID (opcional)</dt>
<dd>ID do grupo de contas pai. Essa opção é exclusiva com `--parent-account-group`.</dd>
</dl>
