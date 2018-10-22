---

copyright:

  years: 2018
lastupdated: "2018-10-11"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Utilisation d'{{site.data.keyword.dev_cli_notm}} à partir d'un conteneur Docker

Le conteneur Docker {{site.data.keyword.dev_cli_notm}} vous permet d'obtenir l'interface CLI {{site.data.keyword.Bluemix}}, ainsi que les outils suivants :

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
{: #prereq}

Vous devez avoir un [compte {{site.data.keyword.Bluemix_notm}} ](https://console.bluemix.net/){: new_window} ![Icône de lin externe](../../../icons/launch-glyph.svg "Icône de lien externe") et vous devez installer la dernière version Docker stable avant d'effectuer les étapes suivantes : 

## Etape 1. Extraire l'image Docker du concentrateur Docker
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Etape 2. Démarrer le conteneur Docker
{: #step2}

La commande suivante vous permet de démarrer le conteneur Docker {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Etape 3. Vous connecter à {{site.data.keyword.Bluemix_notm}} à l'aide de votre IBMid
{: #step3}

```
ibmcloud login
```
{: codeblock}


Si vos données d'identification sont rejetées, vous pouvez utiliser un ID fédéré. Pour plus de détails, voir [Connexion à l'aide d'un ID fédéré](/docs/iam/login_fedid.html#federated_id).
{: tip}

Vous êtes maintenant prêt à utiliser {{site.data.keyword.dev_cli_notm}} pour gérer des ressources {{site.data.keyword.Bluemix_notm}} et développer et déployer vos applications. 
