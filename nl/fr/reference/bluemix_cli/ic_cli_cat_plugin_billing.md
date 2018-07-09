---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commande de l'interface CLI pour la gestion des catalogues, des plug-in et des paramètres de facturation
{: #ibmcloud_commands_settings}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer le catalogue, les plug-in, la facturation et les paramètres de sécurité {{site.data.keyword.Bluemix_notm}}.">
<caption>Tableau 1. Commandes de gestion de catalogue, de plug-in, de facturation et de paramètres de sécurité {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Commandes de gestion des paramètres de catalogue, de plug-in, de facturation et de sécurité {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](ic_cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](ic_cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](ic_cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud catalog search
{: #ibmcloud_catalog_search}

Effectuer des recherches dans des entrées de catalogue

```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--json] [--csv] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-r, --region</dt>
  <dd>Spécifier la région géographique dans laquelle effectuer la recherche. Actuellement, seules les régions "us-south" et "united-kingdom" sont prises en charge.</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrer par type de ressource. Actuellement, seules les options "service-cf", "iaas", "runtime", "template" et "dashboard" sont prises en charge.</dd>
  <dt>-p, --price</dt>
  <dd>Filtrer par prix. Actuellement, seuls les options "free", "paygo", "bluemix-subscription" sont prises en charge.</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrer par étiquette.</dd>
  <dt>--sort-by</dt>
  <dd>Propriétés de tri</dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. En général, "groupe", "fournisseur" et "étiquettes"</dd>
  <dt>--reverse</dt>
  <dd>Inverser l'ordre de tri</dd>
  <dt>--json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>--csv</dt>
  <dd>Fichier CSV de sortie</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Effectuer une recherche dans le service `Automation test` :

```
ibmcloud catalog search -k service -q 'Automation test'
```

### ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Obtenir une entrée de catalogue

```
ibmcloud catalog entry ID [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--children</dt>
  <dd>Obtenir tous les enfants de l'entrée de catalogue</dd>
  <dt>--json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Obtenir l'entrée portant l'ID `a0ef1-d3b4j0` :

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

### ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Créer une nouvelle entrée de catalogue (administrateur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-create [-c PARAMETERS_AS_JSON] [-p, --parent PARENT] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-p, --parent</dt>
  <dd>ID parent de l'objet</dd>
  <dt>-c</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques au catalogue, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir la documentation de l'entrée de catalogue concernée.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Créer une ressource à partir du fichier JSON portant l'ID parent `a0ef1-d3b4j0` :

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

### ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Mettre à jour une entrée de catalogue existante (administrateur ou éditeur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-update ID [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-c</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques au catalogue, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir la documentation de l'entrée de catalogue concernée.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour la ressource `j402-dnf1i` à partir d'un fichier JSON :

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

### ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Supprimer une entrée de catalogue (administrateur de catalogue d'un compte uniquement)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Supprimer la ressource `j402-dnf1i`:

```
ibmcloud catalog delete 'j402-dnf1i'
```

### ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Obtenir la visibilité pour une entrée de catalogue (administrateur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>-global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Obtenir la visibilité de la ressource `j402-dnf1i` dans une portée globale :

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

### ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Mettre à jour la visibilité d'une entrée de catalogue existante (administrateur de catalogue d'un compte uniquement)

```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>

  <dt>--includes-add</dt>
  <dd>Ajout d'un compte (ou d'une liste de comptes séparés par une virgule) à la liste d'inclusions de manière à accorder à la visibilité à l'entrée. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>
  <dt>--includes-remove</dt>
  <dd>Suppression d'un compte (ou d'une liste de comptes séparés par une virgule) de la liste d'inclusions, de manière à révoquer la visibilité de l'entrée. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>  
  <dt>--excludes-add</dt>
  <dd>Ajout d'un compte (ou d'une liste de comptes séparés par une virgule) à la liste d'exclusions. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>
  <dt>--excludes-remove</dt>
  <dd>Suppression d'un compte (ou d'une liste de comptes séparés par une virgule) de la liste d'exclusions, de manière à révoquer la visibilité de l'entrée. Si la liste a été définie par des administrateurs globaux, ces derniers ne peuvent pas supprimer le compte. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés</dd>
  <dt>--owner</dt>
  <dd>Changement de propriétaire d'un objet. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>
  <dt>--restrict</dt>
  <dd>Modification de la restriction de l'objet visibilité en 'Privé'</dd>
  <dt>--unrestrict</dt>
  <dd>Modification de la restriction de l'objet visibilité en 'Public'</dd>  
  <dt>-c</dt>
  <dd>Objet JSON valide contenant des paramètres de configuration spécifiques au catalogue, fournis en ligne ou dans un fichier. Pour obtenir la liste des paramètres de configuration pris en charge, voir la documentation de l'entrée de catalogue concernée.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Définir la visibilité de la ressource `j402-dnf1i` à partir d'un fichier JSON :

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

### ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Répertorier les offres de services de la place du marché

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--cf</dt>
  <dd>Afficher les services Cloud Foundry uniquement</dd>
  <dt>--rc</dt>
  <dd>Afficher les services RC compatibles uniquement</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale</dd>
</dl>

<strong>Exemples</strong> :

Afficher les offres de services dans une portée globale :

```
ibmcloud catalog service-marketplace --global
```

### ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Afficher les modèles de conteneur boilerplate dans {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>-d (facultatif)</dt>
   <dd>Si l'option <i>-d</i> est spécifiée, la description de chaque modèle est également affichée. Sinon, seul l'ID et le nom des modèles sont affichés.</dd>
   </dl>

### ibmcloud catalog template
{: #ibmcloud_catalog_template}

Afficher les informations détaillées d'un modèle de conteneur boilerplate spécifié.

```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>ID du modèle de conteneur boilerplate. Utilisez <i>ibmcloud templates</i> pour afficher tous les ID de modèles.</dd>
   </dl>


<strong>Exemples</strong> :

Afficher les détails du modèle `mobileBackendStarter` :

```
ibmcloud catalog template mobileBackendStarter
```

### ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Créez une application cf reposant sur le modèle spécifié avec l'adresse URL et la description indiquées. Par défaut, la nouvelle application est démarrée automatiquement.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-u URL] [-d DESCRIPTION] [--no-start]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>Modèle sur lequel sera basée l'application lors de sa création. Utilisez <i>ibmcloud templates</i> pour afficher tous les ID de modèles.</dd>
   <dt>CF_APP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf à créer.</dd>
   <dt>-u <i>URL</i> (facultatif)</dt>
   <dd>Route de l'application. Si elle n'est pas spécifiée, la route est définie automatiquement par {{site.data.keyword.Bluemix_notm}} d'après le nom de votre application et le domaine par défaut.</dd>
   <dt>-d <i>DESCRIPTION</i> (facultatif)</dt>
   <dd>Description de l'application.</dd>
   <dt>--no-start (facultatif)</dt>
   <dd>Indique de ne pas démarrer automatiquement l'application après sa création. Si cette option n'est pas spécifiée, l'application est démarrée automatiquement après sa création.</dd>
   </dl>


<strong>Exemples</strong> :

Créez l'application cf `mon-app` d'après le modèle `javaHelloWorld` :

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Créez une application `my-ruby-app` d'après le modèle `rubyHelloWorld` avec la route
`myrubyapp.chinabluemix.net` et la description `Ma première application Ruby dans {{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Créez l'application `mon-app-python` d'après le modèle `pythonHelloWorld` sans démarrage automatique :

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

### ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Obtenir un sous-ensemble de choix de régions dans le format de votre choix.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--json] [--global] [--csv]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-i, --id</dt>
  <dd>Indiquer la géographie par ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Obtenir une liste d'entrées pour le type indiqué.</dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. Actuellement "groupe", "fournisseur" et "balises".</dd>
  <dt>--json</dt>
  <dd>Sortie de la réponse JSON d'origine.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale.</dd>
  <dt>--csv</dt>
  <dd>Fichier CSV de sortie</dd>
</dl>

### ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Afficher les détails d'un contexte d'exécution. Cette commande est uniquement disponible dans un cloud public.

```
ibmcloud catalog runtime RUNTIME_ID
```

<strong>Exemples</strong> :

Afficher les détails du contexte d'exécution "nodejsHelloWorld" :

```
catalog runtime nodejsHelloWorld
```

### ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Afficher tous les contextes d'exécution. Cette commande est uniquement disponible dans un cloud public.

```
ibmcloud catalog runtimes [-d]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-d</dt>
  <dd>Afficher la description de chaque contexte d'exécution</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les contextes d'exécution ainsi que leurs descriptions :

```
ibmcloud catalog runtimes -d
```

### ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Afficher l'utilisation mensuelle du compte en cours (administrateur de compte seulement)

```
ibmcloud billing account-usage [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>

<strong>Exemples</strong> :

Afficher le rapport d'utilisation et des coûts du compte en cours pour 2016-06 :

```
ibmcloud billing account-usage -d 2016-06
```

### ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Afficher l'utilisation mensuelle pour une organisation (administrateur de compte ou gestionnaire de facturation d'organisation seulement)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>ORG_NAME (obligatoire)</dt>
  <dd>Nom de l'organisation.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>

### ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Afficher l'utilisation mensuelle pour un groupe de ressources (administrateur de compte ou administrateur de groupe de ressources seulement)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>GROUP_NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>

### ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Afficher l'utilisation mensuelle des instances de ressource sous le compte en cours.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

<dl>
  <dt>-o ORG_NAME (facultatif)</dt>
  <dd>Filtrer les instances par organisation.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>Filtrer l'instance par groupe de ressources.</dd>
  <dt>-d MONTH_DATE (facultatif)</dt>
  <dd>Afficher les données relatives au mois et à la date spécifiés en utilisant le format AAAA-MM. Si ces données ne sont pas spécifiées, l'utilisation du mois en cours est affichée.</dd>
  <dt>--json (facultatif)</dt>
  <dd>Afficher le résultat de l'utilisation au format JSON.</dd>
</dl>

### ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Répertorier tous les référentiels de plug-in enregistrés dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Prérequis</strong> : Aucun

### ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Ajouter un nouveau référentiel de plug-in dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à ajouter. Vous pouvez définir votre propre nom pour chaque référentiel.</dd>
   <dt>REPO_URL (obligatoire)</dt>
   <dd>URL du référentiel à ajouter. Elle doit contenir le protocole (par exemple http://plugins.ng.bluemix.net au lieu de plugins.ng.bluemix.net). http://plugins.ng.bluemix.net est le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Exemples</strong> :

Ajouter le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} sous la forme `bluemix-repo` :

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

### ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Retirer un référentiel de plug-in de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à supprimer.</dd>
   </dl>

<strong>Exemples</strong> :

Supprimer `référentiel-bluemix` de l'interface de ligne de commande (CLI) {{site.data.keyword.Bluemix_notm}} :

```
ibmcloud plugin repo-remove bluemix-repo
```

### ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Répertorier tous les plug-in disponibles dans tous les référentiels ajoutés ou dans un référentiel spécifique.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Répertorier uniquement les plug-in dans le référentiel spécifié.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier tous les plug-in dans tous les référentiels ajoutés :

```
ibmcloud plugin repo-plugins
```

Répertorier tous les plug-in du référentiel `bluemix-repo` :

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

### ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Afficher les détails d'un plug-in dans le référentiel

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les détails du plug-in "IBM-Containers" dans le référentiel "sample-repo" :

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Afficher les détails du plug-in "IBM-Containers" dans le référentiel par défaut

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

### ibmcloud plugin list
{: #ibmcloud_plugin_list}

Répertorier tous les plug-in installés dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin list
```

<strong>Prérequis</strong> : Aucun

### ibmcloud plugin show
{: #ibmcloud_plugin_show}

Afficher les détails d'un plug-in installé

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Prérequis</strong> : Aucun

### ibmcloud plugin install
{: #ibmcloud_plugin_install}

Installer la version de plug-in spécifique dans l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} à partir du chemin ou du référentiel spécifié.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (obligatoire)</dt>
   <dd>Si -r <i>REPO_NAME</i> n'est pas spécifié, le plug-in est installé depuis le chemin local spécifié ou depuis l'URL distante.</dd>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (facultatif)</dt>
   <dd>Version du plug-in à installer. Si elle n'est pas fournie, la dernière version du plug-in est installée. Cette option n'est valide que si vous installez le plug-in à partir du référentiel.</dd>
   <dt>-f </dt>
   <dd>Forcer l'installation du plug-in sans confirmation.</dd>
    </dl>


Le nom de référentiel officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est `Bluemix`.

<strong>Exemples</strong> :

Installer un plug-in depuis le fichier local :

```
ibmcloud plugin install /downloads/new_plugin
```

Installer un plug-in depuis l'adresse URL distante :

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Installer la dernière version du plug-in 'container-service' à partir du référentiel 'Bluemix' :

```
ibmcloud plugin install container-service -r Bluemix
```

ou simplement :

```
ibmcloud plugin install container-service
```

Installer la version '0.1.425' du plug-in 'container-service' à partir du référentiel de plug-in officiel :

```
ibmcloud plugin install container-service -v 0.1.425
```

### ibmcloud plugin update
{: #ibmcloud_plugin_update}

Mettre à niveau le plug-in à partir d'un référentiel

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nom du plug-in à mettre à jour. Si ce paramètre n'est pas spécifié, la commande recherche des mises à niveau pour tous les plug-ins installés.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (facultatif)</dt>
 <dd>Version du plug-in vers laquelle effectuer la mise à jour. Si elle n'est pas indiquée, le plug-in est mis à jour vers la version disponible la plus récente.</dd>
 <dt>--all</dt>
 <dd>Mettre à jour tous les plug-in disponibles</dd>
</dl>

<strong>Exemples</strong> :

Rechercher toutes les mises à niveau disponibles dans le référentiel de plug-in officiel 'Bluemix' :

```
ibmcloud plugin update -r Bluemix
```

ou simplement :

```
ibmcloud plugin update
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la dernière version :

```
ibmcloud plugin update container-service
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la version '0.1.440' :

```
ibmcloud plugin update container-service -v 0.1.440
```

### ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Désinstaller le plug-in spécifié de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_NAME (obligatoire)</dt>
   <dd>Nom du plug-in à désinstaller.</dd>
    </dl>

<strong>Exemples</strong> :

Désinstaller le plug-in 'container-service' précédemment installé :

```
ibmcloud plugin uninstall container-service
```
