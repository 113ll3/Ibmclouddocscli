---

copyright:

  years: 2015, 2018

lastupdated: "2018-11-15"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Initiation à l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}
{: #overview}

En suivant ce tutoriel, vous allez installer un ensemble d'outils {{site.data.keyword.Bluemix}} Developer Tools, vérifier l'installation et configurer votre environnement. Les outils {{site.data.keyword.Bluemix}} Developer Tools offrent une approche de ligne de commande permettant de créer, de développer et de déployer des applications Web, mobiles et de microservice de bout en bout.
{:shortdesc}

Avec cette installation, vous disposez de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} autonome et des outils suivants :

* `Homebrew` (Mac uniquement)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* Plug-in {{site.data.keyword.dev_cli_notm}}
* Plug-in {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in {{site.data.keyword.registrylong_notm}}
* Plug-in {{site.data.keyword.containerlong_notm}}
* Plug-in `sdk-gen`

## Avant de commencer
{: #prereq}

Vous devez avoir un compte [{{site.data.keyword.Bluemix_notm}} ](https://console.bluemix.net/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") et la configuration système doit être respectée :

* Sous Windows, certaines fonctions ne sont pas prises en charge si vous n'exécutez pas Windows 10 Pro.
* Vous devez utiliser le canal stable pour Docker, avec la version 1.13.1 au minimum.

## Etape 1. Lancez la commande d'installation
{: #step1}

* Pour Mac et Linux, exécutez la commande suivante :

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Pour Windows 10 Pro, exécutez la commande suivante en tant qu'administrateur :

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Cliquez avec le bouton droit de la souris sur l'icône Windows PowerShell et sélectionnez **Exécuter en tant qu'administrateur**.
  {: tip}

  Vous pouvez également télécharger le script du programme d'installation à partir de notre [référentiel GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools).

  Pour savoir comment installer ces outils manuellement, voir [Réinstallation des outils](/docs/cli/ts_createapps.html#appendix).

## Etape 2. Vérifier l'installation
{: #step2}

Pour vérifier que l'installation de l'interface de ligne de commande et des outils de développeur a abouti, exécutez la commande `help` :

```
ibmcloud dev help
```
{: codeblock}
<br>
La sortie inclut les instructions d'utilisation, la version actuelle et les commandes prises en charge.

## Etape 3. Configurer votre environnement
{: #step3}

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
    <br>

	Si vos données d'identification sont rejetées, vous pouvez utiliser un ID fédéré. Pour plus de détails, voir [Connexion à l'aide d'un ID fédéré](/docs/iam/login_fedid.html#federated_id).
	{: tip}

3. Définissez votre organisation et votre espace.

	```
	ibmcloud target --cf
	```
	{: codeblock}

	Vous pouvez, si vous le souhaitez, utiliser la sortie de la commande précédente pour définir manuellement votre organisation et votre espace à l'aide de la commande suivante :

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Etapes suivantes
{: #next-steps}

Vous êtes maintenant prêt à développer et déployer votre première application ! Pour plus d'informations, voir [Création et déploiement d'applications à l'aide de l'interface de ligne de commande](/docs/apps/create-deploy-cli.html).
