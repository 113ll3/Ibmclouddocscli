---
copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Configuration du {{site.data.keyword.dev_cli_notm}}
{: #add-cli}

Le plug-in {{site.data.keyword.dev_cli_short}} est un outil de création , de développement et de déploiement d'applications à l'aide d'une ligne de commande qui est utilisée par les développeurs souhaitant utiliser une ligne de commande pour développer des applications Web, mobiles et de microservice de bout en bout.
{: shortdesc}

## Prérequis
{: #prereq}

Inscrivez-vous auprès de [{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net).

*  Si vous utilisez Microsoft Windows, vous devez utiliser Windows 10 ou une version ultérieure. 

* Vous devez utiliser le canal stable pour Docker, avec la version 1.13.1 au minimum.

## Installation
{: #installation}

Pour installer l'outil, vous pouvez exécuter la commande appropriée afin d'appeler notre programme d'installation. L'exécution de cette commande aura également pour conséquence d'installer des dépendances, telles qu'IBM Cloud CLI, Kubernetes, Helm et Docker. Pour installer ces dépendances, suivez les étapes d'installation ci-dessous :

**Mac et Linux :**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10 :**

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

Vérifiez que l'installation du plug-in a abouti en exécutant la
commande suivante :  

```
bx dev
```
{: codeblock}

## Configuration de votre environnement
{: #configure-environment}

1. Connectez-vous à un noeud final d'API dans votre région [{{site.data.keyword.Bluemix_notm}} ](/docs/overview/cf.html#ov_intro_reg). Entrez, par exemple, la commande suivante pour vous connecter à la région {{site.data.keyword.Bluemix_notm}} Sud des Etats-Unis :

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Connectez-vous à {{site.data.keyword.Bluemix_notm}} à l'aide de votre IBMid.

	```
	bx login
	```
	{: codeblock}

	**Remarque :** si vos données d'identification sont rejetées, vous utilisez peut-être un ID fédéré. Procédez comme suit pour vous authentifier en utilisant un ID fédéré.

	1. Connectez-vous à [{{site.data.keyword.iamshort}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Sélectionnez **Créer une clé d'API**.
		* Entrez une description et un nom de clé d'API.
	3. Téléchargez votre clé d'API.
	4. Ouvrez le fichier et copiez la valeur depuis la zone `apiKey`.
	5. Connectez-vous avec la commande suivante :

		```
		bx login --apikey <value>
		```
		{: codeblock}

3. Définissez votre organisation et votre espace en utilisant ce qui suit :

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## En savoir plus
{: #learn}

Maintenant que le plug-in {{site.data.keyword.dev_cli_short}} est installé, vous pouvez apprendre à utiliser efficacement cet outil puissant :
- [Initiation à l'interface de ligne de commande IDT](index.html)
- [Commandes IDT (bx dev)](commands.html)
- [Developer Tools pour VS Code](vscode.html)
- [Developer Tools pour interfaces IDE Jetbrains](jetbrains.html)

Consultez les [tutoriels](/docs/apps/tutorials/tutorial_bff.html) montrant comment créer des applications natives en cloud à l'aide du plug-in {{site.data.keyword.dev_cli_short}}.

## Pour aller plus loin
{: #learn-more}

Les ressources suivantes peuvent vous être utiles lorsque vous développez des applicatoins natives en cloud avec l'interface de ligne de commande IBM Developer Tools :

- [Principale page d'arrivée IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - Page de produit principale pour l'interface de ligne de commande IDT
- [Programme d'installation d'IBM Developer Tools](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Référentiel GitHub public contenant des instructions d'installation détaillées
- [Service d'application IBM Cloud](https://console.bluemix.net/developer/appservice) - Page de console IBM Cloud qui accompagne les outils IDT pour créer et gérer les applications natives en cloud 
- [Canal slack technique d'outils de développement IBM Cloud](https://ibm-cloud-tech.slack.com) - Echanger au sujet des outils IDT, obtenir des réponses, suggérer des idées, etc. 
	- [Demander un accès par équipe](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Langage ciblé**

- [Node.js sur IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogues et tutoriels**

- [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
