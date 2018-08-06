---

copyright:

  years: 2017, 2018

lastupdated: "2018-07-12"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools pour Visual Studio Code
{: #ibm-dev-tools-for-vscode}

L'extension IBM Cloud Developer Tools pour Visual Studio Code est une extension de l'éditeur qui permet d'accéder aux fonctions de l'interface de ligne de commande (CLI) IBM Developer directement depuis la palette de commandes de l'éditeur Visual Studio Code. Elle vous permet d'accéder rapidement à un sous-ensemble de commandes `ibmcloud dev` pour les flux de travail Docker et Cloud Foundry, y compris le déploiement d'application, le démarrage/l'arrêt/le redémarrage d'applications sur {{site.data.keyword.Bluemix_notm}}, la visualisation de journaux d'applications distants, etc., le tout sans avoir à quitter le contexte de votre éditeur.
{:shortdesc}

![Capture d'écran de l'écran de téléchargement de l'extension IBM Developer Tools.](vscode.png "Ecran de téléchargement d'extension dans Visual Studio Code")

## Dépendances
{: #dependencies}

Pour utiliser l'extension IBM Cloud Developer Tools pour Visual Studio Code, l'interface CLI [{{site.data.keyword.Bluemix_notm}}](https://plugins.ng.bluemix.net/ui/home.html) et le plug-in [IBM Developer CLI](index.html) doivent être installés sur votre système.

## Installation
{: #installation}

Le moyen le plus simple d'installer l'extension IBM Cloud Developers Tools consiste à utiliser la commande 'quick open' de Visual Studio Code :

1. Ouvrez la palette de commandes 'quick open' en utilisant les combinaisons de touches suivantes dans l'éditeur :

  * **Mac** : `cmd + p`
  * **Windows/Linux** : `ctrl + p`

2. Entrez la commande `ext install ibm-developer` et appuyez sur Entrée pour installer l'extension IBM Cloud Developer Tools dans l'éditeur Visual Studio Code.

Vous pouvez également installer l'extension IBM Cloud Developer Tools via la fenêtre de gestion des extensions :

1. Ouvrez la barre d'options latérale **Extensions** dans l'éditeur Visual Studio Code, puis lancez une recherche sur la chaîne `publisher:IBM Developer`. L'extension IBM Cloud Developer Tools apparaît dans les résultats de la recherche.  
2. Cliquez sur le bouton **Install** pour lancer l'installation.

Vous pouvez également accéder à l'extension [IBM Developer Cloud Tools directement à partir de Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer).

## Syntaxe
{: #usage}

Vous lancez les commandes d'extension à l'aide de la palette de commandes de Visual Studio Code.

Tout d'abord, ouvrez la palette de commandes à l'aide de la combinaison de touches suivante :

* **Mac** : `cmd + maj + p`
* **Windows/Linux** : `ctrl + maj + p`

Ensuite, entrez ou sélectionnez la commande que vous souhaitez lancer. Vous pouvez entrer ‘ibmcloud’ dans la palette de commandes pour consulter la liste de toutes les commandes disponibles.

### Utilisation de l'extension IBM Developer pour les flux de travail Docker (conteneurs Docker)
{: #usage-docker}

Vous pouvez commencer à utiliser les flux de travaux `ibmcloud dev` en quelques étapes seulement :
* Créez un projet en utilisant l'une des deux méthodes suivantes :
  * Utilisez la [console Web {{site.data.keyword.Bluemix_notm}}](https://console.ng.bluemix.net/developer/getting-started/) et téléchargez le code généré.
  * Utilisez l'[interface de ligne de commande d'{{site.data.keyword.Bluemix_notm}} Developer](index.html) et générez un projet à l'aide de la commande `ibmcloud dev create`.
* Ouvrez le dossier du projet localement dans l'éditeur Visual Studio Code.
* Utilisez la commande `ibmcloud dev build` pour générer l'application dans une image Docker.
* Utilisez la commande `ibmcloud dev debug` pour exécuter l'application dans un conteneur Docker local à des fins de développement.
> Remarque : pour déboguer une application Node.js qui s'exécute dans le conteneur Docker local, vous devez [ajouter une configuration de débogage pour le conteneur local](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container).
* Utilisez la commande `ibmcloud dev run` pour exécuter l'application dans un conteneur Docker local en mode édition.
* Utilisez la commande `ibmcloud dev deploy` pour déployer l'application dans un environnement d'exécution Cloud Foundry sur {{site.data.keyword.Bluemix_notm}}.

### Utilisation de l'extension IBM Developer pour les flux de travail Cloud Foundry
{: #usage-cloud-foundry}

Pour les utilisateurs qui déploient actuellement des applications dans des environnements d'exécution Cloud Foundry sur IBM {{site.data.keyword.Bluemix_notm}}, la prise en charge de l'ensemble d'opérations `cf` est également fournie.

Vous pouvez démarrer les flux de travail CloudFoundry en quelques étapes seulement :
* Créez une nouvelle application CloudFoundry.
  * Utilisez la [console Web](https://console.ng.bluemix.net/dashboard/cf-apps) et téléchargez le code de démarrage..
  * Créez manuellement une nouvelle application CloudFoundry.
* Ouvrez le dossier du projet localement dans l'éditeur Visual Studio Code.
* Utilisez la commande `ibmcloud cf apps` pour répertorier toutes vos applications.
* Utilisez la commande `ibmcloud cf push` pour envoyer votre application à l'environnement d'exécution Cloud Foundry.
* Utilisez ibmcloud `cf <start/stop/restage/restart>` pour modifier le statut de votre application.
* Utilisez la commande `ibmcloud cf logs` pour afficher le flux de journalisation opérationnel pour votre application.
  * Utilisez la commande `ibmcloud cf logs` pour arrêter le flux de journalisation.
