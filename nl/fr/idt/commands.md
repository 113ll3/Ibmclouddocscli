---

copyright:

   years: 2017, 2018
   
lastupdated: "2018-05-02"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Commandes CLI {{site.data.keyword.dev_cli_notm}} (bx dev)
{: #idt-cli}

Version : 1.2.0
Publication : 8 mars 2018

Utilisez les commandes CLI {{site.data.keyword.dev_cli_notm}} (bx dev) suivantes pour créer un projet, le déployer, le déboguer et le tester :

- La commande [build](#build) vous permet de créer le projet dans un conteneur local.
- La commande [code](#code) vous permet de télécharger le code à partir d'un projet.
- La commande [console](#console) vous permet d'ouvrir la console IBM Cloud pour un projet.
- La commande [create](#create) vous permet de créer un nouveau projet et vous offre la possibilité d'ajouter des services.
- La commande [debug](#debug) vous permet de déboguer votre application dans un conteneur local.
- La commande [delete](#delete) vous permet de supprimer un projet de votre espace.
- La commande [deploy](#deploy) vous permet de déployer une application sur IBM Cloud.
- La commande [enable](#enable) vous permet d'ajouter des fichiers IBM Cloud à un projet existant.
- La commande [get-credentials](#get-credentials) vous permet d'obtenir les données d'identification requises par le projet pour activer l'utilisation de services liés.
- La commande [help](#help) vous permet d'obtenir de l'aide sur la syntaxe et les arguments IDT.
- La commande [list](#list) vous permet de répertorier tous les projets IBM Cloud dans un espace.
- La commande [run](#run) vous permet d'exécuter votre application dans un conteneur local.
- La commande [shell](#shell) vous permet d'ouvrir un interpréteur de commandes dans un conteneur local.
- La commande [status](#status) vous permet de vérifier le statut des conteneurs utilisés par l'interface de ligne de commande.
- La commande [stop](#stop) vous permet d'arrêter un conteneur.
- La commande [test](#test) vous permet de tester votre application dans un conteneur local.
- La commande [view](#view) vous permet d'afficher l'URL déployée pour les applications à des fins de test et de visualisation.
- Les [commandes composées](#compound) vous permettent d'exécuter plusieurs commandes dans une instruction de ligne de commande.



## Commande build
{: #build}

Vous pouvez générer votre application en utilisant la commande `build`. Les commandes `test`, `debug` et `run` s'attendent à trouver un projet compilé, par conséquent, vous devez préalablement exécuter une opération `build`.  

L'élément de configuration `build-cmd-debug` est utilisé afin de générer l'application pour toutes les utilisations, à l'exception de`run`. Vous générez votre application à des fins d débogage en spécifiant l'option de ligne de commande `--debug`.  L'élément de configuration `build-cmd-run` est utilisé lors de la génération de l'application afin de l'utiliser avec la commande `run`.

Pour une génération avec plusieurs conteneurs, votre projet doit contenir un fichier [Compose](https://docs.docker.com/compose/overview/), spécifié dans le fichier `cli-config.yml`, ou vous pouvez utiliser le paramètre de commande `dockerfile-tools` pour en indiquer un. Pour plus d'informations, voir[Fichier Compose ](/docs/apps/projects/compose_file.html).

Exécutez la commande suivante dans votre répertoire de projet en cours pour
générer votre application :  

```
bx dev build [--debug]
```
{: codeblock}


[Paramètres de la commande build](#command-parameters)


## Commande code
{: #code}

Utilisez la commande `code` pour télécharger un projet précédemment créé avec le code de modèle d'application et les fichiers de configuration de {{site.data.keyword.Bluemix_notm}}.  Cela est utile lorsque vous devez extraire une seconde copie d'un projet que vous avez créé.

Exécutez la commande suivante pour télécharger le code à partir du projet spécifié :

```
bx dev code <projectName>
```
{: codeblock}


## Commande console
{: #console}

Utilisez la commande `console` pour ouvrir un navigateur Web sur la console Web de votre application sur IBM Cloud.  Vous pouvez exécuter la commande `bx dev console` depuis l'intérieur du dossier de votre projet. Dans ce cas, l'interface de ligne de commande tente de trouver un projet correspondant sur IBM Cloud portant le même ID de projet que le répertoire en cours. Si le système ne parvient pas à trouver un nom correspondant, il ouvre le tableau de bord Web et mobile sur IBM Cloud au lieu du projet spécifique.

Vous pouvez indiquer un nom de projet ; l'interface de ligne de commande ignore la mise en correspondance basée sur le nom de dossier/d'application. Dans ce cas, l'interface de ligne de commande ouvre la console du projet nommé dans un navigateur Web.  

Exécutez la commande suivante pour ouvrir un navigateur Web sur la console Web de votre application :

```
bx dev console [projectName]
```
{: codeblock}


## Commande create
{: #create}

Créez un projet en invitant à spécifier toutes les informations, y compris, le type de ressource, la langue, le kit de démarrage et les options DevOps Toolchain. Le projet est
créé dans le répertoire de travail.

Pour créer un projet dans le répertoire en cours et pour y associer des services, exécutez la commande suivante :

```
bx dev create
```
{: codeblock}


## Commande debug
{: #debug}

Vous pouvez déboguer votre application avec la commande `debug`. Une
génération doit d'abord être effectuée pour le projet à l'aide de la commande build avec l'argument `--debug`. Le lancement de la commande `debug` entraîne le démarrage d'un conteneur qui fournit un ou plusieurs ports de débogage définis par la valeur `container-port-map-debug` dans le fichier cli-config.yml ou spécifiés sur la ligne de commande. Connectez votre outil de débogage favori au port ou aux ports et vous pourrez déboguer votre application en mode normal.

D'abord, compilez votre projet :

```
bx dev build --debug
```
{: codeblock}

Pour commencer, exécutez la commande suivante dans votre répertoire de projet en cours afin de déboguer votre application :

```
bx dev debug
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
* Syntaxe : `bx dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Paramètre utilisé afin de générer le code pour DEBUG.
* Syntaxe : `bx dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Paramètre utilisé pour spécifier une commande afin d'appeler la fonction
de débogage dans le conteneur tools. Utilisez-le si
`build-cmd-debug` démarre votre application en mode débogage.
* Syntaxe : `bx dev debug --debug-cmd /the/debug/command`



## Commande delete
{: #delete}

Utilisez la commande `delete` pour supprimer des projets de votre espace {{site.data.keyword.Bluemix}}. Vous pouvez exécuter la commande sans paramètres pour afficher la liste des projets disponibles et sélectionner le projet à supprimer dans la liste numérotée. Le
code du projet et les répertoires ne sont pas retirés de votre espace disque local.

Exécutez la commande suivante pour supprimer votre projet depuis {{site.data.keyword.Bluemix}} :

```
bx dev delete <projectName>
```
{: codeblock}


**Remarque : **les services {{site.data.keyword.Bluemix}} ne sont **pas** retirés.


## déployer
{: #deploy}

Vous pouvez déployer une application en tant qu'application Cloud Foundry ou en tant que conteneur.

Pour permettre un déploiement en tant qu'application Cloud Foundry sur {{site.data.keyword.Bluemix}}, un fichier `manifest.yml` doit être présent dans le répertoire racine de votre projet.

Pour déployer une application en tant que conteneur, vous devez installer localement [Kubernetes](https://kubernetes.io/) et [Helm](https://github.com/kubernetes/helm). Assurez-vous que la version du client Helm n'est pas plus récente que la version du serveur Helm. Pour connaître ces informations, exécutez la commande `helm version`. Il est recommandé d'utiliser la version 2.4.2 pour la version du client.

Dans le fichier `cli-config.yml`, vous pouvez choisir de définir l'emplacement d'un graphique Helm dans la propriété `chart-path`, d'affecter à l'élément `deploy-target` la valeur `container` et de configurer l'élément `deploy-image-target` comme illustré dans l'exemple. L'élément `deploy-image-target` dans le fichier `cli-config.yml` est utilisé à la place des éléments `repository` et `tag` dans le fichier `chart/values.yml`. Pour effectuer un déploiement spécifiquement sur {{site.data.keyword.Bluemix}}, affectez à l'élément de configuration `ibm-cluster` le nom du cluster Kubernetes que vous avez créé dans {{site.data.keyword.Bluemix}} comme indiqué dans le [Tutoriel : Création de clusters](/docs/containers/cs_tutorials.html#cs_cluster_tutorial).

Pour plus d'informations sur la mise à disposition, la configuration et le déploiement sur un cluster Kubernetes, voir le tutoriel [Déploiement d'une application Web évolutive sur Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes).

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

Si vous ne définissez pas ces informations dans le fichier cli-config.yml, vous devez effectuer le déploiement avec le paramètre `-t container` afin d'être invité à spécifier toutes les autres valeurs.

Exécutez la commande suivante dans votre répertoire de projet en cours pour
générer votre application :  

```
bx dev build
```
{: codeblock}

Exécutez la commande suivante dans votre répertoire de projet en cours pour déployer votre projet :

```
bx dev deploy
```
{: codeblock}


### Paramètres de la commande deploy
{: #deploy-parameters}

Les paramètres ci-dessous peuvent être utilisés avec la commande `deploy` ou en mettant à jour directement le fichier `cli-config.yml` du projet. Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `chart-path`
{: #chart-path}

* Paramètre utilisé pour un déploiement de conteneur afin de spécifier l'emplacement du graphique Helm utilisé pour le déploiement.
* Syntaxe : `bx dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Paramètre facultatif permettant d'indiquer le type de déploiement à effectuer.  Le type de déploiement par défaut est buildpack.
* Syntaxe : `bx dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Paramètre utilisé avec un déploiement de conteneur comme nom d'image cible du déploiement (par exemple, pour baliser un registre Docker).  La valeur ne doit pas inclure de version, par exemple,: image-name:{version}, car la version est automatiquement incrémentée et ajoutée par `deploy`.
* Syntaxe : `bx dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Paramètre facultatif permettant de définir le nom du cluster kubernetes pour un déploiement de conteneur sur {{site.data.keyword.Bluemix}}.
* Syntaxe : `bx dev deploy --ibm-cluster [cluster-name]`


## Commande enable
{: #enable}

Activez un projet existant pour le déploiement {{site.data.keyword.Bluemix_notm}}. La commande `enable` tente de détecter automatiquement la langue d'un projet existant, puis invite à indiquer les informations supplémentaires nécessaires. Cette opération génère et ajoute des fichiers pouvant être utilisés pour des conteneurs Docker locaux, le déploiement CloudFoundry ou le déploiement Kubernetes/conteneur.

Exécutez la commande suivante pour activer un projet existant dans le répertoire en cours du déploiement {{site.data.keyword.Bluemix_notm}} :

```
bx dev enable
```
{: codeblock}

La présence des fichiers nécessaires permet de détecter une langue de projet pour une structure de projet valide.  

* La présence d'un fichier `package.json` identifie un projet Node.js.
* La présence d'un fichier `package.swift` identifie un projet Swift.
* La présence d'un fichier `setup.py` ou `requirements.txt` identifie un projet Python.
* La présence d'un fichier `pom.xml` ou `build.gradle` identifie un projet Java.
	* La présence d'un fichier `pom.xml` identifie un projet Maven.
	* La présence d'un fichier `build.gradle` identifie un projet Gradle.

Vous pouvez éventuellement substituer la langue de projet détectée à l'aide de l'argument `--language`.  Cependant, seuls les projets valides et terminés sont pris en charge. La commande enable ne modifie pas votre code source.

Les options de langue sont notamment les suivantes :
* node
* swift
* python
* java-ee (interprété comme Java - Java EE)
* java-mp (interprété comme Java - Java MicroProfile)
* java-spring (interprété comme Java - Spring Framework)

Les fichiers créés à l'aide de la commande `bx dev enable` dont les noms sont en conflit avec les noms de fichiers existants dans le dossier de projet sont sauvegardés avec une extension de fichier `.merge`.  

### Paramètres de la commande enable
{: #enable-parameters}

Les paramètres ci-dessous peuvent être utilisés avec la commande `enable` ou en mettant à jour directement le fichier `cli-config.yml` du projet. Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `language`
{: #enable-language}

* Paramètre utilisé pour indiquer la langue du projet à activer.
* Syntaxe : `bx dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Paramètre utilisé pour forcer la réactivation d'un projet déjà activé.
* Syntaxe : `bx dev enable -f|--force`


## Commande get-credentials
{: #get-credentials}

Permet d'obtenir les données d'identification requises par le projet pour activer l'utilisation de services liés.


## Commande help
{: #help}

Par défaut, si aucune action ou aucun argument n'est transmis, ou si
l'action help
est fournie, cette commande affiche un texte d'aide général. L'aide générale affichée
inclut une description des arguments de base ainsi que la liste des actions disponibles.  

Exécutez la commande suivante pour afficher des informations d'aide générales :

```
bx dev help
```
{: codeblock}


## Commande list
{: #list}

Vous pouvez répertorier tous les projets {{site.data.keyword.Bluemix_notm}} d'un espace.

Exécutez la commande suivante pour répertorier vos projets :

```
bx dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
bx dev edit
```
{: codeblock}
-->


## Commande run
{: #run}

Vous pouvez exécuter votre application avec la commande `run`. Une
génération doit d'abord être effectuée pour le projet à l'aide de la commande
`build`. Lorsque vous appelez la commande `run`, le conteneur run est
démarré et expose les ports tels que définis par le paramètre
`container-port-map`. Le paramètre `run-cmd` peut être
utilisé pour appeler l'application si le conteneur run Dockerfile ne contient pas de
point d'entrée pour effectuer cette étape.

Pour une exécution avec plusieurs conteneurs, votre projet doit contenir un fichier [Compose](https://docs.docker.com/compose/overview/), spécifié dans le fichier `cli-config.yml`, ou vous pouvez utiliser le paramètre de commande `dockerfile-run` pour en indiquer un. Pour plus d'informations, voir[Fichier Compose ](/docs/apps/projects/compose_file.html).

D'abord, compilez votre projet :

```
bx dev build
```
{: codeblock}

Exécutez la commande suivante dans votre répertoire de projet en cours pour
démarrer votre application :

```
bx dev run
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
* Syntaxe : `bx dev run --container-name-run [<projectName>]`

#### `container-path-run`
{: #container-path-run}

* Emplacement dans le conteneur à partager à l'exécution.
* Syntaxe : `bx dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Emplacement de partage du conteneur sur le système hôte lors de
l'exécution.
* Syntaxe : `bx dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Fichier Dockerfile pour le conteneur run.
* Si vous prévoyez d'exécuter avec plusieurs conteneurs, il doit s'agir d'un fichier Compose.
* Pour utiliser plusieurs fichiers Compose, placez entre guillemets une liste de fichiers délimitée par des virgules.
* Syntaxe : `bx dev run --dockerfile-run [/path/to/Dockerfile]`
* Syntaxe : `bx dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Image à créer depuis `dockerfile-run`.
* Syntaxe : `bx dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Paramètre utilisé pour exécuter le code dans le conteneur run. Utilisez ce
paramètre si votre image démarre votre application.
* Syntaxe : `bx dev run --run-cmd [/the/run/command]`


## Commande shell
{: #shell}

Vous pouvez ouvrir l'interpréteur de commandes au sein du conteneur run ou tools à l'aide de la commande `shell`.

Pour cela, il vous suffit d'exécuter la commande suivante :

```
bx dev shell
```

L'interface de ligne de commande {{site.data.keyword.dev_cli_short}} ouvrira un interpréteur de commandes interactif dans le conteneur Docker de l'application. Le conteneur cible par défaut pour la commande shell est défini par la valeur `container-shell-target` dans le fichier `cli-config.yml`, où les valeurs valides sont `run` ou `tools`. Si cette valeur n'est pas définie ou n'est pas valide, par défaut, la commande `shell` prend pour cible le conteneur `tools`. La commande shell ouvre le conteneur dans le répertoire spécifié par l'instruction `WORKDIR` dans le fichier Dockerfile correspondant. Si `WORKDIR` n'est pas indiqué dans le fichier Dockerfile, la racine de conteneur est utilisée comme répertoire de travail. Pour plus d'informations, voir[ce document de référence](https://docs.docker.com/engine/reference/builder/#workdir).

Sinon, vous pouvez choisir de transmettre `run` ou `tools` en tant qu'argument à la commande pour que le conteneur soit installé et l'interpréteur de commandes ouvert pour ce conteneur. De même, vous pouvez utiliser le paramètre `container-name` pour transmettre le nom du conteneur dans lequel vous souhaitez exécuter l'interpréteur de commandes. Cependant, cette option doit être réservée pour les situations où aucun conteneur n'est actif. Les arguments `run` et `tools` sont plus souples et vous permettent de passer d'un conteneur à l'autre lorsque l'un d'entre eux est actif. Par exemple, si le conteneur tools est actif et que vous exécutez la commande `bx dev shell run`, le conteneur `tools` s'arrêtera et le conteneur `run` démarrera, et inversement.

Si le conteneur `run` ou `tools` cible n'est pas déjà actif lorsque vous exécutez la commande `shell`, le conteneur cible sera démarré. Toutefois, la valeur par défaut `Cmd` ou `Entrypoint` dans le fichier Dockerfile sera remplacée pour lancer le conteneur directement dans l'interpréteur de commandes au lieu de démarrer le processus serveur. Cela vous permet de démarrer le conteneur `run` ou `tools` et de démarrer manuellement le serveur avec vos propres commandes arbitraires ou personnalisées.


Vous pouvez également spécifier l'exécutable d'interpréteur de commandes que vous souhaitez ouvrir à l'aide du paramètre `container-shell`. Par défaut, `/bin/sh` est utilisé. Si vous préférez utiliser l'interpréteur de commandes bash, affectez au paramètre `container-shell` la valeur`/bin/bash` ; cependant, gardez à l'esprit que l'interpréteur de commandes bash n'est pas automatiquement disponible dans toutes les variantes Linux.

Les arguments supplémentaires que vous transmettez à la commande en plus des options seront analysés en tant que commande à exécuter lors de l'ouverture de l'interpréteur de commandes. Si vous indiquez une commande à exécuter, l'interpréteur de commandes dans le conteneur prendra fin à l'issue de l'exécution de la commande et reviendra à votre terminal.

Par exemple, vous pouvez exécuter la commande Linux `ls` au sein de l'interpréteur de commandes du conteneur tools en appelant `bx dev shell tools ls`.   Vous pouvez également spécifier des options supplémentaires qui seront transmises lors de l'exécution de la commande shell en encapsulant les arguments entre guillemets, par exemple, `bx dev shell "ls -la"`.

### Paramètres de la commande shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nom du conteneur dans lequel vous souhaitez exécuter l'interpréteur de commandes.
* Syntaxe : `bx dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Indique l'interpréteur de commandes à exécuter au sein du conteneur (la valeur par défaut est /bin/sh)
* Syntaxe : `bx dev shell --container-shell [path/to/shell]`


## Commande status
{: #status}

Vous pouvez effectuer une requête relative au statut des conteneurs qui sont utilisés par l'interface de ligne de commande {{site.data.keyword.dev_cli_short}}, comme défini par `container-name-run` et `container-name-tools`.

Exécutez la commande suivante dans votre répertoire de projet actuel pour vérifier le statut du conteneur :

```
bx dev status
```
{: codeblock}


[Paramètres de la commande status](#command-parameters)


## Commande stop
{: #stop}

Vous pouvez arrêter vos conteneurs avec la commande `stop`.

Pour arrêter les conteneurs tools et run, tels que définis dans votre
fichier `cli-config.yml`, exécutez :

```
bx dev stop
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
* Syntaxe : `bx dev stop --container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* Nom de conteneur pour le conteneur tools.
* Syntaxe : `bx dev stop --container-name-tools [<projectName>]`



## Commande test
{: #test}

Vous pouvez tester votre application avec la commande `test`. Une
génération doit d'abord être effectuée pour le projet à l'aide de la commande `build --debug`. Le conteneur tools est ensuite utilisé afin d'appeler `test-cmd` pour l'application.

D'abord, compilez votre projet :

```
bx dev build --debug
```
{: codeblock}

Exécutez la commande suivante pour tester votre application :

```
bx dev test
```
{: codeblock}


### Paramètres de la commande test
{: #test-parameters}

Le paramètre ci-après est réservé à la commande `test`.  Des [paramètres supplémentaires](#command-parameters) sont partagés avec d'autres commandes.

#### `test-cmd`
{: #test-cmd}

* Paramètre utilisé afin de spécifier une commande pour tester le code dans
le conteneur tools.
* Syntaxe : `bx dev test --test-cmd /the/test/command`


## Commande view
{: #view}

Vous pouvez afficher l'URL sur laquelle votre application est déployée en utilisant la commande `view`. Exécutez cette commande dans le répertoire principal de l'application que vous souhaitez afficher. La commande `view` permet également d'ouvrir l'URL dans votre navigateur par défaut.

Pour les applications déployées sur Cloud Foundry, l'URL est composée du nom d'hôte et du domaine de l'application.

Pour les applications déployées sur Kubernetes, l'URL est composée de l'adresse IP du noeud sur lequel elle est déployée et du port public. Si la commande détermine que l'application a été déployée sur Kubernetes, l'outil d'interface de ligne de commande demandera une confirmation. Si vous spécifiez que l'application n'a pas été réellement déployée sur kubernetes, L'URL Cloud Foundry s'affichera. Si contrairement à ce que vous attendiez, la commande n'affiche pas l'URL d'une application déployée sur Kubernetes, assurez-vous que le fichier `cli-config.yml` contient une entrée pour `chart-path` ou indiquez-la via la ligne de commande, comme illustré [ici](#chart-path).

Exécutez la commande suivante pour afficher votre application :

```
bx dev view
```
{: codeblock}

### Paramètres de la commande view
{: #view-parameters}

Les paramètres ci-après sont réservés à la commande `view`.

#### `deploy-target`

* Paramètre facultatif permettant d'indiquer le type de déploiement à effectuer pour ignorer l'invite
* Syntaxe : `bx dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* Paramètre utilisé pour spécifier que le navigateur ne doit pas être ouvert.
* Syntaxe : `bx dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Racine du projet à ajouter à l'URL de l'application Kubernetes
* Syntaxe : `bx dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster2}

* Paramètre facultatif permettant de définir le nom du cluster kubernetes lors du ciblage d'un déploiement de conteneur
* Syntaxe : `bx dev view --ibm-cluster [cluster-name]`


## Commandes composées
{: #compound}

Vous pouvez exécuter plusieurs commandes dans une seule et même instruction de ligne de commande en séparant les commandes IDT par le délimiteur `/`. Des options de ligne de commande supplémentaires peuvent être spécifiées après les commandes composées.  Les exemples de commande suivants illustrent la façon dont vous pouvez utiliser des commandes composées :

```
bx dev build/run
bx dev build/deploy --trace -t buildpack
bx dev build/debug --debug --trace
bx dev build/deploy/view -t container --trace
```
{: codeblock}

Toutes les options doivent suivre la commande finale et seront appliquées à toutes les commandes auxquelles cette option est associée. Dans l'exemple ci-dessus, l'option`--trace` s'applique aux 3 commandes, mais l'option `-t` s'applique uniquement aux 2 commandes finales. Par conséquent, elle ne s'appliquera pas à la commande `build`.

Voici les commandes qui peuvent être utilisées avec cette fonction :
`build, debug, deploy, get-credentials, run, stop, test, view`

Si l'une des commandes échoue pour une raison quelconque, aucune autre commande ne sera exécutée. Si des commandes sont spécifiées après la commande `debug` ou`run`, l'exécution ne se poursuivra que si la commande `debug` ou `run` est terminée par un autre moyen que l'arrêt du processus à partir de la fenêtre de terminal en cours. La combinaison de touches `CTRL+C` permet d'arrêter le processus et de ne pas exécuter les commandes suivantes. Par exemple, vous pouvez exécuter `bx dev stop` à partir d'une autre fenêtre de terminal afin d'arrêter le conteneur actif et de poursuivre l'exécution avec la commande suivante.


## Paramètres des commandes build, debug, run et test
{: #command-parameters}

Les paramètres ci-dessous peuvent être utilisés avec les commandes
`build|debug|run|test` ou en mettant à jour directement le fichier `cli-config.yml` du projet. Des paramètres supplémentaires sont disponibles pour les commandes
[`debug`](#debug-parameters) et
[`run`](#run-parameters).

**Remarque** : les paramètres de commande qui sont entrés dans la ligne de commande sont prioritaires sur ceux du fichier de configuration `cli-config.yml`.

#### `config-file`  
{: #config-file}

* Spécifiez un fichier cli-config.yml à utiliser pour une commande.
* Syntaxe : `bx dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Nom de conteneur pour le conteneur run.
* Syntaxe : `bx dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Nom de conteneur pour le conteneur tools.
* Syntaxe : `bx dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

#### `host-path-tools`
{: #host-path-tools}

* Emplacement de partage sur l'hôte pour les commandes build, debug, test.
* Syntaxe : `bx dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Emplacement de partage dans le conteneur pour les commandes build, debug, test.
* Syntaxe : `bx dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Mappages de port pour le conteneur. La première valeur est le port à
utiliser sur le système d'exploitation hôte et la seconde le port dans le conteneur
[host-port:container-port].
* Syntaxe : `bx dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Fichier Dockerfile pour le conteneur tools.
* Syntaxe : `bx dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Image à créer depuis `dockerfile-tools`.
* Syntaxe : `bx dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Utilisez cette option pour définir des montages entre le système hôte et le conteneur run.
* Les valeurs `host-path-run` et `container-path-run` sont insérées au début de cette liste.
* En tant que meilleure pratique et pour éviter d'obtenir des résultats inattendus, vous devez créer et exécuter les mêmes paramètres de montage.
* Syntaxe : `bx dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilisez cette option pour définir des montages entre le système hôte et le conteneur tools.
* Les valeurs `host-path-tools` et `container-path-tools` sont insérées au début de cette liste.* En tant que meilleure pratique et pour éviter d'obtenir des résultats inattendus, vous devez créer et déboguer les mêmes paramètres de montage.
* Syntaxe : `bx dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Paramètre utilisé afin de spécifier une commande pour générer le code
pour toutes les utilisations sauf DEBUG.
* Syntaxe : `bx dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Utilisez ce paramètre pour générer une sortie prolixe.
* Syntaxe : `bx dev <build|debug|run|test> --trace`

