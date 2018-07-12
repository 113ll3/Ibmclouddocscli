---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-27"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Introduzione alla CLI {{site.data.keyword.Bluemix_notm}}
{: #overview}

In questa esercitazione, vengono forniti i passi per installare una serie di strumenti per sviluppatori {{site.data.keyword.Bluemix}}, verificare l'installazione e configurare il tuo ambiente. Gli strumenti per sviluppatori {{site.data.keyword.Bluemix}} offrono un approccio da riga di comando per la creazione, lo sviluppo e la distribuzione di applicazioni web, mobili e di microservizio end-to-end. 
{:shortdesc}

Con questa installazione, ottieni la CLI {{site.data.keyword.Bluemix_notm}}, oltre ai seguenti strumenti: 

* `Homebrew` (solo Mac)
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

## Prima di iniziare
{: #prereq}

Hai bisogno di un [account {{site.data.keyword.Bluemix_notm}} ](https://console.bluemix.net/){: new_window} ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno") e dei seguenti requisiti di sistema:

* Se stai utilizzando Microsoft Windows&trade;, devi utilizzare Windows 10 o successivi.
* Devi utilizzare il canale stabile per Docker con una versione minima di 1.13.1.

## Passo 1: Esegui il comando di installazione
{: #step1}

* Per Mac e Linux, immetti il seguente comando:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br><br>

* Per Windows 10, immetti il seguente comando come amministratore:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br><br>
  Fai clic con il tasto destro del mouse sull'icona Windows PowerShell e seleziona **Run as administrator**.
  {: tip}

## Passo 2: Verifica l'installazione
{: #step2}

Per verificare che la CLI e gli strumenti per sviluppatori siano stati installati correttamente, esegui il comando `help`:

```
ibmcloud dev help
```
{: codeblock}
<br><br>
L'output elenca le istruzioni di utilizzo, la versione corrente e i comandi supportati.

## Passo 3: Configura il tuo ambiente
{: #step3}

1. Stabilisci una connessione a un endpoint API nella tua regione {{site.data.keyword.Bluemix_notm}}. Ad esempio, immetti il seguente comando per stabilire una connessione alla regione Stati Uniti Sud {{site.data.keyword.Bluemix_notm}}:

	```
	ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Accedi a {{site.data.keyword.Bluemix_notm}} con il tuo ID IBM.

	```
	ibmcloud login
	```
	{: codeblock}
<br><br>
	Se le tue credenziali vengono rifiutate, puoi utilizzare un ID federato. Per ulteriori dettagli, vedi [Accesso con un ID federato](/docs/iam/login_fedid.html#using-an-api-key).
	{: tip}

3. Imposta la tua organizzazione e il tuo spazio.

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Passi successivi
{: #next-steps}

Sei ora pronto per sviluppare e distribuire la tua prima applicazione. Per ulteriori informazioni, consulta [Sviluppo e distribuzione delle tue applicazioni](/docs/cli/idt/index.html).
