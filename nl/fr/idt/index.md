---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

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

1. [Créez ou activez une application pour déploiement](#idt-create).
2. [Codez, générez et exécutez](#code-build-run) localement votre application en utilisant des conteneurs.
3. [Déployez](#cli-deploy) votre application sur {{site.data.keyword.cloud_notm}}.

## Créez ou activez une application pour déploiement en cloud
{: #idt-create}

Il existe plusieurs façons de créer une application.
- Utiliser la [console Web App Services](https://cloud.ibm.com/developer/appservice/dashboard) pour créer des applications Web et des microservices génériques
- Utiliser le [tableau de bord Watson](https://cloud.ibm.com/developer/watson/dashboard) pour créer des applications de démarrage activées pour les fonctions basées sur Watson
    - D'autres tableaux de bord basés sur l'industrie et la technologie sont disponibles dans le menu "Hamburger" sur la page d'accueil de {{site.data.keyword.cloud_notm}}. Ils font tous appel à une approche similaire à celle qui consiste à utiliser des kits de démarrage pour créer de nouvelles applications.
- Interfaces de ligne de commande {{site.data.keyword.dev_cli_notm}} - Commande [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) permettant de créer une application.
- Interfaces de ligne de commande {{site.data.keyword.dev_cli_notm}} - Commande [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) permettant d'activer rapidement le cloud sur une application côté serveur existante.

Le processus est similaire pour toutes les méthodes de création décrites précédemment. Sélectionnez le type de projet, le langage d'implémentation et le modèle d'application à utiliser. Vous pouvez également choisir d'ajouter des services à votre application, tels que l'authentification ou la persistance. Enfin, vous pouvez ajouter la fonction DevOps à l'application, qui fournit une chaîne d'outils complète de contrôle des sources et de communication des équipes. Est également fourni un pipeline qui se déclenche à chaque validation afin de valider, générer et déployer votre application sur {{site.data.keyword.cloud_notm}}.

![Exemple de processus de création à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}](create_flow.png "Exemple de processus de création à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}"){: caption="Figure 1. Exemple de processus de création à l'aide de l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}" caption-side="bottom"}

L'interface de ligne de commande {{site.data.keyword.dev_cli_notm}} fonctionne en étroite collaboration pour fournir une expérience parfaite lors du développement. Les projets créés à partir de l'une des consoles Web incluent un bouton **Télécharger le code** permettant de télécharger le code source généré dans votre poste de travail afin d'effectuer des tâches de développement supplémentaires.

### Commandes utiles offertes par l'interface de ligne de commande
{: #helpful}

Les commandes CLI `ibmcloud dev` suivantes vous aident à gérer votre projet et les consoles Web :
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) vous permet de télécharger le code source des applications sur votre poste de travail.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) vous permet d'ouvrir votre navigateur sur la page de projet de l'application en cours dans {{site.data.keyword.cloud_notm}}.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) vous permet de créer une nouvelle application.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) vous permet de supprimer l'application en cours de la zone de projet {{site.data.keyword.cloud_notm}}.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) vous permet d'activer pour le cloud une application côté serveur existante.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) vous permet d'obtenir les données d'identification requises par le projet pour activer l'utilisation de services liés.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) permet de répertorier toutes les applications que vous avez créées dans l'organisation/espace actuellement sélectionné, que ce soit depuis l'interface de ligne de commande ou les consoles.

### Exploration de la structure de projet d'une application
{: #exploring-project}

Les projets créés ou activés pour être utilisés avec les outils de développement sont fournis avec des paramètres préconfigurés encapsulés dans le fichier `cli-config.yml`. Le fichier `cli-config.yml` contient des entrées par défaut utilisées par les commandes `ibmcloud dev` et qui peuvent être remplacées par des valeurs transmises via la ligne de commande.

### Blogues et vidéos de référence
{: #ref1}

- Vidéo : [Installation d'{{site.data.keyword.cloud_notm}} Developer Tools sur Ubuntu Linux&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
- Blogue : [Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")

## Coder, générer et exécuter
{: #code-build-run}

Une fois votre projet créé, il vous appartient d'en faire quelque chose d'utile. La procédure générale consiste à éditer le code source, puis à exécuter une commande [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) pour compiler l'application dans un conteneur local spécifique au langage et à la configuration de votre application. Selon le langage et le générateur d'application utilisés, il existe un ou plusieurs conteneurs définis par défaut pour prendre en charge la génération et l'exécution en local. En général, il existe un conteneur "tools" dédié aux générations et au débogage en local. Ce conteneur comporte des outils et des fonctions supplémentaires pour vous aider dans vos tâches de développement. Il existe également un conteneur "run" qui reproduit l'environnement d'exécution de votre application une fois celle-ci déployée sur le cloud, que ce soit dans Cloud Foundry ou dans un environnement de conteneur basé sur le système Kubernetes d'IBM.

Vous êtes libre d'utiliser n'importe quelle interface IDE ou n'importe quel éditeur de votre choix pour coder votre application. {{site.data.keyword.IBM_notm}} offre une extension pour l'éditeur Microsoft&trade; Visual Studio Code (VSCode) qui vous permet d'accéder à toutes les commandes IDE directement depuis l'éditeur.

Une fois que le projet est généré, exécutez votre application en utilisant [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) ou [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug). L'application est exécutée dans le conteneur approprié. Certains modèles d'application prennent en charge plusieurs conteneurs externes à vos applications. Les applications sont automatiquement démarrées et configurées lors de l'exécution ou du débogage. Il existe également une commande [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) qui exécute les scénarios de test associés à l'application.

### Utilisation des conteneurs locaux
{: #local-containers}

L'interface de ligne de commande {{site.data.keyword.dev_cli_long}} utilise deux conteneurs pour la génération et le test de votre application. Le premier est le conteneur tools, qui contient les utilitaires nécessaires pour générer et tester votre application. Le fichier Dockerfile pour ce conteneur est défini par le paramètre [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Vous pouvez le considérer comme un conteneur de développement car il contient les outils qui sont normalement utilisés pour le développement d'un environnement d'exécution particulier.

Le second conteneur est le conteneur run. Il peut être déployé pour être utilisé
dans {{site.data.keyword.cloud}}, par exemple. Par conséquent, un point d'entrée démarrant votre application est défini. Lorsque vous choisissez d'exécuter votre application via l'interface de ligne de commande {{site.data.keyword.dev_cli_short}}, ce conteneur est utilisé. Le fichier Dockerfile pour ce conteneur est défini par le paramètre [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

### Commandes utiles offertes par l'interface de ligne de commande
{: #helpful2}

Les commandes CLI suivantes vous permettent de déboguer votre projet :
- La commande [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) permet de créer le projet dans un conteneur local.
- La commande [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) permet de déboguer votre application dans un conteneur local.
- La commande [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) permet d'exécuter votre application dans un conteneur local.
- La commande [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) permet d'ouvrir un shell dans un conteneur local.
- La commande [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) vous permet de vérifier le statut des conteneurs utilisés par l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}.
- La commande [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) permet d'arrêter un conteneur.
- La commande [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) permet de tester votre application dans un conteneur local.

### Débogage d'applications locales
{: #ref2}

- [Débogage d'applications locales](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## Déployer
{: #cli-deploy}

Dans un environnement natif en cloud approprié, vous utilisez un pipeline DevOps complètement fonctionnel pour gérer tous les déploiements, ainsi qu'une multitude d'autres fonctions. Durant le processus de création, vous pouvez configurer votre application pour l'utilisation de la méthodologie DevOps d'IBM Cloud. Si vous n'êtes pas prêt à utiliser la méthodologie DevOps intégrée, vous pouvez soit exécuter manuellement la commande [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) pour déployer votre application, soit utiliser la commande `deploy` dans votre propre pipeline DevOps.

### Commandes utiles offertes par l'interface de ligne de commande
{: #helpful3}

Les commandes CLI suivantes vous aident à gérer votre projet durant le processus de déploiement :
- La commande [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) permet d'ouvrir la console {{site.data.keyword.cloud_notm}} pour un projet.
- La commande [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) permet de déployer une application dans {{site.data.keyword.cloud_notm}}.
- La commande [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) permet d'afficher l'URL déployée de votre projet.

### Blogues et vidéos de référence
{: #ref3}

- Blogue : [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
- Blogue : [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")
