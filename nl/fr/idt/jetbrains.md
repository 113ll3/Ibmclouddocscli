---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-27"

keywords: ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools pour interfaces IDE Jetbrains
{: #ibm-dev-tools-for-jetbrains}

L'extension {{site.data.keyword.cloud}} Developer Tools pour les interfaces IDE Jetbrains, comprenant notamment `IntelliJ`, `WebStorm`, `Android Studio`, offre de nouvelles entrées de menu vous permettant d'accéder directement aux commandes de l'interface CLI {{site.data.keyword.dev_cli_notm}} depuis l'interface IDE. Vous pouvez accéder rapidement à un sous-ensemble de commandes `ibmcloud dev` pour les flux de travail Docker et Cloud Foundry, incluant notamment le déploiement d'application, le démarrage/l'arrêt/le redémarrage d'applications sur {{site.data.keyword.cloud_notm}}, la visualisation de journaux d'applications distants, sans avoir à quitter votre éditeur.
{:shortdesc}

Exemple de menu pour ![Capture d'écran d'IBM Cloud Developer Tools s'exécutant dans l'environnement IDE WebStorm.](jetbrains.png "{{site.data.keyword.cloud_notm}} Developer Tools s'exécutant dans l'environnement IDE WebStorm")


## Dépendances
{: #jetbrains-dependencies}

Pour utiliser l'extension {{site.data.keyword.cloud_notm}} Developer Tools pour les interfaces IDE Jetbrains, l'interface CLI [{{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) doit être installée sur votre système.

## Installation
{: #jetbrains-installation}

Le meilleur moyen d'installer l'extension {{site.data.keyword.cloud_notm}} Developer Tools pour l'interface IDE Jetbrains consiste à accéder à la page [{{site.data.keyword.cloud_notm}} developer tools Github repo's jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") et à suivre les instructions affichées.

## Syntaxe
{: #jetbrains-usage}

Commencez par utiliser une application existante côté serveur et activez-la pour {{site.data.keyword.cloud_notm}} ou utilisez l'interface de ligne de commande {{site.data.keyword.dev_cli_notm}} pour créer une application à partir d'un kit de démarrage (ibmcloud dev create). Une fois votre projet d'application créé, ouvrez-le dans votre interface IDE JetBrains.

Si vous avez une application côté serveur générique, sélectionnez Outils > IBM Cloud Developer Tools > Activer l'application pour {{site.data.keyword.cloud_notm}}. Cette action recherche tous les fichiers requis, ajoute ceux manquants à l'application et déploie cette dernière dans {{site.data.keyword.cloud_notm}} en utilisant une application Cloud Foundry ou dans un cluster Kubernetes.

Développez votre application native en utilisant les actions Générer/Exécuter/Déployer de base du menu {{site.data.keyword.cloud_notm}} Developer Tools. Si vous devez effectuer des actions qui ne figurent pas dans le menu, ouvrez l'onglet Terminal puis entrez les commandes souhaitées manuellement.
