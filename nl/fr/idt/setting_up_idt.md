---
copyright:

  years: 2018

lastupdated: "2018-11-30"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .note}

# Configuration de l'interface de ligne de commande d'{{site.data.keyword.dev_cli_notm}}
{: #add-cli}

L'interface de ligne de commande {{site.data.keyword.dev_cli_short}} est un outil de création, de développement et de déploiement d'applications à l'aide d'une ligne de commande qui est utilisée par les développeurs souhaitant utiliser une ligne de commande pour développer des applications Web, mobiles et de microservice de bout en bout. Commencez rapidement avec un jeu d'outils recommandé en exécutant l'un des scripts ci-après.
{: shortdesc}

## Avant de commencer à utiliser {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Inscrivez-vous auprès de [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

*  Si vous utilisez Microsoft Windows, vous devez utiliser Windows 10 ou une version ultérieure.

* Vous devez utiliser le canal stable pour Docker, avec la version 1.13.1 au minimum.

## Comment installer {{site.data.keyword.dev_cli_notm}}
{: #installation}

Pour installer le jeu d'outils, vous pouvez exécuter la commande appropriée afin de lancer le programme d'installation. Cette action entraîne l'installation des outils recommandés pour le développement d'{{site.data.keyword.Bluemix_notm}} (s'ils ne sont pas déjà installés) : `Homebrew` (Mac uniquement), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, plug-in {{site.data.keyword.dev_cli_notm}}, plug-in Cloud Functions, plug-in Container Registry, plug-in Container Service et plug-in `sdk-gen`. Pour lancer l'installation, procédez comme suit :

**Mac et Linux :**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10 :**

* Remarque : ouvrez Windows PowerShell en cliquant avec le bouton droit de la souris sur l'icône Windows PowerShell et en sélectionnant "Run as Administrator".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

Vous pouvez également télécharger le script du programme d'installation à partir de notre [référentiel GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools).

## Vérification de l'installation
Pour vérifier l'installation, exécutez la commande `help` :

```
ibmcloud dev help
```
{: codeblock}

Si l'installation a abouti, la sortie devrait indiquer les instructions d'utilisation, la version actuelle et les commandes prises en charge.

La section [Réinstallation des outils](/docs/troubleshoot/ts_createapps.html#appendix) contient des informations sur l'installation individuelle des dépendances.

## Configuration de votre environnement
{: #configure-environment}

1. Connectez-vous à un noeud final d'API sur votre emplacement {{site.data.keyword.Bluemix_notm}}. Entrez, par exemple, la commande suivante pour vous connecter à l'emplacement {{site.data.keyword.Bluemix_notm}}, Dallas :

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Connectez-vous à {{site.data.keyword.Bluemix_notm}} à l'aide de votre IBMid.

	```
	ibmcloud login
	```
	{: codeblock}

	Si vos données d'identification sont rejetées, il est possible que vous utilisiez un ID fédéré. Procédez comme suit pour vous authentifier en utilisant un ID fédéré.
	{: note}

	1. Connectez-vous à [{{site.data.keyword.iamshort}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Sélectionnez **Créer une clé d'API**.
		* Entrez une description et un nom de clé d'API.
	3. Téléchargez votre clé d'API.
	4. Ouvrez le fichier et copiez la valeur depuis la zone `apiKey`.
	5. Connectez-vous avec la commande suivante :

		```
		ibmcloud login --apikey <value>
		```
		{: codeblock}

3. Définissez votre organisation et votre espace en utilisant ce qui suit :

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## En savoir plus
{: #learn}

Maintenant que l'interface de ligne de commande {{site.data.keyword.dev_cli_short}} est installée, vous pouvez apprendre à utiliser efficacement cet outil puissant :
- [Initiation à l'interface de ligne de commande IDT](index.html)
- [Commandes IDT (ibmcloud dev)](commands.html)
- [Developer Tools pour VS Code](vscode.html)
- [Developer Tools pour interfaces IDE Jetbrains](jetbrains.html)

Consultez les [tutoriels](/docs/apps/tutorials/tutorial_bff.html) présentant comment créer des applications natives en cloud qui utilisent l'interface de ligne de commande {{site.data.keyword.dev_cli_short}}.

## Pour aller plus loin
{: #learn-more}

Les ressources suivantes peuvent vous être utiles lorsque vous développez des applications natives en cloud avec l'interface de ligne de commande IBM Developer Tools :

- [Principale page d'arrivée IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - Page de produit principale pour l'interface de ligne de commande IDT
- [Programme d'installation d'IBM Developer Tools](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Référentiel GitHub public contenant des instructions d'installation détaillées
- [Service IBM Cloud App](https://{DomainName}/developer/appservice) - Page de la console IBM Cloud qui accompagne les outils IDT pour créer et gérer des applications cloud natives
- [Signalement de problèmes sur GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [Canal IBM Cloud Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com) - Pour demander l'accès à l'équipe, cliquez [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Langage ciblé**

- [Node.js sur IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogues et tutoriels**

- [Deploying to IBM Cloud Private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
