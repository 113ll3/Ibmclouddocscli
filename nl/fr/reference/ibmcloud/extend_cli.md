---

copyright:

  years: 2015, 2018
lastupdated: "2018-11-30"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}

# Extension de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} avec des plug-in
{: #plug-ins}

L'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} prend en charge une structure de plug-in destinée à étendre ses fonctionnalités. Vous pouvez installer un plug-in depuis un référentiel, une URL WEB, ou installer localement un fichier binaire de plug-in.

Le [{{site.data.keyword.Bluemix_notm}} référentiel de plug-in d'interface de ligne de commande](https://tools.ng.bluemix.net){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg) est le référentiel officiel d'hébergement des plug-in.

Pour explorer d'autres commandes de gestion de plug-in, exécutez `ibmcloud plugin` afin d'afficher les messages d'aide.
{: tip}

## Installation d'un plug-in à partir du référentiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}

### Etape 1 : Rechercher le plug-in

1. Utilisez la commande `ibmcloud plugin repo-plugins -r REPO_NAME` pour rechercher un plug-in dans le référentiel.
2. Le référentiel officiel de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} est nommé IBM Cloud ; vous pouvez rechercher les plug-in officiels comme indiqué dans l'exemple suivant :

  ```
  $ ibmcloud plugin repo-plugins
  Getting plug-ins from repository 'IBM Cloud'...

  Repository: IBM Cloud
  Name           Description                                    Versions
  auto-scaling   IBM Cloud CLI plugin for Auto-Scaling service    0.2.1, 0.2.2
  nsg            IBM Cloud Network Security Group plugin          0.1.1

  ```

### Etape 2 : Installer le plug-in

Utilisez la commande `ibmcloud plugin install PLUGIN_NAME -r REPO_NAME` pour installer le plug-in. Par exemple, utilisez la commande suivante pour installer un plug-in à partir du référentiel de plug-in IBM officiel 'IBM Cloud' :

  ```
  $ ibmcloud plugin install auto-scaling 
  Looking up 'auto-scaling' from repository 'IBM Cloud'...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload062468676/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ```

## Installation locale d'un plug-in

Utilisez la commande `ibmcloud plugin install LOCAL_FILE_NAME` pour installer un fichier binaire de plug-in sur votre poste local. Par exemple :

  ```
  $ ibmcloud plugin install ./auto-scaling-darwin-amd64-0.2.2
  Installing plugin './auto-scaling-darwin-amd64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  $
  ```

## Installation d'un plug-in à partir d'une URL Web

Utilisez la commande `ibmcloud plugin install URL` pour installer un plug-in directement à partir d'une URL Web. Par exemple :

  ```
  ~$ ibmcloud plugin install https://plugins.ng.bluemix.net/downloads/bluemix-plugins/auto-scaling/auto-scaling-darwin-amd64-0.2.2
  Attempting to download the binary file...
  9857792 bytes downloaded
  Installing plugin '/var/folder/v7/l3hnkz0x0b9b5mf1fyxh7yw00000gn/T/BluemixFileDownload274645142/auto-scaling-darwin-adm64-0.2.2'...
  OK
  Plugin 'auto-scaling 0.2.2' was successfully installed.
  ~$
  ```
