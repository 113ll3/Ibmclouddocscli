---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-21"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Traitement des incidents liés à {{site.data.keyword.Bluemix_notm}} Developer Tools
{: #troubleshoot}

Les problèmes d'ordre général liés à l'utilisation de l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour créer des applications peuvent inclure des échecs de déploiement ou l'échec de l'extraction du code lors de la création d'une application. Dans de nombreux cas, ces problèmes peuvent être résolus en quelques opérations simples.
{:shortdesc}

## Erreur de nom d'hôte lors de la création d'une application avec un modèle non mobile
{: #hostname-error}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour déployer une application sur Cloud Foundry. Si vous entrez un nom d'hôte que vous jugez unique, il se peut que le message suivant s'affiche tout de même :

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

Cette erreur est provoquée par un jeton de connexion ayant expiré.
{: tsCauses}

Connectez-vous à nouveau.

```
bx login
```
{: codeblock}
{: tsResolve}

## Défaillances d'ordre général au niveau de l'interface de ligne de commande {{site.data.keyword.dev_cli_short}}
{: #general}

L'erreur suivante peut s'afficher si vous utilisez les commandes de l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} `create`, `delete`, `list` ou `code` :

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

Cette erreur est provoquée par un jeton de connexion ayant expiré.
{: tsCauses}

Connectez-vous à nouveau.

```
bx login
```
{: codeblock}
{: tsResolve}

## Erreur : aucune image de ce type lorsque vous exécutez une nouvelle application
{: #nosuchimage}

L'erreur suivante peut s'afficher lorsque vous exécutez une application alors que vous ne l'avez pas généré :

```
$ bx dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```
{: tsSymptoms}

Vous devez générer une application avant de l'exécuter.
{: tsCauses}

Exécutez la commande suivante dans votre répertoire d'application en cours pour générer votre application :

```
bx dev build
```
{: codeblock}

Exécutez la commande suivante dans votre répertoire d'application en cours pour démarrer votre application :

```
bx dev run
```
{: tsResolve}

## Erreur du courtier de services lorsque vous ajoutez la fonction {{site.data.keyword.objectstorageshort}}
{: #os}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour créer deux applications avec la fonctionnalité {{site.data.keyword.objectstorageshort}} :

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

Cette erreur est liée au service {{site.data.keyword.objectstorageshort}}, qui ne fournit qu'une seule instance du plan {{site.data.keyword.objectstorageshort}} gratuit.
{: tsCauses}

Choisissez un autre plan pour éviter cette erreur.
{: tsResolve}

## Echec de l'obtention du code lors de la création d'une application
{: #code}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour créer une application :

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

Cette erreur est due à un dépassement de délai interne.
{: tsCauses}

Vous pouvez obtenir le code de l'une des façons suivantes :

* Exécutez la commande suivante en utilisant l'interface de ligne de commande :

   ```
   bx dev code <your-app-name>
   ```
   {: codeblock}

   Remplacez `<your-app-name>` par le nom d'application que vous avez spécifié au cours de la création de l'application.

* Utilisez la console {{site.data.keyword.dev_console}}.

	1. Sélectionnez votre application [ ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://console.bluemix.net/developer/appservice/apps) dans {{site.data.keyword.dev_console}}.

	2. Cliquez sur **Télécharger le code**.

{: tsResolve}

## Erreur lors de l'exécution de `bx dev run` pour les applications Node.js
{: #node}

L'erreur suivante peut s'afficher si vous exécutez `bx dev run` avec l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour des applications BFF ou Web Node.js :

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: codeblock}
{: tsSymptoms}

Cette erreur survient lorsque le module `appmetrics` est installé dans une architecture différente. Les modules npm natifs qui sont installés sur une architecture ne fonctionnent pas sur une autre architecture. Les images Docker incluses sont basées sur le noyau Linux.
{: tsCauses}

Supprimez le dossier `node_modules` et relancez l'exécution de la commande `bx dev run`.
{: tsResolve}

## Echec du déploiement sur {{site.data.keyword.Bluemix_notm}}

Une défaillance se produit lorsque vous tentez d'effectuer un déploiement sur {{site.data.keyword.Bluemix_notm}} avec l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} mais aucune erreur ne s'affiche.
{: tsSymptoms}

Vous n'êtes peut-être pas connecté à votre compte.
{: tsCauses}

Connectez-vous et réessayez.

```
bx login
```
{: tsResolve}

## Echec du déploiement sur Kubernetes sur {{site.data.keyword.Bluemix_notm}}

L'erreur suivante peut s'afficher après que vous avez entré votre nom de cluster :

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

Cela est très probablement dû à un nom de cluster non valide. Vous pouvez confirmer la cause de cette erreur en exécutant la même commande avec l'option `--trace`, qui permet d'afficher les détails suivants dans la sortie d'erreur :

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'bx cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

Assurez-vous que le cluster utilisé est correct et que vous l'avez bien configuré pour déploiement en exécutant la commande suivante :

```
bx cs cluster-config <cluster-name>
```
{: tsResolve}

## Echec du déploiement d'une cible d'image

L'erreur suivante peut s'afficher après que vous avez indiqué la cible d'image de déploiement :

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

Cela est très probablement dû à une cible d'image de déploiement non valide. Plus spécifiquement, l'espace de nom, qui est la valeur du milieu dans la cible d'image de déploiement, n'est peut-être pas valide.

Assurez-vous que l'espace de nom dans la cible d'image de déploiement correspond à l'un des espaces de nom trouvé à l'issue de l'exécution de la commande suivante :

```
bx cr namespaces
```
{: tsResolve}

## Réinstallation des outils
{: #appendix}

Tous les composants prérequis sont installés pour la plupart des utilisateurs à l'aide des programmes d'installation de plateforme. Si vous devez installer manuellement des composants, suivez les instructions ci-dessous :

Pour installer le plug-in dev, vous devez d'abord installer l'[interface de ligne de commande IBM Cloud](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started).

Pour utiliser le plug-in dev proprement dit, vous devez l'installer en exécutant la commande suivante : `bx plugin install dev -r Bluemix`

Pour exécuter et déboguer des applications localement, vous devez également installer [Docker](https://www.docker.com/get-docker).

Pour déployer une application en tant que conteneur, vous devez également installer Kubernetes, Helm et les plug-in d'interface de ligne de commande IBM Cloud suivants :

Pour installer Kubernetes :
* Utilisateurs Mac :
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Utilisateurs Linux :
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Utilisateurs Windows :
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Pour installer Helm :
* Utilisateurs Mac et Linux :
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Utilisateurs Windows :
Téléchargez et installez le fichier binaire depuis https://github.com/kubernetes/helm/releases/tag/v2.6.0

Pour installer le plug-in container-registry, entrez :
`bx plugin install container-registry`

Pour installer le plug-in container-service, entrez :
`bx plugin install container-service`
