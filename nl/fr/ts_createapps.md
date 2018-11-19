---

copyright:
  years: 2015, 2018
lastupdated: "2018-11-05"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Traitement des incidents liés au plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} Developer Tools
{: #troubleshoot}

Les problèmes d'ordre général liés à l'utilisation de l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour créer des applications peuvent inclure des échecs de déploiement ou l'échec de l'extraction du code. Dans de nombreux cas, ces problèmes peuvent être résolus en quelques opérations simples.
{:shortdesc}

## Pour quelle raison une erreur de nom d'hôte s'affiche-t-elle lors de la création d'une application avec un modèle non mobile ?
{: #hostname-error}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour déployer une application sur Cloud Foundry. Si vous entrez un nom d'hôte unique, il se peut que le message suivant s'affiche tout de même :

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

Cette erreur est provoquée par un jeton de connexion ayant expiré.
{: tsCauses}

Reconnectez-vous à l'aide de la commande suivante :
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Pour quelle raison des échecs de commande générale se produisent-ils ?
{: #general}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez les commandes `create`, `delete`, `list` ou `code` :

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

Cette erreur est provoquée par un jeton de connexion ayant expiré.
{: tsCauses}

Reconnectez-vous à l'aide de la commande suivante :
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Pour quelle raison l'image de ma nouvelle application n'est-elle pas reconnue ?
{: #nosuchimage}
{: troubleshoot}

L'erreur suivante peut s'afficher lorsque vous tentez d'exécuter une application sans l'avoir préalablement générée :

```
$ ibmcloud dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: tsSymptoms}

Vous devez générer une application avant de l'exécuter. Exécutez la commande suivante dans votre répertoire d'application en cours :
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Exécutez la commande suivante dans votre répertoire d'application en cours pour démarrer votre application :
```
ibmcloud dev run
```
{: tsResolve}

## Pour quelle raison une erreur de courtier de services s'affiche-t-elle lorsque j'ajoute la fonction {{site.data.keyword.objectstorageshort}} ?
{: #os}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande pour créer deux applications avec la fonctionnalité {{site.data.keyword.objectstorageshort}} :

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

Cette erreur est liée au service {{site.data.keyword.objectstorageshort}}, qui ne fournit qu'une seule instance du plan {{site.data.keyword.objectstorageshort}} gratuit.
{: tsCauses}

Sélectionnez un autre plan.
{: tsResolve}

## Pour quelle raison mon code n'est-il pas extrait lorsque je crée une application ?
{: #code}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande pour créer une application :

```
FAILED                            
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

Cette erreur est due à un dépassement de délai interne.
{: tsCauses}

Procédez de l'une des façons suivantes pour obtenir le code :

* Exécutez la commande suivante :

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Remplacez `<your-app-name>` par le nom d'application que vous avez spécifié au cours de la création de l'application.

* Utilisez la console {{site.data.keyword.dev_console}}.

	1. Sélectionnez votre application [ ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://console.bluemix.net/developer/appservice/apps) dans {{site.data.keyword.dev_console}}.

	2. Cliquez sur **Télécharger le code**.
{: tsResolve}

## Pour quelle raison l'exécution de la commande `ibmcloud dev run` échoue-t-elle pour les applications Node.js ?
{: #node}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous exécutez la commande `ibmcloud dev run` pour les applications Web Node.js ou BFF :

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

Supprimez le dossier `node_modules` et exécutez à nouveau la commande `ibmcloud dev run`.
{: tsResolve}

## Pour quelle raison ne puis-je pas déployer {{site.data.keyword.Bluemix_notm}} ?
{: troubleshoot}

Une erreur se produit lorsque vous tentez d'effectuer un déploiement sur {{site.data.keyword.Bluemix_notm}} et qu'aucune erreur ne s'affiche.
{: tsSymptoms}

Vous n'êtes peut-être pas connecté à votre compte.
{: tsCauses}

Relancez l'exécution de la commande suivante pour vous connecter puis faites une nouvelle tentative.
```
ibmcloud login
```
{: tsResolve}

## Pour quelle raison ne puis-je pas effectuer un déploiement de Kubernetes sur {{site.data.keyword.Bluemix_notm}} ?
{: troubleshoot}

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
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

Assurez-vous que le cluster utilisé est correct et que vous l'avez bien configuré pour déploiement en exécutant la commande suivante :
```
ibmcloud cs cluster-config <nom_cluster>
```
{: tsResolve}

## Pour quelle raison ne puis-je pas déployer une cible d'image ?
{: troubleshoot}

L'erreur suivante peut s'afficher après que vous avez indiqué la cible d'image de déploiement :
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

Cela est très probablement dû à une cible d'image de déploiement non valide. Plus spécifiquement, l'espace de nom, qui est la valeur du milieu dans la cible d'image de déploiement, n'est peut-être pas valide.
{: tsCauses}

Assurez-vous que l'espace de nom dans la cible d'image de déploiement correspond à l'un des espaces de nom affichés lorsque vous exécutez la commande suivante :
```
ibmcloud cr namespaces
```
{: tsResolve}

## Pour quelle raison la langue de mon application ne peut-elle pas être déterminée ?
{: troubleshoot}

L'erreur suivante peut s'afficher lorsque vous tentez de démarrer votre application :
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: tsSymptoms}

Cette erreur peut être due à l'une des causes suivantes :
- Exécution de la commande [enable](/docs/cli/idt/commands.html#enable) à partir d'un répertoire qui n'est pas le répertoire source de votre application
- Application de la commande [enable](/docs/cli/idt/commands.html#enable) pour une application pour une langue qui n'est pas reconnue pour l'instant.
{: tsCauses}

Prenez soin d'exécuter la commande à partir du répertoire d'application qui contient le code source pour l'application. Si cela ne résout pas le problème et que la langue figure parmi les [langues prises en charge](/docs/cli/idt/commands.html#enable-language-options), utilisez le paramètre `--language` pour spécifier cette langue.
{: tsResolve}

## Pour quelle raison ne puis-je pas générer ou exécuter une application qui a été activée pour le déploiement en cloud ?
{: troubleshoot}

Vous risquez de rencontrer des erreurs lorsque vous tentez de [générer](/docs/cli/idt/commands.html#build) ou d'[exécuter](/docs/cli/idt/commands.html#run) une application qui a été activée.
{: tsSymptoms}


Les nombreuses causes possibles sont décrites dans chacun des liens suivants :
{: tsCauses}

- Pour plus d'informations sur la résolution de ce type de problème avec une application Spring, voir [Activation d'applications Spring Boot existantes pour le déploiement en cloud](/docs/java-spring/enable_existing.html#enable_existing).
- Pour plus d'informations sur la résolution de ce type de problème avec une application `Node.js`, voir [Activation d'applications Node.js existantes pour le déploiement en cloud](/docs/node/enable_existing.html#enable_existing).
{: tsResolve}
