---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: docker, docker container, ibmcloud docker, docker run, docker pull, ibmcloud cli, dockerfile, ibmcloud login

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Utilisation d'{{site.data.keyword.dev_cli_notm}} à partir d'un conteneur Docker
{: #using-idt-from-docker}

Le conteneur Docker {{site.data.keyword.dev_cli_notm}} vous permet d'obtenir l'interface CLI {{site.data.keyword.cloud}}, ainsi que les outils suivants :

* `Git`
* `Helm`
* `kubectl`
* `curl`
* Plug-in {{site.data.keyword.dev_cli_notm}}
* Plug-in {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in {{site.data.keyword.registrylong_notm}}
* Plug-in {{site.data.keyword.containerlong_notm}}
* Plug-in `sdk-gen`

## Avant de commencer
{: #idt-docker-prereq}

Vous devez avoir un compte [{{site.data.keyword.cloud_notm}}](https://{DomainName}){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg "Icône de lien externe") et vous devez installer la dernière version Docker stable avant de suivre la procédure décrite ci-après.

## Etape 1. Extraire l'image Docker du concentrateur Docker
{: #step1-pull-docker-image}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Etape 2. Démarrer le conteneur Docker
{: #step2-start-docker}

La commande suivante vous permet de démarrer le conteneur Docker {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Etape 3. Vous connecter à {{site.data.keyword.cloud_notm}} à l'aide de votre IBMid
{: #step3-ibmcloud-login}

```
ibmcloud login
```
{: codeblock}

Si vos données d'identification sont rejetées, vous pouvez utiliser un ID fédéré. Pour plus de détails, voir [Connexion à l'aide d'un ID fédéré](/docs/iam?topic=iam-federated_id#federated_id).
{: tip}

Le plug-in {{site.data.keyword.dev_cli_notm}} CLI utilise deux conteneurs pour faciliter la génération et le test de votre application. Le premier est le conteneur tools, qui contient les utilitaires nécessaires pour générer et tester votre application. Le fichier `Dockerfile` pour ce conteneur est défini par le paramètre [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Vous pouvez le considérer comme un conteneur de développement car il contient les outils qui sont normalement utilisés pour le développement d'un environnement d'exécution particulier.

Le second conteneur est le conteneur "run" qui reproduit fidèlement l'environnement d'exécution réel de votre application une fois cette dernière déployée sur le cloud. Il peut être déployé pour être utilisé dans {{site.data.keyword.cloud_notm}}, par exemple. Par conséquent, un point
d'entrée démarrant votre application est défini. Lorsque vous choisissez d'exécuter votre application via le plug-in d'interface de ligne de commande {{site.data.keyword.dev_cli_notm}}, ce conteneur est utilisé. Le fichier `Dockerfile` pour ce conteneur est défini par le paramètre [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

Vous êtes maintenant prêt à utiliser {{site.data.keyword.dev_cli_notm}} pour gérer des ressources {{site.data.keyword.cloud_notm}} ainsi que pour développer et déployer vos applications.
