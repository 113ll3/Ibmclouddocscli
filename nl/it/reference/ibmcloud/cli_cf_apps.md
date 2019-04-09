---

copyright:

  years: 2018


lastupdated: "2018-11-29"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione delle applicazioni Cloud Foundry
{: #ibmcloud_commands_apps}

Utilizza i seguenti comandi per gestire le rotte, i domini e le applicazioni Cloud Foundry.
{: shortdesc}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire le applicazioni cf e i domini, le rotte e i certificati relativi all'applicazione.">
 <thead>
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

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf push ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.

## ibmcloud app list
{: #ibmcloud_app_list}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf apps ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.

## ibmcloud app show
{: #ibmcloud_app_show}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf app ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.

## ibmcloud app delete
{: #ibmcloud_app_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.

## ibmcloud app rename
{: #ibmcloud_app_rename}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf rename ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.

## ibmcloud app start
{: #ibmcloud_app_start}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf start ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.

## ibmcloud app stop
{: #ibmcloud_app_stop}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf stop ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.

## ibmcloud app restart
{: #ibmcloud_app_restart}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf restart ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.

## ibmcloud app restage
{: #ibmcloud_app_restage}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf restage ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.

## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf restart-app-instance ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.

## ibmcloud app events
{: #ibmcloud_app_events}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf events ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.

## ibmcloud app files
{: #ibmcloud_app_files}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf files ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.

## ibmcloud app logs
{: #ibmcloud_app_logs}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf logs ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.

## ibmcloud app env
{: #ibmcloud_app_env}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf env ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.

## ibmcloud app env-set
{: #ibmcloud_app_env_set}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf set-env ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.

## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf unset-env ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.

## ibmcloud app stacks
{: #ibmcloud_app_stacks}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf stacks ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.

## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf stack ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.

## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-app-manifest ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Elenca le informazioni sul certificato di un dominio.

```
ibmcloud app domain-cert NOME_DOMINIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_DOMINIO (obbligatorio)</dt>
<dd>Il dominio che ospita il certificato.</dd>
</dl>


<strong>Esempi</strong>:

Visualizza le informazioni sul certificato del dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Aggiunge un certificato al dominio specificato nell'organizzazione corrente.

```
ibmcloud app domain-cert-add DOMINIO -k FILE_CHIAVE PRIVATA -c FILE_CERTIFICATO [-p PASSWORD] [-i FILE_CERTIFICATO_INTERMEDIO] [-t FILE_TRUSTSTORE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio a cui viene aggiunto il certificato.</dd>
   <dt>-k <i>FILE_CHIAVE PRIVATA</i> (obbligatorio)</dt>
   <dd>Il percorso del file della chiave privata.</dd>
   <dt>-c <i>FILE_CERTIFICATO</i> (obbligatorio)</dt>
   <dd>Il percorso del file del certificato.</dd>
   <dt>-p <i>PASSWORD</i> (facoltativo)</dt>
   <dd>La password per il certificato.</dd>
   <dt>-i <i>FILE_CERTIFICATO_INTERMEDIO</i> (optional)</dt>
   <dd>Il percorso del file di certificato intermedio.</dd>
   <dt>-t <i>FILE_TRUSTSTORE</i> (facoltativo)</dt>
   <dd>Il file truststore.</dd>
   </dl>


<strong>Esempi</strong>:

Aggiunge un certificato al dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Rimuove un certificato dal dominio specificato nell'organizzazione corrente.

```
ibmcloud app domain-cert-remove DOMINIO [-f]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio da cui rimuovere il certificato.</dd>
   <dt>-f (facoltativo)</dt>
   <dd>Forza l'eliminazione senza conferma.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf routes ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.

## ibmcloud app route-check
{: #ibmcloud_app_route_check}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf check-route ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.

## ibmcloud app route-map
{: #ibmcloud_app_route_map}

Associa una rotta a un'applicazione cf o a un gruppo di contenitori esistenti che hanno il dominio e il nome host specificati.

```
ibmcloud app route-map NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORE  DOMINIO  [-n NOME_HOST]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORI (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf o del gruppo di contenitori da associare a una rotta.</dd>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio della rotta. Ad esempio, mychinabluemix.net o chinabluemix.net. </dd>
   <dt>-n <i>NOME_HOST</i> (facoltativo)</dt>
   <dd>Il nome host della rotta. Se non viene fornito, il nome host è impostato sul nome applicazione o sul nome gruppo di contenitori per impostazione predefinita.</dd>
   </dl>

<strong>Esempi</strong>:

Associa una rotta `my-app` con il dominio specificato:

```
ibmcloud app route-map my-app mychinabluemix.net
```

Associa una rotta a 'my-container-group' con il dominio e il nome host specificati:

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Annulla l'associazione della rotta specificata a un'applicazione cf o a un gruppo di contenitori esistenti.

```
ibmcloud app route-unmap NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORE  DOMINIO  [-n NOME_HOST]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_APPLICAZIONE_CF|NOME_GRUPPO_CONTENITORI (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf o del gruppo di contenitori.</dd>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio della rotta (ad esempio, mychinabluemix.net o chinabluemix.net).</dd>
   <dt>-n <i>NOME_HOST</i> (facoltativo)</dt>
   <dd>Il nome host della rotta. Se non viene fornito, il nome host è impostato sul nome applicazione o sul nome gruppo di contenitori per impostazione predefinita.</dd>
   </dl>

<strong>Esempi</strong>:

Annulla l'associazione di `my-app.mychinabluemix.net` da `my-app`:

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

Annulla l'associazione di `abc.chinabluexmix.net` da `my-container-group`:

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-create
{: #ibmcloud_app_route_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-route ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.

## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-route ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.

## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-orphaned-routes ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.

## ibmcloud app domains
{: #ibmcloud_app_domains}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf domains ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.

## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.

## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.

## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-shared-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.

## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-shared-domain ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.
