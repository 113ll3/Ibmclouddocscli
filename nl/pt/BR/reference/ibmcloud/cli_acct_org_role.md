---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Contas, Usuários e Orgs
 {: #ibmcloud_commands_account}

 Use os comandos a seguir para gerenciar as contas, os usuários em uma conta, a organização, o espaço, as funções e os
certificados de domínio dos serviços do Cloud Foundry.
  {: shortdesc}

  <table summary="Comandos ibmcloud que podem ser usados para gerenciar contas, organizações, espaços e funções.">
   <thead>
   </thead>
   <tbody>
   <tr>
   <td>[Ibmcloud conta organizações](cli_acct_org_role.html#ibmcloud_account_orgs)</td>
   <td>[conta ibmcloud org](cli_acct_org_role.html#ibmcloud_account_org)</td>
   <td>[conta ibmcloud org-create](cli_acct_org_role.html#ibmcloud_account_org_create)</td>
   <td>[conta ibmcloud org-replicate](cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
   <td>[conta ibmcloud org-rename](cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
   </tr>
   <tr>
   <td>[ibmcloud Espaços de conta](cli_acct_org_role.html#ibmcloud_account_spaces)</td>
   <td>[ibmcloud account space](cli_acct_org_role.html#ibmcloud_account_space)</td>
   <td>[ibmcloud account space-create](cli_acct_org_role.html#ibmcloud_account_space_create)</td>
   <td>[ibmcloud account space-rename](cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
   <td>[ibmcloud account space-delete](cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
   </tr>
   <tr>
   <td>[Os usuários da organização da conta ibmcloud](cli_acct_org_role.html#ibmcloud_account_org_users)</td>
   <td>[ibmcloud account org-user-add](cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
   <td>[ibmcloud account org-user-remove](cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
   <td>[ibmcloud account org-funções](cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
   <td>[conta ibmcloud org-role-set](cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
   </tr>
   <tr>
   <td>[conta ibmcloud org-role-unset](cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
   <td>[ibmcloud account space-users](cli_acct_org_role.html#ibmcloud_account_space_users)</td>
   <td>[ibmcloud account space-funções](cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
   <td>[ibmcloud account space-role-set](cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
   <td>[ibmcloud account space-role-unset](cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
  </tr>
   <td>[Lista conta ibmcloud](cli_acct_org_role.html#ibmcloud_account_list)</td>
   <td>[conta ibmcloud org-account](cli_acct_org_role.html#ibmcloud_account_org_account)</td>
   <td>[usuários da conta ibmcloud](cli_acct_org_role.html#ibmcloud_account_users)</td>
   <td>[account user-remove](cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
   <td>[conta ibmcloud user-invite](cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
   </tr>
   <tr>
    <td>[conta ibmcloud user-reinvite](cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
   </tr>
   </tbody>
   </table>

 ## Ibmcloud conta organizações
{: #ibmcloud_account_orgs}

Liste todas as organizações

```
ibmcloud account orgs [-r REGION_NAME] [--guid | --output FORMAT] [-c ACCOUNT_ID] [-u ACCOUNT_OWNER]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-r REGION_NAME</dt>
   <dd>Nome da região. Lista as organizações na região especificada. Padrão para região atual, se não especificado. Se configurado
como 'all', lista as organizações em todas as regiões.</dd>
   <dt>-- guid</dt>
   <dd>Exiba o guid das organizações. Essa opção é exclusiva com '-- output'.</dd>
   <dt>-- FORMATO de saída</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Esta opção é exclusiva com '-- guid'.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>ID da conta. Lista as organizações na conta fornecida. Usa como padrão a conta atual, se não especificado. Se configurado como
'all', lista as organizações em todas as contas. Essa opção é exclusiva com '-u'.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Nome do proprietário da conta. Lista as organizações nas contas pertencentes ao usuário fornecido. Usa como padrão a conta atual, se não especificado. 
Se configurado como 'all', lista as organizações em todas as contas. Essa opção é exclusiva com '-c'.</dd>
   </dl>

<strong>Exemplos</strong>:

Liste todas as organizações na região: `us-south` com o GUID exibido

```
Ibmcloud conta orgs -r us-south -- guid
```

Listar todas as organizações no formato JSON

```
Orgs da conta ibmcloud -- JSON de saída
```

## Account org ibmcloud
{: #ibmcloud_account_org}

Mostrar as informações da org especificada.

```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>-r REGION</dt>
   <dd>Nome da região. Se não for especificado, o padrão será a região atual. Se for configurado como 'all', as organizações com o nome
especificado em todas as regiões serão listadas.</dd>
   <dt>-- guid</dt>
   <dd>Recupera e exibe o GUID da organização fornecida. Todas as outras saídas para a organização são suprimidas. Essa opção é exclusiva com '-- output'.</dd>
   <dt>--output REGION</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Esta opção é exclusiva com '-- guid'.</dd>
   </dl>

<strong>Exemplos</strong>:

Mostre as informações da organização `IBM` com o GUID exibido

```
Account org ibmcloud IBM -- guid
```

## Create-org conta ibmcloud
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

## ibmcloud account org-replicate
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

## Rename-org conta ibmcloud
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

## Espaços conta ibmcloud
{: #ibmcloud_account_spaces}

Listar todos os espaços

```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-o ORG_NAME</dt>
   <dd>Nome da organização. Listar os espaços sob a organização especificada. Padrão para a organização atual, se não especificada.</dd>
   <dt>-r REGION-NAM</dt>
   <dd>Nome da região. Listar os espaços sob a região especificada. Padrão para região atual, se não especificado.</dd>
   <dt>-- FORMATO de saída</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. </dd>
   </dl>

<strong>Exemplos</strong>:

Listar todos os espaços:

```
Espaços conta ibmcloud
```

Listar todos os espaços da organização `org_example` no formato JSON:

```
ibmcloud account spaces -o org_example --output JSON
```

## Espaço conta ibmcloud
{: #ibmcloud_account_space}

Mostrar as informações do espaço especificado

```
ibmcloud account space SPACE_NAME [-o ORG_NAME] [--guid | --output FORMAT] [--security-group-rules]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>Nome do espaço a ser mostrado.</dd>
   <dt>-o ORG_NAME</dt>
   <dd>Nome da organização. Padrão para a organização atual, se não especificada.</dd>
   <dt>-- guid</dt>
   <dd>Recupera e exibe o GUID do espaço fornecido. Todas as outras saídas para o espaço são suprimidas. Essa opção é exclusiva com '-- output'.</dd>
   <dt>-- FORMATO de saída</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Todas as outras saídas para o espaço são suprimidas. Esta opção é exclusiva com '-- guid'.</dd>
   <dt>---segurança-grupo-regras</dt>
   <dd>Recupera as regras para todos os grupos de segurança associados ao espaço.</dd>
   </dl>

<strong>Exemplos</strong>:

Mostrar as informações do espaço  ` space_exemplo `:

```
space_exemplo de espaço da conta ibmcloud
```

Mostrar o GUID do espaço  ` space_exemplo `:

```
space_exemplo de espaço da conta ibmcloud -- guid
```

Mostrar as informações do espaço `space_example` no formato JSON:

```
ibmcloud space space space_exemplo -- saída JSON
```

Mostrar as regras do grupo de segurança do espaço `space_example`:

```
ibmcloud space space space_exemplo--security-group-rules
```

## Create-space conta ibmcloud
{: #ibmcloud_account_space_create}

Esse comando tem a mesma função e opções que o comando [cf create-space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.

## Account space-rename ibmcloud
{: #ibmcloud_account_space_rename}


Esse comando tem a mesma função e opções que o comando [cf rename-space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.

## Account space-delete ibmcloud
{: #ibmcloud_account_space_delete}


Esse comando tem a mesma função e opções que o comando [cf delete-space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

## Os usuários da organização da conta ibmcloud
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

## Conta-org-user-add
{: #ibmcloud_account_org_user_add}

Inclua um usuário na organização (gerenciador de organização requerido).

```
 Ibmcloud account org-user-add USER_NAME ORG
```

## Ibmcloud account org-user-remove
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

## ibmcloud account org-roles
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

## Set-ibmcloud account org-role
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

## Ibmcloud account org-role-unset
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

## Os usuários do espaço conta ibmcloud
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

## Conta-space-role-set
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

## Ibmcloud account space-role-unset
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

## ibmcloud account list
{: #ibmcloud_account_list}

Liste todas as contas do usuário atual

```
ibmcloud account list
```

<strong>Pré-requisitos</strong>: Terminal, Login

## Account org-account ibmcloud
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

## ibmcloud account users
{: #ibmcloud_account_users}

Exibe os usuários associados à conta. Essa operação pode ser executada somente pelo proprietário da conta.

```
ibmcloud account users
```

## Remove-ibmcloud conta do usuário
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

## Account user-invite ibmcloud
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

## Ibmcloud account user-reinvite
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
