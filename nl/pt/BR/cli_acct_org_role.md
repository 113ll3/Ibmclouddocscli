---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-05"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# Gerenciando contas, usuários e organizações do Cloud Foundry
{: #ibmcloud_commands_account}

Use os comandos a seguir para gerenciar as contas, os usuários em uma conta, a organização, o espaço e as funções
dos ambientes públicos do Cloud Foundry.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

Liste todas as organizações.
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
   <dd>Exiba o guid das organizações. Essa opção é exclusiva com `--output`.</dd>
   <dt>-- FORMATO de saída</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Essa opção é exclusiva com `--guid`.</dd>
   <dt>-c ACCOUNT_ID</dt>
   <dd>ID da conta. Liste as organizações sob a conta. Usa como padrão a conta atual, se não especificado. Se configurado como `all`, listará as organizações em todas as contas. Essa opção é exclusiva com `-u`.</dd>
   <dt>-u ACCOUNT_OWNER</dt>
   <dd>Nome do proprietário da conta. Liste as organizações sob as contas que são de propriedade do usuário. Usa como padrão a conta atual, se não especificado. Se configurado como 'all', lista as organizações em todas as contas. Essa opção é exclusiva com `-c`.</dd>
   </dl>

<strong>Exemplos</strong>:

Liste todas as organizações na região `us-south` com o GUID exibido:
```
ibmcloud account orgs -r us-south --guid
```

Liste todas as organizações no formato JSON:
```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

Mostre as informações da organização especificada.
```
ibmcloud account org ORG_NAME [-r REGION] [--guid | --output REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>-r REGION</dt>
   <dd>Nome da região. Se não for especificado, o padrão será a região atual. Se configurado como `all`, as organizações com o nome especificado em todas as regiões serão listadas.</dd>
   <dt>-- guid</dt>
   <dd>Recuperar e exibir o guid da organização. Todas as outras saídas para a organização são suprimidas. Essa opção é exclusiva com `--output`.</dd>
   <dt>--output REGION</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Essa opção é exclusiva com `--guid`.</dd>
   </dl>

<strong>Exemplos</strong>:

Mostre as informações da organização `IBM` com o GUID exibido.
```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crie uma organização. Essa operação pode ser executada somente pelo proprietário da conta.
```
ibmcloud account org-create ORG_NAME [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização a ser criada.</dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   </dl>

<strong>Exemplos</strong>:

Crie uma organização denominada `IBM`.
```
ibmcloud account org-create IBM 
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replique uma organização a partir da região atual para outra região.
```
ibmcloud account org-replicate ORG_NAME REGION_NAME [-r, --region SOURCE_REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização existente que deve ser replicada.</dd>
   <dt>REGION_NAME (necessário)</dt>
   <dd>O nome da região que hospeda a organização replicada.</dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   </dl>

<strong>Exemplos</strong>:

Replique a organização `myorg` para a região `eu-gb`:
```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Renomeie uma organização. Essa operação pode ser executada somente por um gerenciador de organização.
```
ibmcloud account org-rename OLD_ORG_NAME NEW_ORG_NAME [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>OLD_ORG_NAME (necessário)</dt>
   <dd>O nome antigo da organização que deve ser renomeada.</dd>
   <dt>NEW_ORG_NAME (necessário)</dt>
   <dd>O novo nome da organização que deve ser renomeada.</dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Liste todos os espaços da conta.
```
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-o ORG_NAME (opcional)</dt>
   <dd>Nome da organização. Listar os espaços sob a organização especificada. Padrão para a organização atual, se não especificada.</dd>
   <dt>-r REGION-NAME (opcional)</dt>
   <dd>Nome da região. Listar os espaços sob a região especificada. Padrão para região atual, se não especificado.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
   </dl>

<strong>Exemplos</strong>:

Listar todos os espaços:
```
ibmcloud account spaces
```

Listar todos os espaços da organização `org_example` no formato JSON:
```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

Mostre as informações de um espaço específico.
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
   <dd>Recuperar e exibir o guid do espaço. Todas as outras saídas para o espaço são suprimidas. Essa opção é exclusiva com `--output`.</dd>
   <dt>-- FORMATO de saída</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora. Todas as outras saídas para o espaço são suprimidas. Essa opção é exclusiva com `--guid`.</dd>
   <dt>---segurança-grupo-regras</dt>
   <dd>Recupera as regras para todos os grupos de segurança associados ao espaço.</dd>
   </dl>

<strong>Exemplos</strong>:

Mostrar as informações do espaço `space_example`:
```
ibmcloud account space space_example
```

Mostrar o GUID do espaço `space_example`:
```
ibmcloud account space space_example --guid
```

Mostre as informações do espaço `space_example` no formato JSON:
```
ibmcloud account space space_example --output JSON
```

Mostrar as regras do grupo de segurança do espaço `space_example`:
```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Esse comando tem a mesma função e as opções que o comando [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo").

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

Esse comando tem a mesma função e as opções que o comando [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo").

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

Esse comando tem a mesma função e as opções que o comando [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![Ícone de link externo](../../../icons/launch-glyph.svg "Ícone de link externo").

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Exiba usuários na organização especificada por função.

```
ibmcloud account org-users ORG_NAME [-r, --region REGION] [-a, --all]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>ORG_NAME (necessário)</dt>
<dd>O nome da organização.</dd>
<dt>-a, -all (opcional)</dt>
<dd>Liste todos os usuários na organização especificada, não agrupados por função.</dd>
<dt>-r, --region REGION (opcional)</dt>
<dd>Nome da região. Padrão para região atual, se não especificado.</dd>
</dl> 

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Inclua um usuário na organização (gerenciador de organização requerido).
```
 ibmcloud account org-user-add USER_NAME ORG [-r, --region REGION]
```

<strong>Opções de comando</strong>:
<dl>
<dt>USER_NAME ((necessário))</dt>
<dd>O nome do usuário.</dd>
<dt>ORG (necessário)</dt>
<dd>O nome da organização.</dd>
<dt>-r, --region REGION (opcional)</dt>
<dd>Nome da região. Padrão para região atual, se não especificado.</dd>
</dl>  

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Remova um usuário da organização (somente gerente da organização ou usuário).
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

Obtenha todas as funções de organização do usuário atual.
```
ibmcloud account org-roles [-r, --region REGION] [-u USER_ID] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID do usuário. Se não especificado, o padrão será o usuário atual.</dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Designe uma função de organização a um usuário. Essa operação deve ser executada por um gerenciador de organização.
```
ibmcloud account org-role-set USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário a ser designado.</dd>
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
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
  </dl>

<strong>Exemplos</strong>:

Designe o usuário `Mary` à organização do `IBM` como função `OrgManager`:
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
É possível configurar funções de organização e espaço usando a CLI, mas caso você queira configurar as outras permissões, deve-se usar a IU. Para obter mais informações, consulte [Gerenciando o acesso a recursos](/docs/iam?topic=iam-iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Remover uma função de organização de um usuário. Essa operação pode ser executada somente por um gerenciador de organização.
```
ibmcloud account org-role-unset USER_NAME ORG_NAME ORG_ROLE [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário a ser removido.</dd>
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
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   </dl>

<strong>Exemplos</strong>:

Remova o usuário `Mary` da organização `IBM` como função `OrgManager`:
```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## Os usuários do espaço conta ibmcloud
{: #ibmcloud_account_space_users}

Exiba usuários no espaço especificado por função.
```
ibmcloud account space-users ORG_NAME SPACE_NAME [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>O nome do espaço.</dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   </dl>

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

Obter todas as funções de espaço do usuário atual na organização específica

```
ibmcloud account space-roles ORG [-r, --region REGION] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>ORG (necessário)</dt>
   <dd>O nome da organização.</dd>
   <dt>-r (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Designe uma função de espaço a um usuário. Essa operação pode ser executada somente por um gerenciador de espaço.
```
ibmcloud account space-role-set USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário a ser designado.</dd>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização para a qual esse usuário é designado.</dd>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>O nome do espaço para o qual esse usuário é designado.</dd>
   <dt>SPACE_ROLE (necessário)</dt>
   <dd>O nome da função de espaço para a qual esse usuário é designado. Por exemplo:
   <ul>
   <li>SpaceManager: essa função pode convidar e gerenciar usuários e ativar recursos.</li>
   <li>SpaceDeveloper: essa função pode criar e gerenciar aplicativos e serviços, bem como ver logs e relatórios.</li>
   <li>SpaceAuditor: essa função pode visualizar logs, relatórios e configurações para o espaço.</li>
   </ul>
   </dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
   </dl>

<strong>Exemplos</strong>:

Designe o usuário `Mary` à organização `IBM` e espaço `Cloud` como função `SpaceManager`:
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Remova uma função de espaço de um usuário. Essa operação pode ser executada somente por um gerenciador de espaço.
```
ibmcloud account space-role-unset USER_NAME ORG_NAME SPACE_NAME SPACE_ROLE [-r, --region REGION]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

   <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário a ser removido.</dd>
   <dt>ORG_NAME (necessário)</dt>
   <dd>O nome da organização da qual esse usuário é removido.</dd>
   <dt>SPACE_NAME (necessário)</dt>
   <dd>O nome do espaço do qual esse usuário é removido.</dd>
   <dt>SPACE_ROLE (necessário)</dt>
   <dd>O nome da função de espaço da qual esse usuário é removido. Por exemplo:
   <ul>
   <li>SpaceManager: essa função pode convidar e gerenciar usuários e ativar recursos.</li>
   <li>SpaceDeveloper: essa função pode criar e gerenciar aplicativos e serviços, bem como ver logs e relatórios.</li>
   <li>SpaceAuditor: essa função pode visualizar logs, relatórios e configurações para o espaço.</li>
   </ul></dd>
   <dt>-r, --region REGION (opcional)</dt>
   <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
    </dl>


<strong>Exemplos</strong>:

Remova o usuário `Mary` da organização `IBM` e espaço `Cloud` como função `SpaceManager`:
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Liste todas as contas do usuário atual:
```
ibmcloud account list [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Exiba a conta da organização especificada (usuário da organização necessário).
```
ibmcloud account org-account ORG_NAME [-r, --region REGION] [--guid | --output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
  <dt>-r (opcional)</dt>
  <dd>Nome da região. Padrão para região atual, se não especificado.</dd>
  <dt>--guid (opcional)</dt>
  <dd>Exibir somente o ID da conta</dd>
  <dt>-- output FORMAT (opcional)</dt>
  <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Mostre detalhes da conta.
```
ibmcloud account show
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Mostre detalhes da conta destinada atualmente:
```
ibmcloud account show
```

## Atualização da conta ibmcloud
{: #ibmcloud_account_update}

Atualize uma conta específica:
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Ative ou desative a conectividade de terminais em serviço para uma conta do SoftLayer.</dd>
</dl>

<strong>Exemplos</strong>:

Ative a conectividade do terminal em serviço para a conta atual:
```
ibmcloud account update--service-endpoint-enable true
```

## Logs de auditoria da conta de infraestrutura clássica
{: #classic_account_audit_logs}

Liste os logs de auditoria da conta do SoftLayer:
```
account audit-logs [-u, --user-name USER_NAME] [-t, --object-type OBJECT_TYPE] [-o, --object OBJECT] [-a, --action ACTION] [-s, --start-date START_DATE] [-e, --end-date END_DATE]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-a, --action <i>ACTION</i></dt>
  <dd>Ação. Liste os logs de auditoria com a ação.</dd>
  <dt>-e, --end-date <i>END_DATE</i></dt>
  <dd>Data de encerramento. Listar logs de auditoria antes da data de encerramento. Os formatos suportados são aaaa-MM-ddTHH:mm:ss.</dd>
  <dt>-o, --object <i>OBJECT</i></dt>
  <dd>Objeto. Liste os logs de auditoria com o objeto.</dd>
  <dt>-t, --object-type <i>OBJECT_TYPE</i></dt>
  <dd>Tipo de objeto. Liste os logs de auditoria com o tipo de objeto.</dd>
  <dt>-s, --start-date <i>START_DATE</i></dt>
  <dd>Data de início. Listar os logs de auditoria após a data de início. Os formatos suportados são aaaa-MM-ddTHH:mm:ss.</dd>
  <dt>-u, --user-name <i>USER_NAME</i></dt>
  <dd>Nome do usuário. Liste os logs de auditoria com o nome do usuário.</dd>
</dl>

<strong>Exemplos</strong>:

Liste os logs de auditoria:
```
ibmcloud account audit-logs
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

Listar logs de auditoria da conta

```
ibmcloud account audit-logs [--user-name USER_NAME] [--object-type OBJECT_TYPE] [--object OBJECT] [--action ACTION] [--start-date START_DATE] [--end-date END_DATE] [--output FORMAT]
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>--user-name <i>USER_NAME</i> (opcional)</dt>
   <dd>Liste os logs de auditoria com o nome do usuário.</dd>
   <dt>--object-type <i>OBJECT_TYPE</i> (opcional)</dt>
   <dd>Liste os logs de auditoria com o tipo de objeto.</dd>
   <dt>--object <i>OBJECT</i> (opcional)</dt>
   <dd>Liste os logs de auditoria com o objeto.</dd>
   <dt>--action <i>ACTION</i> (opcional)</dt>
   <dd>Liste os logs de auditoria com a ação.</dd>
   <dt>--start-date <i>START_DATE</i> (opcional)</dt>
   <dd>Listar os logs de auditoria após a data de início. Os formatos suportados são aaaa-MM-ddTHH:mm:ss.</dd>
   <dt>--end-date <i>END_DATE</i> (opcional)</dt>
   <dd>Listar logs de auditoria antes da data de encerramento. Os formatos suportados são aaaa-MM-ddTHH:mm:ss.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud account users
{: #ibmcloud_account_users}

Exibe os usuários que estão associados com a conta. Essa operação deve ser executada pelo proprietário da conta.
```
ibmcloud account users [-c, --account-id ACCOUNT_ID] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>-c (opcional)</dt>
<dd>ID da conta. Se não especificado, o padrão será a conta atual.</dd>
<dt>-- output FORMAT (opcional)</dt>
<dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Remova um usuário de uma conta (somente o proprietário da conta).
```
ibmcloud account user-remove USER_ID [-c ACCOUNT_ID] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>USER_ID (obrigatório)</dt>
<dd>ID do usuário</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID da conta. Se não especificado, o padrão será a conta atual.</dd>
<dt>-f, --force</dt>
<dd>Forçar a remoção sem confirmação.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Convide um usuário para a conta:
```
ibmcloud account user-invite USER_EMAIL [-o ORG [--org-role ORG_ROLE] [-s SPACE, --space-role SPACE_ROLE]]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário a ser convidado.</dd>
   <dt>-o ORG</dt>
   <dd>Organização para convidar usuário</dd>
   <dt>-- org-role ORG_ROLE</dt>
   <dd>Função organizacional. As entradas válidas são: OrgManager, BillingManager, OrgAuditor e OrgUser. Se omitido, a função OrgUser será configurada.</dd>
   <dt>-s SPACE</dt>
   <dd>Espaço de convidar usuário</dd>
   <dt>-- SPACE_ROLE space-role</dt>
   <dd>Função de Espaço. As entradas válidas são: SpaceManager, SpaceDeveloper e SpaceAuditor.</dd>
</dl>

Se você não estiver pronto para designar acesso ou desejar designar uma política do IAM, em vez de acesso ao Cloud Foundry, será possível convidar um usuário sem acesso e designá-lo posteriormente. Para obter mais informações sobre como designar acesso a usuários, consulte [Gerenciando acesso a recursos](/docs/iam?topic=iam-iammanidaccser#assign_new_access).
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Reenvie o convite para um usuário (administrador de conta).
```
ibmcloud account user-reinvite USER_EMAIL
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>USER_EMAIL (necessário)</dt>
   <dd>O e-mail do usuário a ser convidado novamente.</dd>
</dl>

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

Mostrar detalhes da preferência do usuário

```
ibmcloud account user-preference [--output FORMAT]
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

Atualizar a preferência do usuário

```
ibmcloud account user-preference-update (--position NEW_POSITION) [--output FORMAT]
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>--position <i>NEW_POSITION</i> (opcional)</dt>
   <dd>Configure a posição de um usuário, como 'gerente' ou 'estudante'.</dd>
   <dt>-- output FORMAT (opcional)</dt>
   <dd>Especifica o formato de saída. Apenas JSON é suportado agora.</dd>
</dl>

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

Assinar a notificação da plataforma:
```
ibmcloud account platform-notification-subscribe (--type TYPE)
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>--type <i>TYPE</i> (opcional)</dt>
   <dd>Tipo de notificação, um de 'unplanned_events', 'planned_maintenance'.</dd>
</dl>

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

Cancelar a assinatura da notificação da plataforma:
```
ibmcloud account platform-notification-unsubscribe (--type TYPE)
```
<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
   <dt>--type <i>TYPE</i> (opcional)</dt>
   <dd>Tipo de notificação, um de 'unplanned_events', 'planned_maintenance'.</dd>
</dl>

## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

Liste as informações de certificado de um domínio:
```
ibmcloud account domain-cert DOMAIN_NAME
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>DOMAIN_NAME (necessário)</dt>
<dd>O domínio que hospeda o certificado.</dd>
</dl>


<strong>Exemplos</strong>:

Visualize as informações de certificado do domínio `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert ibmcxo-eventconnect.com
```

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

Inclua um certificado no domínio especificado na organização atual.
```
ibmcloud account domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
   <dl>
   <dt>DOMAIN (necessário)</dt>
   <dd>O domínio no qual o certificado é incluído.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (necessário)</dt>
   <dd>O caminho de arquivo de chave privado.</dd>
   <dt>-c <i>CERT_FILE</i> (necessário)</dt>
   <dd>O caminho de arquivo de certificado.</dd>
   <dt>-p <i>PASSWORD</i> (opcional)</dt>
   <dd>A senha para o certificado.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (opcional)</dt>
   <dd>O caminho de arquivo de certificado intermediário.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (opcional)</dt>
   <dd>O arquivo de armazenamento confiável.</dd>
   </dl>


<strong>Exemplos</strong>:

Inclua um certificado no domínio `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

Remova um certificado do domínio especificado na organização atual.
```
ibmcloud account domain-cert-remove DOMAIN [-f]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:

   <dl>
   <dt>DOMAIN (necessário)</dt>
   <dd>Domínio do qual remover o certificado.</dd>
   <dt>-f (opcional)</dt>
   <dd>Force a exclusão sem confirmação.</dd>
   </dl>
