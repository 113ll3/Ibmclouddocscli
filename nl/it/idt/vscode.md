---

copyright:
  years: 2017, 2019
lastupdated: "2019-04-04"

keywords: cli, ibm cloud developer tools, visual studio code, install developer tools, developer extension, vscode cli, vscode plugin, cloud foundry vscode

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools per Visual Studio Code
{: #ibm-dev-tools-for-vscode}

L'estensione IBM Cloud Developer Tools per Visual Studio Code fornisce l'accesso alle funzionalità dalla CLI IBM Developer direttamente all'interno della tavolozza dei comandi dell'editor Visual Studio Code. Puoi accedere rapidamente a un sottoinsieme di comandi `ibmcloud dev` sia per i flussi di lavoro Docker che per quelli Cloud Foundry, che includono la distribuzione dell'applicazione, l'avvio/arresto/riavvio di applicazioni su {{site.data.keyword.cloud}}, la visualizzazione dei log di applicazioni remote e altro ancora, il tutto senza la necessità di uscire dal contesto dell'editor.
{:shortdesc}

![Acquisizione della schermata di download dell'estensione IBM Developer Tools.](vscode.png "Schermata di download dell'estensione in Visual Studio Code")

## Dipendenze
{: #vscode-dependencies}

Per utilizzare l'estensione IBM Cloud Developer Tools per Visual Studio Code, hai bisogno della [CLI di {{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) e del plug-in della CLI {{site.data.keyword.cloud_notm}} installati sul tuo sistema.

## Installazione
{: #vscode-installation}

Il modo più semplice per installare l'estensione {{site.data.keyword.dev_cli_notm}} è quello di utilizzare il comando 'quick open' di Visual Studio Code:

1. Apri il riquadro comandi 'quick open' utilizzando la seguente combinazione di tasti dall'interno dell'editor:

  * **Mac:** `cmd + p`
  * **Windows / Linux:** `ctrl + p`

2. Immetti il comando `ext install ibm-developer` e premi Invio per installare l'estensione {{site.data.keyword.dev_cli_notm}} all'interno dell'editor Visual Studio Code.

In alternativa, puoi installare l'estensione {{site.data.keyword.dev_cli_notm}} mediante la finestra di gestione "Extensions":

1. Apri la barra laterale **Extensions** nell'editor Visual Studio Code ed effettua quindi la ricerca utilizzando la stringa `publisher:IBM Developer`. L'estensione {{site.data.keyword.dev_cli_notm}} viene visualizzata nei risultati della ricerca.  
2. Fai clic su **Installa** per iniziare l'installazione.

Puoi anche accedere all'[estensione IBM Cloud Developer Tools direttamente all'interno di Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").

## Utilizzo
{: #vscode-usage}

Puoi avviare i comandi dell'estensione utilizzando il riquadro comandi di Visual Studio Code.

Per prima cosa, apri il riquadro comandi utilizzando la seguente combinazione di tasti:

* **Mac:** `cmd + shift + p`
* **Windows / Linux:** `ctrl + shift + p`

Successivamente, immetti o seleziona il comando da avviare. Puoi digitare 'ibmcloud' all'interno del riquadro comandi per visualizzare l'elenco di tutti i comandi disponibili.

### Utilizzo dell'estensione IBM Developer per i flussi di lavoro Docker (contenitori Docker)
{: #usage-docker}

Puoi iniziare a utilizzare i flussi di lavoro `ibmcloud dev` in pochi passi:
* Crea un progetto utilizzando uno dei due seguenti metodi:
  * Utilizza la [console web {{site.data.keyword.cloud_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") e scarica il codice generato
  * Utilizza il plug-in della CLI {{site.data.keyword.cloud_notm}} Developer Tools e genera un progetto utilizzando il comando [ibmcloud dev create](/docs/cli/idt?topic=cloud-cli-idt-cli#create).
* Apri la cartella del progetto in locale nell'editor Visual Studio Code
* Utilizza il comando `ibmcloud dev build` per creare l'applicazione in un'immagine Docker
* Utilizza il comando `ibmcloud dev debug` per eseguire l'applicazione nel Docker locale per lo sviluppo
> Nota: per eseguire il debug di un'applicazione Node.js in esecuzione all'interno del contenitore Docker locale, hai bisogno di [aggiungere una configurazione di debug per il contenitore locale](https://github.com/IBM-Cloud/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").
* Utilizza il comando `ibmcloud dev run` per eseguire l'applicazione nel Docker locale in modalità di rilascio
* Utilizza il comando `ibmcloud dev deploy` per distribuire l'applicazione a un runtime Cloud Foundry su {{site.data.keyword.cloud_notm}}

### Utilizzo dell'estensione IBM Developer per i flussi di lavoro Cloud Foundry
{: #usage-cloud-foundry}

Per gli utenti che stanno attualmente distribuendo le applicazioni ai runtime Cloud Foundry su IBM {{site.data.keyword.cloud_notm}}, è presente il supporto anche per la serie di operazioni `cf`.

Puoi iniziare a utilizzare i flussi di lavoro Cloud Foundry in pochi passi:
* Crea una nuova applicazione Cloud Foundry
  * Utilizza la [console web {{site.data.keyword.cloud_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") e scarica il codice starter.
  * Crea una nuova applicazione Cloud Foundry manualmente
* Apri la cartella del progetto in locale nell'editor Visual Studio Code
* Utilizza `ibmcloud cf apps` per elencare tutte le tue applicazioni
* Utilizza `ibmcloud cf push` per distribuire una build della tua applicazione al runtime Cloud Foundry
* Utilizza ibmcloud `cf <start/stop/restage/restart>` per modificare lo stato della tua applicazione
* Utilizza `ibmcloud cf logs` per visualizzare il flusso di log attivo per la tua applicazione
  * Utilizza `ibmcloud cf logs` per arrestare il flusso di log
