---

copyright:

  years: 2015, 2018

lastupdated: "2018-05-14"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Panoramica di {{site.data.keyword.dev_cli_notm}}
{: #overview}

{{site.data.keyword.dev_cli_notm}} è un approccio della riga di comando per la creazione, lo sviluppo e la distribuzione delle applicazioni per gli sviluppatori che desiderano utilizzare una riga di comando per sviluppare le applicazioni web end-to-end, mobile e del microservizio. Inizia rapidamente a lavorare con l'insieme di strumenti consigliato eseguendo uno di questi script.
{: shortdesc} 

## Prerequisiti per {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Registrati per [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

* Se stai utilizzando Microsoft Windows&trade;, devi utilizzare Windows 10 o successivi.

* Devi utilizzare il canale stabile per Docker, con una versione minima di 1.13.1.

## Come installare {{site.data.keyword.dev_cli_notm}}
{: #installation}

Per installare l'insieme di strumenti, puoi eseguire il comando pertinente per avviare il programma di installazione.  Questo installa i seguenti strumenti consigliati per lo sviluppo {{site.data.keyword.Bluemix_notm}} (se non sono già installati): `Homebrew` (solo Mac), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, CLI {{site.data.keyword.Bluemix_notm}}, plugin {{site.data.keyword.dev_cli_notm}}, plugin Cloud Functions, plugin Container Registry, plugin Container Service e plugin `sdk-gen`.

**Mac e Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Nota: apri Windows PowerShell facendo clic con il tasto destro e selezionando "Run as Administrator".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}


## Altri link per esplorare ulteriormente la {{site.data.keyword.dev_cli_notm}}

- [Configurazione dettagliata](/docs/cli/idt/setting_up_idt.html)
- [Utilizzo](/docs/cli/idt/index.html)
- [Comandi](/docs/cli/idt/commands.html)
- [Plugin CLI](/docs/cli/reference/bluemix_cli/extend_cli.html)
- [Estensione IDE VSCode](/docs/cli/idt/vscode.html)
- [Installa la CLI IBM Cloud manualmente](/docs/cli/reference/bluemix_cli/get_started.html)
