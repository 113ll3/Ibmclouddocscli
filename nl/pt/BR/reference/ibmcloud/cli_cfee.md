---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry Enterprise Environments (CFEE)
{: #ibmcloud_commands_cfee}

Com o {{site.data.keyword.cfee_full}} (CFEE), é possível instanciar múltiplas plataformas Cloud Foundry isoladas e de classificação corporativa on-demand. As instâncias do serviço IBM Cloud Foundry Enterprise são executadas em sua própria conta no IBM Cloud. O ambiente é implementado em hardware isolado (clusters do Kubernetes). Você tem controle total sobre o ambiente, incluindo o controle de acesso, a capacidade, as atualizações de versão, o uso de recurso e o monitoramento.

Use os comandos a seguir para gerenciar os ambientes CFEE, as organizações, os espaços, os usuários e as funções.
{: shortdesc}

<table summary="Gerenciar ambientes corporativos do Cloud Foundry (experimental)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[Ambientes cfee ibmcloud
](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee ambiente](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ Orgs de cfee ibmcloud ](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ ibmcloud cfee org-delete ](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ ibmcloud cfee org-users ](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ ibmcloud cfee org-role-set ](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ ibmcloud cfee org-role-unset ](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ espaços de cfee ibmcloud ](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ espaço ibmcloud cfee-criar ](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ ibmcloud cfee space-rename ](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ ibmcloud cfee space-delete ](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ ibmcloud cfee space-role-unset ](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ ibmcloud cfee space-roles ](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ espaço ibmcloud cfee-users ](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 </tr>
 </tbody>
 </table>

 ## Ambientes cfee ibmcloud
{: #ibmcloud_cfee_environments}

Lista de ambientes CFEE.

```
Ambientes cfee ibmcloud
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

## Ambiente cfee ibmcloud
{: #ibmcloud_cfee_environment}

Mostrar detalhes de um ambiente CFEE

```
ibmcloud cfee environment NAME [--id]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>NAME (necessário)</dt>
   <dd>O nome do ambiente a ser mostrado.</dd>
   <dt>--id</dt>
   <dd>Mostrar somente o ID</dd>
  </dl>

<strong>Exemplos</strong>:

Mostrar detalhes de um ambiente CFEE `env_example`:

```
ibmcloud cfee environment env_example
```

Mostrar o ID de um ambiente CFEE `env_example`:

```
ibmcloud cfee environment env_example --id
```

## orgs de cfee ibmcloud
{: #ibmcloud_cfee_orgs}

Listar Todas as Orgs

```
ibmcloud cfee orgs [ -- env ENV ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Listar todas as orgs:

```
orgs de cfee ibmcloud
```

Listar todas as organizações do ambiente CFEE `env_example`:

```
ibmcloud cfee orgs -- env env_exemplo
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Exibir detalhes de uma org

```
ibmcloud cfee org ORG [--guid] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-- guid</dt>
   <dd>Exibe somente a GUID da organização. Todas as outras saídas para a organização são suprimidas</dd>
  </dl>

<strong>Exemplos</strong>:

Mostrar detalhes de uma organização CFEE `org_example`:

```
ibmcloud cfee org org_exemplo
```

Mostrar detalhes de uma organização CFEE `org_example` do ambiente CFEE `env_example`:

```
ibmcloud cfee org org_exemplo -- env env_exemplo
```

Mostrar a GUID de uma organização CFEE `org_example`:

```
ibmcloud cfee org org_exemplo -- guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Criar uma org

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização que está sendo criada.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-q, -- quota QUOTA</dt>
   <dd>Cota para atribuir à organização recém-criada (usar a cota padrão, se não especificada)</dd>
  </dl>

<strong>Exemplos</strong>:

Crie um org. CFEE  ` org_exemplo `:

```
ibmcloud cfee org-create org_exemplo
```

Criar uma organização CFEE `org_example` do ambiente CFEE `env_example`:

```
ibmcloud cfee org-create org_exemplo -- env env_exemplo
```

Criar uma organização CFEE `org_example` com a cota `quote_example`:

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Excluir uma org

```
ibmcloud cfee org-delete ORG [-f, --force] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização que está sendo excluída.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-f, --force</dt>
   <dd>Forçar exclusão sem confirmação</dd>
  </dl>

<strong>Exemplos</strong>:

Exclua um org. CFEE  ` org_exemplo `:

```
ibmcloud cfee org-delete org_exemplo
```

Excluir uma organização CFEE `org_example` do ambiente CFEE `env_example`:

```
ibmcloud cfee org-delete org_exemplo -- env env_exemplo
```

Excluir uma organização CFEE `org_example` sem confirmação:

```
ibmcloud cfee org org-delete org_exemplo -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Exibir usuários na organização especificada por função

```
ibmcloud cfee org-users ORG [-a, --all] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>-a, -- todos</dt>
   <dd>Lista todos os usuários na organização especificada</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Exibir usuários no CFEE org  ` org_exemplo `:

```
ibmcloud cfee org-users org_exemplo
```

Exibir usuários na organização CFEE `org_example` do ambiente CFEE `env_example`:

```
ibmcloud cfee org-users org_example --env env_example
```

Listar todos os usuários na organização CFEE `org_example`:

```
ibmcloud cfee org-users org_exemplo -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Designar uma função de organização para um usuário (gerente da organização necessário)

```
ibmcloud cfee org-role-set USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário que está sendo designado.</dd>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização para a qual esse usuário é designado.</dd>
   <dt>ROLE (necessário)</dt>
   <dd>O nome da função de organização para a qual esse usuário é designado. Por exemplo:
   <ul>
   <li>OrgManager: essa função pode convidar e gerenciar usuários, selecionar e mudar planos e configurar limites de gastos.</li>
   <li>BillingManager: essa função pode criar e gerenciar a conta de cobrança e informações de pagamento.</li>
   <li>OrgAuditor: essa função possui acesso somente leitura para informações e relatórios da organização.</li>
   </ul>
   </dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Atribuir a função `BillingManager` para o usuário `test@exmaple.com` na organização
`org_example`:

```
ibmcloud cfee org-role-set tes@example.com org_exemplo BillingManager
```

Designar a função `BillingManager` para o usuário `test@exmaple.com` na organização
`org_example` do ambiente CFEE `env_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Remover uma função de organização de um usuário (apenas gerente da organização ou o próprio usuário)

```
ibmcloud cfee org-role-unset USER_EMAIL ORG ROLE [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário que está sendo removido.</dd>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização da qual esse usuário é removido.</dd>
   <dt>ROLE (necessário)</dt>
   <dd>O nome da função de organização da qual esse usuário é removido. Por exemplo:
   <ul>
   <li>OrgManager: essa função pode convidar e gerenciar usuários, selecionar e mudar planos e configurar limites de gastos.</li>
   <li>BillingManager: essa função pode criar e gerenciar a conta de cobrança e informações de pagamento.</li>
   <li>OrgAuditor: essa função possui acesso somente leitura para informações e relatórios da organização.</li>
   </ul>
   </dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Remover a função `BillingManager` do usuário `test@exmaple.com` da organização `org_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_exemplo BillingManager
```

Remover a função `BillingManager` do usuário `test@exmaple.com` da organização
`org_example` do ambiente CFEE `env_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## Espaços de cfee ibmcloud
{: #ibmcloud_cfee_spaces}

Listar todos os espaços

```
ibmcloud cfee spaces [-o,--org ORG] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>-o, -- org ORG</dt>
   <dd>Nome da organização. Padrão para a organização atual, se não especificada.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Listar todos os espaços

```
Espaços de cfee ibmcloud
```

Listar todos os espaços da organização `org_example` e do ambiente CFEE `env_example`

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Mostrar as informações do espaço especificado

```
ibmcloud cfee space SPACE [--guid] [--security-group-rules] [-o,--org ORG] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>SPACE (necessário)</dt>
   <dd>Nome do espaço a ser mostrado.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-- guid</dt>
   <dd>Recupera e exibe o GUID do espaço fornecido. Todas as outras saídas para o espaço são suprimidas.</dd>
   <dt>-o, -- org ORG</dt>
   <dd>Nome da organização. Padrão para a organização atual, se não especificada.</dd>
   <dt>---segurança-grupo-regras</dt>
   <dd>Recupera as regras para todos os grupos de segurança associados ao espaço.</dd>
  </dl>

<strong>Exemplos</strong>:

Mostrar as informações do espaço `space_example`:

```
space_exemplo do espaço cfee ibmcloud
```

Recuperar e exibir o GUID do espaço `space_example`:

```
ibmcloud cfee space space_exemplo -- guid
```

Mostrar as regras para todos os grupos de segurança associados ao espaço `space_example`:

```
ibmcloud cfee space space_exemplo--security-group-rules
```

Mostrar as informações do espaço `space_example` da organização `org_example` e do ambiente
CFEE `env_example`:

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Criar um novo espaço

```
ibmcloud cfee space-create SPACE [-o, --org ORG] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>SPACE (necessário)</dt>
   <dd>Nome do espaço que está sendo criado.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-o, -- org ORG</dt>
   <dd>Nome da organização. Padrão para a organização atual, se não especificada.</dd>
  </dl>

<strong>Exemplos</strong>:

Criar um novo espaço `space_example`:

```
ibmcloud cfee space-create space_exemplo
```

Criar um novo espaço `space_example` na organização `org_example` e no ambiente CFEE `env_example`:

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Renomear um espaço

```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>OLD_NAME (obrigatório)</dt>
   <dd>O nome antigo do espaço que deve ser renomeado.</dd>
   <dt>NEW_NAME (obrigatório)</dt>
   <dd>O novo nome do espaço para o qual foi renomeado.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-o, -- org ORG</dt>
   <dd>Nome da organização. Padrão para a organização atual, se não especificada.</dd>
  </dl>

<strong>Exemplos</strong>:

Renomeie o espaço  ` space_exemplo `  para  ` new_pace_exemplo `:

```
ibmcloud cfee space-rename space_exemplo new_pace_exemplo
```

Renomear o espaço `space_example` para `new_pace_example` na organização
`org_example` e no ambiente CFEE `env_example`:

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Excluir um espaço

```
ibmcloud cfee space-delete SPACE [-f, --force] [-o, --org ORG] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>SPACE (necessário)</dt>
   <dd>Nome do espaço a ser excluído.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
   <dt>-f, --force</dt>
   <dd>Force a exclusão sem confirmação.</dd>
   <dt>-o, -- org ORG</dt>
   <dd>Nome da organização. Padrão para a organização atual, se não especificada.</dd>
  </dl>

<strong>Exemplos</strong>:

Excluir espaço  ` space_exemplo `:

```
ibmcloud cfee space-delete space_exemplo
```

Excluir o espaço `space_example` na organização `org_example` e no ambiente CFEE
`env_example` sem confirmação:

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Designar uma função de espaço a um usuário

```
ibmcloud cfee space-role-set USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário que está sendo designado.</dd>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização para a qual esse usuário é designado.</dd>
   <dt>SPACE (necessário)</dt>
   <dd>O nome do espaço para o qual esse usuário é designado.</dd>
   <dt>ROLE (necessário)</dt>
   <dd>O nome da função de espaço para a qual esse usuário é designado. Por exemplo:
   <ul>
   <li>SpaceManager: essa função pode convidar e gerenciar usuários e ativar recursos para um determinado espaço.</li>
   <li>SpaceDeveloper: essa função pode criar e gerenciar aplicativos e serviços, bem como ver logs e relatórios.</li>
   <li>SpaceAuditor: essa função pode visualizar logs, relatórios e configurações para o espaço.</li>
   </ul></dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Designar o usuário `test@exmaple.com` para a organização `org_example` e o espaço `space_example` como a função `SpaceManager`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

Designar o usuário `test@exmaple.com` para a organização `org_example` e o espaço
`space_example` como a função `SpaceManager` no ambiente `env_example`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Remover uma função de espaço de um usuário

```
ibmcloud cfee space-role-unset USER_EMAIL ORG SPACE ROLE [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário que está sendo removido.</dd>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização da qual esse usuário é removido.</dd>
   <dt>SPACE (necessário)</dt>
   <dd>O nome do espaço do qual esse usuário é removido.</dd>
   <dt>ROLE (necessário)</dt>
   <dd>O nome da função de espaço da qual esse usuário é removido. Por exemplo:
   <ul>
   <li>SpaceManager: essa função pode convidar e gerenciar usuários e ativar recursos para um determinado espaço.</li>
   <li>SpaceDeveloper: essa função pode criar e gerenciar aplicativos e serviços, bem como ver logs e relatórios.</li>
   <li>SpaceAuditor: essa função pode visualizar logs, relatórios e configurações para o espaço.</li>
   </ul></dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Remover o usuário `test@exmaple.com` para a organização `org_example` e o espaço
`space_example` como a função `SpaceManager`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

Remover o usuário `test@exmaple.com` para a organização `org_example` e o espaço `space_example` como a função `SpaceManager` no ambiente `env_example`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Obter todas as funções de espaço do usuário atual na organização específica

```
ibmcloud cfee space-roles ORG [ -- env ENV ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Obter todas as funções de espaço do usuário atual na organização `org_example`:

```
ibmcloud cfee space-roles org_exemplo
```

Obter todas as funções de espaço do usuário atual na organização `org_example` e no ambiente
`env_example`:

```
ibmcloud cfee space-roles org_exemplo -- env env_exemplo
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Exibir usuários no espaço especificado por função

```
ibmcloud cfee space-users ORG SPACE [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>SPACE (necessário)</dt>
   <dd>O nome do espaço.</dd>
   <dt>-- env ENV</dt>
   <dd>Nome do ambiente CFEE. Usa como padrão o ambiente CFEE atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Exibir todos os usuários no espaço `space_example` e na organização `org_example`:

```
ibmcloud cfee space-users org_exemplo space_exemplo
```

Exibir todos os usuários no espaço `space_example` e na organização `org_example` e no
ambiente `env_example`:

```
ibmcloud cfee space-users org_example space_example --env env_example
```
