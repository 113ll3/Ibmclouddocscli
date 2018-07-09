---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes de l'interface CLI pour la gestion des applications CF et des domaines, des routes et des certificats liés aux applications
{: #ibmcloud_commands_apps}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les applications cf et les domaines, les routes et les certificats liés aux applications.">
<caption>Tableau 1. Commandes de gestion des applications CF et des domaines, des routes et des certificats liés aux applications</caption>
 <thead>
 <th colspan="5">Commandes de gestion des applications CF et des domaines, des routes et des certificats liés aux applications</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](ic_cli_cf_apps.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](ic_cli_cf_apps.html#ibmcloud_app_list)</td>
 <td>[ibmcloud app show](ic_cli_cf_apps.html#ibmcloud_app_show)</td>
 <td>[ibmcloud app delete](ic_cli_cf_apps.html#ibmcloud_app_delete)</td>
 <td>[ibmcloud app rename](ic_cli_cf_apps.html#ibmcloud_app_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud app start](ic_cli_cf_apps.html#ibmcloud_app_start)</td>
 <td>[ibmcloud app stop](ic_cli_cf_apps.html#ibmcloud_app_stop)</td>
 <td>[ibmcloud app restart](ic_cli_cf_apps.html#ibmcloud_app_restart)</td>
 <td>[ibmcloud app restage](ic_cli_cf_apps.html#ibmcloud_app_restage)</td>
 <td>[ibmcloud app instance-restart](ic_cli_cf_apps.html#ibmcloud_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[ibmcloud app events](ic_cli_cf_apps.html#ibmcloud_app_events)</td>
 <td>[ibmcloud app files](ic_cli_cf_apps.html#ibmcloud_app_files)</td>
 <td>[ibmcloud app logs](ic_cli_cf_apps.html#ibmcloud_app_logs)</td>
 <td>[ibmcloud app env](ic_cli_cf_apps.html#ibmcloud_app_env)</td>
 <td>[ibmcloud app env-set](ic_cli_cf_apps.html#ibmcloud_app_env_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud app env-unset](ic_cli_cf_apps.html#ibmcloud_app_env_unset)</td>
 <td>[ibmcloud app stacks](ic_cli_cf_apps.html#ibmcloud_app_stacks)</td>
 <td>[ibmcloud app stack-show](ic_cli_cf_apps.html#ibmcloud_app_stack_show)</td>
 <td>[ibmcloud app manifest-create](ic_cli_cf_apps.html#ibmcloud_app_manifest_create)</td>
 <td>[ibmcloud app domain-cert](ic_cli_cf_apps.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](ic_cli_cf_apps.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](ic_cli_cf_apps.html#ibmcloud_app_domain_cert_remove)</td>
  <td>[ibmcloud app domains](ic_cli_cf_apps.html#ibmcloud_app_domains)</td>
  <td>[ibmcloud app domain-create](ic_cli_cf_apps.html#ibmcloud_app_domain_create)</td>
  <td>[ibmcloud app domain-delete](ic_cli_cf_apps.html#ibmcloud_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud app shared-domain-create](ic_cli_cf_apps.html#ibmcloud_app_shared_domain_create)</td>
  <td>[ibmcloud app shared-domain-delete](ic_cli_cf_apps.html#ibmcloud_app_shared_domain_delete)</td>
  <td>[ibmcloud app routes](ic_cli_cf_apps.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](ic_cli_cf_apps.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](ic_cli_cf_apps.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](ic_cli_cf_apps.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](ic_cli_cf_apps.html#ibmcloud_app_route_create)</td>
  <td>[ibmcloud app route-delete](ic_cli_cf_apps.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](ic_cli_cf_apps.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>
 
 ### ibmcloud app push
{: #ibmcloud_app_push}

Cette commande possède la même fonction et les mêmes options que la commande [cf push ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window}.

### ibmcloud app list
{: #ibmcloud_app_list}

Cette commande possède la même fonction et les mêmes options que la commande [cf apps ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window}.

### ibmcloud app show
{: #ibmcloud_app_show}

Cette commande possède la même fonction et les mêmes options que la commande [cf app ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window}.

### ibmcloud app delete
{: #ibmcloud_app_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window}.

### ibmcloud app rename
{: #ibmcloud_app_rename}

Cette commande possède la même fonction et les mêmes options que la commande [cf rename ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window}.

### ibmcloud app start
{: #ibmcloud_app_start}

Cette commande possède la même fonction et les mêmes options que la commande [cf start ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window}.

### ibmcloud app stop
{: #ibmcloud_app_stop}

Cette commande possède la même fonction et les mêmes options que la commande [cf stop ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window}.

### ibmcloud app restart
{: #ibmcloud_app_restart}

Cette commande possède la même fonction et les mêmes options que la commande [cf restart ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window}.

### ibmcloud app restage
{: #ibmcloud_app_restage}


Cette commande possède la même fonction et les mêmes options que la commande [cf restage ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window}.

### ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


Cette commande possède la même fonction et les mêmes options que la commande [cf restart-app-instance ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window}.

### ibmcloud app events
{: #ibmcloud_app_events}

Cette commande possède la même fonction et les mêmes options que la commande [cf events ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window}.

### ibmcloud app files
{: #ibmcloud_app_files}

Cette commande possède la même fonction et les mêmes options que la commande [cf files ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window}.

### ibmcloud app logs
{: #ibmcloud_app_logs}

Cette commande possède la même fonction et les mêmes options que la commande [cf logs ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window}.

### ibmcloud app env
{: #ibmcloud_app_env}

Cette commande possède la même fonction et les mêmes options que la commande [cf env ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window}.

### ibmcloud app env-set
{: #ibmcloud_app_env_set}

Cette commande possède la même fonction et les mêmes options que la commande [cf set-env ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window}.

### ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

Cette commande possède la même fonction et les mêmes options que la commande [cf unset-env ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window}.

### ibmcloud app stacks
{: #ibmcloud_app_stacks}

Cette commande possède la même fonction et les mêmes options que la commande [cf stacks ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window}.

### ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

Cette commande possède la même fonction et les mêmes options que la commande [cf stack ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window}.

### ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-app-manifest ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window}.

### ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

Afficher les informations de certificat d'un domaine.

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
<dt>DOMAIN_NAME (obligatoire)</dt>
<dd>Domaine hébergeant le certificat.</dd>
</dl>


<strong>Exemples</strong> :

Affichage des informations de certificat du domaine `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

### ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

Ajouter un certificat au domaine indiqué dans l'organisation en cours.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine auquel ajouter le certificat.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (obligatoire)</dt>
   <dd>Chemin du fichier de clé privée.</dd>
   <dt>-c <i>CERT_FILE</i> (obligatoire)</dt>
   <dd>Chemin du fichier de certificat.</dd>
   <dt>-p <i>PASSWORD</i> (facultatif)</dt>
   <dd>Mot de passe du certificat.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (facultatif)</dt>
   <dd>Chemin du fichier de certificat intermédiaire.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (facultatif)</dt>
   <dd>Fichier de clés certifiées.</dd>
   </dl>


<strong>Exemples</strong> :

Ajouter un certificat au domaine `ibmcxo-eventconnect.com` :

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

### ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

Supprimer un certificat du domaine spécifié dans l'organisation en cours.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine duquel supprimer le certificat.</dd>
   <dt>-f (facultatif)</dt>
   <dd>Force une suppression sans demander de confirmation.</dd>
   </dl>

### ibmcloud app routes
{: #ibmcloud_app_routes}

Cette commande possède la même fonction et les mêmes options que la commande [cf routes ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window}.

### ibmcloud app route-check
{: #ibmcloud_app_route_check}

Cette commande possède la même fonction et les mêmes options que la commande [cf check-route ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window}.

### ibmcloud app route-map
{: #ibmcloud_app_route_map}

Mappez une route à une application cf ou un groupe de conteneurs existant associé au domaine et au nom d'hôte spécifiés.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf ou du groupe de conteneur à mapper à une route.</dd>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine de la route. Par exemple, mychinabluemix.net ou chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i> (facultatif)</dt>
   <dd>Nom d'hôte de la route. S'il n'est pas spécifié, le nom d'hôte est le nom de l'application ou le nom du groupe de conteneurs par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Mappez une route à `mon-app` avec le domaine spécifié :

```
ibmcloud app route-map my-app mychinabluemix.net
```

Mappez une route à 'mon-groupe-conteneurs' avec le domaine et le nom d'hôte spécifiés :

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

### ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

Supprimer le mappage de la route spécifiée à une application cf ou un groupe de conteneurs existant.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf ou du groupe de conteneurs.</dd>
   <dt>DOMAIN (obligatoire)</dt>
   <dd>Domaine de la route (par exemple, mychinabluemix.net ou chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i> (facultatif)</dt>
   <dd>Nom d'hôte de la route. S'il n'est pas spécifié, le nom d'hôte est le nom de l'application ou le nom du groupe de conteneurs par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Supprimer le mappage de la route `mon-app.mychinabluemix.net` de `mon-app` :

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

Supprimer le mappage de la route `abc.chinabluexmix.net` de `mon-groupe-conteneurs` :

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

### ibmcloud app route-create
{: #ibmcloud_app_route_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-route ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window}.

### ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-route ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window}.

### ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-orphaned-routes ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window}.

### ibmcloud app domains
{: #ibmcloud_app_domains}

Cette commande possède la même fonction et les mêmes options que la commande [cf domains ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window}.

### ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window}.

### ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window}.

### ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

Cette commande possède la même fonction et les mêmes options que la commande [cf create-shared-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window}.

### ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

Cette commande possède la même fonction et les mêmes options que la commande [cf delete-shared-domain ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window}.
