---

copyright:

  years: 2018


lastupdated: "2018-11-05"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Groupes de ressources et ressources
{: #ibmcloud_commands_resource}

Un groupe de ressources permet d'organiser vos ressources de compte en regroupements personnalisables. Les commandes suivantes permettent de gérer les ressources et les groupes de ressources {{site.data.keyword.Bluemix}} dans un groupe de ressources.
{: shortdesc}

<table summary="Commandes ibmcloud que vous pouvez utiliser pour gérer les groupes de ressources et les ressources.">
  <thead>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags 
](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Répertorier les groupes de ressources.

```
ibmcloud resource groups [--default] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--default</dt>
  <dd>Obtenir le groupe par défaut du compte en cours.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier tous les groupes de ressources du compte actuellement ciblé :

```
ibmcloud resource groups
```

Répertorier le groupe par défaut du compte actuellement ciblé :

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Afficher les détails d'un groupe de ressources

```
ibmcloud resource group NAME [--id] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID uniquement</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Afficher le groupe de ressources `example-group` :

```
ibmcloud resource group example-group
```

Afficher uniquement le groupe de ressources `example-group` :

```
ibmcloud resource group example-group --id
```

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Créer un groupe de ressources

```
ibmcloud resource group-create NAME QUOTA_NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :

<strong>Exemples</strong> :

Créer un groupe de ressources `example-group` avec le quota `free` :

```
ibmcloud resource group-create example-group free
```

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Mettre à jour un groupe de ressources existant

```
ibmcloud resource group-update NAME [-n, --name NEW_NAME] [-q, --quota NEW_QUOTA_NAME]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources cible</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom du groupe de ressources</dd>
  <dt>-q, --quota</dt>
  <dd>Nom de la nouvelle définition de quota.</dd>
  <dt>-f</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Renommer le groupe de ressources `example-group` en `trial-group` :

```
ibmcloud resource group-update example-group -n trial-group
```

Modifier le quota du groupe de ressources `example-group` et le remplacer par `free` :

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Répertorier toutes les définitions de quota

```
ibmcloud resource quotas
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les définitions de quota :

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Afficher les détails d'une définition de quota

```
ibmcloud resource quota NAME
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du quota</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails du quota `free` :

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrer une instance de service Cloudfoundry dans le groupe de ressources

```
ibmcloud resource cf-service-instance-migrate (SERVICE_INSTANCE_NAME | SERVICE_INSTANCE_ID) [--resource-group-name RESOURCE_GROUP_NAME | --resource-group-id RESOURCE_GROUP_ID] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_INSTANCE_NAME ou SERVICE_INSTANCE_ID (obligatoire)</dt>
  <dd>Nom ou ID de l'instance de service</dd>
  <dt>--resource-group-name</dt>
  <dd>Nom du groupe de ressources. Cette option exclut '--resource-group-id'. Si aucun de ces éléments n'est indiqué, le groupe de ressources actuellement ciblé est utilisé par défaut.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID du groupe de ressources. Cette option exclut '--resource-group-name'. Si aucun de ces éléments n'est indiqué, le groupe de ressources actuellement ciblé est utilisé par défaut.</dd>
  <dt>-f, --force</dt>
  <dd>Migrer sans confirmation</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Répertorier les instances de service

```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--long] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--service-name</dt>
  <dd>Nom du service membre</dd>
  <dt>--location</dt>
  <dd>Filtrer par emplacement</dd>
  <dt>--long</dt>
  <dd>Afficher des zones supplémentaires dans la sortie</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :

Répertorier les instances de service du service `test-service` :

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Afficher les détails d'une instance de service

