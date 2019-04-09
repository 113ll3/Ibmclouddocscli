---

copyright:
  years: 2015, 2019
lastupdated: "2019-03-01"

keywords: IBM Cloud Developer Tools CLI, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Initiation à l'interface de ligne de commande {{site.data.keyword.cloud_notm}}
{: #ibmcloud-cli}

En suivant ce tutoriel, vous allez installer un ensemble d'outils {{site.data.keyword.cloud}} Developer Tools, vérifier l'installation et configurer l'environnement. {{site.data.keyword.cloud_notm}} Developer Tools propose une approche de ligne de commande permettant de créer, de développer et de déployer des applications Web, mobiles et de microservice.
{: shortdesc}

Avec cette installation, vous disposez de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome et des outils suivants :

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
{: #idt-prereq}

Vous devez avoir un compte [{{site.data.keyword.cloud_notm}}](https://cloud.ibm.com/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") et la configuration système suivante doit être respectée :

* Sous Windows 10 Pro, certaines fonctions ne sont pas prises en charge (contrairement aux autres versions de Windows).
* Vous devez utiliser le canal stable pour Docker, avec la version 1.13.1 au minimum.

## Etape 1. Lancez la commande d'installation
{: #step1-install-idt}

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

  Vous pouvez également télécharger le script du programme d'installation à partir de ce [référentiel GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").

<!--Uncomment when this linked topic goes to prod.
  For the steps to install these tools manually, see [Installing the {{site.data.keyword.cloud_notm}} developer tools CLI plug-in components manually](/docs/cli?topic=cloud-cli-install-devtools-manually#install-devtools-manually).
-->

## Etape 2. Vérifier l'installation
{: #step2-verify-idt}

Pour vérifier que l'installation de l'interface CLI et de Developer Tools a abouti, exécutez la commande `help` :
```
ibmcloud dev help
```
{: codeblock}

La sortie inclut les instructions d'utilisation, la version actuelle et les commandes prises en charge.

## Etape 3. Configurer votre environnement
{: #step3-configure-idt-env}

1. Connectez-vous à {{site.data.keyword.cloud_notm}} à l'aide de votre IBMid. Si vous avez plusieurs comptes, vous êtes invité à sélectionner le compte à utiliser. Si vous n'indiquez pas de région avec l'option `-r`, vous devez également choisir une région.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  Si vos données d'identification sont rejetées, vous pouvez utiliser un ID fédéré. Pour vous connecter avec un ID fédéré, utilisez l'option `--sso`. Pour plus de détails, voir [Connexion à l'aide d'un ID fédéré](/docs/iam/federated_id?topic=iam-federated_id#federated_id).
  {: tip}

2. Pour utiliser les services Cloud Foundry, ciblez une organisation et un espace.
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

Vous êtes maintenant prêt à développer et déployer votre première application ! Pour plus d'informations, voir [Création et déploiement d'applications à l'aide de l'interface de ligne de commande](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli).
