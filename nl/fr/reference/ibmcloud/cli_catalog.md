---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Catalogue
{: #ibmcloud_catalog}

Les commandes suivantes permettent de gérer les entrées de catalogue {{site.data.keyword.Bluemix}}, les modèles de requête, les contextes d'exécution et les géolocalisations de centres de données.
{: shortdesc}

<table summary="Commandes ibmcloud permettant de gérer le catalogue {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_catalog.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_catalog.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_catalog.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_catalog.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_catalog.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_catalog.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_catalog.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_catalog.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_catalog.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_catalog.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_catalog.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_catalog.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_catalog.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_catalog.html#ibmcloud_catalog_runtimes)</td>
</tr>
 </tbody>
 </table>
  
  ## ibmcloud catalog search
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

## ibmcloud catalog entry
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

## ibmcloud catalog entry-create
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

## ibmcloud catalog entry-update
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

## ibmcloud catalog entry-delete
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

## ibmcloud catalog entry-visibility
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

## ibmcloud catalog entry-visibility-set
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

## ibmcloud catalog service-marketplace
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

## ibmcloud catalog templates
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

## ibmcloud catalog template
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

## ibmcloud catalog template-run
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

## ibmcloud catalog locations
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

## ibmcloud catalog runtime
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

## ibmcloud catalog runtimes
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
