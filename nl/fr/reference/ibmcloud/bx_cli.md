---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-26"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# Commandes générales de l'interface CLI (ibmcloud)
{: #ibmcloud_cli}

L'interface de ligne de commande {{site.data.keyword.cloud_notm}} fournit un ensemble de commandes qui sont regroupées par espace de nom pour que les utilisateurs puissent interagir avec {{site.data.keyword.cloud_notm}}.

Le client de ligne de commande {{site.data.keyword.cloud_notm}} inclut un client de ligne de commande Cloud Foundry dans son installation. Si votre propre interface CLI cf est installée, n'utilisez pas à la fois les commandes CLI d'{{site.data.keyword.cloud_notm}}, (`ibmcloud [commande]`) et les commandes CLI de Cloud Foundry (`cf [commande]`) de votre propre installation dans le même contexte. Utilisez à la place `ibmcloud cf [commande]` si vous désirez utiliser cf cli pour gérer les ressources Cloud Foundry dans le contexte CLI d'{{site.data.keyword.cloud_notm}}. Notez que la commande `ibmcloud cf api/login/logout/target` n'est pas admise et que vous devez utiliser `ibmcloud api/login/logout/target` à la place.

A compter de mai 2018, les commandes de l'interface CLI d'{{site.data.keyword.cloud_notm}} ont été changées de `bluemix` et `bx` en `ibmcloud`. Vous pouvez toutefois continuer à utiliser les commandes de l'interface CLI `bluemix` et `bx` jusqu'à ce qu'elles soient retirées.
{: tip}

Les listes ci-dessous répertorient les commandes prises en charge par l'interface de ligne de commande {{site.data.keyword.cloud_notm}}, en indiquant leurs noms, leurs arguments, leurs options, leurs prérequis, leurs descriptions, et des exemples.
{: shortdesc}

La zone *Prérequis* répertorie les actions requises avant l'utilisation de la commande. Les commandes pour lesquelles aucune action n'est requise indiquent **Aucun**. Sinon, les prérequis peuvent inclure une ou plusieurs des actions suivantes :

<dl>
<dt>Noeud final</dt>
<dd>Un noeud final d'API doit être défini via <code>ibmcloud api</code> avant l'utilisation de la commande.</dd>
<dt>Connexion</dt>
<dd>Vous devez vous connecter avec la commande <code>ibmcloud login</code> avant d'utiliser cette commande.
Si vous vous connectez avec un ID fédéré, utilisez l'option '--sso' pour vous authentifier avec un code d'accès unique ou utilisez l'option '--apikey' pour vous authentifier avec une clé d'API.
</dd>
<dt>Cible</dt>
<dd>La commande <code>ibmcloud target</code> doit être utilisée pour configurer une organisation et un espace avant d'appeler cette commande.</dd>
<dt>Docker</dt>
<dd>L'interface de ligne de commande Docker (docker) doit être installée pour que vous puissiez exécuter cette commande.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Afficher l'aide générale pour les commandes intégrées de premier niveau et les espaces de nom pris en charge de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}, ou l'aide d'une commande intégrée ou d'un espace de nom spécifique.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>COMMAND|NAMESPACE (facultatif)</dt>
   <dd>Commande ou espace de nom pour lequel afficher l'aide. Si la commande ou l'espace de nom n'est pas spécifié, l'aide générale de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est affichée.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher l'aide générale pour l'interface de ligne de commande {{site.data.keyword.cloud_notm}} :
```
ibmcloud help
```
{: codeblock}

Afficher l'aide pour la commande `dev` :
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Définir ou afficher le noeud final d'API {{site.data.keyword.cloud_notm}}.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>API_ENDPOINT (facultatif)</dt>
   <dd>Noeud final d'API ciblé. Par exemple, `https://cloud.ibm.com`. Si l'option *API_ENDPOINT* et l'option `--unset` sont toutes les deux spécifiées, le noeud final d'API en cours est affiché.</dd>
   <dt>--unset (facultatif)</dt>
   <dd>Supprimer le paramètre de noeud final d'API.</dd>
   <dt>--skip-ssl-validation (facultatif)</dt>
   <dd>Ignorer la validation SSL des demandes HTTP.</dd>
   </dl>
<strong>Exemples</strong> :

Définir le noeud final d'API cloud.ibm.com :
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

Afficher le noeud final d'API en cours :
```
ibmcloud api
```
{: codeblock}

Annuler la définition du noeud final d'API :
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Ecrire les valeurs par défaut dans le fichier de configuration.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>Délai d'attente pour les demandes HTTP. La valeur par défaut est 60 secondes.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>Consigne la trace des demandes HTTP sur le terminal ou dans le fichier spécifié.</dd>
   <dt>--color true|false</dt>
   <dd>Active ou désactive la sortie en couleurs. Elle est activée par défaut.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Définit un environnement local par défaut. Si LOCALE a pour valeur <i>CLEAR</i>, l'environnement local précédent est supprimé.</dd>
   <dt>--check-version true|false</dt>
   <dd>Active ou désactive la vérification de la version de l'interface de ligne de commande.</dd>
   </dl>

