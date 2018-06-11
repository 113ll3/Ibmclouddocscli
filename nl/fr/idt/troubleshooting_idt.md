---
copyright:
  years: 2017, 2018
lastupdated: "2018-05-23"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Traitement des incidents liés à IBM Cloud Developer Tools
{: #ts}

Certains problèmes connus rencontrés avec le plug-in {{site.data.keyword.dev_cli_notm}} sont documentés, et des solutions sont proposées.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Problèmes connus
{: #knownissues}

Les sections ci-dessous décrivent les problèmes connus et la façon dont ils peuvent être résolus.


### Erreur indiquant que le nom d'hôte est pris lorsque vous créez un projet avec un modèle non mobile
{: #hostname}

L'erreur suivante peut s'afficher si vous utilisez le plug-in {{site.data.keyword.dev_cli_short}} pour créer un projet depuis les modèles Application Web, BFF ou Microservice :

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Cause
{: #hostname-cause}

Cette erreur est due à un jeton de connexion arrivé à expiration.


#### Résolution
{: #hostname-resolution}

Connectez-vous à nouveau.

```
ibmcloud login
```
{: codeblock}


### Défaillances générales au niveau du plug-in {{site.data.keyword.dev_cli_short}}
{: #general}

L'erreur suivante peut s'afficher si vous utilisez les commandes create, delete, list ou code de {{site.data.keyword.dev_cli_short}} :

```
Failed to <command> project.
```
{: codeblock}


#### Cause
{: #general-cause}

Cette erreur est due à un jeton de connexion arrivé à expiration.


#### Résolution
{: #general-resolution}

Connectez-vous à nouveau.

```
ibmcloud login
```
{: codeblock}


### Erreur : aucune image de ce type lorsque vous exécutez un nouveau projet
{: #nosuchimage}

L'erreur suivante peut s'afficher lorsque vous exécutez un projet alors que vous ne l'avez pas généré :

```
$ ibmcloud dev run testProject
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


#### Cause
{: #nosuchimage-cause}

Vous devez générer un projet avant de l'exécuter.


#### Résolution
{: #nosuchimage-resolution}

Exécutez la commande suivante dans votre répertoire de projet en cours pour
générer votre application :

```
ibmcloud dev build
```
{: codeblock}

Exécutez la commande suivante dans votre répertoire de projet en cours pour
démarrer votre application :

```
ibmcloud dev run
```


### Erreur du courtier de services lorsque vous ajoutez la fonction {{site.data.keyword.objectstorageshort}}
{: #os}

L'erreur suivante peut s'afficher si vous utilisez le plug-in {{site.data.keyword.dev_cli_short}} pour créer deux projets avec la fonctionnalité {{site.data.keyword.objectstorageshort}} :

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Cause
{: #os-cause}

Cette erreur est due au fait que le service {{site.data.keyword.objectstorageshort}} ne fournit qu'une instance du plan {{site.data.keyword.objectstorageshort}} gratuit.


#### Résolution
{: #os-resolution}

Choisissez un autre plan pour éviter cette erreur.


### Echec lors de l'obtention du code lors de la création d'un projet
{: #code}

L'erreur suivante peut s'afficher si vous utilisez le plug-in {{site.data.keyword.dev_cli_short}} pour créer un projet :

```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}


#### Cause
{: #code-cause}

Cette erreur est due à un dépassement de délai interne.


#### Résolution
{: #code-resolution}

Vous pouvez obtenir le code de l'une des façons suivantes :

* Exécutez la commande suivante en utilisant l'interface de ligne de commande :

   ```
   ibmcloud dev code <your-project-name>
   ```
   {: codeblock}

   Remplacez `<your-project-name>` par le nom de projet que vous avez spécifié au cours de la création du projet.

* Utilisez la console {{site.data.keyword.dev_console}}.

	1. Sélectionnez votre [projet ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://console.{DomainName}/developer/projects) dans {{site.data.keyword.dev_console}} et cliquez sur **Obtenir le code**.

	2. Cliquez sur **Générer le code**.

	3. Une fois le code généré, cliquez sur **Télécharger le code**.


### Erreur lors de l'exécution de `ibmcloud dev run` pour les projets Node.js
{: #node}

L'erreur suivante peut s'afficher si vous exécutez `ibmcloud dev run` avec des projets Web ou BFF du plug-in {{site.data.keyword.dev_cli_short}} for Node.js :

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


#### Cause
{: #node-cause}

Cette erreur survient lorsque le module `appmetrics` est installé dans une architecture différente. Les modules npm natifs qui sont installés sur une architecture ne fonctionnent pas sur une autre architecture. Les images Docker incluses sont basées sur le noyau Linux.


#### Résolution
{: #node-resolution}

Supprimez le dossier `node_modules` et exécutez à nouveau `ibmcloud dev run`.


### Echec du déploiement sur {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploy}

Vous pourriez tenter d'effectuer un déploiement sur {{site.data.keyword.Bluemix_notm}} avec {{site.data.keyword.dev_cli_short}} et constater qu'il n'est pas déployé sur {{site.data.keyword.Bluemix_notm}}, sans pour autant qu'une erreur soit affichée.


#### Cause
{: #cause1}

Vous n'êtes peut-être pas connecté à votre compte.

#### Résolution
{: #resolution1}

Connectez-vous et réessayez.

```
ibmcloud login
```


### Echec du déploiement sur Kubernetes sur {{site.data.keyword.Bluemix_notm}}
{: #failuretodeploytokube}

L'erreur suivante est susceptible de s'afficher après l'invite initiale vous demandant d'entrer le nom de votre cluster :

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### Cause
{: #cause2}

Cette erreur est probablement due à un nom de cluster non valide et peut être confirmée en exécutant la même commande avec `--trace`. La sortie d'erreur que vous obtenez alors peut contenir ce qui suit :

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### Résolution
{: #resolution2}

Assurez-vous que le cluster que vous utilisez est correct et que vous l'avez bien configuré pour déploiement en exécutant la commande suivante :

```
ibmcloud cs cluster-config <nom_cluster>
```


### Echec du déploiement sur Kubernetes sur {{site.data.keyword.Bluemix_notm}}

L'erreur suivante est susceptible de s'afficher après l'invite vous demandant d'entrer la cible de l'image de déploiement :

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### Cause
{: #cause3}

Cette erreur est probablement due à une cible d'image de déploiement non valide. Plus spécifiquement, l'espace de nom, qui est la valeur du milieu dans la cible d'image de déploiement, n'est peut-être pas valide.


#### Résolution
{: #resolution3}

Assurez-vous que l'espace de nom dans la cible d'image de déploiement correspond à l'un des espaces de nom trouvé à l'issue de l'exécution de la commande suivante :

```
ibmcloud cr namespaces
```



## ANNEXE
{: #appendix}

Tous les composants prérequis seront installés pour la plupart des utilisateurs à l'aide des programmes d'installation de plateforme en haut de cette page. Si vous devez installer manuellement des composants, suivez les instructions ci-dessous :

Pour installer le plug-in dev, vous devez d'abord installer l'[interface de ligne de commande IBM Cloud](../reference/bluemix_cli/get_started.md#getting-started).

Pour utiliser le plug-in dev proprement dit, vous devez l'installer en exécutant la commande suivante : `ibmcloud plugin install dev -r Bluemix`

Pour exécuter et déboguer des applications localement, vous devez également installer [Docker ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe")](https://www.docker.com/get-docker).

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

Pour installer le plug-in container-registry :
`ibmcloud plugin install container-registry`

Pour installer le plug-in container-service :
`ibmcloud plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Aide et assistance
{: #gettinghelp}

Si vous rencontrez des problèmes ou avez des questions au sujet d'{{site.data.keyword.dev_console}} de {{site.data.keyword.Bluemix_notm}} ou du plug-in {{site.data.keyword.dev_cli_notm}}, vous pouvez obtenir de l'aide en recherchant des informations ou en posant des questions sur un forum. Vous pouvez également ouvrir un ticket de demande de service.

Lorsque vous publiez des questions sur les forums, vous pouvez les étiqueter de sorte que les équipes de développement {{site.data.keyword.Bluemix_notm}} soient notifiées.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

Si vous avez des questions techniques sur le développement ou le déploiement d'une application avec {{site.data.keyword.dev_console}} ou le plug-in {{site.data.keyword.dev_cli_notm}} :

* Postez votre question sur [stackoverflow![External link icon](../icons/launch-glyph.svg "External link icon")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) et marquez votre question avec les étiquettes `bluemix-dev-services` et `ibm-bluemix`.
* Postez votre question sur [Slack ![External link icon](../icons/launch-glyph.svg "External link icon")](http://ibm-cloud-tech.slack.com/) sur le canal `bluemix-dev-services`. [Inscrivez-vous ![External link icon](../icons/launch-glyph.svg "External link icon")](http://ibm.biz/IBMCloudNativeSlack) maintenant.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

Pour plus d'informations sur l'utilisation des forums, voir la rubrique expliquant [comment obtenir de l'aide ![External link icon](../icons/launch-glyph.svg "External link icon")](/docs/support/index.html#getting-help).

Pour plus d'informations sur l'ouverture d'un ticket de demande de service {{site.data.keyword.IBM}}, sur les niveaux de support disponibles ou les niveaux de gravité des tickets, voir la rubrique expliquant [comment contacter le support![External link icon](../icons/launch-glyph.svg "External link icon")](/docs/support/index.html#contacting-support).

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
