---

copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools pour interfaces IDE Jetbrains
{: #ibm-dev-tools-for-jetbrains}

L'extension {{site.data.keyword.Bluemix}} Developer Tools pour les interfaces IDE Jetbrains, comprenant notamment `IntelliJ`, `WebStorm`, `Android Studio`, offre de nouvelles entrées de menu vous permettant d'accéder directement aux commandes de l'interface CLI {{site.data.keyword.dev_cli_notm}} depuis l'interface IDE. Elle vous permet d'accéder rapidement à un sous-ensemble de commandes `ibmcloud dev` pour les flux de travail Docker et Cloud Foundry, notamment le déploiement d'application, le démarrage/l'arrêt/le redémarrage d'applications sur {{site.data.keyword.Bluemix_notm}}, la visualisation de journaux d'applications distants, le tout sans qu'il soit nécessaire de quitter l'éditeur.
{:shortdesc}

![Capture d'écran d'IBM Cloud Developer Tools s'exécutant dans l'environnement IDE WebStorm.](jetbrains.png "Exemple de menu pour {{site.data.keyword.Bluemix_notm}} Developer Tools s'exécutant dans l'environnement IDE WebStorm")

## Dépendances
{: #dependencies}

Pour utiliser l'extension {{site.data.keyword.Bluemix_notm}} Developer Tools pour les interfaces IDE Jetbrains, l'interface CLI [{{site.data.keyword.dev_cli_notm}}](/docs/cli/index.html#overview) doit également être installée sur votre système.

## Installation
{: #installation}

Le moyen le plus simple d'installer l'extension {{site.data.keyword.Bluemix_notm}} Developer Tools pour l'interface IDE Jetbrains consiste à accéder à la page [{{site.data.keyword.Bluemix_notm}} developer tools Github repo's jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") et à suivre les instructions affichées.

## Syntaxe
{: #usage}

Commencez par utiliser une application existante côté serveur et activez-la pour {{site.data.keyword.Bluemix_notm}} ou utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}} pour créer une application à partir d'un kit de démarrage (ibmcloud dev create). Une fois votre projet d'application créé, ouvrez-le dans votre interface IDE JetBrains.

Si vous avez une application côté serveur générique, sélectionnez Outils > IBM Cloud Developer Tools > Activer l'application pour IBM Cloud. Cette action recherche tous les fichiers requis et ajoute ceux éventuellement manquants pour vous permettre de générer l'application localement et de la déployer dans {{site.data.keyword.Bluemix_notm}} à l'aide d'une application Cloud Foundry ou dans un cluster Kubernetes.

Développez votre application native en utilisant les actions Générer/Exécuter/Déployer de base du menu {{site.data.keyword.Bluemix_notm}} Developer Tools. Si vous devez effectuer des actions qui ne figurent pas dans le menu, ouvrez l'onglet Terminal puis entrez les commandes souhaitées manuellement.
