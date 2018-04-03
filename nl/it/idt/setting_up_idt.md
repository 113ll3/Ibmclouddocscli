---
copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Configurazione di {{site.data.keyword.dev_cli_notm}}
{: #add-cli}

{{site.data.keyword.dev_cli_short}} è un approccio della riga di comando per la creazione, lo sviluppo e la distribuzione delle applicazioni per gli sviluppatori che desiderano utilizzare una riga di comando per sviluppare le applicazioni web end-to-end, mobile e del microservizio.
{: shortdesc}

## Prerequisiti
{: #prereq}

Registrati per [{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net).

*  Se stai utilizzando Microsoft Windows&trade;, devi utilizzare Windows 10 o successivi.

* Devi utilizzare il canale stabile per Docker, con una versione minima di 1.13.1. 

## Installa
{: #installation}

Per installare lo strumento, puoi eseguire il comando pertinente per richiamare il nostro programma di installazione. Questo installerà anche le dipendenze, come la CLI IBM Cloud, Kubernetes, Helm e Docker. Per installarle, utilizza questa procedura di installazione: 

**Mac e Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

Convalida la riuscita dell'installazione del plugin immettendo il seguente comando:   

```
bx dev
```
{: codeblock}

## Configura il tuo ambiente 
{: #configure-environment}

1. Collegati a un endpoint API nella tua [regione {{site.data.keyword.Bluemix_notm}}](/docs/overview/cf.html#ov_intro_reg). Ad esempio, immetti il seguente comando per stabilire una connessione alla regione Stati Uniti Sud {{site.data.keyword.Bluemix_notm}}:

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Accedi a {{site.data.keyword.Bluemix_notm}} con il tuo ID IBM. 

	```
	bx login
	```
	{: codeblock}

	**Nota:** se le tue credenziali vengono rifiutate, puoi utilizzare un ID federato. Segui questa procedura per l'autenticazione utilizzando l'ID federato. 

	1. Accedi a [{{site.data.keyword.iamshort}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Seleziona **Crea chiave API**.
		* Immetti un nome e una descrizione per apiKey 
	3. Scarica la tua apiKey. 
	4. Apri il file e copia il valore dal campo `apiKey`. 
	5. Accedi utilizzando il seguente comando: 

		```
		bx login --apikey <value>
		```
		{: codeblock}

3. Imposta la tua ORGANIZZAZIONE e SPAZIO utilizzando: 

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## Ulteriori informazioni
{: #learn}

Ora che hai installato la tua {{site.data.keyword.dev_cli_short}}, puoi imparare come utilizzare questo potente strumento:
- [Introduzione alla CLI IDT](index.html)
- [Comandi IDT (bx dev)](commands.html)
- [Developer Tools per il codice VS](vscode.html)
- [Developer Tools per l'IDE Jetbrains](jetbrains.html)

Controlla le [esercitazioni](/docs/apps/tutorials/tutorial_bff.html) che mostrano come creare le applicazioni native cloud utilizzando la {{site.data.keyword.dev_cli_short}}.

## Documentazione aggiuntiva
{: #learn-more}

Le seguenti risorse possono essere utili quando sviluppi le applicazioni native cloud con la CLI di IBM Developer Tools: 

- [Pagina di destinazione principale di IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - Pagina del prodotto principale per la CLI IDT
- [IBM Developer Tools Installer](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - Repository GitHub pubblico con le istruzioni di installazione dettagliate
- [IBM Cloud App Service](https://console.bluemix.net/developer/appservice) - La pagina della console IBM Cloud che è complementare agli strumenti IDT di creazione e gestione delle applicazioni native cloud
- [IBM Cloud Tech's Slack - #developer-tools channel](https://ibm-cloud-tech.slack.com) - Discuti degli strumenti IDT, ricevi risposte, suggerisci idee e altro
	- [Request team access](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Incentrati sul linguaggio**

- [Node,js on IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blog ed esercitazioni**

- [Deploying to IBM Cloud private with IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on IBM Cloud with the IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
