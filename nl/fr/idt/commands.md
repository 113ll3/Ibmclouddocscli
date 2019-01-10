---

copyright:

   years: 2017, 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Commandes du plug-in {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev)
{: #idt-cli}

Version : 2.1.4
Publication : 31 août 2018

A compter de mai 2018, les commandes de l'interface CLI d'{{site.data.keyword.Bluemix}} ont été changées de `bluemix` et `bx` en `ibmcloud`. Vous pouvez toutefois continuer à utiliser les commandes de l'interface CLI `bluemix` et `bx` jusqu'à ce qu'elles soient retirées.
{: tip}

Utilisez les commandes {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev) suivantes pour créer une application, la déployer, la déboguer et la tester :

- La commande [build](#build) permet de créer l'application dans un conteneur local.
- La commande [code](#code) permet de télécharger le code pour une application.
- La commande [console](#console) permet d'ouvrir la console IBM Cloud pour une application.
- La commande [create](#create) permet de créer une nouvelle application et offre la possibilité d'ajouter des services.
- La commande [debug](#debug) permet de déboguer votre application dans un conteneur local.
- La commande [delete](#delete) permet de supprimer une application de votre espace.
- La commande [deploy](#deploy) permet de déployer une application sur IBM Cloud.
- [diag](#diag) permet d'afficher les informations de version concernant les dépendances installées.
- La commande [edit](#edit) permet d'ajouter ou de retirer des services pour une application existante
- La commande [enable](#enable) permet de mettre à jour une application existante à utiliser avec IBM Cloud Developer Tools
- La commande [get-credentials](#get-credentials) permet d'obtenir les données d'identification requises par l'application pour activer l'utilisation de services IBM Cloud connectés.
- La commande [help](#help) permet d'obtenir de l'aide sur la syntaxe et les arguments CLI.
- La commande [list](#list) permet de répertorier toutes les applications IBM Cloud d'un groupe de ressources.
- La commande [run](#run) permet d'exécuter votre application dans un conteneur local.
- La commande [shell](#shell) permet d'ouvrir un shell dans un conteneur local.
- La commande [status](#status) permet de vérifier le statut des conteneurs utilisés par l'interface de ligne de commande.
- La commande [stop](#stop) permet d'arrêter un conteneur.
- La commande [test](#test) permet de tester votre application dans un conteneur local.
- La commande [view](#view) permet d'afficher l'URL déployée de l'application à des fins de test et de visualisation.
- Les [commandes composées](#compound) permettent d'exécuter plusieurs commandes dans une seule instruction de ligne de commande.



## Commande build
{: #build}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez générer votre application en utilisant la commande `build`. Les commandes `test`, `debug` et `run` s'attendent à trouver une application compilée, par conséquent, vous devez préalablement exécuter une opération `build`.  

L'élément de configuration `build-cmd-debug` est utilisé afin de générer l'application pour toutes les utilisations, à l'exception de`run`. Vous générez votre application à des fins d débogage en spécifiant l'option de ligne de commande `--debug`.  L'élément de configuration `build-cmd-run` est utilisé lors de la génération de l'application afin de l'utiliser avec la commande `run`.

Pour une génération avec plusieurs conteneurs, votre application doit contenir un fichier [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe"), qui est indiqué dans le fichier `cli-config.yml` ou vous pouvez utiliser le paramètre de commande `dockerfile-tools` pour en indiquer un. Pour plus d'informations, voir [Fichier Compose](/docs/apps/projects/compose_file.html).

Exécutez la commande suivante dans votre répertoire d'application en cours pour générer votre application :  

```
ibmcloud dev build [--debug]
```
{: codeblock}



## Commande code
{: #code}

Utilisez la commande `code` pour télécharger une application précédemment créée avec le code de modèle d'application et les fichiers de configuration de {{site.data.keyword.Bluemix_notm}}.  Cette commande est particulièrement utile lorsque vous devez extraire une deuxième copie d'une application que vous avez créée.

Exécutez la commande suivante pour télécharger le code à partir d'une application spécifiée :

```
ibmcloud dev code <applicationName>
```
{: codeblock}


## Commande console
{: #console}

Utilisez la commande `console` pour ouvrir un navigateur Web dans la console Web de votre application sur IBM Cloud.  Vous pouvez exécuter la commande `ibmcloud dev console` depuis votre dossier d'application, auquel cas l'interface de ligne de commande tente de trouver une application correspondante sur IBM Cloud portant le même ID d'application que le répertoire en cours. Si le système ne parvient pas à trouver de nom correspondant, il ouvre le tableau de bord Web et mobile sur IBM Cloud au lieu de l'application spécifique.

Vous pouvez indiquer un nom d'application ; l'interface de ligne de commande ignore la mise en correspondance basée sur le nom de dossier/d'application. Dans ce cas, l'interface de ligne de commande ouvre la console de l'application nommée dans un navigateur Web.  

Exécutez la commande suivante pour ouvrir un navigateur Web sur la console Web de votre application :

```
ibmcloud dev console [applicationName]
```
{: codeblock}


## Commande create
{: #create}

Créer une application en invitant à spécifier toutes les informations, notamment le type de ressource, le langage, le kit de démarrage et les options DevOps Toolchain. L'application est créée dans le répertoire de travail.

Pour créer une application dans le répertoire de travail et pour y associer des services, exécutez la commande suivante :

```
ibmcloud dev create
```
{: codeblock}


## Commande debug
{: #debug}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez déboguer votre application avec la commande `debug`. Une génération doit d'abord être effectuée pour l'application en utilisant la commande build avec l'argument `--debug`. Le lancement de la commande `debug` entraîne le démarrage d'un conteneur qui fournit un ou plusieurs ports de débogage définis par la valeur `container-port-map-debug` dans le fichier cli-config.yml ou spécifiés sur la ligne de commande. Connectez votre outil de débogage favori au port ou aux ports et vous pourrez déboguer votre application en mode normal.

Compilez tout d'abord votre application :

```
ibmcloud dev build --debug
```
{: codeblock}

Pour commencer, exécutez la commande suivante dans votre répertoire d'application en cours afin de déboguer votre application :

```
ibmcloud dev debug
```
{: codeblock}

Pour effectuer un débogage, associez votre outil de débogage au port spécifié.

Pour quitter la session de débogage, utilisez `CTRL-C`.


### Paramètres de la commande debug
{: #debug-parameters}

Les paramètres ci-dessous, qui sont réservés à la commande
`debug`, facilitent le débogage d'une application. Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `container-port-map-debug`
{: #port-map-debug}

* Mappages de port pour le port de débogage. La première valeur est le port à
utiliser sur le système d'exploitation hôte et la seconde le port dans le conteneur
[host-port:container-port].
* Syntaxe : `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Paramètre utilisé afin de générer le code pour DEBUG.
* Syntaxe : `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Paramètre utilisé pour spécifier une commande afin d'appeler la fonction
de débogage dans le conteneur tools. Utilisez-le si
`build-cmd-debug` démarre votre application en mode débogage.
* Syntaxe : `ibmcloud dev debug --debug-cmd /the/debug/command`



## Commande delete
{: #delete}

Utilisez la commande `delete` pour supprimer des applications de votre espace {{site.data.keyword.Bluemix_notm}}. Vous pouvez exécuter la commande sans paramètre pour afficher la liste des applications disponibles et sélectionner l'application à supprimer dans la liste numérotée. Le code de l'application et les répertoires ne sont pas retirés de votre espace disque local.

Exécutez la commande suivante pour supprimer votre application dans {{site.data.keyword.Bluemix_notm}} :

```
ibmcloud dev delete <applicationName>
```
{: codeblock}


Les services {{site.data.keyword.Bluemix_notm}} ne sont **pas** retirés.
{: note}

## Déploiement
{: #deploy}

Vous pouvez déployer une application en tant qu'application Cloud Foundry ou en tant que conteneur.

Pour le déploiement en tant qu'application Cloud Foundry dans {{site.data.keyword.Bluemix_notm}}, un fichier `manifest.yml` doit être présent dans le répertoire racine de votre application.

Avant de déployer une application en tant que conteneur, vous devez installer localement [Kubernetes](https://kubernetes.io/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") et [Helm](https://github.com/kubernetes/helm){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe"). Assurez-vous que la version du client Helm n'est pas plus récente que la version du serveur Helm. Pour connaître ces informations, exécutez la commande `helm version`. Il est recommandé d'utiliser la version 2.4.2 pour la version du client.

Pour déployer votre application sur Kubernetes, vous devez spécifier l'élément `deploy-target` en tant que `conteneur` dans le fichier `cli-config.yml` ou utiliser le paramètre `-t container`.

D'autres paramètres requis pour la configuration du déploiement Kubernetes peuvent être spécifiés dans le fichier `cli-config.yml`, comme présenté ci-dessous, ou via des arguments de ligne de commande. Si vous ne définissez pas ces informations dans le fichier `cli-config.yml`, vous devez effectuer le déploiement avec le paramètre `-t container`. Vous êtes alors invité à spécifier toutes les autres valeurs.

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

Dans le fichier `cli-config.yml`, vous pouvez choisir de définir l'emplacement d'un graphique Helm dans la propriété `chart-path` et de configurer l'élément `deploy-image-target`, comme cela est présenté dans l'exemple. L'élément `deploy-image-target` dans le fichier `cli-config.yml` est utilisé à la place des éléments `repository` et `tag` dans le fichier `chart/values.yml`. Pour effectuer un déploiement spécifiquement vers {{site.data.keyword.Bluemix_notm}}, affectez à l'élément de configuration `ibm-cluster` le nom du cluster Kubernetes créé dans {{site.data.keyword.Bluemix_notm}}.


Exécutez la commande suivante dans votre répertoire d'application en cours pour générer votre application :  

```
ibmcloud dev build
```
{: codeblock}

Exécutez la commande suivante dans votre répertoire d'application en cours pour déployer votre application :

```
ibmcloud dev deploy
```
{: codeblock}


### Paramètres de la commande deploy
{: #deploy-parameters}

Les paramètres ci-dessous peuvent être utilisés avec la commande `deploy` ou en mettant directement à jour le fichier `cli-config.yml` de l'application. Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `chart-path`
{: #chart-path}

* Paramètre utilisé pour un déploiement de conteneur afin de spécifier l'emplacement du graphique Helm utilisé pour le déploiement.
* Syntaxe `ibmcloud dev deploy --chart-path [/chemin]`

#### `deploy-target`
{: #deploy-target}

* Paramètre facultatif permettant d'indiquer le type de déploiement à effectuer.  Le type de déploiement par défaut est buildpack.
* Syntaxe : `ibmcloud dev deploy -t|--target pack de construction|conteneur`

#### `deploy-image-target`
{: #deploy-image-target}

* Paramètre utilisé avec un déploiement de conteneur comme nom d'image cible du déploiement (par exemple, pour baliser un registre Docker).  La valeur ne doit pas inclure de version, par exemple,: image-name:{version}, car la version est automatiquement incrémentée et ajoutée par `deploy`.
* Syntaxe `ibmcloud dev deploy --deploy-image-target [nom_image]`

#### `ibm-cluster`
{: #ibm-cluster}

* Paramètre facultatif permettant de définir le nom du cluster kubernetes pour un déploiement de conteneur sur {{site.data.keyword.Bluemix_notm}}.
* Syntaxe : `ibmcloud dev deploy --ibm-cluster [nom_cluster]`

#### `hôte`
{: #host}

* Paramètre facultatif permettant de définir le nom d'hôte de l'application lors du déploiement dans Cloud Foundry
* Syntaxe : `ibmcloud dev deploy --host [hostname]`

#### `domaine`
{: #domain}

* Paramètre facultatif permettant de définir le domaine de l'application lors du déploiement dans Cloud Foundry
* Syntaxe : `ibmcloud dev deploy --domain [domain]`


## diag
{: #diag}

Cette commande est utilisée en tant que diagnostic pour afficher les informations de version concernant les dépendances installées pour l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}. Elle vous permet notamment de déterminer si des dépendances sont manquantes ou de déboguer plus facilement les problèmes.

Exécutez la commande suivante pour afficher les versions de vos dépendances installées :

```
ibmcloud dev diag
```
{: codeblock}


## edit
{: #edit}

Modifiez votre application en ajoutant des options, comme la connexion de cette dernière à une application se trouvant déjà dans {{site.data.keyword.Bluemix_notm}}, la gestion des services {{site.data.keyword.Bluemix_notm}} de l'application et de sa chaîne d'outils {{site.data.keyword.Bluemix_notm}}. Avec une application locale connectée à une application dans {{site.data.keyword.Bluemix_notm}}, utilisez `edit` pour ajouter de nouveaux services, connecter et déconnecter les services existants ou retirer des services existants de votre compte. En outre, vous pouvez créer ou afficher une chaîne d'outils {{site.data.keyword.Bluemix_notm}} pour l'application. Exécutez la commande suivante à la racine du répertoire d'application :

```
ibmcloud dev edit
```
{: codeblock}

Si vous n'avez aucun service existant dans votre compte, cette commande affiche une liste des groupes de services à partir desquels vous pouvez sélectionner un service à connecter à votre application.

Cependant, si vous disposez de services existants dans votre compte, cette commande affiche une liste de ces services et indique si chaque service est connecté ou non à l'application.

La sélection d'un service connecté vous permet de déconnecter le service de votre application ou de supprimer le service de votre compte, et donc de le déconnecter de toutes les applications auxquelles il est connecté.

La sélection d'un service déconnecté vous permet de connecter ce service à votre application ou de supprimer le service de votre compte. La connexion d'un service existant entraîne le téléchargement de fichiers, tels que les fichiers de données d'identification ou le code source, qui vous permettent de commencer à utiliser ce service.

Vous pouvez également ajouter un nouveau service à votre application. Des invites de sélection de service s'affichent. De plus, des fichiers supplémentaires sont téléchargés (fichiers de données d'identification ou code source) vous permettant de commencer à utiliser le nouveau service.



## Commande enable
{: #enable}

Activez une application existante pour le déploiement {{site.data.keyword.Bluemix_notm}}. La commande `enable` tente de détecter automatiquement le langage d'une application existante, puis invite à indiquer les informations supplémentaires nécessaires. Cette opération génère et ajoute des fichiers pouvant être utilisés pour des conteneurs Docker locaux, le déploiement Cloud Foundry ou le déploiement Kubernetes/conteneur.

Lorsque vous êtes connecté à {{site.data.keyword.Bluemix_notm}}, vous pouvez choisir de connecter cette application locale à une application se trouvant déjà dans {{site.data.keyword.Bluemix_notm}} ou de créer une application {{site.data.keyword.Bluemix_notm}}. Pour tirer parti des fonctions {{site.data.keyword.Bluemix_notm}}, telles que des services et des chaînes d'outils DevOps, une application est requise dans {{site.data.keyword.Bluemix_notm}}. Lorsqu'une application {{site.data.keyword.Bluemix_notm}} est créée pour une application clonée à partir d'un référentiel Git, l'application {{site.data.keyword.Bluemix_notm}} inclut ce référentiel dans sa configuration. 

`Enable` est une fonction bêta. Si des problèmes surviennent lors de l'activation de votre application, consultez notre [page de traitement des incidents](/docs/cli/ts_createapps.html#troubleshoot). La fonction `enable` n'est pas conçue pour les infrastructures ou les applications mobiles. Pour les applications complexes qui génèrent plusieurs actifs déployables, chaque composant de l'application doit être activé individuellement. 

Exécutez la commande suivante pour activer une application existante dans le répertoire de travail :

```
ibmcloud dev enable
```
{: codeblock}

La présence des fichiers nécessaires permet de détecter un langage d'application pour une structure de projet valide.  

* La présence d'un fichier `package.json` identifie une application Node.js.
* La présence d'un fichier `package.swift` identifie une application Swift.
* La présence d'un fichier `setup.py` ou `requirements.txt` identifie une application Python.
* La présence d'un fichier `pom.xml` ou `build.gradle` identifie une application Java.
	* La présence d'un fichier `pom.xml` identifie une application Maven.
	* La présence d'un fichier `build.gradle` identifie une application Gradle.

Vous pouvez éventuellement substituer le langage d'application détecté à l'aide de l'argument `--language`.  Cependant, seules les applications valides et terminées sont prises en charge. La commande enable ne modifie pas votre code source.

{: #enable-language-options}

Les options de langue sont notamment les suivantes :
* node
* swift
* python
* java-ee (interprété comme Java - Java EE)
* java-mp (interprété comme Java - Java MicroProfile)
* java-spring (interprété comme Java - Spring Framework)

Les fichiers créés à l'aide de la commande `ibmcloud dev enable` et dont les noms entrent en conflit avec des noms de fichiers existants dans le dossier d'application sont sauvegardés avec une extension de fichier `.merge`.  

### Paramètres de la commande enable
{: #enable-parameters}

Les paramètres ci-dessous peuvent être utilisés avec la commande `enable` ou en mettant directement à jour le fichier `cli-config.yml` de l'application. Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `language`
{: #enable-language}

* Paramètre utilisé pour indiquer le langage de l'application à activer.
* Syntaxe : `ibmcloud dev enable -l|--language [langage]`

#### `force`
{: #enable-force}

* Paramètre utilisé pour forcer la réactivation d'une application déjà activée.
* Syntaxe : `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* Paramètre permettant d'éviter de créer une application dans {{site.data.keyword.Bluemix_notm}} lors de la création locale des fichiers d'activation.
* Utilisation de la commande `ibmcloud dev enable --no-create`


## Commande get-credentials
{: #get-credentials}

Permet d'obtenir les données d'identification requises par l'application pour activer l'utilisation de services connectés.


## Commande help
{: #help}

Par défaut, si aucune action ou aucun argument n'est transmis, ou si
l'action help
est fournie, cette commande affiche un texte d'aide général. L'aide générale affichée
inclut une description des arguments de base ainsi que la liste des actions disponibles.  

Exécutez la commande suivante pour afficher des informations d'aide générales :

```
ibmcloud dev help
```
{: codeblock}


## Commande list
{: #list}

Vous pouvez répertorier toutes les applications {{site.data.keyword.Bluemix_notm}} d'un groupe de ressources.

Exécutez la commande suivante pour répertorier vos applications :

```
ibmcloud dev list
```
{: codeblock}


## Commande run
{: #run}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez exécuter votre application avec la commande `run`. Une génération doit d'abord être effectuée pour l'application à l'aide de la commande `build`. Lorsque vous appelez la commande `run`, le conteneur run est démarré et expose les ports tels qu'ils sont définis par le paramètre `container-port-map`. Le paramètre `run-cmd` peut être utilisé pour appeler l'application si le conteneur run Dockerfile ne contient pas de point d'entrée pour effectuer cette étape.

Pour une exécution avec plusieurs conteneurs, votre application doit contenir un fichier [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe"), spécifié dans le fichier `cli-config.yml` ou vous pouvez utiliser le paramètre de commande `dockerfile-run` pour en indiquer un. Pour plus d'informations, voir [Fichier Compose](/docs/apps/projects/compose_file.html).

Compilez tout d'abord votre application :

```
ibmcloud dev build
```
{: codeblock}

Exécutez la commande suivante dans votre répertoire d'application en cours pour démarrer votre application :

```
ibmcloud dev run
```
{: codeblock}

Pour quitter la session, utilisez `CTRL-C`.


### Paramètres de la commande run
{: #run-parameters}

Les paramètres ci-dessous, qui sont réservés à la commande
`run`, facilitent la gestion de votre application dans le conteneur run.
Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `container-name-run`
{: #container-name-run2}

* Nom de conteneur pour le conteneur run.
* Syntaxe : `ibmcloud dev run --container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* Emplacement dans le conteneur à partager à l'exécution.
* Syntaxe : `ibmcloud dev run --container-path-run [/chemin_application]`

#### `host-path-run`
{: #host-path-run}

* Emplacement de partage du conteneur sur le système hôte lors de
l'exécution.
* Syntaxe : `ibmcloud dev run --host-path-run [/chemin_binaire_application]`

#### `dockerfile-run`
{: #dockerfile-run}

* Fichier Dockerfile pour le conteneur run.
* Si vous prévoyez d'exécuter avec plusieurs conteneurs, il doit s'agir d'un fichier Compose.
* Pour utiliser plusieurs fichiers Compose, placez entre guillemets une liste de noms de fichier délimitée par des virgules.
* Syntaxe : `ibmcloud dev run --dockerfile-run [/chemin_Dockerfile]`
* Syntaxe : `ibmcloud dev run --dockerfile-run "/chemin_fichier_compose, chemin_autre_fichier_compose, ..."`

#### `image-name-run`
{: #image-name-run}

* Image à créer depuis `dockerfile-run`.
* Syntaxe ; : `ibmcloud dev run --image-name-run [/chemin_nom_image]`

#### `run-cmd`
{: #run-cmd}

* Paramètre utilisé pour exécuter le code dans le conteneur run. Utilisez ce
paramètre si votre image démarre votre application.
* Syntaxe : `ibmcloud dev run --run-cmd [/commande à exécuter]`


## Commande shell
{: #shell}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez ouvrir l'interpréteur de commandes au sein du conteneur run ou tools à l'aide de la commande `shell`.

Pour cela, il vous suffit d'exécuter la commande suivante :

```
ibmcloud dev shell
```

L'interface de ligne de commande {{site.data.keyword.dev_cli_short}} ouvrira un interpréteur de commandes interactif dans le conteneur Docker de l'application. Le conteneur cible par défaut pour la commande shell est défini par la valeur `container-shell-target` dans le fichier `cli-config.yml`, où les valeurs valides sont `run` ou `tools`. Si cette valeur n'est pas définie ou n'est pas valide, par défaut, la commande `shell` prend pour cible le conteneur `tools`. La commande shell ouvre le conteneur dans le répertoire spécifié par l'instruction `WORKDIR` dans le fichier Dockerfile correspondant. Si `WORKDIR` n'est pas indiqué dans le fichier Dockerfile, la racine de conteneur est utilisée comme répertoire de travail. Pour plus d'informations, voir [cette référence](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").

Sinon, vous pouvez choisir de transmettre `run` ou `tools` en tant qu'argument à la commande pour que le conteneur soit installé et l'interpréteur de commandes ouvert pour ce conteneur. De même, vous pouvez utiliser le paramètre `container-name` pour transmettre le nom du conteneur dans lequel vous souhaitez exécuter le shell. Cependant, cette option doit être réservée pour les situations où aucun conteneur n'est actif. Les arguments `run` et `tools` sont plus souples et vous permettent de passer d'un conteneur à l'autre lorsque l'un d'entre eux est actif. Par exemple, si le conteneur tools est actif et que vous exécutez la commande `ibmcloud dev shell run`, le conteneur `tools` s'arrêtera et le conteneur `run` démarrera, et inversement.

Si le conteneur `run` ou `tools` cible n'est pas déjà actif lorsque vous exécutez la commande `shell`, le conteneur cible sera démarré. Toutefois, la valeur par défaut `Cmd` ou `Entrypoint` dans le fichier Dockerfile sera remplacée pour lancer le conteneur directement dans l'interpréteur de commandes au lieu de démarrer le processus serveur. Cela vous permet de démarrer le conteneur `run` ou `tools` et de démarrer manuellement le serveur avec vos propres commandes arbitraires ou personnalisées.


Vous pouvez également spécifier l'exécutable de shell que vous souhaitez ouvrir à l'aide du paramètre `container-shell`. Par défaut, `/bin/sh` est utilisé. Si vous préférez utiliser l'interpréteur de commandes bash, affectez au paramètre `container-shell` la valeur`/bin/bash` ; cependant, gardez à l'esprit que l'interpréteur de commandes bash n'est pas automatiquement disponible dans toutes les variantes Linux.

Les arguments supplémentaires que vous transmettez à la commande en plus des options seront analysés en tant que commande à exécuter lors de l'ouverture de l'interpréteur de commandes. Si vous indiquez une commande à exécuter, l'interpréteur de commandes dans le conteneur prendra fin à l'issue de l'exécution de la commande et reviendra à votre terminal.

Par exemple, vous pouvez exécuter la commande Linux `ls` depuis l'interpréteur de commandes du conteneur tools en appelant `ibmcloud dev shell tools ls`.   Vous pouvez également spécifier des options supplémentaires qui seront transmises lors de l'exécution de la commande shell en encapsulant les arguments entre guillemets, par exemple, `ibmcloud dev shell "ls -la"`.

### Paramètres de la commande shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nom du conteneur dans lequel vous souhaitez exécuter le shell.
* Syntaxe : `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Indique l'interpréteur de commandes à exécuter au sein du conteneur (la valeur par défaut est /bin/sh)
* Syntaxe : `ibmcloud dev shell --container-shell [chemin_shell]`


## Commande status
{: #status}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez effectuer une requête relative au statut des conteneurs qui sont utilisés par l'interface de ligne de commande {{site.data.keyword.dev_cli_short}}, comme défini par `container-name-run` et `container-name-tools`.

Exécutez la commande suivante dans votre répertoire d'application en cours pour vérifier le statut du conteneur :

```
ibmcloud dev status
```
{: codeblock}


[Paramètres de la commande status](#command-parameters)


## Commande stop
{: #stop}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez arrêter vos conteneurs avec la commande `stop`.

Pour arrêter les conteneurs tools et run, tels que définis dans votre
fichier `cli-config.yml`, exécutez :

```
ibmcloud dev stop
```
{: codeblock}

Pour arrêter un conteneur qui n'est pas défini dans le fichier
`cli-config.yml`, vous pouvez spécifier un paramètre de ligne de
commande supplémentaire à la place du nom de conteneur.  Si
aucun conteneur n'est spécifié dans le fichier `cli-config.yml` ou
sur la ligne de commande, la commande stop s'arrête.

### Paramètres de la commande stop
{: #stop-parameters}

Les paramètres ci-après sont utilisés pour la commande `stop`. Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `container-name-run`
{: #container-name-run}

* Nom de conteneur pour le conteneur run.
* Syntaxe : `ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* Nom de conteneur pour le conteneur tools.
* Syntaxe : `ibmcloud dev stop --container-name-tools [<applicationName>]`



## Commande test
{: #test}

Si vous utilisez Windows, vous devez exécuter Windows 10 Pro ou une version ultérieure.

Vous pouvez tester votre application avec la commande `test`. Une génération doit d'abord être effectuée pour l'application à l'aide de la commande `build --debug`. Le conteneur tools est ensuite utilisé afin d'appeler `test-cmd` pour l'application.

Compilez tout d'abord votre application :

```
ibmcloud dev build --debug
```
{: codeblock}

Exécutez la commande suivante pour tester votre application :

```
ibmcloud dev test
```
{: codeblock}


### Paramètres de la commande test
{: #test-parameters}

Le paramètre ci-après est réservé à la commande `test`.  Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `test-cmd`
{: #test-cmd}

* Paramètre utilisé afin de spécifier une commande pour tester le code dans
le conteneur tools.
* Syntaxe : `ibmcloud dev test --test-cmd commande_de_test`


## Commande view
{: #view}

Vous pouvez afficher l'URL sur laquelle votre application est déployée en utilisant la commande `view`. Exécutez cette commande dans le répertoire principal de l'application que vous souhaitez afficher. La commande `view` permet également d'ouvrir l'URL dans votre navigateur par défaut.

Pour les applications déployées sur Cloud Foundry, l'URL est composée du nom d'hôte et du domaine de l'application.

Pour les applications déployées sur Kubernetes, l'URL est composée de l'adresse IP du noeud sur lequel elle est déployée et du port public. Si la commande détermine que l'application a été déployée dans Kubernetes, l'outil d'interface de ligne de commande demandera une confirmation. Si vous spécifiez que l'application n'a pas été réellement déployée sur kubernetes, L'URL Cloud Foundry s'affichera. Si contrairement à ce que vous attendiez, la commande n'affiche pas l'URL d'une application déployée sur Kubernetes, assurez-vous que le fichier `cli-config.yml` contient une entrée pour `chart-path` ou indiquez-la via la ligne de commande, comme illustré [ici](#chart-path).

Exécutez la commande suivante pour afficher votre application :

```
ibmcloud dev view
```
{: codeblock}

### Paramètres de la commande view
{: #view-parameters}

Les paramètres ci-après sont réservés à la commande `view`.

#### `deploy-target`

* Paramètre facultatif permettant d'indiquer le type de déploiement à effectuer pour ignorer l'invite
* Syntaxe : `ibmcloud dev view -t|--target pack de construction|conteneur`


#### `no-open`
{: #no-open}

* Paramètre utilisé pour spécifier que le navigateur ne doit pas être ouvert.
* Syntaxe : `ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Racine du projet à ajouter à l'URL de l'application Kubernetes et Cloud Foundry
* Syntaxe : `ibmcloud dev view --web-app-root [racine]`


#### `ibm-cluster`
{: #ibm-cluster2}

* Paramètre facultatif permettant de définir le nom du cluster kubernetes lors du ciblage d'un déploiement de conteneur
* Syntaxe : `ibmcloud dev view --ibm-cluster [nom_cluster]`


## Commandes composées
{: #compound}

Vous pouvez exécuter plusieurs commandes dans une seule et même instruction de ligne de commande en séparant les commandes {{site.data.keyword.Bluemix_notm}} Developer Tools par le délimiteur `/`. Des options de ligne de commande supplémentaires peuvent être spécifiées après les commandes composées.  Les exemples de commande suivants illustrent la façon dont vous pouvez utiliser des commandes composées :

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Toutes les options doivent suivre la commande finale et seront appliquées à toutes les commandes auxquelles cette option est associée. Dans l'exemple final ci-dessus, l'option `--trace` s'applique aux trois commandes, mais l'option `-t` s'applique uniquement aux deux commandes finales. Par conséquent, elle ne s'appliquera pas à la commande `build`.

Voici les commandes qui peuvent être utilisées avec cette fonction :
`build, debug, deploy, get-credentials, run, stop, test, view`

Si l'une des commandes échoue pour une raison quelconque, aucune autre commande ne sera exécutée.

Si des commandes sont spécifiées après la commande `debug` ou`run`, l'exécution ne se poursuivra que si la commande `debug` ou `run` est terminée par un autre moyen que l'arrêt du processus à partir de la fenêtre de terminal en cours. La combinaison de touches `CTRL+C` permet d'arrêter le processus et de ne pas exécuter les commandes suivantes. Par exemple, vous pouvez exécuter `ibmcloud dev stop` à partir d'une autre fenêtre de terminal afin d'arrêter le conteneur actif et de poursuivre l'exécution avec la commande suivante.


## Paramètres des commandes build, debug, run et test
{: #command-parameters}

Les paramètres ci-dessous peuvent être utilisés avec les commandes `build|debug|run|test` ou en mettant directement à jour le fichier `cli-config.yml` de l'application. Des paramètres supplémentaires sont disponibles pour les commandes
[`debug`](#debug-parameters) et
[`run`](#run-parameters).

Les paramètres de commande qui sont entrés sur la ligne de commande sont prioritaires par rapport à ceux du fichier de configuration `cli-config.yml`.
{: note}

#### `config-file`  
{: #config-file}

* Spécifiez un fichier cli-config.yml à utiliser pour une commande.
* Syntaxe : `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nom de conteneur pour le conteneur run.
* Syntaxe : `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Nom de conteneur pour le conteneur tools.
* Syntaxe : `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* Emplacement de partage sur l'hôte pour les commandes build, debug, test.
* Syntaxe : `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Emplacement de partage dans le conteneur pour les commandes build, debug, test.
* Syntaxe : `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Mappages de port pour le conteneur. La première valeur est le port à
utiliser sur le système d'exploitation hôte et la seconde le port dans le conteneur
[host-port:container-port].
* Syntaxe : `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Fichier Dockerfile pour le conteneur tools.
* Syntaxe : `ibmcloud dev <build|debug|run|test> --dockerfile-tools [chemin_dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Image à créer depuis `dockerfile-tools`.
* Syntaxe : `ibmcloud dev <build|debug|run|test> --image-name-tools [chemin_nom_image]`

#### `container-mounts-run`
{: #container-mounts-run}

* Utilisez cette option pour définir des montages entre le système hôte et le conteneur run.
* Les valeurs `host-path-run` et `container-path-run` sont insérées au début de cette liste.
* En tant que meilleure pratique et pour éviter d'obtenir des résultats inattendus, vous devez créer et exécuter les mêmes paramètres de montage.
* Syntaxe : `ibmcloud dev <build|run|test> --container-mounts-run [/chemin_relatif_répertoire_hôte:/chemin_absolu_répertoire_conteneur, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilisez cette option pour définir des montages entre le système hôte et le conteneur tools.
* Les valeurs `host-path-tools` et `container-path-tools` sont insérées au début de cette liste.* En tant que meilleure pratique et pour éviter d'obtenir des résultats inattendus, vous devez créer et déboguer les mêmes paramètres de montage.
* Syntaxe : `ibmcloud dev <build|debug|test> --container-mounts-tools [chemin_relatif_répertoire_hôte:/chemin_absolu_répertoire_conteneur, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Paramètre utilisé afin de spécifier une commande pour générer le code
pour toutes les utilisations sauf DEBUG.
* Syntaxe : `ibmcloud dev <build|debug|run|test> --build-cmd-run [commande_de_génération]`

#### `trace`
{: #trace}

* Utilisez ce paramètre pour générer une sortie prolixe.
* Syntaxe : `ibmcloud dev <build|debug|run|test> --trace`
