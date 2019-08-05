---

copyright:
  years: 2015, 2019
lastupdated: "2019-07-24"

keywords: command line interface, cli, getting started, getting started with IBM Cloud CLI, getting started with IBM Cloud CLI and developer tools tutorial, IBM Cloud Developer Tools CLI, ibmcloud cli, download cli, ibmcloud dev, cloud cli, dev plugin, dev plug-in, cloud command line, developer tools, dev tools, install cloud cli, getting started cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}
{:note: .note}

# Initiation à l'interface de ligne de commande {{site.data.keyword.cloud_notm}} et à {{site.data.keyword.dev_cli_short}}
{: #getting-started}

Dans ce tutoriel, vous allez installer un ensemble d'outils de développement {{site.data.keyword.cloud}} incluant la dernière interface de ligne de commande {{site.data.keyword.cloud_notm}}, vérifier l'installation et configurer l'environnement. {{site.data.keyword.dev_cli_notm}} propose une approche d'interface de ligne de commande (CLI) permettant de créer, développer et déployer des applications en cloud.
{: shortdesc}

La commande d'installation présentée dans ce tutoriel installe la dernière version d'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome ainsi que les outils suivants :

* `Homebrew` (Mac uniquement)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* Plug-in {{site.data.keyword.dev_cli_notm}}
* Plug-in {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in {{site.data.keyword.cos_full_notm}}
* Plug-in {{site.data.keyword.registrylong_notm}}
* Plug-in {{site.data.keyword.containerlong_notm}}

## Avant de commencer
{: #idt-prereq}

Vous devez avoir un compte [{{site.data.keyword.cloud_notm}}](https://cloud.ibm.com/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") et la configuration système suivante doit être respectée :

* Sous Windows&trade;, certaines fonctions ne sont pas prises en charge sauf si vous exécutez Windows&trade; 10 Pro.
* Vous devez utiliser le canal stable pour Docker, avec la version 1.13.1 au minimum.

## Etape 1. Lancer la commande d'installation
{: #step1-install-idt}

La dernière version de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} est installée lorsque vous exécutez la commande.

* Pour Mac et Linux, exécutez la commande suivante :
  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Pour Windows&trade; 10 Pro, exécutez la commande suivante en tant qu'administrateur :
  ```
  [Net.ServicePointManager]::SecurityProtocol = "Tls12"; iex(New-Object Net.WebClient).DownloadString('https://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Cliquez avec le bouton droit de la souris sur l'icône Windows&trade; PowerShell et sélectionnez **Exécuter en tant qu'administrateur**.
  {: tip}

Vous pouvez également télécharger le script du programme d'installation à partir de ce [référentiel GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").

Si vous avez besoin d'utiliser une version 32 bits de l'interface de ligne de commande ou une version antérieure autre que la dernière version pour les environnements dédiés {{site.data.keyword.cloud_notm}}, voir [{{site.data.keyword.cloud_notm}}Editions de l'interface CLI](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").
{: note}

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

1. Connectez-vous à {{site.data.keyword.cloud_notm}} à l'aide de votre IBMid. Si vous avez plusieurs comptes, vous êtes invité à sélectionner le compte à utiliser. Si vous n'indiquez pas de région avec l'option `-r`, vous devez également sélectionner une région.
  ```
  ibmcloud login
  ```
  {: codeblock}
  
  Si vos données d'identification sont rejetées, vous pouvez utiliser un ID fédéré. Pour vous connecter avec un ID fédéré, utilisez l'option `--sso`. Pour plus de détails, voir [Connexion à l'aide d'un ID fédéré](/docs/iam/federated_id?topic=iam-federated_id#federated_id).
  {: tip}

2. Pour accéder aux services Cloud Foundry, vous devez spécifier un espace et une organisation Cloud Foundry. Vous pouvez exécuter la commande suivante pour identifier de manière interactive l'organisation et l'espace :
  ```
  ibmcloud target --cf
  ```
  {: codeblock}

  Si vous savez à quelle organisation et à quel espace le service appartient, vous pouvez utiliser la commande suivante :
  ```
  ibmcloud target -o <value> -s <value>
  ```
  {: codeblock}

## Etapes suivantes
{: #next-steps}

* Vous êtes maintenant prêt à développer et déployer votre première application. Pour plus d'informations, voir [Création et déploiement d'applications à l'aide de l'interface de ligne de commande](/docs/apps?topic=creating-apps-create-deploy-app-cli#create-deploy-app-cli).

* Vous pouvez recevoir des notifications sur les nouvelles éditions CLI {{site.data.keyword.cloud_notm}}. Abonnez-vous au [référentiel d'éditions CLI {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-cli-release/releases/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").
