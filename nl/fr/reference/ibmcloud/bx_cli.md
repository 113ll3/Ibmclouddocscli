---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

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
{: shortdesc}

Le client de ligne de commande {{site.data.keyword.cloud_notm}} inclut un client de ligne de commande Cloud Foundry dans son installation. Si votre propre interface de ligne de commande Cloud est installée, n'utilisez pas à la fois les commandes CLI d'{{site.data.keyword.cloud_notm}} et les commandes CLI de Cloud Foundry de votre propre installation dans le même contexte. Utilisez à la place **`ibmcloud cf [commande]`** si vous désirez utiliser l'interface de ligne de commande Cloud Foundry pour gérer les ressources Cloud Foundry dans le contexte CLI d'{{site.data.keyword.cloud_notm}}. Notez que la commande **`ibmcloud cf api/login/logout/target`** n'est pas admise et que vous devez utiliser **`ibmcloud api/login/logout/target`** à la place.

A compter de mai 2018, les commandes de l'interface CLI d'{{site.data.keyword.cloud_notm}} ont été changées de **`bluemix`** et **`bx`** en **`ibmcloud`**. Vous pouvez toutefois continuer à utiliser les commandes de l'interface CLI **`bluemix`** et **`bx`** jusqu'à ce qu'elles soient retirées.
{: tip}

Les listes ci-dessous répertorient les commandes prises en charge par l'interface de ligne de commande {{site.data.keyword.cloud_notm}}, en indiquant leurs noms, leurs arguments, leurs options, leurs prérequis, leurs descriptions, et des exemples.

La zone Prérequis répertorie les actions requises avant l'utilisation de la commande et peut inclure une ou plusieurs des actions suivantes :

<dl>
<dt>Docker</dt>
<dd>Installez l'interface CLI Docker.</dd>
<dt>Noeud final</dt>
<dd>Utilisez la commande **`ibmcloud api`** pour définir un noeud final d'API. </dd>
<dt>Se connecter</dt>
<dd>Utilisez la commande **`ibmcloud login`** pour vous connecter. Si vous vous connectez avec un ID fédéré, utilisez l'option **`--sso`** pour vous authentifier avec un code d'accès unique ou utilisez l'option **`--apikey`** pour vous authentifier avec une clé d'API.</dd>
<dt>Cible</dt>
<dd>Utilisez la commande **`ibmcloud target`** pour configurer une organisation et un espace. </dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Affiche l'aide générale pour les commandes intégrées de premier niveau et les espaces de nom pris en charge de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}, ou l'aide d'une commande intégrée ou d'un espace de nom spécifique.

```
ibmcloud help [COMMAND|NAMESPACE]
```

