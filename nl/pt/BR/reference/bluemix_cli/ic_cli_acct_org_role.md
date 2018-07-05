---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandos da CLI para gerenciar contas, organizações e funções
 {: #ibmcloud_commands_account}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar contas, organizações, espaços e funções.">
<caption>Tabela 1. Comandos para gerenciar contas, organizações, espaços e funções</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar contas, organizações, espaços e funções</th>
 </thead>
 <tbody>
 <tr>
 <td>[Ibmcloud conta organizações](ic_cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[conta ibmcloud org](ic_cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[conta ibmcloud org-create](ic_cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[conta ibmcloud org-replicate](ic_cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[conta ibmcloud org-rename](ic_cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud Espaços de conta](ic_cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](ic_cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](ic_cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](ic_cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](ic_cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[Os usuários da organização da conta ibmcloud](ic_cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](ic_cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](ic_cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-funções](ic_cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[conta ibmcloud org-role-set](ic_cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[conta ibmcloud org-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](ic_cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-funções](ic_cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](ic_cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[Lista conta ibmcloud](ic_cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[conta ibmcloud org-account](ic_cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[usuários da conta ibmcloud](ic_cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[account user-remove](ic_cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[conta ibmcloud user-invite](ic_cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[conta ibmcloud user-reinvite](ic_cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](ic_cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](ic_cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[Ibmcloud iam access-group-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[Ibmcloud iam access-group-policy](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[Ibmcloud iam access-group-policy-create](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[Ibmcloud iam access-group-policy-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
 </tr>
 </tbody>
 </table>
 
 ### Ibmcloud conta organizações
{: #ibmcloud_account_orgs}

Liste todas as organizações

```
Ibmcloud conta orgs [-r REGION ] [ -- guid ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-r <i>REGION</i> (opcional)</dt>
   <dd>Para qual região as informações da organização são mostradas. Se configurado como 'all', todas as organizações em todas as regiões serão listadas.</dd>
   <dt>--guid (opcional)</dt>
   <dd>Exiba o GUID das organizações.</dd>
   </dl>

<strong>Exemplos</strong>:

Liste todas as organizações na região: `us-south` com o GUID exibido

```
Ibmcloud conta orgs -r us-south -- guid
```

### Account org ibmcloud
{: #ibmcloud_account_org}

Mostre as informações para a organização especificada.

```
Account org ibmcloud ORG_NAME [ -- guid ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>--guid (opcional)</dt>
   <dd>Exiba o GUID da organização.</dd>
   </dl>

<strong>Exemplos</strong>:

Mostre as informações da organização `IBM` com o GUID exibido

```
Account org ibmcloud IBM -- guid
```

### Create-org conta ibmcloud
{: #ibmcloud_account_org_create}

Criar uma nova organização. Essa operação pode ser executada somente pelo proprietário da conta.

```
Ibmcloud account org-create ORG_NAME [ -f ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização que está sendo criada.</dd>
   <dt>-f</dt>
   <dd>Force a criação sem confirmação.</dd>
   </dl>

<strong>Exemplos</strong>:

Crie uma organização denominada `IBM`.

```
Ibmcloud account org-create IBM
```

### ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replique uma organização a partir da região atual para outra região.

```
-org conta replicate ORG_NAME REGION_NAME ibmcloud
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização existente que deve ser replicada.</dd>
   <dt>REGION_NAME (necessário)</dt>
   <dd>O nome da região que hospeda a organização replicada.</dd>
   </dl>

<strong>Exemplos</strong>:

Replique a organização `myorg` para a região `eu-gb`:

```
Ibmcloud conta org-replicate myorg eu-gb
```

### Rename-org conta ibmcloud
{: #ibmcloud_account_org_rename}

Renomeie uma organização. Essa operação pode ser executada somente por um gerenciador de organização.

```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>OLD_ORG_NAME (necessário)</dt>
   <dd>O nome antigo da organização que deve ser renomeada.</dd>
   <dt>NEW_ORG_NAME (necessário)</dt>
   <dd>O novo nome da organização para o qual ela é renomeada.</dd>
   </dl>

### Espaços conta ibmcloud
{: #ibmcloud_account_spaces}

Listar todos os espaços

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Opções de comando</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Nome da organização. Listar os espaços sob a organização especificada. Padrão para a organização atual, se não especificada.</dd>
   <dt>-r</dt>
   <dd>Nome da região. Listar os espaços sob a região especificada. Padrão para região atual, se não especificado.</dd>
   </dl>

### Espaço conta ibmcloud
{: #ibmcloud_account_space}

Esse comando tem a mesma função e opções que o comando [cf space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.

### Create-space conta ibmcloud
{: #ibmcloud_account_space_create}

Esse comando tem a mesma função e opções que o comando [cf create-space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.

### Account space-rename ibmcloud
{: #ibmcloud_account_space_rename}


Esse comando tem a mesma função e opções que o comando [cf rename-space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.

### Account space-delete ibmcloud
{: #ibmcloud_account_space_delete}


Esse comando tem a mesma função e opções que o comando [cf delete-space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

### Os usuários da organização da conta ibmcloud
{: #ibmcloud_account_org_users}

Exiba usuários na organização especificada por função.

```
Os usuários da organização da conta ibmcloud ORG_NAME [ -a ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>ORG_NAME (necessário)</dt>
<dd>O nome da organização.</dd>
<dt>-a (opcional)</dt>
<dd>Liste todos os usuários na organização especificada, não agrupados por função.</dd>
</dl>

### Conta-org-user-add
{: #ibmcloud_account_org_user_add}

Inclua um usuário na organização (gerenciador de organização requerido).

```
 Ibmcloud account org-user-add USER_NAME ORG
```

### Ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Remova um usuário da organização (gerente da organização ou o próprio usuário somente)

```
   ibmcloud account org-user-remove USER_NAME ORG [-f, --force]
```

<strong>Opções de comando</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Force a exclusão sem confirmação.</dd>
</dl>

### ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Obtenha todas as funções de organização do usuário atual

```
Ibmcloud conta org-roles [-u USER_ID ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID do usuário. Se não especificado, o padrão será o usuário atual.</dd>
  </dl>

### Set-ibmcloud account org-role
{: #ibmcloud_account_org_role_set}

Designe uma função de organização a um usuário. Essa operação pode ser executada somente por um gerenciador de organização.

```
Ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário que está sendo designado.</dd>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização para a qual esse usuário é designado.</dd>
   <dt>ORG_ROLE (necessário)</dt>
   <dd>O nome da função de organização para a qual esse usuário é designado. Por exemplo:
   <ul>
   <li>OrgManager: essa função pode convidar e gerenciar usuários, selecionar e mudar planos e configurar limites de gastos.</li>
   <li>BillingManager: essa função pode criar e gerenciar a conta de cobrança e informações de pagamento.</li>
   <li>OrgAuditor: essa função possui acesso somente leitura para informações e relatórios da organização.</li>
   </ul>
   </dd>
  </dl>

<strong>Exemplos</strong>:

Designe o usuário `Mary` à organização do `IBM` como função `OrgManager`:

```
Ibmcloud conta org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Nota**: é possível configurar as funções de organização/espaço usando a CLI, mas se você desejar configurar as outras permissões, precisará usar a UI. Para obter detalhes adicionais, veja [Designando o acesso de usuário](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

### Ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Remover uma função de organização de um usuário. Essa operação pode ser executada somente por um gerenciador de organização.

```
Ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário que está sendo removido.</dd>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização da qual esse usuário é removido.</dd>
   <dt>ORG_ROLE (necessário)</dt>
   <dd>O nome da função de organização da qual esse usuário é removido. Por exemplo:
   <ul>
   <li>OrgManager: essa função pode convidar e gerenciar usuários, selecionar e mudar planos e configurar limites de gastos.</li>
   <li>BillingManager: essa função pode criar e gerenciar a conta de cobrança e informações de pagamento.</li>
   <li>OrgAuditor: essa função possui acesso somente leitura para informações e relatórios da organização.</li>
   </ul>
   </dd>
    </dl>

<strong>Exemplos</strong>:

Remova o usuário `Mary` da organização `IBM` como função `OrgManager`:

```
Ibmcloud account org-role-unset Mary IBM OrgManager
```

### Os usuários do espaço conta ibmcloud
{: #ibmcloud_account_space_users}

Exiba usuários no espaço especificado por função.

```
ibmcloud account space-users ORG_NAME SPACE_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>O nome do espaço.</dd>
   </dl>

### Conta-space-role-set
{: #ibmcloud_account_space_role_set}

Designe uma função de espaço a um usuário. Essa operação pode ser executada somente por um gerenciador de espaço.

```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário que está sendo designado.</dd>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização para a qual esse usuário é designado.</dd>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>O nome do espaço para o qual esse usuário é designado.</dd>
   <dt>SPACE_ROLE (necessário)</dt>
   <dd>O nome da função de espaço para a qual esse usuário é designado. Por exemplo:
   <ul>
   <li>SpaceManager: essa função pode convidar e gerenciar usuários e ativar recursos para um determinado espaço.</li>
   <li>SpaceDeveloper: essa função pode criar e gerenciar aplicativos e serviços, bem como ver logs e relatórios.</li>
   <li>SpaceAuditor: essa função pode visualizar logs, relatórios e configurações para o espaço.</li>
   </ul></dd>
    </dl>

<strong>Exemplos</strong>:

Designe o usuário `Mary` à organização `IBM` e espaço `Cloud` como função `SpaceManager`:

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

### Ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Remova uma função de espaço de um usuário. Essa operação pode ser executada somente por um gerenciador de espaço.

```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário que está sendo removido.</dd>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização da qual esse usuário é removido.</dd>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>O nome do espaço do qual esse usuário é removido.</dd>
   <dt>SPACE_ROLE (necessário)</dt>
   <dd>O nome da função de espaço da qual esse usuário é removido. Por exemplo:
   <ul>
   <li>SpaceManager: essa função pode convidar e gerenciar usuários e ativar recursos para um determinado espaço.</li>
   <li>SpaceDeveloper: essa função pode criar e gerenciar aplicativos e serviços, bem como ver logs e relatórios.</li>
   <li>SpaceAuditor: essa função pode visualizar logs, relatórios e configurações para o espaço.</li>
   </ul></dd>
    </dl>


<strong>Exemplos</strong>:

Remova o usuário `Mary` da organização `IBM` e espaço `Cloud` como função `SpaceManager`:

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

### ibmcloud account list
{: #ibmcloud_account_list}

Liste todas as contas do usuário atual

```
ibmcloud account list
```

<strong>Pré-requisitos</strong>: Terminal, Login

### Account org-account ibmcloud
{: #ibmcloud_account_org_account}

Exibir a conta da organização especificada (usuário da organização necessário)

```
Ibmcloud account org-account ORG_NAME [ -- guid ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>--guid (opcional)</dt>
  <dd>Exibir somente o ID da conta</dd>
</dl>

### ibmcloud account users
{: #ibmcloud_account_users}

Exibe os usuários associados à conta. Essa operação pode ser executada somente pelo proprietário da conta.

```
ibmcloud account users
```

### Remove-ibmcloud conta do usuário
{: #ibmcloud_account_user_remove}

Remover um usuário de uma conta (somente o proprietário da conta)

```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>USER_ID (obrigatório)</dt>
<dd>ID do Usuário</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID da conta. Se não especificado, o padrão será a conta atual.</dd>
<dt>-f, --force</dt>
<dd>Forçar a remoção sem confirmação.</dd>
</dl>

### Account user-invite ibmcloud
{: #ibmcloud_account_user_invite}

Convidar um usuário para a conta

```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário que está sendo convidado.</dd>
   <dt>-o ORG</dt>
   <dd>Organização para convidar usuário</dd>
   <dt>-- org-role ORG_ROLE</dt>
   <dd>Função organizacional. As entradas válidas são: OrgManager, BillingManager, OrgAuditor e OrgUser. Se omitida, a função
OrgUser será configurada.</dd>
   <dt>-s SPACE</dt>
   <dd>Espaço de convidar usuário</dd>
   <dt>-- SPACE_ROLE space-role</dt>
   <dd>Função de Espaço. As entradas válidas são: SpaceManager, SpaceDeveloper e SpaceAuditor.</dd>
</dl>

### Ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Reenviar o convite a um usuário (administrador de conta)

```
Ibmcloud account user-reinvite USER_EMAIL
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário que está sendo convidado novamente.</dd>
</dl>

### ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Listar grupos de acesso na conta atual

```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-u</dt>
  <dd>Listar grupos de acesso aos quais o usuário pertence. Essa sinalização é exclusiva para '-s'.</dd>
  <dt>-s</dt>
  <dd>Listar grupos de acesso aos quais o ID de serviço pertence. Essa sinalização é exclusiva para '-u'.</dd>
</dl>

<strong>Exemplos</strong>:

Listar todos os grupos de acesso:

```
ibmcloud iam access-groups
```

### Grupo de acesso iam ibmcloud
{: #ibmcloud_iam_access_group}

Mostrar detalhes de um grupo de acesso

```
Grupo de acesso iam ibmcloud GROUP_NAME [ -- id ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-id</dt>
  <dd>Mostrar somente o ID</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes do grupo de acesso `example_group`:

```
Ibmcloud iam access-group example_group
```

### ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Criar um grupo de acesso

```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Descrição de grupo de acesso</dd>
</dl>

<strong>Exemplos</strong>:

Criar um grupo de acesso `example_group`:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

### Ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Atualizar um grupo de acesso

```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>O novo nome do grupo de acesso</dd>
  <dt>-d, --description</dt>
  <dd>Nova descrição</dd>
  <dt>-f, --force</dt>
  <dd>Forçar atualização sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Renomear o grupo de acesso `example_group` para `hello_world_group`:

```
Ibmcloud iam access-group-update example_group -- name "hello_world_group"
```

### Ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Excluir um grupo de acesso

```
ibmcloud iam access-group-delete GROUP_NAME [-f, --force] [-r, --recursive]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
  <dt>-r, --recursive</dt>
  <dd>Excluir grupo de acesso e seus membros</dd>
</dl>

<strong>Exemplos</strong>:

Excluir acesso ao grupo `example_group`:

```
Ibmcloud iam access-group-delete example_group -- force
```

### Ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Listar os usuários em um grupo de acesso

```
Ibmcloud iam access-group-users GROUP_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Listar todos os usuários no grupo de acesso `example_group`:

```
Ibmcloud iam access-group-users example_group
```

### Ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Incluir um ou mais usuários em um grupo de acesso

```
Ibmcloud iam access-group-user-add GROUP_NAME USER_NAME [ USER_NAME2 ...]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Incluir o usuário `name@example.com` ao grupo de acesso
`example_group`:

```
Ibmcloud iam access group-user-add example_group name@example.com
```

### Ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Remover um usuário de um grupo de acesso

```
Ibmcloud iam access-group-user-remove GROUP_NAME USER_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Remover o usuário `name@example.com` do grupo de acesso `example_group`:

```
Ibmcloud iam access-group-user-remove example_group name@example.com
```

### Ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Remover usuário de todos os grupos de acesso

```
Ibmcloud iam access-group-user-purge USER_NAME [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Excluir sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Remover usuário `name@example.com` de todos os grupos de acesso:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

### Ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Listar IDs de serviço em um grupo de acesso

```
ibmcloud iam access-group-service-ids GROUP_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Listar todos os IDs de serviço no grupo de acesso `example_group`:

```
Ibmcloud iam access-group-service-ids example_group
```

### Ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Incluir ID de serviço em um grupo de acesso

```
Ibmcloud iam access-group-service-id-add GROUP_NAME SERVICE_ID_NAME [ SERVICE_ID_NAME2 ...]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Incluir o ID de serviço `exemple-service` no grupo de acesso
`example_group`:

```
Ibmcloud iam access-group-service-id-add example_group example-service
```

### Ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Remover um ID de serviço de um grupo de acesso

```
Ibmcloud iam access-group-service-id-remove GROUP_NAME SERVICE_ID_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Remover o ID de serviço `example-service` do grupo de acesso
`example_group`:

```
Ibmcloud iam access-group-service-id-remove example_group example-service
```

### Ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Remover ID de serviço de todos os grupos de acesso

```
Ibmcloud iam access-group-service-id-purge SERVICE_ID_NAME [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Excluir sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Remover o ID de serviço `example-service` de todos os grupos de acesso:

```
Ibmcloud iam access-group-service-id-purge example -- force
```

### Ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Listar políticas de um grupo de acesso

```
Ibmcloud iam access-group-policies GROUP_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Liste todas as políticas do grupo de acesso `example_group`:

```
Ibmcloud iam access-group-policies example_group
```

### Ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Mostrar detalhes de uma política de grupo de acesso

```
Ibmcloud iam access-group-policy GROUP_NAME POLICY_ID
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes de política `51b9717e-76b0-4f6a-bda7-b8132431f926` do grupo de acesso
`example_group`:

```
Ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

### Ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Criar uma política de grupo de acesso

```
ibmcloud iam access-group-policy-create GROUP_NAME {--file @JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>Arquivo JSON de definição de política</dd>
  <dt>-roles</dt>
  <dd>Os nomes de função da definição de política. Para funções suportadas de um serviço específico, execute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opção é exclusiva com '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome do serviço da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID da instância de serviço da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-region</dt>
  <dd>Região da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-resource</dt>
  <dd>Recurso da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-name'.</dd>
</dl>

<strong>Exemplos</strong>:

Criar uma política de grupo de acesso por meio de um arquivo JSON:

```
Ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Fornecer ao `example_group` a função `Administrator` para todos
os recursos do `sample-service`:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Fornecer a função de `Editor` a `example_group` para o recurso `key123` da
instância `sample-service` com a GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` na região `us-south`:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance
d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Fornecer ao `example_group` a função `Operator` para o grupo de
recursos com ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Fornecer ao `example_group` a função `Viewer` para os membros do grupo
de recursos `sample-resource-group`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Fornecer ao `example_group` a função `Viewer` para os membros do
grupo de recursos com ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Atualizar uma política do grupo de acesso

```
ibmcloud iam access-group-policy-update GROUP_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>Arquivo JSON de definição de política</dd>
  <dt>-- roles</dt>
  <dd>Os nomes de função da definição de política. Para funções suportadas de um serviço específico, execute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opção é exclusiva com '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome do serviço da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID da instância de serviço da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-region</dt>
  <dd>Região da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-resource</dt>
  <dd>Recurso da definição de política. Esta opção é exclusiva com '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-name'.</dd>
</dl>

<strong>Exemplos</strong>:

Atualizar a política de grupo de acesso com aquela no arquivo JSON de política:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Atualizar a política de grupo de acesso para fornecer a função `Administrator`
do `example_group` para todos os recursos do `sample-service`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Atualizar a política de grupo de acesso para fornecer a função de `Editor` a `example_group` para o recurso `key123` da instância `sample-service` com a GUID
`d161aeea-fd02-40f8-a487-df1998bd69a9` na região `us-south`:
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Atualizar a política de grupo de acesso para fornecer ao `example_group`
a função `Operator` para o grupo de recursos com ID
`dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Atualizar a política do grupo de acesso para fornecer ao `example_group`
a função `Viewer` para os membros do grupo de recursos
`sample-resource-group`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Atualizar a política de grupo de acesso para fornecer ao `example_group`
a função `Viewer` para membros do grupo de recursos com ID
`dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### Ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Excluir uma política de grupo de acesso

```
ibmcloud iam access-group-policy-delete GROUP_NAME POLICY_ID [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Excluir a política `51b9717e-76b0-4f6a-bda7-b8132431f926` do grupo de acesso
`example_group`:
```
Ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
