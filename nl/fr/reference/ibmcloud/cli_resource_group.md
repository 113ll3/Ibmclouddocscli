---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, manage resources, resource group, ibmcloud resource group, ibmcloud resource, service-instance, quotas, resource group cli, resource cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Utilisation de ressources et de groupes de ressources
{: #ibmcloud_commands_resource}

Un groupe de ressources permet d'organiser vos ressources de compte en regroupements personnalisables. Les commandes suivantes permettent de gérer les ressources {{site.data.keyword.cloud}} dans un groupe de ressources.
{: shortdesc}

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
{: codeblock}

Répertorier le groupe par défaut du compte actuellement ciblé :
```
ibmcloud resource groups --default
```
{: codeblock}

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
{: codeblock}

Afficher uniquement le groupe de ressources `example-group` :
```
ibmcloud resource group example-group --id
```
{: codeblock}

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Créer un groupe de ressources :
```
ibmcloud resource group-create NAME
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom du groupe de ressources</dd>
</dl>

<strong>Exemples</strong> :

Créer un groupe de ressources `example-group` :
```
ibmcloud resource group-create example-group
```
{: codeblock}

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
{: codeblock}

Modifier le quota du groupe de ressources `example-group` et le remplacer par `free` :
```
ibmcloud resource group-update example-group -q free
```
{: codeblock}

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Répertorier toutes les définitions de quota
```
ibmcloud resource quotas
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
</dl>

<strong>Exemples</strong> :

Répertorier toutes les définitions de quota :
```
ibmcloud resource quotas
```
{: codeblock}

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Afficher les détails d'une définition de quota.
```
ibmcloud resource quota NAME
```
{: codeblock}

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
{: codeblock}

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migrer une instance de service Cloud Foundry dans le groupe de ressources
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

Répertorier les instances de service.
```
ibmcloud resource service-instances [--service-name SERVICE_NAME] [--location LOCATION] [--type INSTANCE_TYPE] [-g RESOURCE_GROUP] [--long] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>--service-name <i>SERVICE_NAME</i></dt>
  <dd>Nom du service membre</dd>
  <dt>--location <i>LOCATION</i></dt>
  <dd>Filtrer par emplacement</dd>
  <dt>--type <i>INSTANCE_TYPE</i></dt>
  <dd>Type des instances. Si aucun élément n'est indiqué, le type `service_instance` est utilisé. Utilisez all pour répertorier tous les types d'instance.</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--long</dt>
  <dd>Afficher des zones supplémentaires dans la sortie</dd>
  <dt>--output <i>FORMAT</i></dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. </dd>
</dl>

<strong>Exemples</strong> :

Répertorier les instances de service du service `test-service` :
```
ibmcloud resource service-instances --service-name test-service
```
{: codeblock}

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Afficher les détails d'une instance de service.

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
{: codeblock}

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Créer une instance de service.
```
ibmcloud resource service-instance-create NAME (SERVICE_NAME | SERVICE_ID) SERVICE_PLAN_NAME LOCATION [-d, --deployment DEPLOYMENT_NAME] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de l'instance de service</dd>
  <dt>SERVICE_NAME ou SERVICE_ID (obligatoire)</dt>
  <dd>Nom ou ID du service. Pour répertorier les offres de service, utilisez la [commande](/docs/cli/reference/ibmcloud/cli_catalog.html#ibmcloud_catalog_service_marketplace) `ibmcloud catalog service-marketplace`.</dd>
  <dt>SERVICE_PLAN_NAME ou SERVICE_PLAN_ID (obligatoire)</dt>
  <dd>Nom ou ID du plan de service</dd>
  <dt>LOCATION (obligatoire)</dt>
  <dd>Environnement ou emplacement cible pour créer l'instance de service</dd>
  <dt>-d, --deployment <i>DEPLOYMENT_NAME</i></dt>
  <dd>Nom du déploiement</dd>
  <dt>-p, --parameters <i>@JSONFILE or JSON_STRING</i></dt>
  <dd>Fichier JSON ou chaînes de paramètres JSON pour la création de l'instance de service</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Types des noeuds finaux de service</dd>
</dl>

<strong>Exemples</strong> :

Créer une instance de service nommée `my-service-instance` en utilisant le plan de service `test-service-plan` du service `test-service` à l'emplacement `eu-gb` :
```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```
{: codeblock}

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Mettre à jour l'instance de service.
```
ibmcloud resource ( NAME | ID ) [-n, --name NEW_NAME] [--service-plan-id SERVICE_PLAN_ID] [-p, --parameters @JSON_FILE | JSON_STRING ] [-g RESOURCE_GROUP] [--service-endpoints SERVICE_ENDPOINTS_TYPE] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>Name (obligatoire)</dt>
  <dd>Nom de l'instance de service, exclut ID</dd>
  <dt>ID (obligatoire)</dt>
  <dd>ID de l'instance de service, exclut NAME</dd>
  <dt>-n, --name <i>NEW_NAME</i></dt>
  <dd>Nouveau nom de l'instance de service</dd>
  <dt>--service-plan-id <i>SERVICE_PLAN_ID</i></dt>
  <dd>Nouvel ID du plan de service</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_STRING</i></dt>
  <dd>Fichier JSON ou chaînes de paramètres JSON pour la création de l'instance de service</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--service-endpoints <i>SERVICE_ENDPOINTS_TYPE</i></dt>
  <dd>Types des noeuds finaux de service</dd>
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

Supprimer l'instance de service.
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

Supprimer l'instance de service de ressource `my-service-instance` :
```
ibmcloud resource service-instance-delete my-service-instance
```
{: codeblock}

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Afficher les liaisons vers l'alias de service.
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

Afficher les liaisons de ressource à l'alias de service `my-service-alias` :
```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Afficher les détails d'une liaison de service.
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
{: codeblock}

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Créer une liaison de service.
```
ibmcloud resource service-binding-create SERVICE_ALIAS_NAME APP_NAME ROLE_NAME [-n BINDING_NAME] [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>SERVICE_ALIAS_NAME (obligatoire)</dt>
  <dd>Nom de l'alias de service</dd>
  <dt>APP_NAME (obligatoire)</dt>
  <dd>Nom d'application CloudFoundry</dd>
  <dt>ROLE_NAME (obligatoire)</dt>
  <dd>Nom du rôle utilisateur</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Nom ou identificateur unique universel de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameter <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Type du noeud final de service</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer une liaison de service entre l'alias de service `my-service-alias` et l'application `my-app` avec le rôle `Administrateur` :
```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```
{: codeblock}

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Supprimer une liaison de service.
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
{: codeblock}

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Répertorier les clés de service de l'instance de service ou de l'alias de service.
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

Affiche des informations détaillées sur les clés de service, où les premiers caractères *n* du nom de clé de service correspondent à l'élément KEY_NAME indiqué.
```
ibmcloud resource service-key (NAME | ID) [-g RESOURCE_GROUP] [--id] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME</dt>
  <dd>Nom de la clé</dd>
  <dt>ID</dt>
  <dd>ID de la clé</dd>
  <dt>-g</dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--id</dt>
  <dd>Affiche l'ID de la clé de service. Cette option exclut '--output'.</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--output FORMAT (facultatif)</dt>
  <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant. Cette option exclut '--id'.</dd>
</dl>

<strong>Exemples</strong> :

Afficher les détails des clés de service `my-service-key` :
```
ibmcloud resource service-key my-service-key
```
<strong>Exemples</strong> :
Afficher les détails de la clé de service portant l'ID `crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79` :

```
ibmcloud resource service-key crn:v1:bluemix:public:cloudantnosqldb:us-south:a/537860630a5ba7115be954e8d5aa5689:cc2a6d6c-8f5e-4038-b975-b09b51d1d8dc:resource-key:9057f12e-fbf5-421d-8865-764422217a79
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Créer une clé de service.
```
ibmcloud resource service-key-create NAME ROLE_NAME ( --instance-id SERVICE_INSTANCE_ID | --instance-name SERVICE_INSTANCE_NAME | --alias-id SERVICE_ALIAS_ID | --alias-name SERVICE_ALIAS_NAME) [--service-id SERVICE_ID] [-p, --parameters @JSON_FILE | JSON_TEXT] [-g RESOURCE_GROUP] [--service-endpoint SERVICE_ENDPOINT_TYPE] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME (obligatoire)</dt>
  <dd>Nom de la clé</dd>
  <dt>ROLE_NAME (obligatoire)</dt>
  <dd>Nom du rôle utilisateur</dd>
  <dt>--instance-id <i>SERVICE_INSTANCE_ID</i></dt>
  <dd>ID de l'instance de service</dd>
  <dt>--instance-name <i>SERVICE_INSTANCE_NAME</i></dt>
  <dd>Nom de l'instance de service</dd>
  <dt>--alias-id <i>SERVICE_ALIAS_ID</i></dt>
  <dd>ID de l'alias de service</dd>
  <dt>--alias-name <i>SERVICE_ALIAS_NAME</i></dt>
  <dd>Nom de l'alias de service</dd>
  <dt>--service-id <i>SERVICE_ID</i></dt>
  <dd>Nom ou identificateur unique universel de l'ID de service auquel le rôle appartient</dd>
  <dt>-p, --parameters <i>@JSON_FILE | JSON_TEXT</i></dt>
  <dd>Fichier JSON ou chaîne JSON de paramètres</dd>
  <dt>-g <i>RESOURCE_GROUP</i></dt>
  <dd>Nom du groupe de ressources</dd>
  <dt>--service-endpoint <i>SERVICE_ENDPOINT_TYPE</i></dt>
  <dd>Type du noeud final de service</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la création sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Créer une clé de service nommée `my-service-key` avec le rôle `Administrateur` pour l'instance de service `my-service-instance` :
```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Mettre à jour une clé de service.
```
ibmcloud resource service-key-update ( NAME | ID ) [-n, --name NEW_NAME] [-g RESOURCE_GROUP] [-f, --force]
```

<strong>Prérequis</strong> : Noeud final, Connexion, Cible

<strong>Options de commande</strong> :
<dl>
  <dt>NAME | ID</dt>
  <dd>Nom ou ID de la clé</dd>
  <dt>-n, --name NEW_NAME</dt>
  <dd>Nouveau nom de la clé</dd>
  <dt>-g RESOURCE_GROUP</dt>
  <dd>ID du groupe de ressources auquel la clé appartient</dd>
  <dt>-f, --force</dt>
  <dd>Forcer la mise à jour sans confirmation</dd>
</dl>

<strong>Exemples</strong> :

Mettre à jour une clé de service nommée `my-service-key` et lui attribuer le nouveau nom `my-service-key-2` :
```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Supprimer une clé de service.
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

Répertorier les alias d'une instance de service.
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

Répertorier les alias de service de l'instance de service `my-service-instance` :
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Afficher les détails d'un alias de service.
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

Créer un alias d'une instance de service.
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

Mettre à jour un alias de service.
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

Supprimer un alias de service.
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

Rechercher des ressources à l'aide de la syntaxe de requête Lucene.
```
ibmcloud search LUCENE_QUERY [-o, --offset OFFSET] [-l, --limit LIMIT] [-s, --sort-by (name, family, region, type, crn)] [-p, --provider PROVIDER]
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
  <dt>-p, --provider</dt>
  <dd>Afficher les ressources d'infrastructure classique. La seule valeur autorisée est classic-infrastructure</dd>
</dl>

<strong>Attributs pouvant faire l'objet d'une recherche</strong>
Vous pouvez rechercher les attributs suivants :

<dl>
  <dt>name</dt>
  <dd>Nom défini par l'utilisateur de la ressource.</dd>
  <dt>région</dt>
  <dd>Emplacement géographique où la ressource est mise à disposition. Par exemple : us-south, us-east, au-syd, eu-gb, eu-de et jp-tok.</dd>
  <dt>service_name</dt>
  <dd>Nom du service, tel qu'il apparaît dans la colonne de nom de la sortie de l'élément 'ibmcloud catalog service-marketplace'.</dd>
  <dt>family</dt>
  <dd>Composant de cloud auquel votre ressource appartient. Les valeurs autorisées sont les suivantes : cloud_foundry, containers,  resource_controller, vmware ou ims.</dd>
  <dt>organization_id</dt>
  <dd>ID global unique de l'organisation Cloud Foundry.</dd>
  <dt>doc.space_id</dt>
  <dd>ID global unique de l'espace Cloud Foundry.</dd>
  <dt>doc.resource_group_id</dt>
  <dd>ID du groupe de ressources.</dd>
  <dt>type</dt>
  <dd>Type de ressource. Les valeurs autorisées sont les suivantes : k8-cluster, cf-service-instance, cf-user-provided-service-instance, cf-organization, cf-service-binding, cf-space, cf-application, resource-instance, resource-alias, resource-binding, resource-group, vmware-solutions, cloud-objects-storage-infrastructure, block-storage, file-storage, cloud-backup.</dd>
  <dt>creation_date</dt>
  <dd>Date de création de la ressource.</dd>
  <dt>modification_date</dt>
  <dd>Date de dernière modification de la ressource. Elle est au format aaaa-mm-jjThh:mm:ssZ </dd>
  <dt>_objectType</dt>
  <dd>Type de la ressource d'infrastructure classique. Les valeurs autorisées sont les suivantes : SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall et SoftLayer_Virtual_Guest. </dd>
  <dt>tags, tagReferences.tag.name</dt>
  <dd>Etiquette associée à une ressource. Utilisez tagReferences.tag.name lors de la recherche d'étiquettes associées aux ressources de l'infrastructure classique </dd> 
</dl>

<strong>Exemples</strong> :

Rechercher les applications Cloud Foundry dont le nom commence par un texte indiqué :
```
ibmcloud resource search "name:my* AND type:cf-application"
```

Rechercher les instances de service Cloud Foundry portant le nom de service indiqué :
```
ibmcloud resource search "service_name:messagehub AND type:cf-service-instance"
```

Rechercher les liaisons de service Cloud Foundry dans l'organisation portant l'ID indiqué :
```
ibmcloud resource search "organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding"
```

Rechercher les espaces Cloud Foundry portant le nom indiqué et situés dans l'une des deux régions spécifiées :
```
ibmcloud resource search "name:dev AND type:cf-space AND region:(us-south OR eu-gb)"
```

Rechercher les ressources dont le nom contient le mot dev dans l'espace Cloud Foundry portant l'ID indiqué :
```
ibmcloud resource search "name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7"
```

Rechercher les ressources Resource Controller dans l'emplacement indiqué (par exemple, dans la région us-south) :
```
ibmcloud resource search "region:us-south AND family:resource_controller"
```

Rechercher les ressources ou les alias dans le groupe de ressources portant l'ID indiqué :
```
ibmcloud resource search "(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)"
```

Rechercher les groupes de ressources portant le nom default :
```
ibmcloud resource search "name:default AND type:resource-group"
```

Rechercher les liaisons de ressources pour le nom de service indiqué :
```
ibmcloud resource search "service_name:cloud-object-storage AND type:resource-binding"
```

Rechercher une ressource portant le nom de ressource de cloud indiqué :
```
ibmcloud resource search "crn:\"crn:v1:bluemix:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Rechercher une ressource avec la balise indiqué :
```
ibmcloud resource search "tags:\"mykey:myvalue\""
```
{: codeblock}

Rechercher la ressource d'invité virtuel d'infrastructure classique avec l'ID spécifié (uniquement avec -p classic-infrastructure) :
```
ibmcloud resource search "id:12345678 _objectType:SoftLayer_Virtual_Guest"
```
{: codeblock}

Rechercher la ressource de matériel d'infrastructure classique avec le nom d'étiquette indiqué (uniquement avec -p classic-infrastructure) :
```
ibmcloud resource search "tagReferences.tag.name:name _objectType:SoftLayer_Hardware"
```
{: codeblock}

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Répertorier toutes les étiquettes de votre compte de facturation

```
ibmcloud resource tags [-o, --offset OFFSET] [-l, --limit LIMIT] [-p, --provider classic-infrastructure] [-d, --details true]
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>-o, -offset</dt>
  <dd>Numéro de position de l'étiquette de début</dd>
  <dt>-l, -limit</dt>
  <dd>Nombre d'étiquettes à renvoyer (valeur maximale : 1 000, valeur par défaut : 100 )</dd>
  <dt>-p; --provider</dt> 
  <dd>Indiquer classic-infrastructure lors de la recherche d'étiquettes d'infrastructure classique</dd>
  <dt>-d, --details</dt>
  <dd>Afficher le nombre de ressources étiquetées.</dd>
</dl>


## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Associer une ou plusieurs étiquettes à une ressource :
```
ibmcloud resource tag-attach --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```
<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-names (obligatoire)</dt>
  <dd>Liste de noms d'étiquettes séparés par des virgules</dd>
  <dt>--resource-name</dt>
  <dd>Nom de la ressource à laquelle les étiquettes doivent être associées. Cette option ne peut pas être utilisée avec des ressources d'infrastructure classique. </dd>
  <dt>--resource-id</dt>
  <dd>Nom CRN de la ressource à laquelle les étiquettes vont être associées. Pour les ressources de l'infrastructure classique, il s'agit de l'ID de la ressource. Vous pouvez obtenir ce nom ou l'ID de la ressource en utilisant la commande 'ibmcloud resource search'.</dd>
  <dt>--resource-type</dt>
  <dd>Type de la ressource à laquelle les étiquettes vont êtes associées. Ce paramètre est requis en cas d'association d'une étiquette à une ressource d'infrastructure classique. Les valeurs possibles pour --resource-type sont les suivantes : SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall et SoftLayer_Virtual_Guest. </dd>
</dl>

<strong>Exemples</strong> :

* Pour associer l'étiquette `MyTag` à un cluster Kubernetes nommé `MyCluster`, recherchez tout d'abord le nom CRN du cluster que vous souhaitez étiqueter :
  ```
  ibmcloud resource search 'type:k8\-cluster AND name:MyCluster'
  ```
  {: codeblock}

  Notez le nom CRN, qui est une chaîne similaire à l'exemple suivant : 
  ```
  crn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a::
  ```
  {: screen}

  Pour associer l'étiquette, exécutez la commande suivante :
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id rn:v1:bluemix:public:containers-kubernetes:us-south:a/a27a4741a57dcf5c965939adb66fe1c7:a46242e638ca47b09f10e9a3cbe5687a:: 
  ```
  {: codeblock}

* Pour associer l'étiquette `MyTag` à un nom de ressource `MyResource` :
  ```
  ibmcloud resource tag-attach --tag-name MyTag --resource-name  'MyResource'
  ```
  {: codeblock}
  
  
* Pour associer l'étiquette `MyTag` à un invité virtuel de l'infrastructure classique nommé `MyVM`, recherchez tout d'abord l'ID de l'invité virtuel que vous souhaitez étiqueter :
  ```
  ibmcloud resource search 'fullyQualifiedDomainName:MyVM  _objectType:SoftLayer_Virtual_Guest' -p classic-infrastructure
  ```
  {: codeblock}

  Notez l'ID, qui est une chaîne similaire à `48373549`.

  Pour associer l'étiquette, exécutez la commande suivante :
  ```
  ibmcloud resource tag-attach --tag-names MyTag --resource-id 48373549 --resource-type SoftLayer_Virtual_Guest  
  ```
  {: codeblock}

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Dissociation d'une ou de plusieurs étiquettes d'une ressource :
```
ibmcloud resource tag-detach  --tag-names TAG_NAMES (--resource-name NAME | --resource-id RESOURCE_ID ) [--resource-type RESOURCE_TYPE]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-names (obligatoire)</dt>
  <dd>Liste de noms d'étiquettes séparés par des virgules</dd>
  <dt>--resource-name</dt>
  <dd>Nom de la ressource dont les étiquettes doivent être enlevées. Cette option ne peut pas être utilisée avec des ressources d'infrastructure classique. </dd>
  <dt>--resource-id</dt>
  <dd>Nom CRN de la ressource dont les étiquettes vont être enlevées. Pour les ressources de l'infrastructure classique, il s'agit de l'ID de la ressource. Vous pouvez obtenir ce nom ou l'ID de la ressource en utilisant la commande 'ibmcloud resource search'.</dd>
  <dt>--resource-type</dt>
  <dd>Type de la ressource dont les étiquettes vont êtes dissociées. Ce paramètre est requis en cas d'association d'une étiquette à une ressource d'infrastructure classique. Les valeurs possibles pour --resource-type sont les suivantes : SoftLayer_Virtual_DedicatedHost, SoftLayer_Hardware, SoftLayer_Network_Application_Delivery_Controller, SoftLayer_Network_Subnet_IpAddress, SoftLayer_Network_Vlan, SoftLayer_Network_Vlan_Firewall et SoftLayer_Virtual_Guest. </dd>
</dl>


## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Suppression d'une étiquette :
```
ibmcloud resource tag-delete --tag-name TAG_NAME [-p, --provider PROVIDER]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
  <dt>--tag-name (obligatoire)</dt>
  <dd>Nom de l'étiquette à supprimer.</dd>
  <dt>-p; --provider</dt> 
  <dd>Indiquez classic-infrastructure lors de la suppression d'une étiquette d'infrastructure classique</dd>
</dl>

Une étiquette ne peut être supprimée que si elle n'est associée à aucune ressource.
