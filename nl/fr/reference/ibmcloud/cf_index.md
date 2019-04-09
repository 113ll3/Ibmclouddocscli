---

copyright:
  years: 2016, 2019
lastupdated: "2019-02-26"

keywords: cf commands, cloud foundry commands, cloud foundry cli, cf apps, cf help, cf logs, cf api

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:note: .note}

# Utilisation de Cloud Foundry (commandes cf)
{: #cf}

L'interface de ligne de commande Cloud Foundry (cf) fournit un ensemble de commandes permettant de gérer vos applications. Les informations ci-après répertorient les commandes cf le plus souvent utilisées pour gérer les applications avec leurs noms, leurs options, leur syntaxe, les éléments prérequis, leur description et des exemples. Pour afficher toutes les commandes cf et les informations d'aide associées, entrez `cf help`. Entrez `cf nom_commande -h` afin d'afficher des informations d'aide détaillées pour une commande particulière.
{: shortdesc}

Pour apprendre à utiliser l'interface de ligne de commande Cloud Foundry, voir [Getting Started](https://github.com/cloudfoundry/cli#getting-started){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

Pour obtenir une liste plus détaillée des commandes `cf CLI`, voir le document [Cloud Foundry CLI Reference Guide](https://docs.cloudfoundry.org/cf-cli/cf-help.html){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").

Sur votre réseau, si un serveur proxy HTTP se trouve entre l'hôte qui exécute les commandes cf et le noeud final d'API Cloud Foundry, vous devez spécifier le nom d'hôte ou l'adresse IP du serveur proxy en définissant la variable d'environnement `HTTP_PROXY`. Pour plus de détails, voir [Using the cf CLI with a Proxy Server](http://docs.cloudfoundry.org/devguide/installcf/http-proxy.html){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe").
{: note}

## Index des commandes de l'interface de ligne de commande Cloud Foundry
{: #CLIname_commands_index}

Utilisez l'index du tableau suivant pour consulter les commandes Cloud Foundry fréquemment utilisées :

<table summary="Commandes Cloud Foundry générales classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Commandes générales Cloud Foundry</caption>
 <thead>
 <th colspan="6">Commandes Cloud Foundry générales</th>
 </thead>
 <tbody>
 <tr>
 <td>[api](#cf_api)</td>
 <td>[help](#cf_help)</td>
 <td>[login](#cf_login)</td>
 <td>[stacks](#cf_stacks)</td>
 <td>[target](#cf_target)</td>
 <td>[-v ](#cf_v)</td>
 </tr>
   </tbody>
 </table>

<table summary="Commandes classées par ordre alphabétique pour la gestion des applications, des espaces et des services, avec un lien vers des informations supplémentaires.">
<caption>Tableau 2. Commandes pour la gestion des applications, des espaces et des services</caption>
 <thead>
 <th colspan="5">Commandes pour la gestion des applications, des espaces et des services</th>
 </thead>
 <tbody>
 <tr>
 <td>[apps](#cf_apps)</td>
 <td>[bind-service](#cf_bind-service)</td>
 <td>[create-service](#cf_create-service)</td>
 <td>[create-space](#cf_create-space)</td>
 <td>[delete](#cf_delete)</td>
  </tr>
 <tr>
 <td>[delete-space](/#cf_delete-space)</td>
 <td>[events](#cf_events)</td>
 <td>[logs](#cf_logs)</td>
 <td>[marketplace](#cf_marketplace)</td>
 <td>[push](#cf_push)</td>
  </tr>
 <tr>
 <td>[scale](#cf_scale)</td>
 <td>[services](#cf_services)
 <td>[set-env](#cf_set-env)</td>
 <td>[ssh](#cf_ssh)</td>
 <td>[stop](#cf_stop)</td>
 </tr>
 </tbody>
 </table>

## cf api
{: #cf_api}

Utiliser cette commande pour afficher ou spécifier l'adresse URL du noeud final d'API de {{site.data.keyword.cloud}}.
```
cf api [BluemixServerURL] [--skip-ssl-validation] [--unset]
```

<strong>Prérequis</strong> : aucun.

<strong>Options de commande</strong> :

   <dl>
   <dt>URL_serveur_Bluemix (facultatif)</dt>
   <dd>Adresse URL du noeud final de l'API {{site.data.keyword.cloud_notm}} que vous devez spécifier lorsque vous vous connectez à {{site.data.keyword.cloud_notm}}. En général, il s'agit de `https://api.{NomDomaine}`.
   Si vous voulez afficher l'adresse URL du noeud final de l'API que vous utilisez actuellement, il n'est pas nécessaire de spécifier ce paramètre pour la commande cf api.</dd>
   <dt>* --skip-ssl-validation</dt>
   <dd>Désactive le processus de validation SSL. L'utilisation de ce paramètre peut entraîner des problèmes de sécurité.</dd>
   <dt>* --unset</dt>
   <dd>Supprime les informations de connexion pour tous les noeuds finaux d'API.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher le noeud final d'API en cours.
```
cf api
```
{: codeblock}

Retirer la connexion à tous les noeuds finaux d'API pour api.us-south.cf.cloud.ibm.com :
```
cf api api.us-south.cf.cloud.ibm.com --unset
```
{: codeblock}

Désactiver le processus de validation SSL pour api.us-south.cf.cloud.ibm.com :
```
cf api api.us-south.cf.cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

## cf apps
{: #cf_apps}

Répertorie toutes les applications que vous avez déployées dans l'espace en cours. Le statut de
chaque application est également affiché.

Supposez que vous disposez d'une instance pour une application. La colonne des instances de la réponse générée par la commande cf apps comporte la
valeur 1/1 si votre application est en cours d'exécution et 0/1 si elle est arrêtée. Si la valeur ?/1 est affichée, valeur indiquant que l'état de l'instance d'application est inconnu, vous pouvez copier l'adresse URL de l'application dans votre navigateur afin de vérifier si votre application répond, ou n'afficher que les dernières lignes du journal avec la commande `cf logs nom_app` pour déterminer si l'application génère un contenu de journal.

```
cf apps
```
{: codeblock}

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

## cf bind-service
{: #cf_bind-service}

Lie une instance de service existante à votre application

```
cf bind-service appname service_instance
```
{: codeblock}

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

   <dl>
   <dt>appname (requis)</dt>
   <dd>Nom de l'application.</dd>
   <dt>service_instance (requis)</dt>
   <dd>Nom de l'instance de service existante.</dd>
    </dl>

<strong>Exemples</strong> :

Liez une instance de service appelée `my_dataworks` à votre application appelée `my_app`.
```
cf bind-service my_app my_dataworks
```
{: codeblock}


## cf create-service
{: #cf_create-service}

Crée une instance de service.

```
cf create-service service_name service_plan service_instance
```
{: codeblock}

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

   <dl>
   <dt>service_name (requis)</dt>
   <dd>Nom du service.</dd>
   <dt>service_plan (requis)</dt>
   <dd>Nom du plan de service.</dd>
   <dt>service_instance (requis)</dt>
   <dd>Nom à utiliser pour la nouvelle instance de service que vous créez.</dd>
    </dl>

<strong>Exemples</strong> :

Créer une instance du service {{site.data.keyword.dataworks_short}} avec un plan `free`.
```
cf create-service DataWorks free my_dataworks
```
{: codeblock}


## cf create-space
{: #cf_create-space}

Crée un espace.

```
cf create-space space_name [-o] [-q]
```

<strong>Prérequis</strong> : `cf api`, `cf login`

<strong>Options de commande</strong> :

   <dl>
   <dt>space_name (requis)</dt>
   <dd>Nom de l'espace.</dd>
   <dt>*-o* (facultatif)</dt>
   <dd>Nom de l'organisation dans laquelle créer un espace.</dd>
   <dt>*-q* (facultatif)</dt>
   <dd>Quota à affecter au nouvel espace. S'il n'est pas spécifié, un quota par défaut est affecté automatiquement.</dd>
    </dl>

<strong>Exemples</strong> :

Créez un espace appelé new_space.
```
cf create-space new_space
```
{: codeblock}


## cf delete
{: #cf_delete}

Supprime une application existante.

```
cf delete appname [-f] [-r]
```

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

   <dl>
   <dt>appname (requis)</dt>
   <dd>Nom de l'application.</dd>
   <dt>*-f* (facultatif)</dt>
   <dd>Force la suppression de l'application sans confirmation.</dd>
   <dt>*-r* (facultatif)</dt>
   <dd>Supprime tous les noms de domaine associés à l'application. </dd>
    </dl>

<strong>Exemples</strong> :

Supprime une application nommée `my_app` (confirmation requise).
```
cf delete my_app
```
{: codeblock}

Supprime une application appelée `my_app` sans confirmation.
```
cf delete my_app -f
```
{: codeblock}

Supprime une application appelée `my_app` et tous les noms de domaine associés à `my_app`.
```
cf delete my_app -r
```
{: codeblock}

Supprime une application appelée `my_app` et tous les noms de domaine associés à `my_app` sans confirmation.
```
cf delete my_app -f -r
```
{: codeblock}


## cf delete-space
{: #cf_delete-space}

Supprime un espace.
```
cf delete-space space_name [-f]
```

<strong>Prérequis</strong> : `cf api`, `cf login`

<strong>Options de commande</strong> :

   <dl>
   <dt>space_name (requis)</dt>
   <dd>Nom de l'espace.</dd>
   <dt>*-f* (facultatif)</dt>
   <dd>Force la suppression de l'espace sans confirmation.</dd>
   *Remarque :* la suppression d'un espace est une opération irréversible.
   </dl>

<strong>Exemples</strong> :

Supprime une application nommée `my_app` (confirmation requise).
```
cf delete my_app
```
{: codeblock}

Supprime une application appelée `my_app` sans confirmation.
```
cf delete my_app -f
```
{: codeblock}

Supprime une application appelée `my_app` et tous les noms de domaine associés à `my_app`.
```
cf delete my_app -r
```
{: codeblock}

Supprime une application appelée `my_app` et tous les noms de domaine associés à `my_app` sans confirmation.
```
cf delete my_app -f -r
```
{: codeblock}


## cf events
{: #cf_events}

Affiche les événements d'exécution liés à une application.

```
cf events [appname]
```
{: codeblock}

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

   <dl>
   <dt>appname</dt>
   <dd>Nom de l'application.</dd>
   </dl>

<strong>Exemples</strong> :

Affiche les événements pour une application appelée `my_app`.
```
cf events my_app
```
{: codeblock}


## cf help
{: #cf_help}

Affiche les informations d'aide pour toutes les commandes cf ou pour une commande cf spécifique.

```
cf help [command_name]
```
{: codeblock}

<strong>Prérequis</strong> : aucun.

<strong>Options de commande</strong> :

   <dl>
   <dt>command_name (facultatif)</dt>
   <dd>Nom d'une commande.</dd>
    </dl>

<strong>Exemples</strong> :

Afficher les informations d'aide pour toutes les commandes cf.
```
cf help
```
{: codeblock}

Afficher les informations d'aide pour la commande events.
```
cf help events
```
{: codeblock}


## cf login
{: #cf_login}

Vous connecte à {{site.data.keyword.cloud_notm}}. Si vous êtes connecté à l'aide d'un ID fédéré, vous devez utiliser le paramètre de connexion unique (SSO) pour vous connecter.

Vous pouvez également utiliser une clé d'API de plateforme {{site.data.keyword.cloud_notm}} pour vous connecter. Servez-vous du nom d'utilisateur `apikey` et de la valeur de votre clé d'API comme mot de passe. Pour plus d'informations sur la création d'une clé d'API, voir [Description des clés d'API](/docs/iam?topic=iam-manapikey#manapikey).
{: note}

```
cf login [-a url] [-u user_name] [-p password] [-sso] [-o organization_name] [-s space_name] [--skip-ssl-validation]
```

<strong>Prérequis</strong> : aucun.

<strong>Options de commande</strong> :

<dl>
<dt>*-a* https://api.{NomDomaine} (facultatif)</dt>
<dd>Adresse URL du noeud final d'API de {{site.data.keyword.cloud_notm}}.</dd>
<dt>*-u* user_name (facultatif)</dt>
<dd>Votre nom d'utilisateur.</dd>
<dt>*-p* password (facultatif)</dt>
<dd>Votre mot de passe.</dd>
<dd>*Important :* si vous indiquez un mot de passe avec le paramètre *-p* dans l'interface de ligne de commande, le mot
de passe peut être enregistré dans l'historique de la ligne de commande. Pour des raisons de sécurité, évitez de fournir le mot de passe
avec le paramètre -p. A la place,
entrez le mot de passe lorsque l'interface de ligne de commande vous y invite.</dd>
<dt>*-sso*</dt>
<dd>Vous devez utiliser l'option de connexion unique (SSO) pour vous connecter à l'aide d'un ID fédéré. Cela n'est pas obligatoire lorsque vous vous connectez avec un IBMid. Si vous essayez de vous connecter avec un ID fédéré sans spécifier le paramètre de connexion unique, vous êtes invité à l'inclure. Lorsque vous utilisez le paramètre de connexion unique, vous êtes invité à entrer un code d'accès unique lors de la connexion.</dd>
<dt>*-o* organization_name</dt>
<dd>Nom de l'organisation à laquelle vous voulez vous connecter.</dd>
<dt>*-s* space_name</dt>
<dd>Nom de l'espace auquel vous voulez vous connecter.</dd>
<dt>*--skip-ssl-validation* (facultatif)</dt>
<dd>Désactive le processus de validation SSL. L'utilisation de ce paramètre peut entraîner des problèmes de sécurité.</dd>
</dl>

*Remarque :* si vous indiquez votre mot de passe dans le paramètre *-p* de cette commande, votre mot de passe peut être
enregistré dans le fichier
historique de la commande shell et peut être visible pour les autres utilisateurs du système d'exploitation local.

<strong>Exemples</strong> :

Se connecter à {{site.data.keyword.cloud_notm}}.
```
cf login
```
{: codeblock}

Se connecter à {{site.data.keyword.cloud_notm}} avec un noeud final défini `https://api.us-south.cf.cloud.ibm.com`.
```
cf login -a https://api.us-south.cf.cloud.ibm.com
```
{: codeblock}

Se connecter à {{site.data.keyword.cloud_notm}} avec le noeud final défini `https://api.us-south.cf.cloud.ibm.com`, le nom d'utilisateur `nom_utilisateur`, sans spécifier de mot de passe pour des raisons de sécurité.
```
cf login -a https://api.us-south.cf.cloud.ibm.com -u user_name
```
{: codeblock}

Se connecter à {{site.data.keyword.cloud_notm}} avec le noeud final défini `https://api.us-south.cf.cloud.ibm.com`, le nom d'utilisateur `user_name`, sans spécifier de mot de passe pour des raisons de sécurité, le nom d'organisation `org_name` et le nom d'espace `space_name`.
```
cf login -a https://api.us-south.cf.cloud.ibm.com -u user_name -o org_name -s space_name
```
{: codeblock}

Se connecter à {{site.data.keyword.cloud_notm}} avec un noeud final défini `https://api.us-south.cf.cloud.ibm.com` à l'aide d'une clé d'API. Utilisez `apikey` comme nom d'utilisateur et la clé d'API réelle comme mot de passe.
```
cf login -a https://api.us-south.cf.cloud.ibm.com -u apikey -p ThisValueIsYourAPIKey
```
{: codeblock}


## cf logs
{: #cf_logs}

Affiche les flux de journalisation de sortie standard et d'erreur standard d'une application.

```
cf logs appname [--recent]
```
<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

<dl>
<dt>appname</dt>
<dd>Nom de l'application.</dd>
<dt>*--recent* (facultatif)</dt>
<dd>Extrait les journaux récents.</dd>
</dl>

<strong>Exemples</strong> :

Affichez les flux de journalisation pour une application appelée `my_app`.
```
cf logs my_app
```
{: codeblock}

Affichez les flux de journalisation récents pour une application appelée `my_app`.
```
cf logs my_app --recent
```
{: codeblock}


## cf marketplace
{: #cf_marketplace}

Répertorie tous les services disponibles sur la place de marché. Les services répertoriés par cette commande apparaissent également dans le catalogue
{{site.data.keyword.cloud_notm}}.

```
cf marketplace
```
<strong>Prérequis</strong> : `cf api`

<strong>Options de commande</strong> : aucune.

<strong>Exemples</strong> :

Afficher la liste de tous les services de la place de marché.
```
cf marketplace
```
{: codeblock}


## cf push
{: #cf_push}

Déploie une nouvelle application dans {{site.data.keyword.cloud_notm}} ou met à jour une application existante dans
{{site.data.keyword.cloud_notm}}.

```
cf push appname [-b buildpack_name] [-c start_command] [-f manifest_path] [-i instance_number] [-k disk_limit] [-m memory_limit] [-n host_name] [-p app_path] [-s stack_name] [-t timeout_length] [--no-hostname] [--no-manifest] [--no-route] [--no-start] [--random-route]
```

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

<dl>
<dt>appname (requis)</dt>
<dd>Nom de l'application.</dd>
<dt>*-b* buildpack_name (facultatif)</dt>
<dd>Nom du pack de construction. buildpack_name peut être le nom d'un
pack de construction personnalisé (par exemple, liberty-for-java), une
adresse URL Git (par exemple, https://github.com/cloudfoundry/java-buildpack.git), ou une adresse URL Git
avec une branche ou une balise (par exemple, https://github.com/cloudfoundry/java-buildpack.git#v3.3.0 pour la balise v3.3.0).</dd>
<dt>*-c* start_command (facultatif)</dt>
<dd>Commande de démarrage de votre application. Pour utiliser la commande de démarrage par défaut, spécifiez la valeur null pour cette option. </dd>
<dt>*-f* manifest_path (facultatif)</dt>
<dd>Chemin d'accès au fichier manifeste. Le fichier manifeste par défaut est manifest.yml sous le répertoire racine de votre application.</dd>
<dt>*-i* instance_number (facultatif)</dt>
<dd>Nombre d'instances.</dd>
<dt>*-k* disk_limit (facultatif)</dt>
<dd>Limite de disque pour l'application. Les valeurs admises sont *256M*, *1024M* et *1G*.</dd>
<dt>*-m* memory_limit (facultatif)</dt>
<dd>Limite de mémoire pour l'application. Les valeurs admises sont *256M*, *1024M* et *1G*.</dd>
<dt>*-n* host_name (facultatif)</dt>
<dd>Nom d'hôte de l'application, par exemple *mon_sous-domaine*.</dd>
<dt>*-p* app_path (facultatif)</dt>
<dd>Chemin d'accès au répertoire de l'application ou au fichier archive de l'application.</dd>
<dt>*-s* stack_name (facultatif)</dt>
<dd>Pile pour l'exécution des applications. Une pile est un système de fichiers préconfiguré incluant le système d'exploitation. Utilisez `cf
stacks` pour afficher les piles disponibles dans {{site.data.keyword.Bluemix_notm}}.</dd>
<dt>*-t* timeout (facultatif)</dt>
<dd>Délai maximal de démarrage de l'application, en secondes. Il se peut que d'autres délais d'attente côté serveur remplacent cette valeur.</dd>
<dt>*--no-hostname* (facultatif)</dt>
<dd>Mappe le domaine de système {{site.data.keyword.cloud_notm}} à cette application.</dd>
<dt>*--no-manifest* (facultatif)</dt>
<dd>Ignore le fichier manifeste par défaut.</dd>
<dt>*--no-route* (facultatif)</dt>
<dd>Ne mappe pas de route à cette application.</dd>
<dt>*--no-start* (facultatif)</dt>
<dd>Ne démarre pas l'application après le déploiement de l'application.</dd>
<dt>*--random-route* (facultatif)</dt>
<dd>Crée une route aléatoire pour l'application.</dd>
</dl>

<strong>Exemples</strong> :

Démarrez une application appelée `my_app` avec la commande de démarrage par défaut.
```
cf push `my_app` -c null
```
{: codeblock}

Démarrez une application appelée `my_app` avec l'option permettant d'exécuter un fichier script appelé `run.sh`.
```
cf push `my_app` -c "bash ./<run.sh>"
```
{: codeblock}



## cf scale
{: #cf_scale}

Affiche ou change le nombre d'instances, la limite d'espace disque et la limite de mémoire pour une application.

```
cf scale appname [-i instance_number] [-k disk_limit] [-m memory_limit] [-f]
```

<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

<dl>
<dt>appname (requis)</dt>
<dd>Nom de l'application.</dd>
<dt>*-i* instance_number (facultatif)</dt>
<dd>Nombre d'instances.</dd>
<dt>*-k* disk_limit (facultatif)</dt>
<dd>Limite de disque pour l'application ; les valeurs admises sont `256M`, `1024M` et `1G`.</dd>
<dt>*-m* memory_limit (facultatif)</dt>
<dd>Limite de mémoire pour l'application ; les valeurs admises sont `256M`, `1024M` et `1G`.</dd>
<dt>*-f* (facultatif)</dt>
<dd>Force l'application à redémarrer sans invite.</dd>
</dl>

<strong>Exemples</strong> :

Affichez le nombre d'instances, la limite d'espace disque et la limite de mémoire pour une application appelée `my_app`.
```
cf scale my_app
```
{: codeblock}

Modifier le nombre d'instances en spécifiant `1234`, la limite d'espace disque en spécifiant `1G` et la limite de mémoire en spécifiant `1G` pour une application appelée `my_app`.
```
cf scale appname -i 1234 -k 1G -m 1G
```
{: codeblock}


## cf services
{: #cf_services}

Répertorie tous les services disponibles dans l'espace en cours.

```
cf services
```
<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> : aucune.

<strong>Exemples</strong> :

Afficher la liste de tous les services dans l'espace en cours.
```
cf services
```
{: codeblock}


## cf set-env
{: #cf_set-env}

Définit une variable d'environnement pour une application.

```
cf set-env appname var_name var_value
```
<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

<dl>
<dt>appname (requis)</dt>
<dd>Nom de l'application.</dd>
<dt>var_name (requis)</dt>
<dd>Nom de la variable d'environnement.</dd>
<dt>var_value (requis)</dt>
<dd>Valeur de la variable d'environnement.</dd>
</dl>

<strong>Exemples</strong> :

Définissez une variable d'environnement appelée `variable_a` avec la valeur `123` pour l'application appelée `my_app`.
```
cf set-env my_app variable_a 123
```
{: codeblock}


## cf ssh
{: #cf_ssh}

Accédez au conteneur d'applications de manière sécurisée. La commande `cf ssh` permet de configurer une session SSH interactive, d'exécuter des commandes à distance, de transférer des fichiers et de configurer l'acheminement de port avec une instance de conteneur d'applications spécifique.

```
cf ssh
```
<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

Par défaut, l'accès SSH est activé pour les applications Diego. Vous pouvez utiliser la commande `cf ssh-enabled` pour vérifier si l'accès SSH est activé ou la commande `cf enable-ssh` pour activer l'accès s'il a été désactivé.

<strong>Options de commande</strong> :

<dl>
<dt>appname</dt>
<dd>Nom de l'application.</dd>
<dt>-c</dt>
<dd>Indique une commande distante à exécuter.</dd>
<dt>-i</dt>
<dd>Cible une instance spécifique d'une application. Si cette option n'est pas spécifiée, la première instance de l'application est utilisée (instance dotée de l'index 0).</dd>
<dt>-L</dt>
<dd>Active l'acheminement de port local, ce qui lie un port de sortie de votre machine à un port d'entrée sur la machine virtuelle de l'application.</dd>
<dt>-N</dt>
<dd>N'exécute pas de commande distante.</dd>
<dt>-t, -tt ou -T</dt>
<dd>Vous permet d'exécuter une session SSH en mode pseudo-tty plutôt que de générer une sortie sous forme de ligne de terminal.<dd>
</dl>

<strong>Exemples</strong> :

Démarrer une session SSH interactive avec l'instance de conteneur exécutant l'application `my_app`.
```
$ cf ssh my_app
```
{: codeblock}

Exécuter une seule commande sur l'instance de conteneur d'applications `my_app`.
```
$ cf ssh my_app -c "ls -l"
```

Transférer un seul fichier à partir de l'instance de conteneur d'applications `my_app`.
```
$ cf ssh my_app -c "/bin/cat logs/messages.log" > messages.log
```

Configurez l'acheminement du port 7777 de la machine locale vers le port 8888 de l'instance de conteneur d'applications `my_app`.
```
$ cf ssh -N -T -L 7777:localhost:8888 my_app

```

## cf stacks
{: #cf_stacks}

Répertorie toutes les piles. Une pile est un système de fichiers préconfiguré incluant un système d'exploitation pouvant exécuter des applications.

```
cf stacks
```
<strong>Prérequis</strong> : `cf api`, `cf login`

<strong>Options de commande</strong> : aucune.

<strong>Exemples</strong> :

Afficher la liste de toutes les piles.
```
cf stacks
```
{: codeblock}


## cf stop
{: #cf_stop}

Arrête une application.

```
cf stop appname
```
<strong>Prérequis</strong> : `cf api`, `cf login`, `cf target`

<strong>Options de commande</strong> :

<dl>
<dt>appname (requis)</dt>
<dd>Nom de l'application.</dd>
</dl>

<strong>Exemples</strong> :

Arrêtez l'application appelée `my_app`.
```
cf stop my_app
```
{: codeblock}


## cf target
{: #cf_target}

Définit ou affiche l'organisation ou l'espace ciblé.

```
cf target [-o org_name] [-s space_name]
```
<strong>Prérequis</strong> : `cf api`, `cf login`

<strong>Options de commande</strong> :

<dl>
<dt>-o *org_name* (facultatif)</dt>
<dd>Nom de l'organisation dans laquelle se trouve l'espace.</dd>
<dt>-s *space_name* (facultatif)</dt>
<dd>Nom de l'espace.</dd>
</dl>

<strong>Exemples</strong> :

Définissez comme cible l'organisation appelée "my_org" et l'espace appelé "my_space".
```
cf target -o my_org -s my_space
```
{: codeblock}


## cf -v
{: #cf_v}

Affiche la version de l'interface de ligne de commande Cloud Foundry.

```
cf -v
```
<strong>Prérequis</strong> : aucun.

<strong>Options de commande</strong> : aucune.

<strong>Exemples</strong> :

Afficher la version de l'interface de ligne de commande Cloud Foundry.
```
cf -v
```
{: codeblock}


## Liens connexes
{: #cf-related}

* [Téléchargement de l'interface de ligne de commande Cloud Foundry](https://github.com/cloudfoundry/cli/releases){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
* [Quick Reference Card - cf commands](ftp://public.dhe.ibm.com/cloud/bluemix/cf_cli_refcard.html){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe")