```
ibmcloud resource service-instance (NAME|ID) [--location LOCATION] [--id] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire), exclut ID</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>ID (obligatoire), exclut NAME</dt>
  <dd>ID de l'instance de service</dd>
  <dt>--location</dt>
  <dd>Filtrer par emplacement</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID de l'instance de service</dd>
  <dt>--output</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut '--id'.</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'instance de service `my-service-instance` :

```
ibmcloud resource service-instance my-service-instance
```

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Créer une instance de service

```
ibmcloud resource service-instance-create NAME SERVICE_NAME|SERVICE_ID SERVICE_PLAN_NAME|SERVICE_PLAN_ID LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>SERVICE_NAME ou SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou ID du service</dd>
  <dt>SERVICE_PLAN_NAME ou SERVICE_PLAN_ID (obligatoire)</dt>
  <dd>Nom ou ID du plan de service</dd>
  <dt>LOCATION</dt>
  <dd>Environnement ou emplacement cible pour créer l'instance de service</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaînes de paramètres JSON pour la création de l'instance de service</dd>
  <dt>-d, --deployment</dt>
  <dd>Nom du déploiement</dd>
</dl>

<strong>Exemples</strong>:
Créer une instance de service `my-service-instance` en utilisant le plan de service `test-service-plan` du service `test-service` sur l'emplacement `eu-gb` :

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Mettre à jour une instance de service

```
ibmcloud resource service-instance-update (NAME|ID) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [--parameters @JSON_FILE | JSON_STRING] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>Name (obligatoire)</dt>
  <dd>Nom de l'instance de service, exclut ID</dd>
  <dt>ID (obligatoire)</dt>
  <dd>ID de l'instance de service, exclut NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de l'instance de service</dd>
  <dt>--service-plan-id</dt>
  <dd>Nouvel ID du plan de service</dd>
  <dt>--parameters @JSON_FILE | JSON_STRING</dt>
  <dd>Fichier JSON ou chaînes de paramètres JSON pour la création de l'instance de service</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Mettre à jour l'instance de service `my-service-instance` et remplacer son nom par `new-service-instance` :

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Supprimer une instance de service

```
ibmcloud resource service-instance-delete (NAME|ID) [-f, --force] [--recursive]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>Name (obligatoire)</dt>
  <dd>Nom de l'instance de service, exclut ID</dd>
  <dt>ID (obligatoire)</dt>
  <dd>ID de l'instance de service, exclut NAME</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
  <dt>--recursive</dt>
  <dd>Supprimer toutes les ressources membres</dd>
</dl>

<strong>Exemples</strong> :
Supprimer l'instance de service `my-service-instance` :

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Afficher les liaisons vers l'alias de service

```
ibmcloud resource service-bindings SERVICE_ALIAS [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :
Afficher les liaisons de ressources à l'alias de service `my-service-alias`:

```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Afficher les détails d'une liaison de service

```
ibmcloud resource service-binding ALIAS_NAME APP_NAME [--id] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Seul l'ID s'affiche. Toute autre sortie pour la liaison de service est supprimée. Cette option exclut '--output'.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut '--id'.</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de liaison de service entre l'alias de service `my-service-alias` et l'application `my-app` :

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Créer une liaison de service

```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nom du rôle utilisateur</dd>
  <dt>--service-id</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameter</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Créer une liaison de service entre l'alias de ressource `my-service-alias` et l'application `my-app` avec le rôle `Administrateur` :

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Supprimer une liaison de service

```
ibmcloud resource service-binding-delete SERVICE_ALIAS APP_NAME [-f, --force]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Supprimer une liaison de service entre l'alias de service `my-service-alias` et l'application `my-app` :

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Répertorier les clés de service de l'instance de service ou de l'alias de service

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NAME | --alias-id ID | --alias-name NAME ] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>--alias-id</dt>
  <dd>ID de l'alias de service</dd>
  <dt>--alias-name</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les clés de service de l'instance de service `my-service-instance` :

```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMAT]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Afficher les détails d'une clé de service

