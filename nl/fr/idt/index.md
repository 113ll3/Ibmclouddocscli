---
copyright:

  years: 2018

lastupdated: "2018-07-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Développement et déploiement de vos applications
{: #developing}

Le développement d'applications natives en cloud à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}} est un processus relativement simple :

1. [Créer ou activer une application](#create)
2. [Coder, générer et exécuter](#build) votre application localement à l'aide de conteneurs
3. [Déployer](#deploy) votre application sur {{site.data.keyword.Bluemix_notm}}

## Créer ou activer une application
{: #create}

Il existe plusieurs façons de créer une application en cloud.
- Utiliser la [console Web App Services](https://console.bluemix.net/developer/appservice) pour créer des applications Web et des microservices génériques
- Utiliser le [tableau de bord Watson](https://console.bluemix.net/dashboard/watson) pour créer des applications de démarrage activées pour les fonctions basées sur Watson
    - D'autres tableaux de bord basés sur l'industrie et la technologie sont disponibles dans le menu "Hamburger" sur la page d'accueil de {{site.data.keyword.Bluemix_notm}}. Ils font tous appel à une approche similaire à celle qui consiste à utiliser des kits de démarrage pour créer de nouvelles applications.
- Interfaces de ligne de commande {{site.data.keyword.dev_cli_notm}} - [commande `ibmcloud dev create`](./commands.html#create) de création d'une nouvelle application.
- Interfaces de ligne de commande {{site.data.keyword.dev_cli_notm}} - [commande `ibmcloud dev enable`](./commands.html#enable) d'activation rapide du cloud sur une application existante côté serveur.

Le processus est similaire pour toutes les méthodes de création décrites précédemment. Vous pouvez choisir le type de projet, le langage d'implémentation et le modèle d'application à utiliser. Vous pouvez également choisir d'ajouter des services à valeur ajoutée à votre application, tels que l'authentification ou la persistance. Enfin, vous pouvez choisir d'activer la fonction DevOps pour l'application, qui fournit une chaîne d'outils complète de contrôle des sources et de communication des équipes, ainsi qu'un pipeline qui se déclenche à chaque validation afin de valider, générer et déployer votre application sur IBM Cloud.

![Exemple de processus de création à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}](create_flow.png "Exemple de processus de création à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}") <br> Figure 2. Exemple de processus de création à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}

L'interface de ligne de commande {{site.data.keyword.dev_cli_notm}} fonctionne en étroite collaboration pour fournir une expérience transparente lors du développement. Les projets créés dans n'importe laquelle des consoles Web présentent un bouton "Télécharger le code" permettant de télécharger le code source généré sur votre poste de travail afin d'effectuer davantage de développement.

### Commandes utiles offertes par l'interface de ligne de commande
{: #helpful}

Les commandes suivantes offertes par l'interface de ligne de commande vous aident à gérer votre projet et les consoles Web :
- La commande [`code`](./commands.html#code) vous permet d'extraire le code source généré d'une application directement sur votre poste de travail.
- La commande [`console`](./commands.html#console) vous permet d'ouvrir votre navigateur sur la page de projet de l'application en cours dans {{site.data.keyword.Bluemix_notm}}.
- La commande [`create`](./commands.html#create) vous permet de créer une nouvelle application.
- La commande [`delete`](./commands.html#delete) vous permet de supprimer l'application en cours de la zone de projet {{site.data.keyword.Bluemix_notm}}.
- La commande [`enable`](./commands.html#enable) vous permet d'activer pour le cloud une application côté serveur existante.
- La commande [`get-credentials`](./commands.html#get-credentials) vous permet d'obtenir les données d'identification requises par le projet pour activer l'utilisation de services liés.
- La commande [`list`](./commands.html#list) vous permet de répertorier toutes les applications que vous avez créées dans l'organisation/espace actuellement sélectionné, que ce soit depuis l'interface de ligne de commande ou les consoles.


### Exploration de la structure de projet d'une application
{: #exploring-project}

Les projets créés ou activés pour être utilisés avec l'outil sont fournis avec des paramètres préconfigurés encapsulés dans le fichier `cli-config.yml`. Le fichier `cli-config.yml` contient des entrées par défaut qui sont utilisées par les commandes de l'outil, qui peuvent être remplacées par des valeurs transmises via la ligne de commande.

D'autres détails concernant les structures de projet sont disponibles dans les rubriques suivantes :
- [Projets Java](/docs/apps/projects/java_project_contents.html)
- [Projets NodeJS](/docs/apps/projects/node_project_contents.html)
- [Projets Python](/docs/apps/projects/python_project_contents.html)
- [Projets Swift](/docs/apps/projects/swift_project_contents.html)


### Blogues et vidéos de référence
{: #ref1}

- Vidéo : [Installation d'{{site.data.keyword.Bluemix_notm}} Developer Tools sur Ubuntu Linux](https://www.youtube.com/watch?v=sr7KjHAKpEs)
- Blogue : [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)



## Coder, générer et exécuter
{: #build}


Une fois votre projet créé, il vous appartient d'en faire quelque chose d'utile. La procédure générale consiste à éditer le code source, puis à exécuter une commande [`ibmcloud dev build`](commands.html#build) pour compiler l'application dans un conteneur local spécifique au langage et à la configuration de votre application. Selon le langage et le générateur d'application utilisés, il existe un ou plusieurs conteneurs définis par défaut pour prendre en charge la génération et l'exécution en local.  En général, il existe un générateur "tools" dédié aux générations et au débogage en local. Ce conteneur comporte généralement des outils et des fonctions supplémentaires pour vous aider dans vos tâches de développement. Il existe également un conteneur "run" qui reproduit fidèlement l'environnement d'exécution réel de votre application une fois celle-ci déployée sur le cloud, que ce soit dans Cloud Foundry ou dans un environnement de conteneur basé sur le système Kubernetes d'IBM.


Vous êtes libre d'utiliser n'importe quelle interface IDE ou n'importe quel éditeur de votre choix pour coder votre application. Nous offrons une extension pour l'éditeur Microsoft VisualStudio Code (VSCode) qui vous permet d'accéder à toutes les commandes IDE directement depuis l'éditeur.

Une fois le projet créé, vous souhaiterez ensuite exécuter votre application à l'aide de la commande [`ibmcloud dev run`](commands.html#run) ou [`ibmcloud dev debug`](commands.html#debug), selon la configuration de votre générateur d'application. Cette commande exécutera l'application dans le conteneur approprié. Certains modèles d'application prennent en charge plusieurs conteneurs externes à vos applications, tels que la persistance ou d'autres fonctions, dont le démarrage et la configuration se feront automatiquement lors de l'exécution ou du débogage. Il existe également une commande [`ibmcloud dev test`](commands.html#test) exécutant n'importe quel scénario de test éventuellement associé à l'application.


### Utilisation des conteneurs locaux
{: #local-containers}

L'interface de ligne de commande {{site.data.keyword.dev_cli_long}} utilise deux conteneurs pour faciliter la génération et le test de votre application. Le premier est le conteneur tools, qui contient les utilitaires nécessaires pour générer et tester votre application. Le fichier Dockerfile pour ce conteneur est défini par le paramètre [`dockerfile-tools`](commands.html#command-parameters). Vous pouvez le considérer comme un conteneur de développement car il contient les outils normalement utilisés pour le développement d'un environnement d'exécution particulier.

Le second conteneur est le conteneur run. Il peut être déployé pour être utilisé
dans {{site.data.keyword.Bluemix}}, par exemple. Par conséquent, un point
d'entrée démarrant votre application est défini. Lorsque vous choisissez d'exécuter votre application via l'interface de ligne de commande {{site.data.keyword.dev_cli_short}}, ce conteneur est utilisé. Le fichier Dockerfile pour ce conteneur est défini par le paramètre [`dockerfile-run`](commands.html#run-parameters).


### Commandes utiles offertes par l'interface de ligne de commande
{: #helpful2}

Les commandes suivantes offertes par l'interface de ligne de commande vous aident à gérer votre projet durant les cycles de codage, de génération et d'exécution :
- La commande [`build`](./commands.html#build) vous permet de créer le projet dans un conteneur local.
- La commande [`debug`](./commands.html#debug) vous permet de déboguer votre application dans un conteneur local.
- La commande [`run`](./commands.html#run) vous permet d'exécuter votre application dans un conteneur local.
- La commande [`shell`](./commands.html#shell) vous permet d'ouvrir un interpréteur de commandes dans un conteneur local.
- La commande [`status`](./commands.html#status) vous permet de vérifier le statut des conteneurs utilisés par l'interface de ligne de commande.
- La commande [`stop`](./commands.html#stop) vous permet d'arrêter un conteneur.
- La commande [`test`](./commands.html#test) vous permet de tester votre application dans un conteneur local.

### Blogues et vidéos de référence
{: #ref2}

- [Débogage d'applications locales](local_debug.html)





## Déployer
{: #deploy}

Dans un environnement natif en cloud approprié, vous souhaiterez utiliser un environnement DevOps complètement fonctionnel pour gérer tous les déploiements, ainsi qu'une multitude d'autres fonctions. Durant le processus de création, vous pouvez configurer votre application pour l'utilisation de la méthodologie DevOps d'IBM Cloud. Si vous n'êtes pas prêt à utiliser la méthodologie DevOps intégrée, vous pouvez soit déployer manuellement votre application (commande [`ibmcloud dev deploy`](./commands.html#deploy)), soit utiliser la commande deploy dans votre propre pipeline DevOps.  



### Commandes utiles offertes par l'interface de ligne de commande
{: #helpful3}

Les commandes suivantes offertes par l'interface de ligne de commande vous aident à gérer votre projet durant le processus de déploiement :
- La commande [`console`](./commands.html#console) vous permet d'ouvrir la console IBM Cloud pour un projet.
- La commande [`deploy`](./commands.html#deploy) vous permet de déployer une application sur IBM Cloud.
- La commande [`view`](./commands.html#view) vous permet d'afficher l'URL déployée de votre projet.


### Blogues et vidéos de référence
{: #ref3}

- Blogue : [Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- Blogue : [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
