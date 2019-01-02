---

copyright:

  years: 2018


lastupdated: "2018-11-29"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gerenciando aplicativos do Cloud Foundry
{: #ibmcloud_commands_apps}

Use os comandos a seguir para gerenciar os aplicativos, os domínios e as rotas do Cloud Foundry.
{: shortdesc}

<table summary="Comandos ibmcloud que podem ser usados para gerenciar apps cf e domínios, rotas e certificados relacionados ao app.">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](cli_cf_apps.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](cli_cf_apps.html#ibmcloud_app_list)</td>
 <td>[Ibmcloud app show](cli_cf_apps.html#ibmcloud_app_show)</td>
 <td>[ibmcloud app delete](cli_cf_apps.html#ibmcloud_app_delete)</td>
 <td>[ibmcloud app rename](cli_cf_apps.html#ibmcloud_app_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud app start](cli_cf_apps.html#ibmcloud_app_start)</td>
 <td>[ibmcloud app stop](cli_cf_apps.html#ibmcloud_app_stop)</td>
 <td>[ibmcloud app restart](cli_cf_apps.html#ibmcloud_app_restart)</td>
 <td>[ibmcloud app restage](cli_cf_apps.html#ibmcloud_app_restage)</td>
 <td>[ibmcloud app instance-restart](cli_cf_apps.html#ibmcloud_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[ibmcloud app eventos](cli_cf_apps.html#ibmcloud_app_events)</td>
 <td>[ibmcloud arquivos de app](cli_cf_apps.html#ibmcloud_app_files)</td>
 <td>[Ibmcloud logs de app](cli_cf_apps.html#ibmcloud_app_logs)</td>
 <td>[ibmcloud app env](cli_cf_apps.html#ibmcloud_app_env)</td>
 <td>[ibmcloud app env-set](cli_cf_apps.html#ibmcloud_app_env_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud app env-unset](cli_cf_apps.html#ibmcloud_app_env_unset)</td>
 <td>[ibmcloud app stacks](cli_cf_apps.html#ibmcloud_app_stacks)</td>
 <td>[ibmcloud app stack-show](cli_cf_apps.html#ibmcloud_app_stack_show)</td>
 <td>[ibmcloud app manifest-create](cli_cf_apps.html#ibmcloud_app_manifest_create)</td>
 <td>[ibmcloud app domain-cert](cli_cf_apps.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
 <td>[ibmcloud app domain-cert-add](cli_cf_apps.html#ibmcloud_app_domain_cert_add)</td>
 <td>[ibmcloud app domain-cert-remove](cli_cf_apps.html#ibmcloud_app_domain_cert_remove)</td>
 <td>[ibmcloud app domains](cli_cf_apps.html#ibmcloud_app_domains)</td>
  <td>[ibmcloud app domain-create](cli_cf_apps.html#ibmcloud_app_domain_create)</td>
  <td>[ibmcloud app domain-delete](cli_cf_apps.html#ibmcloud_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud app shared-domain-create](cli_cf_apps.html#ibmcloud_app_shared_domain_create)</td>
  <td>[ibmcloud app shared-domain-delete](cli_cf_apps.html#ibmcloud_app_shared_domain_delete)</td>
  <td>[ibmcloud app rotas](cli_cf_apps.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](cli_cf_apps.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](cli_cf_apps.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](cli_cf_apps.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](cli_cf_apps.html#ibmcloud_app_route_create)</td>
  <td>[Delete-route app ibmcloud](cli_cf_apps.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](cli_cf_apps.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>

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
