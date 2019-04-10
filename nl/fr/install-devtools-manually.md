---

copyright:
  years: 2019
lastupdated: "2019-02-28"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installation manuelle des composants du plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-manually}

Si vous préférez avoir un contrôle plus granulaire pour l'installation des composants Developer Tools, vous pouvez les installer manuellement en procédant comme suit. Sinon, tous les composants prérequis sont automatiquement installés pour la plupart des utilisateurs en utilisant les [programmes d'installation de plateforme](/docs/cli?topic=cloud-cli-ibmcloud-cli#step1-install-idt).
{: shortdesc}

## Avant de commencer
{: cli-before-you-begin}

* Installez l'interface CLI [{{site.data.keyword.cloud}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) autonome, de telle sorte que vous puissiez prendre en charge l'installation des plug-in de ligne de commande pour `ibmcloud`.
* Installez la commande [curl](https://curl.haxx.se/download.html){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") pour le téléchargement de packages via la ligne de commande.

## Etape 1. Installation du plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-idt}

Vous pouvez utiliser les commandes de l'interface CLI {{site.data.keyword.cloud_notm}} Developer Tools (ibmcloud dev) pour créer une application, la gérer, la déployer, la déboguer et la tester.

Installez le plug-in `dev` en exécutant la commande suivante : 
```
ibmcloud plugin install dev
```
{: codeblock}

## Etape 2. Installation de Docker
{: #install-devtools-docker}

Pour l'exécution et le débogage d'applications localement, installez [Docker](https://www.docker.com/get-docker){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").

## Etape 3. Installation de Kubernetes
{: #idt-install-kube}

Kubernetes est un moteur d'orchestration de conteneur open source pour l'automatisation du déploiement, la mise à l'échelle et la gestion des applications conteneurisées.

Pour prendre en charge les déploiements conteneurisés, installez Kubernetes pour votre plateforme :

* MacOS :
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
  ```
  {: codeblock}

* Linux :
  ```
  curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
  ```
  {: codeblock}

* Windows :
  ```
  curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
  ```
  {: codeblock}

## Etape 4. Installation des plug-in d'interface de ligne de commande Kubernetes
{: #idt-install-kubernetes-cli-plugins}

Pour gérer les déploiements Kubernetes à partir de la ligne de commande, installez les plug-in de conteneur suivants :

* Installez le plug-in `container-registry` :
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

* Installez le plug-in `container-service` :
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Pour plus d'informations, voir [Configuration de l'interface CLI et de l'API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Etape 5. Installation de Helm
{: #idt-install-helm}

Installez [Helm](https://helm.sh/docs/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe"), qui est un gestionnaire de packages Kubernetes.

* Utilisateurs MacOS et Linux, exécutez les commandes suivantes :
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Les utilisateurs Windows peuvent télécharger et installer le [fichier binaire Helm](https://github.com/kubernetes/helm/releases/tag/v2.7.2){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").

## Etape 6. Installation du plug-in d'interface de ligne de commande {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

Vous pouvez utiliser l'interface de ligne de commande {{site.data.keyword.openwhisk}} pour gérer vos fragments de code dans les actions, créer des déclencheurs et des règles afin de permettre à vos actions de répondre aux événements et de regrouper les actions dans des packages.

Pour installer le plug-in de l'interface de ligne de commande {{site.data.keyword.openwhisk_short}}, exécutez la commande suivante :
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Pour plus d'informations, voir [Configuration de l'interface de ligne de commande {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cloudfunctions_cli#cloudfunctions_cli).

## Etape 7. Installation du plug-in d'interface de ligne de commande SDK Generator
{: #idt-install-sdk-gen}

En tant que développeur sous {{site.data.keyword.cloud_notm}}, vous pouvez utiliser ce plug-in pour générer des SDK depuis votre définition d'API REST conforme à la [spécification Open API ](https://www.openapis.org/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe"). Lorsque vous apportez des modifications à votre définition d'API REST, vous pouvez utiliser ce plug-in pour ne régénérer que le SDK au lieu de régénérer l'ensemble du projet.

Installez le plug-in d'interface de ligne de commande SDK Generator :
```
ibmcloud plugin install sdk-gen
```
{: codeblock}

Pour plus d'informations, voir [Générateur de SDK](/docs/cli/sdk?topic=cloud-cli-sdk-cli#sdk-cli).