Une seule de ces options peut être indiquée à la fois.

<strong>Exemples</strong> :

Définir le délai d'attente des demandes HTTP à 30 secondes :
```
ibmcloud config --http-timeout 30
```
{: codeblock}

Activer la sortie de trace pour les demandes HTTP :
```
ibmcloud config --trace true
```
{: codeblock}

Consigner la trace des demandes HTTP dans le fichier spécifié */home/usera/my_trace* :
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

Désactiver la sortie couleur :
```
ibmcloud config --color false
```
{: codeblock}

Définir l'environnement local zh_Hans :
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

Effacer les paramètres d'environnement local :
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

La commande `ibmcloud info` n'est plus disponible depuis la version `0.14` de l'interface de ligne de commande. Pour installer la dernière version, voir [Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud cf
{: #ibmcloud_cf}

Appeler l'interface CLI CF imbriquée
```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>-q, --quiet</dt>
  <dd>Désactiver le message "Appel de commande cf..."</dd>
</dl>

<strong>Exemples</strong> :

Liste d'applications CF :

```
ibmcloud cf apps
```

Répertorier les services CF sans le message "Appel de commande cf...":
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Connecter l'utilisateur.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>Prérequis</strong> : Aucun

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Options de commande</strong> :
<dl>
  <dt> -a <i>API_ENDPOINT</i> (facultatif)</dt>
  <dd> Noeud final de l'API (par exemple, cloud.ibm.com)</dd>
  <dt> --apikey <i>API_KEY ou @API_KEY_FILE_PATH</i>
  <dd> Contenu de clé d'API ou chemin d'un fichier de clés d'API indiqué par @</dd>
  <dt> --sso (facultatif) </dt>
  <dd> Utiliser un code d'accès unique pour la connexion </dd>
  <dt> -u <i>USERNAME</i> (facultatif)</dt>
  <dd> Nom d'utilisateur</dd>
  <dt> -p <i>PASSWORD</i> (facultatif)</dt>
  <dd> Mot de passe</dd>
  <dt> -c <i>ACCOUNT_ID</i> (facultatif) </dt>
  <dd> ID du compte cible. Cette option exclut --no-account</dd>
  <dt> --no-account (facultatif) </dt>
  <dd> Forcer la connexion sans compte. Cette option n'est pas recommandée. Elle exclut -c.</dd>
  <dt> -g <i>RESOURCE_GROUP</i> (facultatif) </dt>
  <dd> Nom du groupe de ressources cible</dd>
  <dt> -r REGION</dt>
  <dd> Nom de la région, comme 'us-south' ou 'eu-gb'</dt>
  <dt> --no-region</dt>
  <dd> Forcer la connexion sans cibler de région.</dd>
  <dt> -o <i>ORG</i> (facultatif)</dt>
  <dd> Nom de l'organisation cible (obsolète, utilisez 'ibmcloud target -o ORGANISATION')</dd>
  <dt> -s <i>SPACE</i> (facultatif) </dt>
  <dd> Nom de l'espace cible (obsolète, utilisez 'ibmcloud target -s ESPACE')</dd>
  <dt> --no-iam </dt>
  <dd> Imposer une authentification avec un serveur de connexion plutôt qu'avec un système IAM public</dd>
  <dt> --skip-ssl-validation (facultatif) </dt>
  <dd> Ignorer la validation SSL des demandes HTTP. Cette option n'est pas recommandée.</dd>
</dl>

<strong>Exemples</strong> :

### Connexion en mode interactif

```
ibmcloud login
```
{: codeblock}

Connectez-vous avec un nom d'utilisateur et un mot de passe, puis définissez un compte, une organisation et un espace cible :
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Connectez-vous avec un code d'accès unique et définissez un compte, une organisation et un espace cible
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### Utilisation des services Cloud Foundry

Pour utiliser les services Cloud Foundry, vous devez cibler un espace et une organisation Cloud Foundry. Vous pouvez exécuter la commande suivante pour choisir de manière interactive l'organisation et l'espace :
```
ibmcloud target --cf
```
{: codeblock}

Vous pouvez, si vous le souhaitez, utiliser la sortie de la commande précédente pour définir manuellement votre organisation et votre espace à l'aide de la commande suivante :
```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

### Un compte est associé à une clé d'API

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### Aucun compte n'est associé à une clé d'API

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Remarque :</strong> si un compte est associé à la clé d'API, le passage à un autre compte n'est pas autorisé.

### Utilisez un code d'accès unique
```
ibmcloud login -u UserID --sso
```
{: codeblock}

L'interface de ligne de commande fournit ensuite un lien d'URL et demande un code d'accès :
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Ouvrez le lien dans un navigateur pour obtenir un code secret. Entrez le code d'accès qui vous a été fourni dans la console, vous pouvez alors vous connecter.

## ibmcloud logout
{: #ibmcloud_logout}

Déconnectez l'utilisateur.
```
ibmcloud logout
```
{: codeblock}

<strong>Prérequis</strong> : Aucun

## ibmcloud regions
{: #ibmcloud_regions}

Afficher les informations pour toutes les régions dans {{site.data.keyword.Bluemix_notm}}.
```
ibmcloud regions
```
{: codeblock}

<strong>Prérequis</strong> : Noeud final

## ibmcloud target
{: #ibmcloud_target}


Définir ou afficher le compte, la région, l'organisation ou l'espace cible :
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

<strong>Prérequis</strong> : Noeud final, Connexion

<strong>Options de commande</strong> :
<dl>
   <dt>-c <i>ACCOUNT_ID</i> (facultatif)</dt>
   <dd>ID du compte à cibler.</dd>
   <dt>-r <i>REGION_NAME</i> (facultatif)</dt>
   <dd>Nom de la région vers laquelle commuter, par exemple 'us-south' ou 'eu-gb'.</dd>
   <dt>-g <i>RESOURCE_GROUP</i> (facultatif)</dt>
   <dd>Nom du groupe de ressources</dd>
   <dt>--cf</dt>
   <dd>Sélectionner l'organisation et l'espace cible de manière interactive</dd>
   <dt>--cf-api</dt>
   <dd>Noeud final d'API Cloud Foundry</dd>
   <dt>-o <i>ORG_NAME</i> (facultatif)</dt>
   <dd>Nom de l'organisation à cibler.</dd>
   <dt>-s <i>SPACE_NAME</i> (facultatif)</dt>
   <dd>Nom de l'espace à cibler.</dd>
   <dt>--unset-region</dt>
   <dd>Annuler la définition de la région ciblée</dd>
   <dt>--unset-resource-group</dt>
   <dd>Annuler la définition du groupe de ressources ciblé</dd>
   <dt>--output <i>FORMAT</i></dt>
   <dd>Indiquez un format de sortie. Seul JSON est pris en charge pour l'instant.</dd>
</dl>
Si aucune de ces options n'est spécifiée, le compte, la région, l'organisation et l'espace en cours s'affichent.

<strong>Exemples</strong> :

Définir le compte, l'organisation et l'espace en cours :
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

Basculer vers une nouvelle région :
```
ibmcloud target -r eu-gb
```
{: codeblock}

Afficher le compte, la région, l'organisation et l'espace en cours :
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

Mettre à jour l'interface de ligne de commande vers la version la plus récente.
```
ibmcloud update [-f]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
  <dt>-f</dt>
  <dd>Forcer la mise à jour sans confirmation. Privilège de superutilisateur (root) requis.</dd>
</dl>


## Commandes générales du service d'infrastructure classique
{: #softlayer_cli}

Les commandes de l'infrastructure classique dans l'interface de ligne de commande (CLI) {{site.data.keyword.cloud_notm}} permettent de configurer et de gérer les services de l'infrastructure.

Exécutez la commande `ibmcloud sl` pour consulter la liste des commandes disponibles :
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Gen1 infrastructure Block Storage
   cdn             Gen1 infrastructure Content Delivery Network
   file            Gen1 infrastructure File Storage
   dns             Gen1 infrastructure Domain Name System
   globalip        Gen1 infrastructure Global IP addresses
   hardware        Gen1 infrastructure hardware servers
   image           Gen1 infrastructure Compute images
   ipsec           Gen1 infrastructure IPSEC VPN
   loadbal         Gen1 infrastructure Load balancers
   security        Gen1 infrastructure SSH Keys and SSL Certificates
   securitygroup   Gen1 infrastructure network security groups
   subnet          Gen1 infrastructure Network subnets
   ticket          Gen1 infrastructure Manage Tickets
   vlan            Gen1 infrastructure Network VLANs
   vs              Gen1 infrastructure Virtual Servers
   order           Gen1 infrastructure Orders
   user            Gen1 infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

Pour afficher les informations sur une commande, exécutez :
```
ibmcloud sl [command] -h
```

La commande `ibmcloud sl init` n'est plus disponible depuis la version `0.14` de l'interface de ligne de commande. Pour installer la dernière version, voir [Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Permet d'afficher des informations d'aide pour toutes les commandes exécutées dans un environnement d'infrastructure classique.
```
ibmcloud sl help
```
{: codeblock}

