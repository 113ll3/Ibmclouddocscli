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

# Utilizzo {{site.data.keyword.dev_cli_notm}} da un contenitore Docker

Con il contenitore Docker di {{site.data.keyword.dev_cli_notm}}, ottieni la CLI {{site.data.keyword.Bluemix}}, oltre ai seguenti strumenti:

* `Git`
* `Helm`
* `kubectl`
* `curl`
* Plug-in {{site.data.keyword.dev_cli_notm}}
* Plug-in {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in {{site.data.keyword.registrylong_notm}}
* Plug-in {{site.data.keyword.containerlong_notm}}
* Plug-in `sdk-gen`

## Prima di iniziare
{: #prereq}

Hai bisogno di un [account {{site.data.keyword.Bluemix_notm}}](https://console.bluemix.net/){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno") e devi installare la versione Docker stabile più recente prima di procedere con i seguenti passi.

## Passo 1. Estrai l'immagine Docker dall'hub Docker.
{: #step1}

```
docker pull ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Passo 2. Avvia il contenitore Docker.
{: #step2}

Utilizza il seguente comando per avviare il contenitore Docker di {{site.data.keyword.dev_cli_notm}}.

```
docker run -ti ibmcom/ibm-cloud-developer-tools-amd64
```
{: codeblock}

## Passo 3: Accedi a {{site.data.keyword.Bluemix_notm}} con il tuo ID IBM.
{: #step3}

```
ibmcloud login
```
{: codeblock}


Se le tue credenziali vengono rifiutate, puoi utilizzare un ID federato. Per ulteriori dettagli, vedi [Accesso con un ID federato](/docs/iam/login_fedid.html#federated_id).
{: tip}

Ora sei pronto a utilizzare la {{site.data.keyword.dev_cli_notm}} per gestire le risorse {{site.data.keyword.Bluemix_notm}} e sviluppare e distribuire le tue applicazioni.