```
ibmcloud resource service-key KEY_NAME [--id]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>KEY_NAME</dt>
  <dd>Nom de la clé</dd>
  <dt>--id</dt>
  <dd>Afficher l'ID de la clé de service</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de la clé de service `my-service-key` :

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Créer une clé de service

```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME ) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-f, --force]]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME</dt>
  <dd>Nom de la clé</dd>
  <dt>ROLE_NAME</dt>
  <dd>Nom du rôle utilisateur</dd>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>--alias-id</dt>
  <dd>ID de l'alias de service</dd>
  <dt>--alias-name</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--service-id</dt>
  <dd>Nom ou identificateur unique universel de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Créer une clé de service nommée `my-service-key` avec le rôle `Administrateur` pour l'instance de service `my-service-instance` :

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Supprimer une clé de service

```
ibmcloud resource service-key-delete ( KEY_NAME | KEY_ID ) [-f, --forece]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>KEY_NAME | KEY_ID</dt>
  <dd>Nom de la clé ou de l'ID de la clé</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Supprimer la clé de service `my-service-key` :

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Répertorier les alias d'une instance de service

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NAME ] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service membre.</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service membre.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>

<strong>Exemples</strong> :
Répertorier les alias de l'instance de service `my-service-instance` :
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Afficher les détails d'un alias de service

```
ibmcloud resource service-alias ALIAS_NAME [--id] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--id</dt>
  <dd>Seul l'ID de l'alias du service donné s'affiche. Toute autre sortie de l'alias est supprimée. Cette option exclut '--output'.</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>--output value  Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut '--id'.</dd>
</dl>

<strong>Exemples</strong> :
Afficher les détails de l'alias de service `my-service-alias` :
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Créer un alias d'une instance de service

