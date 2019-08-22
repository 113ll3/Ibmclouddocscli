---

copyright:
  years: 2019
lastupdated: "2019-06-19"

keywords: IBM Cloud Developer Tools CLI, manual, manual install, tools, components, developer tools, ibmcloud cli, ibmcloud, ibmcloud dev, cli, plugin, plug-in, command line, command-line, developer tools, kubernetes, kubectl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}

# Installation manuelle du plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-manually}

Vous pouvez installer manuellement le plug-in d'interface de ligne de commande {{site.data.keyword.cloud}} Developer Tools si vous préférez avoir un contrôle plus granulaire pour l'installation des composants. Sinon, tous les composants prérequis sont automatiquement installés pour la plupart des utilisateurs en utilisant les [programmes d'installation de plateforme](/docs/cli?topic=cloud-cli-getting-started#step1-install-idt).
{: shortdesc}

## Avant de commencer
{: cli-before-you-begin}

* Installez l'interface de ligne de commande [{{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli) autonome pour obtenir du support en matière d'installation des plug-in de ligne de commande pour {{site.data.keyword.cloud_notm}}.
* Installez la commande [curl](https://curl.haxx.se/download.html){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") pour le téléchargement de packages via la ligne de commande.

## Installation du plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}} Developer Tools
{: #install-devtools-idt}

Vous pouvez utiliser les commandes de l'interface CLI {{site.data.keyword.cloud_notm}} Developer Tools pour créer une application, la gérer, la déployer, la déboguer et la tester.

Pour installer le plug-in {{site.data.keyword.cloud_notm}} Developer Tools, exécutez la commande suivante : 
```
ibmcloud plugin install dev
```
{: codeblock}

## Installation de Docker
{: #install-devtools-docker}

Pour l'exécution et le débogage d'applications localement, installez [Docker](https://www.docker.com/get-started){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").

## Installation de l'outil de ligne de commande Kubernetes
{: #idt-install-kube}

Pour afficher une version locale du tableau de bord Kubernetes et pour déployer des applications dans vos clusters, installez l'[outil de ligne de commande Kubernetes](https://kubernetes.io/docs/tasks/tools/install-kubectl/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe") pour votre plateforme :

* Mac :
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

Le préfixe pour l'exécution des commandes lors de l'utilisation de l'outil de ligne de commande Kubernetes est `kubectl`. Pour plus d'informations, voir [Configuration de l'interface CLI et de l'API](/docs/containers?topic=containers-cs_cli_install#cs_cli_install).

## Installation du plug-in d'interface de ligne de commande de {{site.data.keyword.cos_full_notm}}

Le plug-in {{site.data.keyword.cos_full_notm}} étend l'interface de ligne de commande {{site.data.keyword.cloud_notm}} avec un encapsuleur d'API pour l'utilisation de ressources Object Storage.

* Pour installer le plug-in {{site.data.keyword.cos_full_notm}}, exécutez la commande suivante :
  ```
  ibmcloud plugin install cloud-object-storage
  ```
  {: codeblock}

Pour plus d'informations, voir la [référence de commande {{site.data.keyword.cos_full_notm}}](/docs/cloud-object-storage-cli-plugin?topic=cloud-object-storage-cli-ic-cos-cli).

## Installation du plug-in d'interface de ligne de commande de {{site.data.keyword.registrylong_notm}}
{: #idt-install-container-registry-cli-plugin}

Vous pouvez utiliser le plug-in d'interface de ligne de commande `container-registry` pour configurer votre propre espace de nom d'image dans un registre privé géré et hébergé par IBM. Vous pourrez y stocker et partager des images Docker avec tous les utilisateurs de votre compte {{site.data.keyword.cloud_notm}}.

* Pour installer le plug-in {{site.data.keyword.registrylong}}, exécutez la commande suivante :
  ```
  ibmcloud plugin install container-registry
  ```
  {: codeblock}

Pour plus d'informations, voir la [référence de commande {{site.data.keyword.registrylong}}](/docs/services/Registry?topic=container-registry-cli-plugin-containerregcli).

## Installation du plug-in d'interface de ligne de commande de {{site.data.keyword.containerlong_notm}}
{: #idt-install-kubernetes-cli-plugin}

Création et gestion de clusters Kubernetes dans {{site.data.keyword.containerlong}}

* Pour installer le plug-in {{site.data.keyword.registryshort_notm}}, exécutez la commande suivante :
  ```
  ibmcloud plugin install container-service
  ```
  {: codeblock}

Pour plus d'informations, voir la référence de commande [{{site.data.keyword.registryshort_notm}}](/docs/containers-cli-plugin?topic=containers-cli-plugin-cs_cli_reference).

## Installation de Helm
{: #idt-install-helm}

Installez [Helm](https://helm.sh/docs/){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe"), qui est un gestionnaire de packages Kubernetes.

* Utilisateurs Mac et Linux, exécutez les commandes suivantes :
  ```
  export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
  ```
  {: codeblock}

* Les utilisateurs Windows peuvent télécharger et installer le [fichier binaire Helm](https://github.com/helm/helm/releases/tag/v2.7.2){: new_window} ![Icône de lien externe](../icons/launch-glyph.svg "Icône de lien externe").

## Installation du plug-in d'interface de ligne de commande de {{site.data.keyword.openwhisk_short}}
{: #idt-install-functions}

Vous pouvez utiliser le plug-in d'interface de ligne de commande {{site.data.keyword.openwhisk}} pour gérer vos fragments de code dans les actions, rassembler les actions dans des packages et créer des déclencheurs et des règles afin de permettre à vos actions de répondre aux événements.

Pour installer le plug-in de l'interface de ligne de commande {{site.data.keyword.openwhisk_short}}, exécutez la commande suivante :
```
ibmcloud plugin install cloud-functions
```
{: codeblock}

Pour plus d'informations, voir [Installation du plug-in d'interface de ligne de commande de {{site.data.keyword.openwhisk_short}}](/docs/openwhisk?topic=cloud-functions-cli_install).

