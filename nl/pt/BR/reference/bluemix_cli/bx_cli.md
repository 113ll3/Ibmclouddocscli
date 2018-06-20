---



copyright:

  years: 2015, 2018
lastupdated: "2018-06-08"

---


{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} (ibmcloud) comandos
{: #bluemix_cli}

Versão: 0.7.1

A interface de linha de comandos (CLI) do {{site.data.keyword.Bluemix_notm}} fornece um conjunto de comandos que são agrupados por namespace para que os usuários interajam com o {{site.data.keyword.Bluemix_notm}}.

A partir da versão 0.5.0, o cliente da linha de comandos do {{site.data.keyword.Bluemix_notm}} empacota um cliente da linha de comandos Cloud Foundry em sua instalação. Se você tiver seu próprio cf cli instalado, não use os comandos do {{site.data.keyword.Bluemix_notm}} CLI `ibmcloud [command]` e do Cloud Foundry CLI `cf [command]` de sua própria instalação no mesmo contexto. Em vez disso, use `ibmcloud cf [command]` se desejar usar cf cli para gerenciar recursos do Cloud Foundry no contexto do {{site.data.keyword.Bluemix_notm}} CLI.  Observe que `ibmcloud cf api/login/logout/target` não é permitido e deve-se usar `ibmcloud api/login/logout/target` no lugar.

Desde maio de 2018 comandos da CLI do {{site.data.keyword.Bluemix_notm}} mudaram de `bluemix` e `bx` para `ibmcloud`. No entanto, ainda é possível usar os comandos da CLI `bluemix` e `bx` até que sejam removidos em uma data posterior.
{: tip}

A seguir são listados os comandos detalhados que são suportados pelo {{site.data.keyword.Bluemix_notm}} CLI, incluindo seus nomes, argumentos, opções, pré-requisitos, descrições e exemplos.
{:shortdesc}

**Nota:** *Pré-requisitos* listam quais ações são necessárias antes de usar o comando. Os comandos que não têm ações de pré-requisito listam **Nenhum**. Caso contrário, os pré-requisitos podem incluir uma ou mais das ações a seguir:

<dl>
<dt>Nó de Extremidade</dt>
<dd>Um terminal de API deve ser configurado por meio de <code>bluemix api</code> antes de usar o comando.</dd>
<dt>Login</dt>
<dd>É necessário efetuar login usando o comando <code>bluemix login</code> antes de usar esse comando.
Se estiver efetuando login com o ID federado, use a opção '--sso' para se autenticar com uma senha única ou use '--apikey' para se autenticar com a chave API. Acesse o console do {{site.data.keyword.Bluemix_notm}} **Gerenciar** &gt; **Segurança** &gt; **Chaves API da plataforma** para criar chaves API.
</dd>
<dt>Destino</dt>
<dd>O comando <code>bluemix target</code> deve ser usado para configurar uma organização e um espaço antes de usar esse comando.</dd>
<dt>Docker</dt>
<dd>A CLI do Docker (docker) deve estar instalada para executar esse comando.</dd>
</dl>


Use os índices nas tabelas a seguir para se referir aos comandos ibmcloud usados frequentemente.

## Comandos ibmcloud gerais
{: #bx_commands_index}

<table summary="General ibmcloud commands.">
<caption>Tabela 1. Comandos gerais ibmcloud</caption>
 <thead>
 <th colspan="5">Comandos ibmcloud gerais</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](bx_cli.html#ibmcloud_help)</td>
 <td>[ibmcloud api](bx_cli.html#ibmcloud_api)</td>
 <td>[ibmcloud config](bx_cli.html#ibmcloud_config)</td>
 <td>[ibmcloud info](bx_cli.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](bx_cli.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](bx_cli.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](bx_cli.html#ibmcloud_logout) </td>
 <td>[ibmcloud regiões](bx_cli.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](bx_cli.html#ibmcloud_target)</td>
 <td>[ibmcloud update](bx_cli.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>

 ## Comandos para gerenciar e configurar os serviços de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}} (ibmcloud sl)
  {: #bx_commands_softlayer}

Os comandos para gerenciar a infraestrutura do {{site.data.keyword.BluSoftlayer_notm}} foram mesclados no {{site.data.keyword.Bluemix_notm}} CLI. Para obter informações adicionais sobre como usar a CLI do {{site.data.keyword.Bluemix_notm}} para configurar e gerenciar os serviços de infraestrutura do {{site.data.keyword.BluSoftlayer_notm}}, consulte: [Comandos da infraestrutura da CLI do {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.BluSoftlayer_notm}} (sl ibmcloud)](/docs/cli/reference/softlayer/index.html#softlayer_cli).

 ## Comandos para gerenciar contas, organizações e funções
 {: #bx_commands_account}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar contas, organizações, espaços e funções.">
<caption>Tabela 2. Comandos para gerenciar contas, organizações, espaços e funções</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar contas, organizações, espaços e funções</th>
 </thead>
 <tbody>
 <tr>
 <td>[Ibmcloud conta organizações](bx_cli.html#ibmcloud_account_orgs)</td>
 <td>[conta ibmcloud org](bx_cli.html#ibmcloud_account_org)</td>
 <td>[conta ibmcloud org-create](bx_cli.html#ibmcloud_account_org_create)</td>
 <td>[conta ibmcloud org-replicate](bx_cli.html#ibmcloud_account_org_replicate)</td>
 <td>[conta ibmcloud org-rename](bx_cli.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud Espaços de conta](bx_cli.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](bx_cli.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](bx_cli.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](bx_cli.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](bx_cli.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[Os usuários da organização da conta ibmcloud](bx_cli.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](bx_cli.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](bx_cli.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-funções](bx_cli.html#ibmcloud_account_org_roles)</td>
 <td>[conta ibmcloud org-role-set](bx_cli.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[conta ibmcloud org-role-unset](bx_cli.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](bx_cli.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-funções](bx_cli.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](bx_cli.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](bx_cli.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[Lista conta ibmcloud](bx_cli.html#ibmcloud_account_list)</td>
 <td>[conta ibmcloud org-account](bx_cli.html#ibmcloud_account_org_account)</td>
 <td>[usuários da conta ibmcloud](bx_cli.html#ibmcloud_account_users)</td>
 <td>[account user-remove](bx_cli.html#ibmcloud_account_user_remove)</td>
 <td>[conta ibmcloud user-invite](bx_cli.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[conta ibmcloud user-reinvite](bx_cli.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](bx_cli.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](bx_cli.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](bx_cli.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](bx_cli.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[Ibmcloud iam access-group-delete](bx_cli.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](bx_cli.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](bx_cli.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](bx_cli.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](bx_cli.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](bx_cli.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](bx_cli.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](bx_cli.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](bx_cli.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](bx_cli.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[Ibmcloud iam access-group-policy](bx_cli.html#ibmcloud_iam_access-group-policy)</td>
  <td>[Ibmcloud iam access-group-policy-create](bx_cli.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](bx_cli.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[Ibmcloud iam access-group-policy-delete](bx_cli.html#ibmcloud_iam_access_group_policy_delete)</td>
 </tr>
 </tbody>
 </table>


 ## Comandos para gerenciar recursos e grupos de recursos
{: #bx_commands_resource}

<table summary="Comando ibmcloud que pode ser usado para gerenciar grupos de recursos e recursos.">
  <caption>Tabela 3. Comandos para gerenciar grupos de recursos e recursos</caption>
  <thead>
    <th colspan="5">Comandos para gerenciar recursos e grupos de recursos</th>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud grupos de recursos](bx_cli.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud grupo de recursos](bx_cli.html#ibmcloud_resource_group)</td>
      <td>[resource group-create](bx_cli.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](bx_cli.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud cotas de recurso](bx_cli.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-instances](bx_cli.html#ibmcloud_resource_service_instances)</td>
      <td>[Instância de serviço de recurso ibmcloud](bx_cli.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](bx_cli.html#ibmcloud_resource_service_instance_create)</td>
      <td>[ibmcloud resource service-instance-update](bx_cli.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](bx_cli.html#ibmcloud_resource_service_instance_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-bindings](bx_cli.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](bx_cli.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](bx_cli.html#ibmcloud_resource_service_binding_create)</td>
      <td>[ibmcloud resource service-binding-delete](bx_cli.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[Ibmcloud resource cf-service-instance-migrate](bx_cli.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>
    <tr>
      <td>[ibmcloud cota de recursos](bx_cli.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](bx_cli.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](bx_cli.html#ibmcloud_resource_service_key)</td>
      <td>[Ibmcloud resource service-key-create](bx_cli.html#ibmcloud_resource_service_key_create)</td>
      <td>[ibmcloud resource service-key-delete](bx_cli.html#ibmcloud_resource_service_key_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-aliases](bx_cli.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](bx_cli.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](bx_cli.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](bx_cli.html#ibmcloud_resource_service_alias_update)</td>
      <td>[ibmcloud resource service-alias-delete](bx_cli.html#ibmcloud_resource_service_alias_delete)</td>
    </tr>
    <tr>
      <td>[ibmcloud recursos de procura](bx_cli.html#ibmcloud_resource_search)</td>
      <td>[resource tags](bx_cli.html#ibmcloud_resource_tags)</td>
      <td>[recurso de identificação](bx_cli.html#ibmcloud_resource_tag)</td>
      <td>[recurso tag-create](bx_cli.html#ibmcloud_resource_tag_create)</td>
      <td>[recurso tag-delete](bx_cli.html#ibmcloud_resource_tag_delete)</td>
    </tr>
    <tr>
      <td>[recurso de identificação de conexão](bx_cli.html#ibmcloud_resource_tag_attach)</td>
      <td>[recurso tag-detach](bx_cli.html#ibmcloud_resource_tag_detach)</td>
      <td>[recurso tag-update](bx_cli.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>


 ## Comandos para gerenciar chaves API e políticas
 {: #bx_commands_iam}
 <table summary="Comandos ibmcloud que podem ser usados para gerenciar chaves API e políticas.">
 <caption>Tabela 4. Comandos para gerenciar as chaves API e as políticas</caption>
  <thead>
  <th colspan="5">Comandos para gerenciar chaves API e políticas</th>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-id](bx_cli.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](bx_cli.html#ibmcloud_iam_service_id_create)</td>
   <td>[Ibmcloud iam service-id-update](bx_cli.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](bx_cli.html#ibmcloud_iam_service_id_delete)</td>
   <td>[>ibmcloud iam service-id-de bloqueio](bx_cli.html#ibmcloud_iam_service_id_lock)</td>
  </tr>
  <tr>
   <td>[>ibmcloud iam service-id-unlock](bx_cli.html#ibmcloud_iam_service_id_unlock)</td>
   <td>[ibmcloud iam service-ids](bx_cli.html#ibmcloud_iam_service_ids)</td>
   <td>[ibmcloud iam api-keys](bx_cli.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](bx_cli.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](bx_cli.html#ibmcloud_iam_api_key_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-key-update](bx_cli.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam api-key-lock](bx_cli.html#ibmcloud_iam_api_key_lock)</td>
   <td>[>ibmcloud iam api-key-unlock](bx_cli.html#ibmcloud_iam_api_key_unlock)</td>
   <td>[ibmcloud iam service-api-keys](bx_cli.html#ibmcloud_iam_service_api_keys)</td>
   <td>[ibmcloud iam service-api-key](bx_cli.html#ibmcloud_iam_service_api_key)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key-create](bx_cli.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[Ibmcloud iam service-api-key-update](bx_cli.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](bx_cli.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[>ibmcloud iam service-api-key-bloqueio](bx_cli.html#ibmcloud_iam_service_api_key_lock)</td>
   <td>[>ibmcloud iam service-api-key-unlock](bx_cli.html#ibmcloud_iam_service_api_key_unlock)</td>
  </tr>
  <tr>
    <td>[ibmcloud iam service-policies](bx_cli.html#ibmcloud_iam_service_policies)</td>
    <td>[ibmcloud iam service-policy](bx_cli.html#ibmcloud_iam_service_policy)</td>
    <td>[ibmcloud iam service-policy-create](bx_cli.html#ibmcloud_iam_service_policy_create)</td>
    <td>[ibmcloud iam service-policy-update](bx_cli.html#ibmcloud_iam_service_policy_update)</td>
    <td>[ibmcloud iam service-policy-delete](bx_cli.html#ibmcloud_iam_service_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policies](bx_cli.html#ibmcloud_iam_user_policies)</td>
   <td>[ibmcloud iam user-policy](bx_cli.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](bx_cli.html#ibmcloud_iam_user_policy_create)</td>
   <td>[Ibmcloud iam user-policy-update](bx_cli.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](bx_cli.html#ibmcloud_iam_user_policy_delete)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam oauth-tokens](bx_cli.html#ibmcloud_iam_oauth_tokens)</td>
     <td>[ibmcloud iam dedicated-id-disconnect](bx_cli.html#ibmcloud_iam_dedicated_id_disconnect)</td>
     <td>[ibmcloud iam authorization-policy-create](bx_cli.html#ibmcloud_iam_authorization_policy_create)</td>
     <td>[ibmcloud iam authorization-policy-delete](bx_cli.html#ibmcloud_iam_authorization_policy_delete)</td>
     <td>[ibmcloud iam authorization-policy](bx_cli.html#ibmcloud_iam_authorization_policy)</td>
  </tr>
  <tr>
     <td>[ibmcloud iam authorization-policies](bx_cli.html#ibmcloud_iam_authorization_policies)</td>
  </tr>
  </tbody>
  </table>

 ## Comandos para gerenciar apps cf e domínios, rotas e certificados relacionados ao app
 {: #bx_commands_apps}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar apps cf e domínios, rotas e certificados relacionados ao app.">
<caption>Tabela 5. Comandos para gerenciar aplicativos cf e domínios, rotas e certificados relacionados a aplicativos</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar apps cf e domínios, rotas e certificados relacionados aos apps</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](bx_cli.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](bx_cli.html#ibmcloud_app_list)</td>
 <td>[Ibmcloud app show](bx_cli.html#ibmcloud_app_show)</td>
 <td>[ibmcloud app delete](bx_cli.html#ibmcloud_app_delete)</td>
 <td>[ibmcloud app rename](bx_cli.html#ibmcloud_app_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud app start](bx_cli.html#ibmcloud_app_start)</td>
 <td>[ibmcloud app stop](bx_cli.html#ibmcloud_app_stop)</td>
 <td>[ibmcloud app restart](bx_cli.html#ibmcloud_app_restart)</td>
 <td>[ibmcloud app restage](bx_cli.html#ibmcloud_app_restage)</td>
 <td>[ibmcloud app instance-restart](bx_cli.html#ibmcloud_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[ibmcloud app eventos](bx_cli.html#ibmcloud_app_events)</td>
 <td>[ibmcloud arquivos de app](bx_cli.html#ibmcloud_app_files)</td>
 <td>[Ibmcloud logs de app](bx_cli.html#ibmcloud_app_logs)</td>
 <td>[ibmcloud app env](bx_cli.html#ibmcloud_app_env)</td>
 <td>[ibmcloud app env-set](bx_cli.html#ibmcloud_app_env_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud app env-unset](bx_cli.html#ibmcloud_app_env_unset)</td>
 <td>[ibmcloud app stacks](bx_cli.html#ibmcloud_app_stacks)</td>
 <td>[ibmcloud app stack-show](bx_cli.html#ibmcloud_app_stack_show)</td>
 <td>[ibmcloud app manifest-create](bx_cli.html#ibmcloud_app_manifest_create)</td>
 <td>[ibmcloud app domain-cert](bx_cli.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](bx_cli.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](bx_cli.html#ibmcloud_app_domain_cert_remove)</td>
  <td>[ibmcloud app domains](bx_cli.html#ibmcloud_app_domains)</td>
  <td>[ibmcloud app domain-create](bx_cli.html#ibmcloud_app_domain_create)</td>
  <td>[ibmcloud app domain-delete](bx_cli.html#ibmcloud_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud app shared-domain-create](bx_cli.html#ibmcloud_app_shared_domain_create)</td>
  <td>[ibmcloud app shared-domain-delete](bx_cli.html#ibmcloud_app_shared_domain_delete)</td>
  <td>[ibmcloud app rotas](bx_cli.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](bx_cli.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](bx_cli.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](bx_cli.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](bx_cli.html#ibmcloud_app_route_create)</td>
  <td>[Delete-route app ibmcloud](bx_cli.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](bx_cli.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>

 ## Comandos para gerenciar serviços do {{site.data.keyword.Bluemix_notm}}
 {: #bx_commands_services}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar serviços do {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabela 6. Comandos para gerenciar {{site.data.keyword.Bluemix_notm}} serviços</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar serviços do {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud ofertas de serviço](bx_cli.html#ibmcloud_service_offerings)</td>
 <td>[ibmcloud lista de serviços](bx_cli.html#ibmcloud_service_list)</td>
 <td>[ibmcloud serviço show](bx_cli.html#ibmcloud_service_show)</td>
 <td>[ibmcloud serviço criar](bx_cli.html#ibmcloud_service_create)</td>
 <td>[ibmcloud serviço de atualização](bx_cli.html#ibmcloud_service_update)</td>
 </tr>
 <tr>
 <td>[ibmcloud serviço delete](bx_cli.html#ibmcloud_service_delete)</td>
 <td>[ibmcloud serviço rename](bx_cli.html#ibmcloud_service_rename)</td>
 <td>[ibmcloud serviço bind](bx_cli.html#ibmcloud_service_bind)</td>
 <td>[Service unbind ibmcloud](bx_cli.html#ibmcloud_service_unbind)</td>
 <td>[ibmcloud service key-create](bx_cli.html#ibmcloud_service_key_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud service key-delete](bx_cli.html#ibmcloud_service_key_delete)</td>
 <td>[ibmcloud chaves de serviço](bx_cli.html#ibmcloud_service_keys)</td>
 <td>[ibmcloud service key-show](bx_cli.html#ibmcloud_service_key_show)</td>
 <td>[serviço ibmcloud user-provided-create](bx_cli.html#ibmcloud_service_user_provided_create)</td>
 <td>[serviço ibmcloud user-provided-update](bx_cli.html#ibmcloud_service_user_provided_update)</td>
 </tr>
  </tbody>
 </table>


 ## Comandos para gerenciar configurações de catálogo, de plug-ins e de faturamento
 {: #bx_commands_settings}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar o catálogo, os plug-ins, o faturamento e as configurações de segurança do {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabela 7. Comandos para gerenciar as configurações de catálogo, de plug-ins, de faturamento e de segurança do
{{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Comandos para gerenciar o catálogo, os plug-ins, o faturamento e as configurações de segurança do {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](bx_cli.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud entrada no catálogo](bx_cli.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](bx_cli.html#ibmcloud_catalog_entry_create)</td>
  <td>[Update-ibmcloud entrada no catálogo](bx_cli.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](bx_cli.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](bx_cli.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](bx_cli.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](bx_cli.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catálogo de modelos](bx_cli.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](bx_cli.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](bx_cli.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catálogo locais](bx_cli.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catálogo de execução](bx_cli.html#ibmcloud_catalog_runtime)</td>
  <td>[Ibmcloud tempos no catálogo](bx_cli.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](bx_cli.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](bx_cli.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](bx_cli.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](bx_cli.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](bx_cli.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](bx_cli.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin install](bx_cli.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](bx_cli.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](bx_cli.html#ibmcloud_plugin_update)</td>
  <td>[Uso de conta de cobrança ibmcloud](bx_cli.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](bx_cli.html#ibmcloud_billing_org_usage)</td>
</tr>
<tr>
  <td>[Ibmcloud billing resource-group-usage](bx_cli.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[Ibmcloud billing resource-instances-usage](bx_cli.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ## Gerenciar Cloud Foundry Enterprise Environments (experimental)
{: #bx_commands_cfee}

<table summary="Manage Cloud Foundry Enterprise Environments (experimental)">
<caption>Tabela 8. Gerenciar ambientes corporativos do Cloud Foundry (experimental)</caption>
 <thead>
 <th colspan="5">Gerenciar Cloud Foundry Enterprise Environments (experimental)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee ambientes](bx_cli.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee ambiente](bx_cli.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>

## ibmcloud help
{: #ibmcloud_help}
Exiba a ajuda geral para comandos integrados de primeiro nível e namespaces suportados da CLI {{site.data.keyword.Bluemix_notm}} ou a ajuda para um comando ou namespace integrado específico.

```
Ibmcloud help [ COMMAND | NAMESPACE ]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE (opcional)</dt>
   <dd>O comando ou namespace para o qual a ajuda é exibida. Se não especificado, a ajuda geral para a CLI do {{site.data.keyword.Bluemix_notm}} será mostrada.</dd>
   </dl>



<strong>Exemplos</strong>:

Exiba a ajuda geral para a CLI do {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud help
```

Exiba a ajuda para o comando `info`:

```
Informações de ajuda ibmcloud
```



## ibmcloud api
{: #ibmcloud_api}
Configure ou visualize o terminal da API do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>API_ENDPOINT (opcional)</dt>
   <dd>O terminal da API que é o destino, por exemplo, `https://api.chinabluemix.net`. Se as opções *API_ENDPOINT* e `--unset` não forem ambas especificadas, o terminal de API atual será exibido.</dd>
   <dt>--unset (opcional)</dt>
   <dd>Remova a configuração do terminal de API.</dd>
   <dt>--skip-ssl-validation (opcional)</dt>
   <dd>Validação SSL de bypass de solicitações de HTTP.</dd>
   </dl>
<strong>Exemplos</strong>:

Configure o terminal da API para api.chinabluemix.net:

```
Ibmcloud api api.chinabluemix.net
```

```
Api https://api.chinabluemix.net--skip-ssl-validation
```

Visualize o terminal de API atual:

```
ibmcloud api
```

Desconfigure o terminal de API:

```
Ibmcloud api -- unset
```

## Ibmcloud config
{: #ibmcloud_config}


Grave os valores padrão no arquivo de configuração.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>O valor de tempo limite para solicitações de HTTP. O valor padrão é 60 segundos.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Rastreie solicitações de HTTP para o terminal ou arquivo especificado.</dd>
   <dt>--color true|false</dt>
   <dd>Ative ou desative a saída de cor. A saída de cor é ativada por padrão.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Configure um código padrão de idioma. Se LOCALE for <i>CLEAR</i>, o código de idioma anterior será excluído.</dd>
   <dt>--check-version true|false</dt>
   <dd>Ative ou desative a verificação de versão da CLI.</dd>
   </dl>

Somente uma dessas opções pode ser especificada por vez.

<strong>Exemplos</strong>:

Configure o tempo limite de solicitação de HTTP como 30 segundos:

```
Ibmcloud config -- http-timeout 30
```

Ative a saída de rastreio para solicitações de HTTP:

```
Ibmcloud config -- trace true
```

Rastreie solicitações de HTTP para um arquivo especificado */home/usera/my_trace*:

```
Ibmcloud config -- trace
```

Desative a saída de cor:

```
Ibmcloud config -- color false
```

Configure o código de idioma como zh_Hans:

```
Ibmcloud config -- locale zh_Hans
```

Limpe as configurações do código de idioma:

```
Ibmcloud config -- locale CLEAR
```



## ibmcloud info
{: #ibmcloud_info}

Visualize as informações básicas do {{site.data.keyword.Bluemix_notm}}, incluindo a região atual, a versão do controlador de nuvem e alguns terminais úteis, como terminais para login e a troca de token de acesso.

```
ibmcloud info
```

<strong>Pré-requisitos</strong>: Terminal


## Cf ibmcloud
{: #ibmcloud_cf}

Chamar o CF CLI integrado

```
Ibmcloud [ -q, -- quiet ] cf COMMAND ...
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Desativar a mensagem "Chamando comando cf..."</dd>
</dl>

<strong>Exemplos</strong>:

Liste apps cf:

```
Ibmcloud cf apps
```

Listar serviços cf sem a mensagem "Chamando comando cf...":

```
Ibmcloud -q cf services
```


## ibmcloud login
{: #ibmcloud_login}

Efetue login do usuário.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>Pré-requisitos</strong>: Nenhum

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opções de comando</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i> (opcional)</dt>
  <dd> Terminal de API (Por exemplo: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY ou @API_KEY_FILE_PATH</i>
  <dd> Conteúdo da chave API ou o caminho de um arquivo de chave API indicado por @</dd>
  <dt> --sso (opcional) </dt>
  <dd> Use uma senha única para efetuar login </dd>
  <dt> -u <i>USERNAME</i> (opcional)</dt>
  <dd> Nome do usuário</dd>
  <dt> -p <i>PASSWORD</i> (opcional)</dt>
  <dd> Senha</dd>
  <dt> -c <i>ACCOUNT_ID</i> (opcional) </dt>
  <dd> ID da conta de destino</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (opcional) </dt>
  <dd> Nome do grupo de recursos de destino</dd>
  <dt> -o <i>ORG</i> (opcional)</dt>
  <dd> Nome da organização de destino (descontinuado, use 'ibmcloud target -o ORG')</dd>
  <dt> -s <i>SPACE</i> (opcional) </dt>
  <dd> Nome do espaço de destino (descontinuado, use 'ibmcloud target -s SPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Forçar a autenticação com o servidor de login em vez do IAM público</dd>
  <dt> --skip-ssl-validation (opcional) </dt>
  <dd> Validação SSL de bypass de solicitações de HTTP. Essa opção não é recomendada.</dd>
</dl>

<strong>Exemplos</strong>:

#### Login interativo

```
ibmcloud login
```

Efetuar login com nome de usuário e senha e configurar a conta de destino, a organização e o espaço:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Efetuar login com uma senha única e configurar a conta de destino, a organização e o espaço

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Efetuar login com a chave API e configurar os destinos:

#### A chave API tem conta associada

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### A chave API não tem conta associada

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> se a chave API tiver uma conta associada, não será permitido alternar para outra conta.

#### Usar uma senha única

```
ibmcloud login -u UserID --sso
```

Em seguida, a CLI fornecerá um link de URL e solicitará a senha:
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

Abra o link no navegador, que fornecerá instrução para obter a senha. Digite a senha especificada no console e você poderá efetuar login.

## ibmcloud logout
{: #ibmcloud_logout}

Efetue logout do usuário.

```
ibmcloud logout
```

<strong>Pré-requisitos</strong>: Nenhum

## ibmcloud regions
{: #ibmcloud_regions}

Visualize as informações para todas as regiões no {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Pré-requisitos</strong>: Terminal


## ibmcloud target
{: #ibmcloud_target}


Configure ou visualize a conta de destino, região, organização ou espaço.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i> (opcional)</dt>
   <dd>Nome da região a ser alternada, como 'us-south' ou 'eu-gb'.</dd>
   <dt>-c <i>ACCOUNT_ID</i> (opcional)</dt>
   <dd>O ID da conta que será o destino.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (opcional)</dt>
   <dd>Nome do grupo de recursos</dd>
   <dt>--cf</dt>
   <dd>Selecione de forma interativa o espaço e a organização de destino</dd>
   <dt>-o <i>ORG_NAME</i> (opcional)</dt>
   <dd>O nome da organização que será o destino.</dd>
   <dt>-s <i>SPACE_NAME</i> (opcional)</dt>
   <dd>O nome do espaço que será o destino.</dd>
   </dl>
Se nenhuma das opções for especificada, a conta, a região, a organização e o espaço atuais serão exibidos.

<strong>Exemplos</strong>:

Configure a conta atual, a organização e o espaço:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Alterne para uma nova região:

```
ibmcloud target -r eu-gb
```

Visualize a conta, a região, a organização e o espaço atuais:

```
ibmcloud target
```

## Atualizar ibmcloud
{: #ibmcloud_update}

Atualize a CLI para a versão mais recente.

```
Atualizar ibmcloud [ -f ]
```

<strong>Pré-requisitos</strong>: Nenhum

<strong>Opções de comando</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forçar atualização sem confirmação. Privilégio de administrador é necessário.</dd>
</dl>

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

## Account org ibmcloud
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
ibmcloud account spaces [-o ORG_NAME] [-r REGION-NAME]
```

<strong>Opções de comando</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Nome da organização. Listar os espaços sob a organização especificada. Padrão para a organização atual, se não especificada.</dd>
   <dt>-r</dt>
   <dd>Nome da região. Listar os espaços sob a região especificada. Padrão para região atual, se não especificado.</dd>
   </dl>



## Espaço conta ibmcloud
{: #ibmcloud_account_space}

Esse comando tem a mesma função e opções que o comando [cf space ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.


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
   <dd>O nome da função de organização para a qual esse usuário é designado. Por
exemplo:
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
   <dd>O nome da função de organização da qual esse usuário é removido. Por
exemplo:
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
   <dd>O nome da função de espaço para a qual esse usuário é designado. Por
exemplo:
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
   <dd>O nome da função de espaço da qual esse usuário é removido. Por
exemplo:
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

## ibmcloud iam access-groups
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

## Grupo de acesso iam ibmcloud
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

## ibmcloud iam access-group-create
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

## Ibmcloud iam access-group-update
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

## Ibmcloud iam access-group-delete
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

## Ibmcloud iam access-group-users
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

## Ibmcloud iam access-group-user-add
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

## Ibmcloud iam access-group-user-remove
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

## Ibmcloud iam access-group-user-purge
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

## Ibmcloud iam access-group-service-ids
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

## Ibmcloud iam access-group-service-id-add
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

## Ibmcloud iam access-group-service-id-remove
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

## Ibmcloud iam access-group-service-id-purge
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

## Ibmcloud iam access-group-policies
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

## Ibmcloud iam access-group-policy
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

## Ibmcloud iam access-group-policy-create
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

## ibmcloud iam access-group-policy-update
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

## Ibmcloud iam access-group-policy-delete
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

## IDs de serviço iam ibmcloud
{: #ibmcloud_iam_service_ids}

Listar todos os IDs de serviço

```
Ibmcloud iam service-ids [ -- uuid ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Mostrar somente o UUID dos IDs de serviço</dd>
</dl>

<strong>Exemplos</strong>:
liste o UUID de todos os IDs de serviço na conta atual

```
ibmcloud iam service-ids --uuid
```


## Ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Exibir detalhes de um ID de serviço

```
Ibmcloud iam service-id (NAME | UUID) [ -- uuid ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>--uuid</dt>
  <dd>Exibir o UUID do ID de serviço</dd>
</dl>

<strong>Exemplos</strong>:

Mostre detalhes do ID de serviço `sample-test`

```
Ibmcloud iam service-id sample-teste
```
Mostrar detalhes do ID do serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
Ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## Ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Criar um ID de serviço

```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço</dd>
  <dt>-d, --description</dt>
  <dd>Descrição do ID de serviço</dd>
  <dt>-- bloqueio</dt>
  <dd>Bloquear o ID do serviço ao criá-lo</dd>
</dl>

<strong>Exemplos</strong>:

Crie um ID de serviço com o nome de serviço `sample-test` e a descrição `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Criar um ID de serviço bloqueado com o nome do serviço `sample-teste` e a descrição `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' -- bloqueio
```


## Ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Atualizar um ID de serviço

```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>-n, --name</dt>
  <dd>Novo nome do serviço</dd>
  <dt>-d, --description</dt>
  <dd>Nova descrição do serviço</dd>
  <dt>-f, --force</dt>
  <dd>Atualizar sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Renomeie o ID de serviço `sample-test` para `sample-test-2` sem confirmação

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Atualize a descrição de serviço `sample-teste`

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Renomear o ID de serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` para
`sample-test-3` com uma nova descrição

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```


## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Excluir um ID de serviço

```
Ibmcloud iam service-id-delete (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>-f, --force</dt>
  <dd>Excluir sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Exclua o ID de serviço `sample-teset` sem confirmação

```
Ibmcloud iam service-id-delete sample-teset -f
```

Excluir o ID do serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
Ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## Ibmcloud iam service-id-bloqueio
{: #ibmcloud_iam_service_id_lock}

Bloquear um ID de serviço

```
Ibmcloud iam service-id-bloqueio (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Bloquear ID de serviço `sample-teset` sem confirmação

```
Ibmcloud iam service-id-bloqueio sample-teset -f
```

Bloquear ID do serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
Ibmcloud iam service-id-de bloqueio ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Desbloquear um ID de serviço

```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome do serviço, exclusivo com UUID</dd>
  <dt>UUID (necessário)</dt>
  <dd>UUID do serviço, exclusivo com NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Desbloquear ID de serviço `sample-teset` sem confirmação

```
Ibmcloud iam service-id-unlock sample-teset -f
```

Desbloquear ID de serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
Ibmcloud iam service-id-desbloquear ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Liste todas as chaves API da plataforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-keys
```

<strong>Pré-requisitos</strong>: Terminal, Login

## Ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Crie uma nova chave API da plataforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser criada.</dd>
<dt>-d <i>DESCRIPTION</i> (opcional)</dt>
<dd>Descrição da chave de API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Salve as informações da chave API para o arquivo especificado. Se não configuradas, o conteúdo JSON será exibido.</dd>
<dt>-- bloqueio</dt>
<dd>Bloquear a chave API ao criá-la</dd>
</dl>

<strong>Exemplos</strong>:

Crie uma chave API e salve em um arquivo

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Criar uma chave API bloqueada com o nome "test-key"

```
Ibmcloud iam api-key-create test-key -- bloqueio
```

## Ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Atualize uma chave API da plataforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>O nome antigo da chave API a ser atualizada, exclusivo com UUID</dd>
<dt>UUID (necessário)</dt>
<dd>O UUID da chave API a ser atualizada, exclusivo com NAME</dd>
<dt>-n <i>NAME</i> (opcional)</dt>
<dd>O nome novo da chave API</dd>
<dt>-d <i>DESCRIPTION</i> (opcional)</dt>
<dd>A nova descrição da chave API</dd>
</dl>

<strong>Exemplos</strong>:

Atualize a descrição de uma chave API:

```
ibmcloud iam api-key-update MyKey -d "the new description of my key"
```

## Ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

Excluir uma chave API da plataforma {{site.data.keyword.Bluemix_notm}}

```
Ibmcloud iam api-key-delete (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser excluída, exclusivo com UUID</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser excluída, exclusivo com NAME</dd>
<dt>-f, --force</dt>
<dd>Force a exclusão sem confirmação.</dd>
</dl>

## Ibmcloud api-key-bloqueio
{: #ibmcloud_iam_api_key_lock}

Bloquear uma chave API da plataforma

```
Ibmcloud iam api-key-bloqueio (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser bloqueada, exclusivo com UUID</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser bloqueada, exclusivo com NAME</dd>
<dt>-f, --force</dt>
<dd>Forçar a fechadura sem confirmação.</dd>
</dl>

<strong>Exemplos</strong>:

Bloquear teste chave API-api-key

```
Ibmcloud iam api-key-bloqueio de teste api-key
```

Bloquear a chave API com o UUID fornecido sem confirmação

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## Ibmcloud api-key-desbloquear
{: #ibmcloud_iam_api_key_unlock}

Desbloquear uma chave API da plataforma

```
Ibmcloud iam api-key-desbloquear (NAME | UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
<dl>
<dt>NAME (necessário)</dt>
<dd>Nome da chave API a ser desbloqueada, exclusivo com UUID</dd>
<dt>UUID (necessário)</dt>
<dd>UUID da chave API a ser desbloqueada, exclusivo com NAME</dd>
<dt>-f, --force</dt>
<dd>Forçar o desbloqueio sem confirmação.</dd>
</dl>

<strong>Exemplos</strong>:

Desbloquear chave API de teste api-key

```
Ibmcloud iam api-key-unlock-api-chave de teste
```

Desbloquear a chave API com o UUID fornecido sem confirmação

```
Ibmcloud iam api-key-desbloquear ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe -- force
```

## Ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Listar todas as chaves API de um serviço

```
Ibmcloud iam service-api-keys (SERVICE_ID_NAME | SERVICE_ID_UUID) [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Exibir as chaves API de serviço sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Liste todas as chaves API do serviço `sample-service`:

```
Ibmcloud iam service-api-keys sample-service
```

## Ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Listar detalhes de uma chave API de serviço

```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>--uuid</dt>
  <dd>Exibir o UUID da chave API de serviço</dd>
  <dt>-f, --force</dt>
  <dd>Exibir a chave API de serviço sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Mostrar detalhes da chave API de serviço `sample-key` do serviço `sample-serviço`:

```
Ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Criar uma chave API de serviço

```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [-f, --force] [--lock]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>NAME (necessário)</dt>
  <dd>Nome ou nova chave API de serviço criada</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-d, --description</dt>
  <dd>Descrição da chave de API</dd>
  <dt>--file</dt>
  <dd>Salve as informações da chave API para o arquivo especificado. Se não configuradas, o conteúdo JSON será exibido.</dd>
  <dt>-f, --force</dt>
  <dd>Forçar a criação sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Criar uma chave API de serviço `sample-key` para o serviço
`sample-service` sem confirmação:

```
Ibmcloud iam service-api-key-create sample-key sample-service -f
```

## Ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Atualizar uma chave API de serviço

```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-n, --name</dt>
  <dd>Novo nome da chave API de serviço</dd>
  <dt>-d, --description</dt>
  <dd>Nova descrição da chave API de serviço</dd>
  <dt>-f, --force</dt>
  <dd>Atualizar sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Renomeie a chave API de serviço `sample-key` para `new-sample-key`:

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## Ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Excluir uma chave API de serviço

```
ibmcloud iam service-api-key-delete (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Excluir sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Excluir a chave API de serviço `sample-key` do ID de serviço `sample-serviço`:

```
Ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Bloquear uma chave API de serviço

```
ibmcloud iam service-api-key-lock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Bloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Bloquear a chave API de serviço `sample-key` do ID do serviço `sample-service`:

```
Ibmcloud iam service-api-key-bloqueio sample-key sample-service
```

## Ibmcloud iam service-api-key-desbloquear
{: #ibmcloud_iam_service_api_key_unlock}

Desbloquear uma chave API de serviço

```
ibmcloud iam service-api-key-unlock (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>APIKEY_NAME (necessário)</dt>
  <dd>Nome da chave API, exclusivo com APIKEY_UUID</dd>
  <dt>APIKEY_UUID (necessário)</dt>
  <dd>UUID da chave API, exclusivo com APIKEY_NAME</dd>
  <dt>SERVICE_ID_NAME (necessário)</dt>
  <dd>Nome do ID do serviço, exclusivo com SERVICE_ID_UUID</dd>
  <dt>SERVICE_ID_UUID (necessário)</dt>
  <dd>UUID do ID do serviço, exclusivo com SERVICE_ID_NAME</dd>
  <dt>-f, --force</dt>
  <dd>Desbloquear sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Desbloquear a chave API de serviço `sample-key` do ID do serviço `sample-service`:

```
Ibmcloud iam service-api-key-desbloquear sample-key sample-service
```

## Ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Listar as políticas do usuário `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

<strong>Pré-requisitos</strong>: terminal, login, conta de destino

<strong>Opções de comando</strong>:
<dl>
<dt>USER_NAME ((necessário))</dt>
<dd>Nome do usuário ao qual as políticas pertencem</dd>
</dl>

<strong>Exemplos</strong>:

Listar as políticas do usuário `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

## Ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Exibir detalhes de uma política do usuário

```
Ibmcloud iam user-policy USER_NAME POLICY_ID
```

<strong>Pré-requisitos</strong>: terminal, login, conta de destino

<strong>Opções de comando</strong>:
<dl>
<dt>USER_NAME ((necessário))</dt>
<dd>Nome do usuário ao qual a política pertence</dd>
<dt>POLICY_ID (necessário)</dt>
<dd>ID da política</dd>
</dl>

<strong>Exemplos</strong>:

Liste a política `0bb730daa` do usuário `name@example.com`:

```
Ibmcloud iam user-policy name@example.com 0bb730daa
```

## Ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Criar uma política do usuário

```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Pré-requisitos</strong>: terminal, login, conta de destino

<strong>Opções de comando</strong>:
<dl>
<dt>USER_NAME ((necessário))</dt>
<dd>Nome do usuário ao qual a política pertence</dd>
<dt>--file <i>FILE</i> (opcional)</dt>
<dd>Arquivo JSON de definição de política</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (opcional)</dt>
<dd>Os nomes de função da definição de política. Para funções suportadas de um serviço específico, execute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opção é exclusiva com '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (opcional)</dt>
<dd>Nome de serviço da definição de política; é exclusivo com a sinalização '--file'.</dd>
<dt>-- serivce-instance <i>SERVICE_INSTANCE_GUID</i> (opcional)</dt>
<dd>GUID da instância de serviço da definição de política. Isso é exclusivo com a sinalização '-- file'.</dd>
<dt>--region <i>REGION</i> (opcional)</dt>
<dd>Região da definição de política; é exclusiva com a sinalização '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (opcional)</dt>
<dd>Tipo de recurso da definição de política; é exclusivo com a sinalização '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (opcional)</dt>
<dd>Recurso da definição de política; é exclusivo com a sinalização '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (opcional)</dt>
<dd>Nome do grupo de recursos; é exclusivo com as sinalizações '--file', '--resource' e '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (opcional)</dt>
<dd>ID do grupo de recursos; é exclusivo com as sinalizações '--file', '--resource' e '--resource-group-name'.</dd>
</dl>

<strong>Exemplos</strong>:

Crie a política de usuário para o usuário `name@example.com` do arquivo JSON de política `policy.json`:

```
Ibmcloud iam user-policy-create name@example.com -- file
```

Dê a `name@example.com` a função `Administrator` para todos os recursos `sample-service`:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Fornecer a função de `Editor` a `name@example.com` para o recurso `key123` da
instância de serviço de amostra com o GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` na região `us-south`:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance
d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Dê a `name@example.com` a função `Operator` para o grupo de recursos com ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Dê a `name@example.com` a função `Viewer` para os membros do grupo de recursos `sample-resource-group`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Dê a `name@example.com` a função `Viewer` para os membros do grupo de recursos com ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## Ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Atualizar uma política do usuário

```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]}
```

<strong>Pré-requisitos</strong>: terminal, login, conta de destino

<strong>Opções de comando</strong>:
<dt>USER_NAME ((necessário))</dt>
<dd>Nome do usuário ao qual a política pertence</dd>
<dt>POLICY_ID (necessário)</dt>
<dd>ID da política a ser atualizada</dd>
<dt>--file <i>FILE</i> (opcional)</dt>
<dd>Arquivo JSON de definição de política</dd>
<dt>--roles <i>ROLE_NAME1,ROLE_NAME2...</i> (opcional)</dt>
<dd>Os nomes de função da definição de política. Para funções suportadas de um serviço específico, execute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opção é exclusiva com '--file'.</dd>
<dt>--service-name <i>SERVICE_NAME</i> (opcional)</dt>
<dd>Nome de serviço da definição de política; é exclusivo com a sinalização '--file'.</dd>
<dt>-- serivce-instance <i>SERVICE_INSTANCE_GUID</i> (opcional)</dt>
<dd>GUID da instância de serviço da definição de política. Isso é exclusivo com a sinalização '-- file'.</dd>
<dt>--region <i>REGION</i> (opcional)</dt>
<dd>Região da definição de política; é exclusiva com a sinalização '--file'.</dd>
<dt>--resource-type <i>RESOURCE_TYPE</i> (opcional)</dt>
<dd>Tipo de recurso da definição de política; é exclusivo com a sinalização '--file'.</dd>
<dt>--resource <i>RESOURCE</i> (opcional)</dt>
<dd>Recurso da definição de política; é exclusivo com a sinalização '--file'.</dd>
<dt>--resource-group-name <i>RESOURCE_GROUP_NAME</i> (opcional)</dt>
<dd>Nome do grupo de recursos; é exclusivo com as sinalizações '--file', '--resource' e '--resource-group-id'.</dd>
<dt>--resource-group-id <i>RESOURCE_GROUP_ID</i> (opcional)</dt>
<dd>ID do grupo de recursos; é exclusivo com as sinalizações '--file', '--resource' e '--resource-group-name'.</dd>
</dl>

<strong>Exemplos</strong>:

Atualize a política de usuário com aquela do arquivo JSON

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Atualize a política de usuário para dar a `name@example.com` a função `Administrator` para todos os recursos `sample-service`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Atualizar a política do usuário para fornecer a função de `Editor` a `name@example.com` para
o recurso `key123` da instância de serviço de amostra com o GUID `d161aeea-fd02-40f8-a487-df1998bd69a9`
na região `us-south`:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Atualize a política de usuário para dar a `name@example.com` a função `Operator` para o grupo de recursos com ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Atualize a política de usuário para dar a `name@example.com` a função `Viewer` para os membros do grupo de recursos `sample-resource-group`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Atualize a política de usuário para dar a `name@example.com` a função `Viewer` para membros do grupo de recursos com ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## Ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Excluir uma política do usuário

```
ibmcloud iam user-policy-delete USER_ID POLICY_ID [-f, --force]
```

<strong>Pré-requisitos</strong>: terminal, login, conta de destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Exclua a política do usuário sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:
excluir as políticas `user-policy-id` do usuário `name@example.com`:

```
Delete-ibmcloud iam user-policy name@example.com user-policy-id
```

Excluir as políticas `user-policy-id` do usuário `name@example.com` sem confirmação:

```
Ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## As políticas de serviço iam ibmcloud
{: #ibmcloud_iam_service_policies}

Listar todas as políticas de serviço do serviço especificado

```
ibmcloud iam service-policies SERVICE_ID [--json] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ID (necessário)</dt>
  <dd>Nome ou UUID do ID do serviço</dd>
  <dt>-json</dt>
  <dd>Exibir a política no formato JSON</dd>
  <dt>-f, --force</dt>
  <dd>Exibir políticas de serviço sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Liste políticas do serviço `test`:

```
ibmcloud iam service-policies test
```
Listar políticas de serviço `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
Ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```


## Ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Exibir detalhes de uma política de serviço

```
ibmcloud iam service-policy SERVICE_ID POLICY_ID [--json] [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ID (necessário)</dt>
  <dd>Nome ou UUID do ID do serviço</dd>
  <dt>POLICY_ID (necessário)</dt>
  <dd>ID da política de serviço<dd>
  <dt>-json</dt>
  <dd>Exibir a política no formato JSON</dd>
  <dt>-f, --force</dt>
  <dd>Exibir política de serviço sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Mostre a política `140798e2-8ea7db3` do serviço `test`:

```
Ibmcloud iam service-policies test 140798e2-8ea7db3
```
Mostrar a política `140798e2-8ea7db3` de serviço
`ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
Ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```


## Ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Criar uma política de serviço

```
ibmcloud iam service-policy-create SERVICE_ID {--file JSON_FILE | -r, --roles ROLE_NAME1,ROLE_NAME2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ID (necessário)</dt>
  <dd>Nome ou UUID do ID do serviço</dd>
  <dt>--file</dt>
  <dd>Arquivo JSON de definição de política. Isso é exclusivo com as sinalizações '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' e '--resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Os nomes de função da definição de política. Para funções suportadas de um serviço específico, execute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opção é exclusiva com '--file'.</dd>
  <dt>--service-name</dt>
  <dd>Nome do serviço da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>-- service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID da instância de serviço da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>-region</dt>
  <dd>Região da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>--resource-type</dt>
  <dd>Tipo de recurso da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>--resource</dt>
  <dd>Recurso da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Criar política de serviço sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Crie a política de serviço do arquivo JSON para o serviço `test`:

```
ibmcloud iam service-policy-create test --file @policy.json
```
Criar a política de serviço por meio do arquivo JSON para o serviço
`ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
Ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -- file
```


## Ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Atualizar uma política de serviço

```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [-f, --force]",
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ID (necessário)</dt>
  <dd>Nome ou UUID do ID do serviço</dd>
  <dt>POLICY_ID (necessário)</dt>
  <dd>ID da política de serviço<dd>
  <dt>--file</dt>
  <dd>Arquivo JSON de definição de política. Isso é exclusivo com as sinalizações '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' e 'resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Os nomes de função da definição de política. Para funções suportadas de um serviço específico, execute 'ibmcloud iam roles --service SERVICE_NAME'. Esta opção é exclusiva com '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome do serviço da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>-service-instance <i>SERVICE_INSTANCE_GUID</i></dt>
  <dd>GUID da instância de serviço da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>-region</dt>
  <dd>Região da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo de recurso da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>-resource</dt>
  <dd>Recurso da definição de política. Isso é exclusivo com a sinalização '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID do grupo de recursos. Esta opção é exclusiva com '--file' e '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Atualizar a política de serviço sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Atualize a política de serviço `140798e2-8ea7db3` do arquivo JSON para o serviço `test`:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Atualizar a política de serviço `140798e2-8ea7db3` por meio do arquivo JSON para o serviço
`ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## Ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Excluir uma política de serviço

```
ibmcloud iam service-policy-delete SERVICE_ID POLICY_ID [-f, --force]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SERVICE_ID (necessário)</dt>
  <dd>Nome ou UUID do ID do serviço</dd>
  <dt>POLICY_ID (necessário)</dt>
  <dd>ID da política de serviço<dd>
  <dt>-f, --force</dt>
  <dd>Excluir sem confirmação</dd>
</dl>

<strong>Exemplos</strong>:

Exclua a política `140798e2-8ea7db3` do serviço `test`

```
Ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Excluir a política `140798e2-8ea7db3` de serviço
`ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
Ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Recuperar e exibir os tokens OAuth da sessão atual

```
ibmcloud iam oauth-tokens
```

<strong>Pré-requisitos</strong>: Login, Destino

<strong>Opções de comando</strong>:
<dl>
</dl>

<strong>Exemplos</strong>:

Atualizar e exibir tokens OAuth

```
ibmcloud iam oauth-tokens
```

## Ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Desconectar o IBMid público com um não IBMid dedicado

```
Ibmcloud iam dedicated-id-disconnect [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forçar desconexão sem confirmação</dd>
</dl>


## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Criar uma política de autorização para permitir que uma instância de serviço acesse outra instância de serviço.

```
ibmcloud iam authorization-policy-create SOURCE_SERVICE_NAME TARGET_SERVICE_NAME ROLE_NAME1,ROLE_NAME2... [--source-service-instance SOURCE_SERVICE_INSTANCE_NAME ] [--target-service-instance TARGET_SERVICE_INSTANCE_NAME ]
```

<strong>Pré-requisitos</strong>: Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>SOURCE_SERVICE_NAME</dt>
  <dd>Serviço de origem que pode ser autorizado para acesso.</dd>
  <dt>TARGET_SERVICE_NAME</dt>
  <dd>Serviço de destino que o serviço de origem pode ser autorizado a acessar.</dd>
  <dt>ROLE_NAME1,ROLE_NAME2...</dt>
  <dd>As funções que fornecem acesso para o serviço de origem.</dd>  
  <dt>—-source-service-instance SOURCE_SERVICE_INSTANCE_NAME</dt>
  <dd>Nome da instância de serviço de origem, se não especificado, todas as instâncias do serviço de origem terão o acesso autorizado.</dd>
  <dt>—-target-service-instance TARGET_SERVICE_INSTANCE_NAME</dt>
  <dd>Nome da instância de serviço de destino, se não especificado, todas as instâncias do serviço de destino terão o acesso autorizado.</dd>
</dl>

## Ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Excluir uma política de autorização.

```
Ibmcloud iam authorization-policy-delete AUTHORIZATION_POLICY_ID [ -f, -- force ]
```

<strong>Pré-requisitos</strong>: Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID da política de autorização para exclusão.</dd>
  <dt>-f, --force</dt>
  <dd>Forçar exclusão sem confirmação.</dd>
</dl>

## Ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Mostrar detalhes de uma política de autorização.

```
Ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID
```

<strong>Pré-requisitos</strong>: Login, Destino

<strong>Opções de comando</strong>:
<dl>
  <dt>AUTHORIZATION_POLICY_ID</dt>
  <dd>ID da política de autorização para exibição.</dd>
</dl>


## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Listar políticas de autorização sob a conta atual.

```
ibmcloud iam authorization-policies
```

<strong>Pré-requisitos</strong>: Login, Destino


## ibmcloud resource groups
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

## ibmcloud resource group
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


## Create-ibmcloud grupo de recursos
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


## Update-ibmcloud grupo de recursos
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

## ibmcloud resource quotas
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

## Cota de recurso ibmcloud
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

## Ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrar uma instância de serviço Cloudfoundry no grupo de recursos

```
bx resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
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


## Ibmcloud app push
{: #ibmcloud_app_push}

Esse comando tem a mesma função e opções que o comando [cf push ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.


## ibmcloud app list
{: #ibmcloud_app_list}

Esse comando tem a mesma função e opções que o comando [cf apps ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.


## Ibmcloud app show
{: #ibmcloud_app_show}

Esse comando tem a mesma função e opções que o comando [cf app ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.


## Excluir app ibmcloud
{: #ibmcloud_app_delete}

Esse comando tem a mesma função e opções que o comando [cf delete ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.


## Ibmcloud app rename
{: #ibmcloud_app_rename}

Esse comando tem a mesma função e opções que o comando [cf rename ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.


## Ibmcloud app start
{: #ibmcloud_app_start}

Esse comando tem a mesma função e opções que o comando [cf start ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.


## Ibmcloud app stop
{: #ibmcloud_app_stop}

Esse comando tem a mesma função e opções que o comando [cf stop ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.


## Reiniciar app ibmcloud
{: #ibmcloud_app_restart}

Esse comando tem a mesma função e opções que o comando [cf restart ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.


## Ibmcloud app restage
{: #ibmcloud_app_restage}


Esse comando tem a mesma função e opções que o comando [cf restage ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.


## App instance-restart ibmcloud
{: #ibmcloud_app_instance_restart}


Esse comando tem a mesma função e opções que o comando [cf restart-app-instance ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.


## Ibmcloud eventos de app
{: #ibmcloud_app_events}

Esse comando tem a mesma função e opções que o comando [cf events ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.


## ibmcloud app files
{: #ibmcloud_app_files}

Esse comando tem a mesma função e as opções que o comando [cf files ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.


## Ibmcloud logs de app
{: #ibmcloud_app_logs}

Esse comando tem a mesma função e opções que o comando [cf logs ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.


## Ibmcloud app env
{: #ibmcloud_app_env}

Esse comando tem a mesma função e opções que o comando [cf env ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.


## Ibmcloud app env-set
{: #ibmcloud_app_env_set}

Esse comando tem a mesma função e opções que o comando [cf set-env ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.


## Ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Esse comando tem a mesma função e opções que o comando [cf unset-env ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.


## Ibmcloud app stacks
{: #ibmcloud_app_stacks}

Esse comando tem a mesma função e opções que o comando [cf stacks ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.


## App stack-show ibmcloud
{: #ibmcloud_app_stack_show}

Esse comando tem a mesma função e opções que o comando [cf stack ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.


## App manifest-create ibmcloud
{: #ibmcloud_app_manifest_create}

Esse comando tem a mesma função e opções que o comando [cf create-app-manifest ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## App domain-cert ibmcloud
{: #ibmcloud_app_domain_cert}

Liste as informações de certificado de um domínio.

```
Ibmcloud app domain-cert DOMAIN_NAME
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
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## Ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Inclua um certificado no domínio especificado na organização atual.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
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
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## Ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Remova um certificado do domínio especificado na organização atual.

```
Ibmcloud app domain-cert-remove DOMAIN [ -f ]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:

   <dl>
   <dt>DOMAIN (necessário)</dt>
   <dd>Domínio do qual remover o certificado.</dd>
   <dt>-f (opcional)</dt>
   <dd>Force a exclusão sem confirmação.</dd>
   </dl>

## Rotas do app ibmcloud
{: #ibmcloud_app_routes}

Esse comando tem a mesma função e opções que o comando [cf routes ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.


## Check-route app ibmcloud
{: #ibmcloud_app_route_check}

Esse comando tem a mesma função e opções que o comando [cf check-route ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.


## Map-route app ibmcloud
{: #ibmcloud_app_route_map}

Mapeie uma rota para um aplicativo cf ou grupo de contêiner existente que tenha o domínio e o nome do host especificados.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (obrigatório)</dt>
   <dd>O nome do aplicativo cf ou grupo de contêiner a ser mapeado com uma rota.</dd>
   <dt>DOMAIN (necessário)</dt>
   <dd>O domínio da rota. Por exemplo, mychinabluemix.net ou chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i> (opcional)</dt>
   <dd>O nome do host da rota. Se não fornecido, o nome do host será configurado para o nome do app ou grupo de contêiner por padrão.</dd>
   </dl>

<strong>Exemplos</strong>:

Mapeie uma rota para `my-app` com o domínio especificado:

```
Ibmcloud app route-map my-app
```

Mapeie uma rota para 'my-container-group' com o domínio e nome do host especificados:

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```


## Ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Remova o mapeamento da rota especificada de um aplicativo cf ou grupo de contêiner existente.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Pré-requisitos</strong>: Terminal, Login, Destino

<strong>Opções de comando</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (obrigatório)</dt>
   <dd>O nome do aplicativo cf ou grupo de contêiner.</dd>
   <dt>DOMAIN (necessário)</dt>
   <dd>O domínio da rota (por exemplo, mychinabluemix.net ou chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i> (opcional)</dt>
   <dd>O nome do host da rota. Se não fornecido, o nome do host será configurado para o nome do app ou grupo de contêiner por padrão.</dd>
   </dl>

<strong>Exemplos</strong>:

Remover o mapeamento `my-app.mychinabluemix.net` de `my-app`:

```
Ibmcloud app route-unmap my-app
```

Remover o mapeamento `abc.chinabluexmix.net` de `my-container-group`:

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```


## Create-route app ibmcloud
{: #ibmcloud_app_route_create}

Esse comando tem a mesma função e as opções que o comando [cf create-route ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.


## Delete-route app ibmcloud
{: #ibmcloud_app_route_delete}

Esse comando tem a mesma função e opções que o comando [cf delete-route ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.


## Ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Esse comando tem a mesma função e opções que o comando [cf-delete-orphaned-routes ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.


## ibmcloud app domains
{: #ibmcloud_app_domains}

Esse comando tem a mesma função e opções que o comando [cf domains ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.


## Create-domain app ibmcloud
{: #ibmcloud_app_domain_create}

Esse comando tem a mesma função e opções que o comando [cf create-domain ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.


## Delete-domain app ibmcloud
{: #ibmcloud_app_domain_delete}

Esse comando tem a mesma função e opções que o comando [cf delete-domain ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.


## Ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Esse comando tem a mesma função e opções que o comando [cf create-shared-domain ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.


## Ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Esse comando tem a mesma função e opções que o comando [cf delete-shared-domain ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.


## As ofertas de serviço ibmcloud
{: #ibmcloud_service_offerings}


Esse comando tem a mesma função e opções que o comando [cf marketplace ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/marketplace.html){: new_window}.


## Ibmcloud lista de serviços
{: #ibmcloud_service_list}

Esse comando tem a mesma função e opções que o comando [cf services ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/services.html){: new_window}.


## Ibmcloud show de serviço
{: #ibmcloud_service_show}

Esse comando tem a mesma função e as opções que o comando [cf service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service.html){: new_window}.


## Criar serviço ibmcloud
{: #ibmcloud_service_create}

Esse comando tem a mesma função e opções que o comando [cf create-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service.html){: new_window}.


## Atualização de serviço ibmcloud
{: #ibmcloud_service_update}

Esse comando tem a mesma função e opções que o comando [cf update-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-service.html){: new_window}.


## ibmcloud service delete
{: #ibmcloud_service_delete}

Esse comando tem a mesma função e opções que o comando [cf delete-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service.html){: new_window}.


## Renomeação de serviço ibmcloud
{: #ibmcloud_service_rename}

Esse comando tem a mesma função e opções que o comando [cf rename-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-service.html){: new_window}.


## Ligação de serviço ibmcloud
{: #ibmcloud_service_bind}

Esse comando tem a mesma função e opções que o comando [cf bind-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/bind-service.html){: new_window}.


## Service unbind ibmcloud
{: #ibmcloud_service_unbind}

Esse comando tem a mesma função e opções que o comando [cf unbind-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unbind-service.html){: new_window}.


## Create-chave de serviço ibmcloud
{: #ibmcloud_service_key_create}

Esse comando tem a mesma função e opções que o comando [cf create-service-key ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-service-key.html){: new_window}.


## Service key-delete ibmcloud
{: #ibmcloud_service_key_delete}

Esse comando tem a mesma função e opções que o comando [cf delete-service-key ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-service-key.html){: new_window}.


## Chaves de serviço ibmcloud
{: #ibmcloud_service_keys}

Esse comando tem a mesma função e opções que o comando [cf service-keys ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-keys.html){: new_window}.


## Service key-show ibmcloud
{: #ibmcloud_service_key_show}

Esse comando tem a mesma função e opções que o comando [cf service-key ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/service-key.html){: new_window}.


## Serviço ibmcloud user-provided-create
{: #ibmcloud_service_user_provided_create}

Esse comando tem a mesma função e opções que o comando [cf create-user-provided-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-user-provided-service.html){: new_window}.


## Ibmcloud de serviço do usuário a atualização fornecida
{: #ibmcloud_service_user_provided_update}

Esse comando tem a mesma função e opções que o comando [cf update-user-provided-service ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/update-user-provided-service.html){: new_window}.


## ibmcloud resource service-instances
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

## ibmcloud resource service-instance
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

## Ibmcloud resource service-instance-create
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

## Ibmcloud resource service-instance-delete
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

## As ligações de serviço do recurso ibmcloud
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
## ibmcloud resource service-binding
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

## Ibmcloud resource service-binding-create
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
## Ibmcloud resource service-binding-delete
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

## Resource service-keys ibmcloud
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

## Ibmcloud recurso de serviço de chave
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

## Ibmcloud resource service-key-create
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

## Service-aliases de recursos ibmcloud
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

## Resource service-alias ibmcloud
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

## Ibmcloud resource service-alias-create
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

## Ibmcloud resource service-alias-update
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

## Ibmcloud resource service-alias-delete
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

## Ibmcloud recursos de procura
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

## Tags de recursos ibmcloud
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

## Tag de recurso ibmcloud
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

## Create-tag de recurso ibmcloud
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

## Delete-tag de recurso ibmcloud
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

## Ibmcloud recurso de tag de conexão
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

## Ibmcloud recurso de identificação detach
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

## Update-tag de recurso ibmcloud
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


## Ibmcloud de procura de catálogo
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
Ibmcloud entrada no catálogo 'a0ef1-d3b4j0'
```


## Create-ibmcloud entrada no catálogo
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


## Update-ibmcloud entrada no catálogo
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
Ibmcloud catalog entry-update 'j402-dnf1i' -c
```

## Delete-entrada no catálogo ibmcloud
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


## Catalog entry-visibility ibmcloud
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


## Ibmcloud catalog entry-visibility-set
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
Ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c
```


## Catalog service-marketplace ibmcloud
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

## ibmcloud catalog templates
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


## Modelo do catálogo ibmcloud
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


## Catalog template-run ibmcloud
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
Catalog runtime RUNTIME_ID ibmcloud
```

<strong>Exemplos</strong>:

Mostrar detalhes do tempo de execução "nodejsHelloWorld":

```
catalog runtime nodejsHelloWorld
```

## Ibmcloud tempos no catálogo
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

## Uso de conta de cobrança ibmcloud
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

## Billing org-usage ibmcloud
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


## Ibmcloud billing resource-group-usage
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

## Ibmcloud billing resource-instances-usage
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

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Listar todos os repositórios de plug-in que estão registrados na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Pré-requisitos</strong>: Nenhum


## Plugin repo-add ibmcloud
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


## Plugin repo-remove ibmcloud
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


## ibmcloud plugin repo-plugins
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

## Plugin ibmcloud
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


## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Listar todos os plug-ins instalados na CLI do {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Pré-requisitos</strong>: Nenhum

## Ibmcloud plugin show
{: #ibmcloud_plugin_show}

Mostrar detalhes de um plug-in instalado.

```
Ibmcloud plugin show PLUGIN-NAME
```

<strong>Pré-requisitos</strong>: Nenhum


## Plugin install ibmcloud
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

## ibmcloud plugin update
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

## Ibmcloud plugin uninstall
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

## Ambientes cfee ibmcloud
{: #ibmcloud_cfee_environments}

Lista de ambientes CFEE.

```
Ambientes cfee bx
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:


## Ambiente cfee ibmcloud
{: #ibmcloud_cfee_environment}

Mostrar detalhes de um ambiente CFEE.

```
bx cfee environment NAME [--id]
```

<strong>Pré-requisitos</strong>: Terminal, Login

<strong>Opções de comando</strong>:
  <dl>
   <dt>--id</dt>
   <dd>Mostrar somente o ID.</dd>
  </dl>

<strong>Exemplos</strong>:

Mostrar detalhes de um ambiente CFEE env_example:

```
Env_example ambiente cfee bx
```

Mostrar ID de um ambiente CFEE env_example:

```
bx cfee environment env_example --id
```