```
ibmcloud resource service-alias-create ALIAS_NAME ( --instance-id ID | --instance-name NAME ) [-s SPACE_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_TEXT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--instance-id</dt>
  <dd>ID de l'instance de service membre.</dd>
  <dt>--instance-name</dt>
  <dd>Nom de l'instance de service membre.</dd>
  <dt>-s</dt>
  <dd>Nom de l'espace dans lequel l'alias est créé. Il s'agit de l'espace en cours par défaut.</dd>
  <dt>-t, --tags</dt>
  <dd>Liste d'étiquettes.</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres.</dd>
</dl>

<strong>Exemples</strong> :
Créer un alias de service nommé `my-service-alias` pour l'instance de service `my-service-instance` :
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Mettre à jour un alias de service

```
ibmcloud resource service-alias-update ALIAS_NAME [-n, --name NEW_NAME] [-t, --tags TAGS] [-p, --parameters @JSON_FILE | JSON_STRING ][-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>-n, --name</dt>
  <dd>Nouveau nom de l'alias de service.</dd>
  <dt>-t, --tags</dt>
  <dd>Liste d'étiquettes.</dd>
  <dt>-p, --parameters</dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres.</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation de l'utilisateur</dd>
</dl>

<strong>Exemples</strong> :
Mettre à jour l'alias de service `my-service-alias` et remplacer son nom par `new-service-alias` :

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Supprimer un alias de service

```
ibmcloud resource service-alias-delete ALIAS_NAME [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la suppression sans confirmation</dd>
</dl>

<strong>Exemples</strong> :
Supprimer l'alias de service `my-service-alias` :

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Rechercher des ressources à l'aide de la syntaxe de requête Lucene

```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-o, -offset</dt>
  <dd>Numéro de position de ressource de début</dd>
  <dt>-l, -limit</dt>
  <dd>Nombre de ressources à renvoyer (10000 au maximum)</dd>
  <dt>-s, --sort-by</dt>
  <dd>Propriété à utiliser pour le tri. Les entrées acceptées sont les suivantes : `name`, `family`, `region`, `type` et `crn`.</dd>
</dl>

<strong>Exemples</strong> :
Rechercher les applications Cloud Foundry dont le nom commence par un texte indiqué :

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Rechercher les instances de service Cloud Foundry portant le nom de service indiqué :

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Rechercher les liaisons de service Cloud Foundry dans l'organisation portant l'ID indiqué :

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Rechercher les espaces Cloud Foundry portant le nom indiqué et situés dans l'une des deux régions spécifiées :

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Rechercher les ressources dont le nom contient le mot dev dans l'espace Cloud Foundry portant l'ID indiqué :

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Rechercher les ressources Resource Controller dans l'emplacement indiqué (par exemple, dans la région us-south) :

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Rechercher les ressources ou les alias dans le groupe de ressources portant l'ID indiqué :

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Rechercher les groupes de ressources portant le nom default :

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Rechercher les liaisons de ressources pour le nom de service indiqué :

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Rechercher une ressource portant le nom de ressource de cloud indiqué :

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Rechercher une ressource avec la balise indiqué :

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Répertorier toutes les étiquettes

```
ibmcloud resource tags [--tag-type TAG_TYPE] [-o, --offset OFFSET] [-l, --limit LIMIT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-type</dt>
  <dd>Type d'étiquette (valeurs prises en charge : utilisateur, restreinte)</dd>
  <dt>-o, --offset</dt>
  <dd>Numéro de position de ressource de départ (valeur par défaut : 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Nombre de ressources à renvoyer (valeur maximale et valeur par défaut : 10 000)</dd>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les étiquettes

```
ibmcloud resource tags
```

Répertorier toutes les étiquettes restreintes

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Afficher les détails d'une étiquette

```
ibmcloud resource tag (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, exclut --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, exclut --tag-name</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails de l'étiquette "Ray Brown"

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Créer une étiquette

```
ibmcloud resource tag-create --tag-name TAG_NAME [--tag-type TAG_TYPE]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom de l'étiquette</dd>
  <dt>--tag-type</dt>
  <dd>Type d'étiquette (valeurs prises en charge : utilisateur, restreinte ; valeur par défaut : utilisateur)</dd>
</dl>

<strong>Exemples</strong> :

Créer une étiquette utilisateur ayant le nom think:2018

```
ibmcloud resource tag-create --tag-name think:2018
```

Créer une étiquette restreinte ayant le nom department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Créer une étiquette utilisateur portant le nom "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Créer une étiquette restreinte portant le nom "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Supprimer une étiquette

```
ibmcloud resource tag-delete (--tag-name TAG_NAME | --tag-crn TAG_CRN)
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, exclut --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, exclut --tag-name</dd>
</dl>

<strong>Exemples</strong> :

Supprimer l'étiquette "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Ajouter une étiquette à une ressource

```
ibmcloud resource tag-attach (--tag-name TAG_NAME | --tag-crn TAG_CRN ) --resource-crn RESOURCE_CRN
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, exclut --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, exclut --tag-name</dd>
  <dt>--resource-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de la ressource</dd>
</dl>

<strong>Exemples</strong> :

Ajouter l'étiquette "Ray Brown" à la ressource dont le nom de ressource de cloud est resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Retirer une étiquette d'une ressource

```
ibmcloud  tag-detach (--tag-name TAG_NAME | --tag-crn TAG_CRN) --resource-crn RESOURCE_CRN
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, exclut --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, exclut --tag-name</dd>
  <dt>--resource-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de la ressource</dd>
</dl>

<strong>Exemples</strong> :

Retirer l'étiquette "Ray Brown" de la ressource dont le nom de ressource de cloud est resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Basculer l'étiquette utilisateur vers une étiquette restreinte et inversement

```
ibmcloud tag-update (--tag-name TAG_NAME | --tag-crn TAG_CRN) --tag-type TAG_TYPE
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom d'étiquette, exclut --tag-crn</dd>
  <dt>--tag-crn (obligatoire)</dt>
  <dd>Nom de ressource de cloud de l'étiquette, exclut --tag-name</dd>
  <dt>--tag-type (obligatoire)</dt>
  <dd>Type d'étiquette</dd>
</dl>

<strong>Exemples</strong> :

Basculer l'étiquette "Ray Brown" vers une étiquette restreinte

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
