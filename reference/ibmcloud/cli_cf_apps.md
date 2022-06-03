---

copyright:
  years: 2018, 2022
lastupdated: "2022-06-03"

keywords: cli, cloud foundry app, ibmcloud app, app list, app push, app show, app delete, app rename, app start, app stop, app routes, manage cloud foundry apps, manage apps, app domains, manage routes

subcollection: cli

---

{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:external: target="_blank" .external}
{:deprecated: .deprecated}

# Managing Cloud Foundry applications (ibmcloud app)
{: #ibmcloud_commands_apps}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage Cloud Foundry applications, domains, and routes.
{: shortdesc}



The `ibmcloud app` commands are deprecated. To work with Cloud Foundry applications, use the [`ibmcloud cf app` commands](/docs/cli?topic=cli-ibmcloud_cli#ibmcloud_cf) instead. You can also use the [{{dev_cli_short}} (`ibmcloud dev`) commands](/docs/cli?topic=cli-idt-cli) to build, test, run, and deploy apps on {{site.data.keyword.cloud_notm}}.
{: deprecated}

## ibmcloud app push
{: #ibmcloud_app_push}

This command has the same function and options as the [cf push](http://cli.cloudfoundry.org/en-US/cf/push.html){: external} command.

## ibmcloud app list
{: #ibmcloud_app_list}

This command has the same function and options as the [cf apps](http://cli.cloudfoundry.org/en-US/cf/apps.html){: external} command.

## ibmcloud app show
{: #ibmcloud_app_show}

This command has the same function and options as the [cf app](http://cli.cloudfoundry.org/en-US/cf/app.html){: external} command.

## ibmcloud app delete
{: #ibmcloud_app_delete}

This command has the same function and options as the [cf delete](http://cli.cloudfoundry.org/en-US/cf/delete.html){: external} command.

## ibmcloud app rename
{: #ibmcloud_app_rename}

This command has the same function and options as the [cf rename](http://cli.cloudfoundry.org/en-US/cf/rename.html){: external} command.

## ibmcloud app start
{: #ibmcloud_app_start}

This command has the same function and options as the [cf start](http://cli.cloudfoundry.org/en-US/cf/start.html){: external} command.

## ibmcloud app stop
{: #ibmcloud_app_stop}

This command has the same function and options as the [cf stop](http://cli.cloudfoundry.org/en-US/cf/stop.html){: external} command.

## ibmcloud app restart
{: #ibmcloud_app_restart}

This command has the same function and options as the [cf restart](http://cli.cloudfoundry.org/en-US/cf/restart.html){: external} command.

## ibmcloud app restage
{: #ibmcloud_app_restage}

This command has the same function and options as the [cf restage](http://cli.cloudfoundry.org/en-US/cf/restage.html){: external} command.

## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}

This command has the same function and options as the [cf restart-app-instance](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: external} command.

## ibmcloud app events
{: #ibmcloud_app_events}

This command has the same function and options as the [cf events](http://cli.cloudfoundry.org/en-US/cf/events.html){: external} command.

## ibmcloud app files
{: #ibmcloud_app_files}

This command has the same function and options as the [cf files](http://cli.cloudfoundry.org/en-US/cf/files.html){: external} command.

## ibmcloud app logs
{: #ibmcloud_app_logs}

This command has the same function and options as the [cf logs](http://cli.cloudfoundry.org/en-US/cf/logs.html){: external} command.

## ibmcloud app env
{: #ibmcloud_app_env}

This command has the same function and options as the [cf env](http://cli.cloudfoundry.org/en-US/cf/env.html){: external} command.

## ibmcloud app env-set
{: #ibmcloud_app_env_set}

This command has the same function and options as the [cf set-env](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: external} command.

## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

This command has the same function and options as the [cf unset-env](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: external} command.

## ibmcloud app stacks
{: #ibmcloud_app_stacks}

This command has the same function and options as the [cf stacks](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: external} command.

## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

This command has the same function and options as the [cf stack](http://cli.cloudfoundry.org/en-US/cf/stack.html){: external} command.

## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

This command has the same function and options as the [cf create-app-manifest](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: external} command.

## ibmcloud app domain-cert
{: #cf-list-domain-cert}

List the certificate information of a domain.
```bash
ibmcloud app domain-cert DOMAIN_NAME
```

**Command options**:

DOMAIN_NAME (required)
:   The domain that hosts the certificate.

**Examples:**

View the certificate information of the domain `ibmcxo-eventconnect.com`:

```bash
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #cf-add-domain-cert}

Add a certificate to the specified domain in the current org.

```bash
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

**Command options**:

DOMAIN (required)
:   The domain that the certificate is added to.

-k *PRIVATE_KEY_FILE* (required)
:   The private key file path.

-c *CERT_FILE* (required)
:   The certificate file path.

-p *PASSWORD* (optional)
:   The password for the certificate.

-i *INTERMEDIATE_CERT_FILE* (optional)
:   The intermediate certificate file path.

-t *TRUST_STORE_FILE* (optional)
:   The truststore file.

**Examples:**

Add a certificate to the domain `ibmcxo-eventconnect.com`:

```bash
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #cf-remove-domain-cert}

Remove a certificate from the specified domain in current org.

```bash
ibmcloud app domain-cert-remove DOMAIN [-f]
```

**Command options**:

DOMAIN (required)
:   Domain to remove the certificate from.

-f  (optional)
:   Force deletion without confirmation.

## ibmcloud app routes
{: #ibmcloud_app_routes}

This command has the same function and options as the [cf routes](http://cli.cloudfoundry.org/en-US/cf/routes.html){: external} command.

## ibmcloud app route-check
{: #ibmcloud_app_route_check}

This command has the same function and options as the [cf check-route](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: external} command.

## ibmcloud app route-map
{: #ibmcloud_app_route_map}

Map a route to an existing cf application or container group that has the specified domain and host name.

```bash
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

**Command options**:

CF_APP_NAME|CONTAINER_GROUP_NAME (required)
:   The name of the cf application or container group to be mapped with a route.

DOMAIN (required)
:   The domain of the route. For example, mybluemix.net.

-n *HOST_NAME* (optional)
:   The host name of the route. If not provided, the host name is set to the app name or container group name by default.

**Examples:**

Map a route to `my-app` with specified domain:
```bash
ibmcloud app route-map my-app mybluemix.net
```
{: codeblock}

Map a route to 'my-container-group' with specified domain and host name:
```bash
ibmcloud app route-map my-container-group bluemix.net -n abc
```
{: codeblock}

The default shared domain is `mybluemix.net`, but `appdomain.cloud` is another domain option that you can use. For more information about migrating to `appdomain.cloud`, see [Updating your domain](/docs/cloud-foundry-public?topic=cloud-foundry-public-update-domain).
{: tip}

## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Unmap the specified route from an existing cf application or container group.
```bash
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

**Command options**:

CF_APP_NAME|CONTAINER_GROUP_NAME (required)
:   The name of the cf application or container group.

DOMAIN (required)
:   The domain of the route. For example, mybluemix.net.

-n *HOST_NAME* (optional)
:   The host name of the route. If not provided, the host name is set to app name or container group name by default.

**Examples:**

Unmap `my-app.mybluemix.net` from `my-app`:
```bash
ibmcloud app route-unmap my-app mybluemix.net
```
{: codeblock}

Unmap `abc.bluexmix.net` from `my-container-group`:
```bash
ibmcloud app route-unmap my-container-group bluemix.net -n abc
```
{: codeblock}

The default shared domain is `mybluemix.net`, but `appdomain.cloud` is another domain option that you can use. For more information about migrating to `appdomain.cloud`, see [Updating your domain](/docs/cloud-foundry-public?topic=cloud-foundry-public-update-domain).
{: tip}

## ibmcloud app route-create
{: #ibmcloud_app_route_create}

This command has the same function and options as the [cf create-route](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: external} command.

## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

This command has the same function and options as the [cf delete-route](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: external} command.

## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

This command has the same function and options as the [cf delete-orphaned-routes](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: external} command.

## ibmcloud app domains
{: #ibmcloud_app_domains}

This command has the same function and options as the [cf domains](http://cli.cloudfoundry.org/en-US/cf/domains.html){: external} command.

## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

This command has the same function and options as the [cf create-domain](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: external} command.

## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

This command has the same function and options as the [cf delete-domain](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: external} command.

## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

This command has the same function and options as the [cf create-shared-domain](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: external} command.

## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

This command has the same function and options as the [cf delete-shared-domain](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: external} command.
