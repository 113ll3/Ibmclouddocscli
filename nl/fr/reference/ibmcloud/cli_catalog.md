---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-19"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Recherche et gestion des offres de catalogue
{: #ibmcloud_catalog}

Les commandes suivantes permettent de gérer les entrées de catalogue {{site.data.keyword.cloud}}, les modèles de requête, les contextes d'exécution et les géolocalisations de centres de données.
{: shortdesc}
  
## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Effectuer des recherches dans des entrées de catalogue :
```
ibmcloud catalog search <QUERY> [-r, --region REGION] [-k, --kind KIND] [-p, --price PRICE] [-t, --tag TAG] [--sort-by PROPERTY] [--col COLUMNS] [--reverse] [--output TYPE] [--csv] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-r, --region</dt>
  <dd>Spécifier la région géographique dans laquelle effectuer la recherche. Actuellement, seules les régions "us-south" et "united-kingdom" sont prises en charge.</dd>
  <dt>-k, --kind</dt>
  <dd>Filtrer par type de ressource. Actuellement, seules les options "service-cf", "iaas", "runtime", "template" et "dashboard" sont prises en charge.</dd>
  <dt>-p, --price</dt>
  <dd>Filtrer par prix. Actuellement, seules les options "free", "paygo", "ibmcloud-subscription" sont prises en charge.</dd>
  <dt>-t, --tag</dt>
  <dd>Filtrer par étiquette.</dd>
  <dt>--sort-by</dt>
  <dd>Propriétés de tri</dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. En général, "group", "provider" et "tags"</dd>
  <dt>--reverse</dt>
  <dd>Inverser l'ordre de tri</dd>
  <dt>--output TYPE (facultatif)</dt>
  <dd>--output value  Indiquez un type de sortie. Seul JSON est actuellement pris en charge. Cette option exclut '--id'.</dd>
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

Obtenir une entrée de catalogue :
```
ibmcloud catalog entry ID [--children] [--output TYPE] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--children</dt>
  <dd>Obtenir tous les enfants de l'entrée de catalogue</dd>
  <dt>--output TYPE (facultatif)</dt>
  <dd>--output value  Indiquez un type de sortie. Seul JSON est actuellement pris en charge.</dd>
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

Créer une entrée de catalogue (administrateur de catalogue d'un compte uniquement) :
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

Mettre à jour une entrée de catalogue existante (administrateur ou éditeur de catalogue d'un compte uniquement) :
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
ibmcloud catalog delete `j402-dnf1i`
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

Obtenir la visibilité pour une entrée de catalogue (administrateur de catalogue d'un compte uniquement)
```
ibmcloud catalog entry-visibility ID  [--output TYPE] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>-json</dt>
  <dd>Imprimer la réponse JSON d'origine</dd>
  <dt>--output TYPE (facultatif)</dt>
  <dd>--output value  Indiquez un type de sortie. Seul JSON est actuellement pris en charge.</dd>
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

Mettre à jour la visibilité d'une entrée de catalogue existante (administrateur de catalogue d'un compte uniquement) :
```
ibmcloud catalog entry-visibility-set ID [--includes-add LIST] [--includes-remove LIST] [--excludes-add LIST] [--excludes-remove LIST] [--owner ID or Email] [--restrict] [--unrestrict] [-c PARAMETERS_AS_JSON] [--global]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>

  <dt>--includes-add</dt>
  <dd>Ajout d'un compte (ou d'une liste de comptes séparés par des virgules) à la liste d'inclusions de manière à accorder la visibilité à l'entrée. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>
  <dt>--includes-remove</dt>
  <dd>Suppression d'un compte (ou d'une liste de comptes séparés par des virgules) de la liste d'inclusions de manière à révoquer la visibilité de l'entrée. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>  
  <dt>--excludes-add</dt>
  <dd>Ajout d'un compte (ou d'une liste de comptes séparés par des virgules) à la liste d'exclusions. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>
  <dt>--excludes-remove</dt>
  <dd>Suppression d'un compte (ou d'une liste de comptes séparés par des virgules) de la liste d'exclusions de manière à révoquer la visibilité de l'entrée. Si le compte a été défini par des administrateurs globaux, ces derniers ne peuvent pas supprimer le compte. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>
  <dt>--owner</dt>
  <dd>Changement de propriétaire d'un objet. Les adresses électroniques et les identificateurs globaux uniques de compte sont acceptés.</dd>
  <dt>--restrict</dt>
  <dd>Modification de la restriction de l'objet visibilité en 'Privé'.</dd>
  <dt>--unrestrict</dt>
  <dd>Modification de la restriction de l'objet visibilité en 'Public'.</dd>  
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

