---

copyright:
  years: 2017, 2019
lastupdated: "2019-02-27"

keywords: ibm cloud developer tools, visual studio code, install developer tools, developer extension, vscode cli, vscode plugin, cloud foundry vscode

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools pour Visual Studio Code
{: #ibm-dev-tools-for-vscode}

L'extension IBM Cloud Developer Tools pour Visual Studio Code permet d'accéder aux fonctions de l'interface CLI IBM Developer directement dans la palette de commandes de l'éditeur Visual Studio Code. Vous pouvez accéder rapidement à un sous-ensemble de commandes `ibmcloud dev` pour les flux de travail Docker et Cloud Foundry, incluant notamment le déploiement d'application, le démarrage/l'arrêt/le redémarrage d'applications sur {{site.data.keyword.cloud}}, la visualisation de journaux d'applications distants, sans avoir à quitter votre éditeur.
{:shortdesc}

![Capture d'écran de l'écran de téléchargement de l'extension IBM Developer Tools.](vscode.png "Ecran de téléchargement d'extension dans Visual Studio Code")

## Dépendances
{: #vscode-dependencies}

Pour utiliser l'extension IBM Cloud Developer Tools pour Visual Studio Code, l'interface CLI [{{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) et le plug-in {{site.data.keyword.cloud_notm}} CLI doivent être installés sur votre système.

## Installation
{: #vscode-installation}

Le moyen le plus simple d'installer l'extension {{site.data.keyword.dev_cli_notm}} consiste à utiliser la commande 'quick open' de Visual Studio Code :

1. Ouvrez la palette de commandes 'quick open' en utilisant les combinaisons de touches suivantes dans l'éditeur :

  * **Mac** : `cmd + p`
  * **Windows/Linux** : `ctrl + p`

2. Entrez la commande `ext install ibm-developer` et appuyez sur Entrée pour installer l'extension {{site.data.keyword.dev_cli_notm}} dans l'éditeur Visual Studio Code.

Vous pouvez également installer l'extension {{site.data.keyword.dev_cli_notm}} via la fenêtre de gestion des extensions :

1. Ouvrez la barre latérale **Extensions** dans l'éditeur Visual Studio Code, puis recherchez la chaîne `publisher:IBM Developer`. L'extension {{site.data.keyword.dev_cli_notm}} s'affiche dans les résultats de la recherche.  
2. Cliquez sur **Installer** pour lancer l'installation.

Vous pouvez également accéder à l'extension [IBM Cloud Developer Tools directement à partir de Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").

## Syntaxe
{: #vscode-usage}

Vous lancez les commandes d'extension à l'aide de la palette de commandes de Visual Studio Code.

Tout d'abord, ouvrez la palette de commandes à l'aide de la combinaison de touches suivante :

* **Mac** : `cmd + maj + p`
* **Windows/Linux** : `ctrl + maj + p`

Ensuite, entrez ou sélectionnez la commande que vous souhaitez lancer. Vous pouvez entrer ‘ibmcloud’ dans la palette de commandes pour consulter la liste de toutes les commandes disponibles.

### Utilisation de l'extension IBM Developer pour les flux de travail Docker (conteneurs Docker)
{: #usage-docker}

Vous pouvez commencer à utiliser les flux de travaux `ibmcloud dev` en quelques étapes seulement :
* Créez un projet en utilisant l'une des deux méthodes suivantes :
  * Utilisez la console Web [{{site.data.keyword.cloud_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") et téléchargez le code généré. 
  * Utilisez le plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} Developer Tools et générez un projet en utilisant la commande [ibmcloud dev create](/docs/cli/idt?topic=cloud-cli-idt-cli#create).
* Ouvrez le dossier du projet localement dans l'éditeur Visual Studio Code.
* Utilisez la commande `ibmcloud dev build` pour générer l'application dans une image Docker.
* Utilisez la commande `ibmcloud dev debug` pour exécuter l'application dans un conteneur Docker local à des fins de développement.
> Remarque : pour déboguer une application Node.js qui s'exécute dans le conteneur Docker local, vous devez [ajouter une configuration de débogage pour le conteneur local](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe").
* Utilisez la commande `ibmcloud dev run` pour exécuter l'application dans un conteneur Docker local en mode édition.
* Utilisez la commande `ibmcloud dev deploy` pour déployer l'application dans un environnement d'exécution Cloud Foundry sur {{site.data.keyword.cloud_notm}}.

### Utilisation de l'extension IBM Developer pour les flux de travail Cloud Foundry
{: #usage-cloud-foundry}

Pour les utilisateurs qui déploient actuellement des applications dans des environnements d'exécution Cloud Foundry sur {{site.data.keyword.cloud_notm}}, la prise en charge de l'ensemble d'opérations `cf` est également fournie.

Vous pouvez démarrer les flux de travail Cloud Foundry en quelques étapes seulement :
* Créez une nouvelle application Cloud Foundry.
  * Utilisez la console Web [{{site.data.keyword.cloud_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe") et téléchargez le code de démarrage. 
  * Créez manuellement une application Cloud Foundry
* Ouvrez le dossier du projet localement dans l'éditeur Visual Studio Code.
* Utilisez la commande `ibmcloud cf apps` pour répertorier toutes vos applications.
* Utilisez la commande `ibmcloud cf push` pour envoyer votre application à l'environnement d'exécution Cloud Foundry.
* Utilisez ibmcloud `cf <start/stop/restage/restart>` pour modifier le statut de votre application.
* Utilisez la commande `ibmcloud cf logs` pour afficher le flux de journalisation opérationnel pour votre application.
  * Utilisez la commande `ibmcloud cf logs` pour arrêter le flux de journalisation.
