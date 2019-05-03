---

copyright:
  years: 2015, 2019
lastupdated: "2019-04-15"

keywords: cli, troubleshoot cli, debug app cli, developer tools debug, ibmcloud cli debug, ibmcloud help, ibmcloud dev help, cli debug, plugin debug, debug plug-in, command line, command-line, developer tools troubleshoot

subcollection: cloud-cli

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
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Traitement des incidents liés au plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} Developer Tools
{: #troubleshoot}

Les problèmes d'ordre général liés à l'utilisation de l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour créer des applications peuvent inclure des échecs de déploiement ou l'échec de l'extraction du code. Dans de nombreux cas, ces problèmes peuvent être résolus en quelques opérations simples.
{: shortdesc}

## Pour quelle raison une erreur de nom d'hôte s'affiche-t-elle lors de la création d'une application avec un modèle non mobile ?
{: #ts-cli-hostname-error}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} pour déployer une application sur Cloud Foundry. Si vous entrez un nom d'hôte unique, il se peut que le message suivant s'affiche tout de même :
```
The hostname <myHostname> is taken.
```
{: screen}
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
{: #ts-cli-general-failures}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez les commandes `create`, `delete`, `list` ou `code` :
```
Failed to <command> app.
```
{: screen}
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
{: #ts-cli-nosuchimage}
{: troubleshoot}

Lorsque vous tentez d'exécuter la commande `ibmcloud dev run` sans la générer auparavant, le message d'erreur suivant peut s'afficher :
```
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
{: screen}
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
{: #ts-cli-object-storage}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande pour créer deux applications avec la fonctionnalité {{site.data.keyword.objectstorageshort}} :

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

Cette erreur est liée au service {{site.data.keyword.objectstorageshort}}, qui ne fournit qu'une seule instance du plan {{site.data.keyword.objectstorageshort}} gratuit.
{: tsCauses}

Sélectionnez un autre plan.
{: tsResolve}

## Pour quelle raison mon code n'est-il pas extrait lorsque je crée une application ?
{: #retrieve-code-error}
{: troubleshoot}

L'erreur suivante peut s'afficher si vous utilisez l'interface de ligne de commande pour créer une application :
```
FAILED                            
App created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

Cette erreur est due à un dépassement de délai interne.
{: tsCauses}

Procédez de l'une des façons suivantes pour obtenir le code :

* Exécutez la commande suivante :

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Remplacez `<your-app-name>` par le nom d'application spécifié lors de la création de l'application. 

* Utilisez la console {{site.data.keyword.dev_console}}.

	1. Sélectionnez votre [application ](https://cloud.ibm.com/resources){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") dans la console {{site.data.keyword.dev_console}}.

	2. Cliquez sur **Télécharger le code**.
{: tsResolve}

## Pour quelle raison l'exécution de la commande `ibmcloud dev run` échoue-t-elle pour les applications Node.js ?
{: #ts-cli-node}
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
{: screen}
{: tsSymptoms}

Cette erreur survient lorsque le module `appmetrics` est installé dans une architecture différente. Les modules npm natifs qui sont installés sur une architecture ne fonctionnent pas sur une autre architecture. Les images Docker incluses sont basées sur le noyau Linux.
{: tsCauses}

Supprimez le dossier `node_modules` et exécutez à nouveau la commande `ibmcloud dev run`.
{: tsResolve}

## Pour quelle raison ne puis-je pas déployer {{site.data.keyword.cloud_notm}} ?
{: #ts-cli-deploy-issues}
{: troubleshoot}

Un échec survient lorsque vous tentez d'effectuer un déploiement sur {{site.data.keyword.cloud_notm}} mais aucune erreur ne s'affiche.
{: tsSymptoms}

Vous n'êtes peut-être pas connecté à votre compte.
{: tsCauses}

Relancez l'exécution de la commande suivante pour vous connecter puis faites une nouvelle tentative.
```
ibmcloud login
```
{: tsResolve}

## Pour quelle raison ne puis-je pas effectuer un déploiement de Kubernetes sur {{site.data.keyword.cloud_notm}} ?
{: #ts-cli-kube-deploy}
{: troubleshoot}

L'erreur suivante peut s'afficher après que vous avez entré votre nom de cluster :
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

Cela est très probablement dû à un nom de cluster non valide. Vous pouvez confirmer la cause de cette erreur en exécutant la même commande avec l'option `--trace`, qui permet d'afficher les détails suivants dans la sortie d'erreur :
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

Assurez-vous que vous utilisez le cluster correct et que ce dernier est configuré en exécutant :
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## Pour quelle raison ne puis-je pas déployer une cible d'image ?
{: #ts-deploy-image-target}
{: troubleshoot}

L'erreur suivante peut s'afficher après que vous avez indiqué la cible d'image de déploiement :
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'us.icr.io/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

Cela est très probablement dû à une cible d'image de déploiement non valide. Plus spécifiquement, l'espace de nom, qui est la valeur du milieu dans la cible d'image de déploiement, n'est peut-être pas valide.
{: tsCauses}

Assurez-vous que l'espace de nom de l'image de déploiement correspond à l'un des espaces de nom affichés lorsque vous exécutez la commande suivante :
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## Pour quelle raison le langage de mon application ne peut-il pas être déterminé ?
{: #ts-cli-determine-language}
{: troubleshoot}

L'erreur suivante peut s'afficher lorsque vous tentez de démarrer votre application :
```
FAILED
Could not determine the language of your app.

Try using the --language flag to specify the language of your app 
directly. 
```
{: screen}
{: tsSymptoms}

Cette erreur peut être due à l'une des causes suivantes :
- Exécution de la commande [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) à partir d'un répertoire qui n'est pas le répertoire source de votre application
- Exécution de la commande [enable](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) pour une application utilisant un langage qui n'est pas reconnu.
{: tsCauses}

Prenez soin d'exécuter la commande à partir du répertoire d'application qui contient le code source pour l'application. Si cela ne résout pas le problème et que le langage figure parmi les [langages pris en charge](/docs/cli/idt?topic=cloud-cli-idt-cli#enable-language-options), utilisez le paramètre `--language` pour spécifier ce langage.
{: tsResolve}

## Pour quelle raison ne puis-je pas générer ou exécuter une application qui a été activée pour le déploiement en cloud ?
{: #ts-cli-cloud-enabled-apps}
{: troubleshoot}

Vous risquez de rencontrer des erreurs lorsque vous tentez de [générer](/docs/cli/idt?topic=cloud-cli-idt-cli#build) ou d'[exécuter](/docs/cli/idt?topic=cloud-cli-idt-cli#run) une application qui a été activée.
{: tsSymptoms}

Les nombreuses causes possibles sont décrites dans chacun des liens suivants :
{: tsCauses}

- Pour plus d'informations sur la résolution de ce type de problème avec une application Spring, voir [Activation d'applications Spring Boot existantes pour le déploiement en cloud](/docs/java-spring?topic=java-spring-enable_existing#enable_existing).
- Pour plus d'informations sur la résolution de ce type de problème avec une application `Node.js`, voir [Activation d'applications Node.js existantes pour le déploiement en cloud](/docs/node?topic=nodejs-enable_existing#enable_existing).
{: tsResolve}

## Installation manuelle et séparée des composants de l'interface CLI {{site.data.keyword.dev_cli_notm}}
{: #ts-cli-install-devtools-manually}
{: troubleshoot}

Pour installer manuellement et séparément les composants de l'interface CLI {{site.data.keyword.dev_cli_notm}}, vous pouvez suivre cette [procédure](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).

## Pourquoi ne puis-je pas générer l'image Docker ?
{: $ts-cli-docker}
{: troubleshoot}

Si l'erreur suivante s'affiche : 
```
FAILED
An error exit status 1 was encountered while building the Docker 
image.
```
{: screen}

elle peut être due à l'une des causes suivantes :
- Docker n'est pas installé.
- Le démon Docker n'est pas en cours d'exécution.
{: tsCauses}

Assurez-vous que Docker est installé et en cours d'exécution :
- Pour installer ou démarrer [Docker pour Mac](https://docs.docker.com/docker-for-mac/install/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")
- Pour installer ou démarrer [Docker pour Windows](https://docs.docker.com/docker-for-windows/install/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")
- Pour installer ou démarrer [Docker pour Linux](https://docs.docker.com/v17.12/install/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")
{: tsResolve}

## Comment résoudre le problème lié aux versions Helm incompatibles ?
{: ts-cli-helm}
{: troubleshoot}

Si les versions Helm client et serveur ne sont pas synchronisées, les erreurs suivantes peuvent être générées :
```
FAILED
Failed to execute the action:  exit status 1: Error: UPGRADE FAILED: 
configmaps is forbidden: User "system:serviceaccount:kube-system:default" 
cannot list resource "configmaps" in API group "" in the namespace 
"kube-system"
```
{: screen}

```
FAILED
The 'helm upgrade ' command failed to complete due to: exit status 1
```
{: screen}

Pour résoudre ce problème, indiquez une version de client identique à la version du cluster. Par exemple, pour installer la version Helm 2.8.1, exécutez les commandes suivantes :
{: tsResolve}

* Pour Mac et Linux, exécutez les commandes suivantes :
  ```
  export DESIRED_VERSION=v2.8.1

  curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash

  export HELM_HOME=~/.helm
  ```

* Pour Windows, effectuez les actions suivantes en tant qu'administrateur :
  Téléchargez et installez le fichier binaire `helm` à partir de la page [https://github.com/helm/helm/releases/tag/v2.9.1](https://github.com/helm/helm/releases/tag/v2.9.1){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").
  
  Sur le terminal PowerShell, utilisez les commandes suivantes :
  ```
  Set-Location Env:
  Set-Item HELM_HOME C:\.helm\
  ```

## Pourquoi la génération ibmcloud dev échoue-t-elle lorsqu'un nom d'utilisateur inclut le caractère "@" ?
{: ts-cli-username}
{: troubleshoot}
Lors du processus de génération d'image, votre nom d'utilisateur est employé pour l'utilisateur dans l'image des outils Docker. Si le nom d'utilisateur contient des caractères spéciaux, tels '@' ou '-', le processus de génération d'image Docker échoue et l'erreur suivante peut être générée :
```
Image will have user johnsmith@acme.com with id 501 added

Executing docker image build  --file Dockerfile-tools --tag pythonmicroservicewithflaskfnzat-flask-tools --rm --pull --build-arg bx_dev_userid=501 --build-arg bx_dev_user=johnsmith@acme.com .

FAILED
An error exit status 1 was encountered while building the Docker image.

Dumping output from the command:
```
{: screen}

Pour résoudre le problème, modifiez votre nom d'utilisateur de telle sorte qu'il ne comporte aucun caractère spécial ou indiquez l'option suivante pour utiliser à la place l'utilisateur root :
```
ibmcloud dev build --use-root-user-tools
```
{: codeblock}
{: tsResolve}
