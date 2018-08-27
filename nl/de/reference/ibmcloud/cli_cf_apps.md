---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CF-Apps sowie Domänen, Routen und Zertifikate für Apps verwalten
{: #ibmcloud_commands_apps}

<table summary="ibmcloud-Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps.">
<caption>Tabelle 1. Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps</caption>
 <thead>
 <th colspan="5">Befehle zur Verwaltung von CF-Apps und von Domänen, Routen und Zertifikaten für Apps</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](cli_cf_apps.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](cli_cf_apps.html#ibmcloud_app_list)</td>
 <td>[ibmcloud app show](cli_cf_apps.html#ibmcloud_app_show)</td>
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
 <td>[ibmcloud app events](cli_cf_apps.html#ibmcloud_app_events)</td>
 <td>[ibmcloud app files](cli_cf_apps.html#ibmcloud_app_files)</td>
 <td>[ibmcloud app logs](cli_cf_apps.html#ibmcloud_app_logs)</td>
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
  <td>[ibmcloud app routes](cli_cf_apps.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](cli_cf_apps.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](cli_cf_apps.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](cli_cf_apps.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](cli_cf_apps.html#ibmcloud_app_route_create)</td>
  <td>[ibmcloud app route-delete](cli_cf_apps.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](cli_cf_apps.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>

 ## ibmcloud app push
{: #ibmcloud_app_push}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf push ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.

## ibmcloud app list
{: #ibmcloud_app_list}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf apps ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.

## ibmcloud app show
{: #ibmcloud_app_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf app ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.

## ibmcloud app delete
{: #ibmcloud_app_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.

## ibmcloud app rename
{: #ibmcloud_app_rename}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf rename ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.

## ibmcloud app start
{: #ibmcloud_app_start}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf start ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.

## ibmcloud app stop
{: #ibmcloud_app_stop}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stop ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.

## ibmcloud app restart
{: #ibmcloud_app_restart}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restart ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.

## ibmcloud app restage
{: #ibmcloud_app_restage}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restage ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.

## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf restart-app-instance ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.

## ibmcloud app events
{: #ibmcloud_app_events}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf events ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.

## ibmcloud app files
{: #ibmcloud_app_files}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf files ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.

## ibmcloud app logs
{: #ibmcloud_app_logs}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf logs ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.

## ibmcloud app env
{: #ibmcloud_app_env}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.

## ibmcloud app env-set
{: #ibmcloud_app_env_set}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf set-env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.

## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf unset-env ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.

## ibmcloud app stacks
{: #ibmcloud_app_stacks}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stacks ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.

## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf stack ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.

## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-app-manifest ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Die Zertifikatsinformationen für eine Domäne auflisten

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung

<strong>Befehlsoptionen</strong>:
<dl>
<dt>DOMAIN_NAME (erforderlich)</dt>
<dd>Die Domäne, in der das Zertifikat gehostet wird.</dd>
</dl>


<strong>Beispiele</strong>:

Die Zertifikatsinformationen für die Domäne `ibmcxo-eventconnect.com` anzeigen:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Der angegebenen Domäne in der aktuellen Organisation ein Zertifikat hinzufügen.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:
   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, der das Zertifikat hinzugefügt wird.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (erforderlich)</dt>
   <dd>Der Pfad der Datei mit dem privaten Schlüssel.</dd>
   <dt>-c <i>CERT_FILE</i> (erforderlich)</dt>
   <dd>Der Pfad der Zertifikatsdatei.</dd>
   <dt>-p <i>PASSWORD</i> (optional)</dt>
   <dd>Das Kennwort für das Zertifikat.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (optional)</dt>
   <dd>Der Pfad für die Zwischenzertifikatsdatei.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (optional)</dt>
   <dd>Die Truststore-Datei.</dd>
   </dl>


<strong>Beispiele</strong>:

Zertifikat der Domäne `ibmcxo-eventconnect.com` hinzufügen:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Zertifikat aus der angegebenen Domäne in der aktuellen Organisation entfernen.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne, aus der das Zertifikat entfernt werden soll.</dd>
   <dt>-f  (optional)</dt>
   <dd>Löschung ohne Bestätigung erzwingen.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf routes ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.

## ibmcloud app route-check
{: #ibmcloud_app_route_check}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf check-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.

## ibmcloud app route-map
{: #ibmcloud_app_route_map}

Eine Route einer vorhandenen cf-Anwendung oder -Containergruppe zuordnen, die über die angegebene Domäne oder den angegebenen Hostnamen verfügt.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung oder -Containergruppe für die Zuordnung der Route.</dd>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne der Route. Beispiele: mychinabluemix.net oder chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i> (optional)</dt>
   <dd>Der Hostname der Route. Wenn der Hostname nicht angegeben wird, wird standardmäßig der Anwendungsname oder der Containergruppenname festgelegt.</dd>
   </dl>

<strong>Beispiele</strong>:

Route zu `my-app` mit angegebener Domäne zuordnen:

```
ibmcloud app route-map my-app mychinabluemix.net
```

Route zu 'my-container-group' mit angegebener Domäne und angegebenem Hostnamen zuordnen:

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Zuordnung der angegebenen Route zu einer vorhandenen cf-Anwendung oder -Containergruppe aufheben.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Voraussetzungen</strong>: Endpunkt, Anmeldung, Ziel

<strong>Befehlsoptionen</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (erforderlich)</dt>
   <dd>Der Name der cf-Anwendung oder -Containergruppe.</dd>
   <dt>DOMAIN (erforderlich)</dt>
   <dd>Die Domäne der Route (Beispiele: mychinabluemix.net oder chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i> (optional)</dt>
   <dd>Der Hostname der Route. Wenn der Hostname nicht angegeben wird, wird standardmäßig der Anwendungsname oder der Containergruppenname festgelegt.</dd>
   </dl>

<strong>Beispiele</strong>:

Zuordnung von `my-app.mychinabluemix.net` zu `my-app` aufheben:

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

Zuordnung von `abc.chinabluexmix.net` zu `my-container-group` aufheben:

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-create
{: #ibmcloud_app_route_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.

## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-route ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.

## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-orphaned-routes ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.

## ibmcloud app domains
{: #ibmcloud_app_domains}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf domains ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.

## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.

## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.

## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf create-shared-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.

## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Dieser Befehl hat dieselbe Funktion und dieselben Optionen wie der Befehl [cf delete-shared-domain ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.
