---

copyright:

  years: 2018

lastupdated: "2018-06-21"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools pour interfaces IDE Jetbrains
{: #ibm-dev-tools-for-jetbrains}

L'extension IBM Developer Tools pour les interfaces IDE Jetbrains, comprenant IntelliJ, WebStorm, Android Studio, etc., offre de nouvelles entrées de menu vous permettant d'accéder directement aux commandes CLI IDT depuis l'interface IDE. Elle vous permet d'accéder rapidement à un sous-ensemble de commandes `ibmcloud dev` pour les flux de travail Docker et CloudFoundry, y compris le déploiement d'application, le démarrage/l'arrêt/le redémarrage d'applications sur {{site.data.keyword.Bluemix_notm}}, la visualisation de journaux d'applications distants, etc., le tout sans avoir à quitter le contexte de votre éditeur.
{:shortdesc}

![Capture d'écran d'IBM Developer Tools s'exécutant dans une interface IDE WebStorm.](jetbrains.png "Exemple de menu IDT s'exécutant dans une interface IDE de WebStorm")

## Dépendances
{: #dependencies}

L'utilisation de l'extension IBM Developer Tools pour les interfaces IDE basées sur Jetbrains requiert que [l'interface de ligne de commande IBM Cloud Developer Tools](index.html) soit installée sur votre système.

## Installation
{: #installation}

Le moyen le plus simple d'installer l'extension IBM Developers Tools pour une interface IDE Jetbrains consiste à accéder à la page [ibm-cloud-developer-tools/jetbrains/ pour le référentiel IDT sur GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) et à suivre les instructions affichées.

## Syntaxe
{: #usage}

Vous pouvez soit commencer avec une application existante côté serveur et l'activer pour IBM Cloud, soit utiliser l'interface de ligne de commande IDT afin de créer une nouvelle application à partir d'un kit de démarrage (ibmcloud dev create). Une fois le projet de vos applications créé, ouvrez-le dans votre interface IDE JetBrains.

Si vous avez une application côté serveur générique, sélectionnez Outils > IBM Cloud Developer Tools > Activer l'application pour IBM Cloud. Cette action recherche tous les fichiers requis et ajoute ceux éventuellement manquants pour vous permettre de générer l'application dans un cluster Kubernetes ou localement puis de la déployer dans IBM Cloud à l'aide d'une application Cloud Foundry.

Développez votre application native en cloud en utilisant les actions Générer/Exécuter/Déployer de base du menu IDT. Si vous devez effectuer des actions qui ne figurent pas dans le menu, ouvrez l'onglet Terminal et entrez manuellement les commandes appropriées.
