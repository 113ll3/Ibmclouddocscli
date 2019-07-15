---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Trabalhando com o serviço do ambiente corporativo do Cloud Foundry
{: #ibmcloud_commands_cfee}

Com o {{site.data.keyword.cfee_full}} (CFEE), é possível instanciar múltiplas plataformas Cloud Foundry isoladas e de classificação corporativa on-demand. Instâncias do serviço do IBM Cloud Foundry Enterprise são executadas dentro de sua própria conta no {{site.data.keyword.cloud_notm}}. O ambiente é implementado em hardware isolado (clusters do Kubernetes). Você tem controle total sobre o ambiente, incluindo controle de acesso, capacidade, atualizações de versão, uso de recursos e monitoramento.

Use os comandos a seguir para gerenciar ambientes, organizações, espaços, usuários e funções do CFEE.
{: shortdesc}

## Ambientes cfee ibmcloud
{: #ibmcloud_cfee_environments}

Listar ambientes CFEE:
```
Ambientes cfee ibmcloud
```
{: codeblock}

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:

## Ambiente cfee ibmcloud
{: #ibmcloud_cfee_environment}

Mostrar detalhes de um ambiente CFEE:
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
{: codeblock}

Mostrar o ID de um ambiente CFEE `env_example`:
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## orgs de cfee ibmcloud
{: #ibmcloud_cfee_orgs}

Listar todas as orgs:
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
{: codeblock}

Listar todas as organizações do ambiente CFEE `env_example`:
```
ibmcloud cfee orgs -- env env_exemplo
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Exibir detalhes de uma org:
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
{: codeblock}

Mostrar detalhes de uma organização CFEE `org_example` do ambiente CFEE `env_example`:
```
ibmcloud cfee org org_exemplo -- env env_exemplo
```
{: codeblock}

Mostrar a GUID de uma organização CFEE `org_example`:
```
ibmcloud cfee org org_exemplo -- guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Crie uma organização:
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
{: codeblock}

Criar uma organização CFEE `org_example` do ambiente CFEE `env_example`:
```
ibmcloud cfee org-create org_exemplo -- env env_exemplo
```
{: codeblock}

Criar uma organização CFEE `org_example` com a cota `quote_example`:
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Excluir uma org:
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

Excluir um org. CFEE  ` org_exemplo `:
```
ibmcloud cfee org-delete org_exemplo
```
{: codeblock}

Excluir uma organização CFEE `org_example` do ambiente CFEE `env_example`:
```
ibmcloud cfee org-delete org_exemplo -- env env_exemplo
```
{: codeblock}

Excluir uma organização CFEE `org_example` sem confirmação:
```
ibmcloud cfee org org-delete org_exemplo -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Exiba os usuários na organização especificada por função:
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
{: codeblock}

Exibir usuários na organização CFEE `org_example` do ambiente CFEE `env_example`:
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

Listar todos os usuários na organização CFEE `org_example`:
```
ibmcloud cfee org-users org_exemplo -a
```
{: codeblock}

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
{: codeblock}

Designar a função `BillingManager` para o usuário `test@exmaple.com` na organização
`org_example` do ambiente CFEE `env_example`:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Remova uma função de organização de um usuário (somente gerenciador de organização ou usuário):
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
{: codeblock}

Remover a função `BillingManager` do usuário `test@exmaple.com` da organização
`org_example` do ambiente CFEE `env_example`:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## Espaços de cfee ibmcloud
{: #ibmcloud_cfee_spaces}

Listar todos os espaços:
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

Listar todos os espaços:
```
Espaços de cfee ibmcloud
```
{: codeblock}

Listar todos os espaços da organização `org_example` e do ambiente CFEE `env_example`
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

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
{: codeblock}

Recuperar e exibir o GUID do espaço `space_example`:
```
ibmcloud cfee space space_exemplo -- guid
```
{: codeblock}

Mostrar as regras para todos os grupos de segurança associados ao espaço `space_example`:
```
ibmcloud cfee space space_exemplo--security-group-rules
```
{: codeblock}

Mostrar as informações do espaço `space_example` da organização `org_example` e do ambiente
CFEE `env_example`:
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

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
{: codeblock}

Criar um novo espaço `space_example` na organização `org_example` e no ambiente CFEE `env_example`:
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Renomear um espaço:
```
ibmcloud cfee space-rename OLD_NAME NEW_NAME [-o, --org ORG] [--env ENV]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>OLD_NAME (obrigatório)</dt>
   <dd>O nome antigo do espaço que deve ser renomeado.</dd>
   <dt>NEW_NAME (obrigatório)</dt>
   <dd>O novo nome do espaço para o qual ele foi renomeado.</dd>
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
{: codeblock}

Renomear o espaço `space_example` para `new_pace_example` na organização
`org_example` e no ambiente CFEE `env_example`:
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Excluir um espaço:
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
{: codeblock}

Excluir o espaço `space_example` na organização `org_example` e no ambiente CFEE
`env_example` sem confirmação:
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

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
{: codeblock}

Designar o usuário `test@exmaple.com` para a organização `org_example` e o espaço
`space_example` como a função `SpaceManager` no ambiente `env_example`:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
{: codeblock}

Remover o usuário `test@exmaple.com` para a organização `org_example` e o espaço `space_example` como a função `SpaceManager` no ambiente `env_example`:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
{: codeblock}

Obter todas as funções de espaço do usuário atual na organização `org_example` e no ambiente
`env_example`:
```
ibmcloud cfee space-roles org_exemplo -- env env_exemplo
```
{: codeblock}

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
{: codeblock}

Exibir todos os usuários no espaço `space_example` e na organização `org_example` e no
ambiente `env_example`:
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Faça a solicitação para criar uma nova instância do Cloud Foundry Enterprise Environment:
```
ibmcloud cfee create NAME LOCATION [--cells CELLS] [--isolation ISOLATION] [--private-vlan ID, --public-vlan ID] [--plan ID]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
  <dl>
   <dt>NAME (necessário)</dt>
   <dd>O nome da instância.</dd>
   <dt>LOCATION (necessário)</dt>
   <dd>O local no qual criar a instância.</dd>
   <dt>--cells CELLS</dt>
   <dd>Especifique o número de células para esse CFEE. O padrão é 2 e o mínimo é 1. Em um CFEE de 1 célula, não pode haver alta disponibilidade.</dd>
   <dt>--isolation ISOLATION</dt>
   <dd>Especifique o isolamento do cluster do IBM Kubernetes. As opções são "dedicado" e "compartilhado". O padrão é
"compartilhado", e um cluster "dedicado" tem uma cobrança mais alta.</dd>
   <dt>--private-vlan ID</dt>
   <dd>Especifique o ID da VLAN privada. Por padrão, localizaremos um conjunto de VLANs disponível ou criaremos um par.</dd>
   <dt>--public-vlan ID</dt>
   <dd>Especifique o ID da VLAN pública. Por padrão, localizaremos um conjunto de VLANs disponível ou criaremos um par.</dd>
   <dt>--plan ID</dt>
   <dd>Especifique o ID do plano. Por padrão, forneceremos no plano Standard.</dd>
  </dl>

<strong>Exemplos</strong>:

Crie uma instância denominada `test-cfee` em `dal10`:

```
ibmcloud cfee create test-cfee dal10
```

Crie uma instância `dedicated` chamada `test-cfee` em `dal10`
com `4` células:

```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

Faça uma solicitação para obter uma lista de data centers disponíveis para as regiões de destino
```
ibmcloud cfee create-locations
```
{: codeblock}

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:


## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Verifique se um usuário tem todas as permissões que são necessárias para criar uma instância do CFEE. O comando verifica as seguintes políticas de acesso para o usuário de destino: função de editor para os serviços do CFEE, função de administrador para o serviço do Kubernetes, função de editor para a plataforma e de gerenciador para o acesso de serviço para o serviço Cloud Object Storage e função do desenvolvedor para o espaço atual na organização atual para o fornecimento do Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>O nome do grupo de acesso no qual verificar as permissões. O grupo de acesso padrão é "cfee-provision-access-group".</dd>
   <dt>--output FORMAT</dt>
   <dd>Especifique o formato de saída das permissões, somente JSON é suportado no momento.</dd>
  </dl>
  
<strong>Exemplos</strong>:

Verifique as permissões de criação do CFEE para o usuário `name@example.com`:

```
ibmcloud cfee create-permission-get name@example.com
```

Verifique as permissões de criação do CFEE para o usuário `name@example.com` e no grupo de acesso `test-access-group`:

```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Forneça ao usuário todas as permissões necessárias para criar uma instância do CFEE. O comando cria as seguintes políticas de acesso para o usuário de destino: função de editor para o serviço CFEE, função de administrador para o serviço do Kubernetes, função de editor para a plataforma e função de gerenciador para o acesso de serviço para o serviço Cloud Object Storage e a função de desenvolvedor para o espaço atual na organização atual para o fornecimento do Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
  <dl>
   <dt>USER_NAME ((necessário))</dt>
   <dd>O nome do usuário.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>O nome do grupo de acesso no qual conceder as permissões. O grupo de acesso padrão é "cfee-provision-access-group".</dd>
  </dl>
  
<strong>Exemplos</strong>:

Forneça as permissões de criação do CFEE para o usuário `name@example.com` por meio do grupo
de acesso padrão:
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

Forneça as permissões de criação do CFEE para o usuário `name@example.com` por meio do grupo de acesso `test-access-group`:
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Verifique o status de fornecimento de uma instância do CFEE:
```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>NAME ou ID (necessário)</dt>
   <dd>O nome ou o ID da instância do CFEE.</dd>
   <dt>--poll</dt>
   <dd>Especifique se você gostaria de tornar essa chamada recorrente para pesquisar até estar no estado estável</dd>
   <dt>-- FORMATO de saída</dt>
   <dd>Especifique o formato de saída de status. No momento, somente JSON é suportado.</dd>
  </dl>