Répertorier les offres de services de la place du marché :
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
{: codeblock}

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Afficher les modèles de conteneur boilerplate dans {{site.data.keyword.cloud_notm}}.
```
ibmcloud catalog templates [-d] [--output json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :

   <dl>
   <dt>-d (facultatif)</dt>
   <dd>Si l'option <i>-d</i> est spécifiée, la description de chaque modèle est également affichée. Sinon, seul l'ID et le nom des modèles sont affichés.</dd>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Afficher les informations détaillées d'un modèle de conteneur boilerplate spécifié.
```
ibmcloud catalog template TEMPLATE_ID [--output json]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>ID du modèle de conteneur boilerplate. Utilisez <i>ibmcloud templates</i> pour afficher tous les ID de modèles.</dd>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
   </dl>


<strong>Exemples</strong> :

Afficher les détails du modèle `mobileBackendStarter` :
```
ibmcloud catalog template mobileBackendStarter
```
{: codeblock}

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Créez une application cf reposant sur le modèle spécifié avec l'adresse URL et la description indiquées. Par défaut, la nouvelle application est démarrée automatiquement.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
   <dl>
   <dt>TEMPLATE_ID (obligatoire)</dt>
   <dd>Modèle utilisé pour la création de l'application. Utilisez <i>ibmcloud templates</i> pour afficher tous les ID de modèles.</dd>
   <dt>CF_APP_NAME (obligatoire)</dt>
   <dd>Nom de l'application cf à créer.</dd>
   <dt>-n<i>HOSTNAME</i></dt>
   <dd>Nom d'hôte de l'application CF. S'il n'est pas spécifié, la route est définie automatiquement par {{site.data.keyword.cloud_notm}} d'après le nom de votre application et le domaine par défaut.</dd>
   <dt>-d<i>DOMAINNAME</i></dt>
   <dd>Domaine de l'application CF. S'il n'est pas spécifié, la route est définie automatiquement par {{site.data.keyword.cloud_notm}} d'après le nom de votre application et le domaine par défaut.</dd>
   <dt>--desc <i>DESCRIPTION</i> (facultatif)</dt>
   <dd>Description de l'application.</dd>
   <dt>--no-start (facultatif)</dt>
   <dd>Ne démarrez pas automatiquement l'application après sa création. Si cette option n'est pas spécifiée, l'application est démarrée automatiquement après sa création.</dd>
   </dl>


<strong>Exemples</strong> :

Créer une application `cf` nommée `my-app` à partir d'un modèle `javaHelloWorld` :
```
ibmcloud catalog template-run javaHelloWorld my-app
```
{: codeblock}

Créer une application `my-ruby-app` à partir d'un modèle `rubyHelloWorld` avec une description :
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```
{: codeblock}

Créer une application `my-python-app` à partir d'un modèle `pythonHelloWorld` sans démarrage automatique :
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```
{: codeblock}

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Obtenir un sous-ensemble de choix de régions dans le format de votre choix.
```
ibmcloud catalog locations [-i, --id ID] [-k, --kind KIND] [--col COLUMNS] [--output TYPE] [--global] [--csv]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-i, --id</dt>
  <dd>Indiquer la géographie par ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Obtenir une liste d'entrées pour le type indiqué.</dd>
  <dt>--col</dt>
  <dd>Spécifier des colonnes supplémentaires pour la table. Actuellement, "group", "provider" et "tags".</dd>
  <dt>--output TYPE (facultatif)</dt>
  <dd>--output value  Indiquez un type de sortie. Seul JSON est actuellement pris en charge. Cette option exclut '--id'.</dd>
  <dt>--global</dt>
  <dd>Exploiter dans une portée globale.</dd>
  <dt>--csv</dt>
  <dd>Fichier CSV de sortie</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Afficher les détails d'un contexte d'exécution. Cette commande est uniquement disponible dans un cloud public.
```
ibmcloud catalog runtime RUNTIME_ID [--output json]
```

<strong>Options de commande</strong> :
<dl>
   <dt>--output FORMAT (facultatif)</dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails du contexte d'exécution "nodejsHelloWorld" :
```
catalog runtime nodejsHelloWorld
```
{: codeblock}

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Afficher tous les contextes d'exécution. Cette commande est uniquement disponible dans un cloud public.
```
ibmcloud catalog runtimes [-d] [--output json]
```

<strong>Options de commande</strong> :

<dl>
  <dt>-d</dt>
  <dd>Afficher la description de chaque contexte d'exécution</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les contextes d'exécution ainsi que leurs descriptions :
```
ibmcloud catalog runtimes -d
```
{: codeblock}