### Prérequis
{: #help-prereqs}

Néant.

### Options de commande
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>Commande ou espace de nom pour lequel afficher l'aide. Si la commande ou l'espace de nom n'est pas spécifié, l'aide générale de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est affichée. Facultatif.</dd>
</dl>

### Exemples
{: #help-examples}

Afficher l'aide générale pour l'interface de ligne de commande {{site.data.keyword.cloud_notm}} :
```
ibmcloud help
```
{: codeblock}

Afficher l'aide pour la commande **`dev`** :
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

### Prérequis
{: #api-prereqs}

Néant.

### Options de commande
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>Noeud final d'API ciblé. Par exemple, `https://cloud.ibm.com`. Si aucune des options **`API_ENDPOINT`** et **`--unset`** n'est spécifiée, le noeud final d'API en cours est affiché. Facultatif.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Ignorer la validation SSL des demandes HTTP. Facultatif.</dd>
<dt>--unset</dt>
<dd>Supprimer le paramètre de noeud final d'API.</dd>
</dl>

### Exemples
{: #api-examples}

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

Retirer le noeud final d'API :
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Ecrit les valeurs par défaut dans le fichier de configuration.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### Prérequis
{: #config-prereqs}

Néant.

### Options de commande
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>Active ou désactive la vérification de la version de l'interface de ligne de commande. Les valeurs valides sont `true` ou `false`.</dd>
<dt>--color</dt>
<dd>Active ou désactive la sortie en couleurs. Cette option est désactivée par défaut. Les valeurs valides sont `true` ou `false`.</dd>
<dt>--http-timeout</dt>
<dd>Délai d'attente, en secondes, pour les demandes HTTP. La valeur par défaut est 60 secondes.</dd>
<dt>--locale</dt>
<dd>Définit un environnement local par défaut. Si aucune valeur n'est spécifiée, l'environnement local précédent est supprimé. </dd>
<dt>--trace </dt>
<dd>Consigne la trace des demandes HTTP sur le terminal ou dans le fichier spécifié. Les valeurs valides sont `true` ou `false`.</dd>
</dl>

Vous ne pouvez spécifier qu'une seule des options à la fois.
{: tip}

### Exemples
{: #config-examples}

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

Consigne la trace des demandes HTTP dans le fichier `/home/usera/my_trace` :
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

La commande **`ibmcloud info`** n'est plus disponible depuis la version 0.14 de l'interface de ligne de commande. Pour installer la dernière version, voir [Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).

## ibmcloud cf
{: #ibmcloud_cf}

Appelez l'interface de ligne de commande Cloud Foundry imbriquée. 
```
ibmcloud [-q, --quiet] cf COMMAND...
```

### Prérequis
{: #info-prereqs}

Néant.

### Options de commande
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>Ne pas afficher le message d'appel. </dd>
</dl>

### Exemples
{: #info-examples}

Répertorier les applications Cloud Foundry :
```
ibmcloud cf apps
```
{: codeblock}

Répertorier les services Cloud Foundry sans afficher le message `Invoking cf command...` :
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

Installer une interface CLI Cloud Foundry pour IBM Cloud CLI
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### Prérequis
{: #cfinstall-prereqs}

Néant.

### Options de commande
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>Indiquer la version de l'interface CLI Cloud Foundry à installer</dd>
  <dt>--restore</dt>
  <dd>Restaurer la version pré-intégrée de l'interface CLI Cloud Foundry</dd>
  <dt>-f, --force</dt>
  <dd>Forcer l'installation sans confirmation</dd>
</dl>

### Exemples
{: #cfinstall-examples}

Installer l'interface CLI Cloud Foundry `6.44.1` :

```
ibmcloud cf install -v 6.44.1
```

Installer la dernière version de l'interface CLI Cloud Foundry sans confirmation :

```
ibmcloud cf install -f
```

Récupérer l'interface CLI Cloud Foundry intégrée par défaut :

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

Se connecter à l'interface de ligne de commande d'{{site.data.keyword.cloud_notm}}.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```
### Prérequis
{: #login-prereqs}

Néant.

### Options de commande
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>Noeud final de l'API, par exemple, `cloud.ibm.com`. </dd>
<dt>--apikey API_KEY or @API_KEY_FILE_PATH</dt>
<dd>Contenu de clé d'API ou chemin d'un fichier de clés d'API indiqué par le symbole @.</dd>
<dt>-u USER_NAME</dt>
<dd>Nom de l'utilisateur. Facultatif.</dd>
<dt>-p PASS_WORD</dt>
<dd>Mot de passe de l'utilisateur. Facultatif.</dd>
<dt>-c ACCOUNT_ID</dt>
<dd>ID du compte cible. Cette option exclut l'option **`--no account`**. </dd>
<dt>--no-account</dt>
<dd>Connexion forcée sans le compte. Cette option n'est pas recommandée et elle exclut l'option **`-c`**. </dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>Nom du groupe de ressources cible. Facultatif.</dd>
<dt>-r REGION</dt>
<dd>Nom de la région cible, par exemple, us-south ou eu-gb.</dd>
<dt>--no-region</dt>
<dd>Connexion forcée sans cibler une région. </dd>
<dt>-o ORG</dt>
<dd>Nom de l'organisation cible. Cette option est obsolète. Utilisez **`ibmcloud target -o org_name`** à la place. Facultatif.</dd>
<dt>-s SPACE</dt>
<dd>Nom de l'espace cible. Cette option est obsolète. Utilisez **`ibmcloud target -s space_name`** à la place. Facultatif.</dd>
<dt>--no-iam</dt>
<dd>Imposer une authentification avec un serveur de connexion plutôt qu'avec un système IAM public. </dd>
<dt>--skip-ssl-validation</dt>
<dd>Ignorer la validation SSL des demandes HTTP. Cette option n'est pas recommandée.</dd>
</dl>

### Exemples
{: #login-examples}

Se connecter de manière interactive. 

```
ibmcloud login
```
{: codeblock}

Se connecter avec un nom d'utilisateur et un mot de passe, puis définissez un compte, une organisation et un espace cible :
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Se connecter avec un code d'accès unique et définir un compte, une organisation et un espace cible :
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Configurez vos organisation et espace Cloud Foundry. Vous pouvez exécuter la commande suivante pour identifier de manière interactive l'organisation et l'espace :

```
ibmcloud target --cf
```
{: codeblock}

Si vous savez à quelle organisation et à quel espace le service appartient, vous pouvez utiliser la commande suivante :

```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

Utilisez une clé d'API avec un compte associé :

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

Utilisez une clé d'API sans compte associé :

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

Si un compte est associé à la clé d'API, le passage à un autre compte n'est pas autorisé. { :Remarque}

Utiliser un code d'accès unique :

```
ibmcloud login -u UserID --sso
```
{: codeblock}

L'interface de ligne de commande fournit ensuite un lien d'URL et vous demande de fournir un code d'accès :

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Ouvrez le lien dans un navigateur pour obtenir un code d'accès. Entrez le code d'accès donné dans la console pour vous connecter. 

## ibmcloud logout
{: #ibmcloud_logout}

Se déconnecter de l'interface de ligne de commande. 

```
ibmcloud logout
```
{: codeblock}

### Prérequis
{: #logout-prereqs}

Néant.

## ibmcloud regions
{: #ibmcloud_regions}

Afficher les informations pour toutes les régions dans {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```
{: codeblock}

### Prérequis
{: #regions-prereqs}

Utilisez la commande **`ibmcloud api`** pour définir un noeud final d'API. 

## ibmcloud target
{: #ibmcloud_target}

Définir ou afficher le compte, la région, l'organisation ou l'espace cible :

```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORG] [-s SPACE] [--output FORMAT]
```

### Prérequis
{: #target-prereqs}

* Utilisez la commande **`ibmcloud api`** pour définir un noeud final d'API. 
* Utilisez la commande **`ibmcloud login`** pour vous connecter. Si vous vous connectez avec un ID fédéré, utilisez l'option **`--sso`** pour vous authentifier avec un code d'accès unique ou utilisez l'option **`--apikey`** pour vous authentifier avec une clé d'API.


### Options de commande
{: #target-options}

<dl>
<dt>-c ACCOUNT_ID</dt>
<dd>ID du compte cible. Facultatif.</dd>
<dt>-r REGION</dt>
<dd>Nom de la région cible, par exemple, us-south ou eu-gb.Facultatif.</dd>
<dt>-g RESOURCE_GROUP</dt>
<dd>Nom du groupe de ressources cible. Facultatif.</dd>
<dt>--cf</dt>
<dd>Spécifier l'organisation ou l'espace cible de manière interactive. </dd>
<dt>--cf-api</dt>
<dd>Noeud final de l'API Cloud Foundry. </dd>
<dt>-o ORG</dt>
<dd>Nom de l'organisation cible. Facultatif.</dd>
<dt>-s SPACE</dt>
<dd>Nom de l'espace cible. Facultatif.</dd>
<dt>--unset-region</dt>
<dd>Effacer la région ciblée. </dd>
<dt>--unset-resource-group</dt>
<dd>Effacer le groupe de ressources ciblé. </dd>
<dt>--output FORMAT</dt>
<dd>Format de sortie spécifié. JSON est actuellement le seul format pris en charge. </dd>
</dl>

Si aucune de ces options n'est spécifiée, le compte, la région, l'organisation et l'espace en cours s'affichent.
{: note}

### Exemples
{: #target-examples}

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
### Prérequis
{: #update-prereqs}

### Options de commande
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>Forcer une mise à jour sans confirmation. Privilège de superutilisateur (root) requis.</dd>
</dl>

## Commandes générales du service d'infrastructure classique
{: #softlayer_cli}

Utilisez les commandes de l'infrastructure classique dans l'interface de ligne de commande (CLI) {{site.data.keyword.cloud_notm}} pour configurer et gérer les services de l'infrastructure.

Exécutez la commande **`ibmcloud sl`** pour consulter la liste des commandes disponibles :
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

Pour afficher les informations d'aide sur une commande, exécutez la commande suivante :
```
ibmcloud sl [command] -h
```

La commande **`ibmcloud sl init`** n'est plus disponible depuis la version `0.14` de l'interface de ligne de commande. Pour installer la dernière version, voir [Installation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Permet d'afficher des informations d'aide pour toutes les commandes exécutées dans un environnement d'infrastructure classique.
```
ibmcloud sl help
```
{: codeblock}

