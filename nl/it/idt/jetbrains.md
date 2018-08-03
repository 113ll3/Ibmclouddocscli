---

copyright:

  years: 2018

lastupdated: "2018-07-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools per gli IDE Jetbrains
{: #ibm-dev-tools-for-jetbrains}

L'estensione {{site.data.keyword.Bluemix_notm}} Developer Tools per gli IDE Jetbrains, che includono `IntelliJ`, `WebStorm`, `Android Studio` e altro, fornisce nuove voci di menu per accedere direttamente ai comandi della CLI {{site.data.keyword.dev_cli_notm}} dall'interno dell'IDE. Ti consente di accedere rapidamente a un sottoinsieme di comandi `ibmcloud dev` sia per i flussi di lavoro Docker che per quelli Cloud Foundry, che includono la distribuzione dell'applicazione, l'avvio/arresto/riavvio di applicazioni su {{site.data.keyword.Bluemix_notm}}, la visualizzazione dei log di applicazioni remote e altro ancora, il tutto senza la necessità di uscire dal contesto dell'editor.
{:shortdesc}

![Acquisizione di schermo di IBM Cloud Developer Tools in esecuzione nell'IDE WebStorm.](jetbrains.png "{{site.data.keyword.Bluemix_notm}} Developer Tools - menu di esempio in esecuzione nell'IDE WebStorm")

## Dipendenze
{: #dependencies}

Per utilizzare l'estensione {{site.data.keyword.Bluemix_notm}} Developer Tools per gli IDE basati su Jetbrains, avrai bisogno anche della [CLI {{site.data.keyword.dev_cli_notm}}](index.html) installata sul tuo sistema.

## Installazione
{: #installation}

Il modo più semplice per installare l'estensione {{site.data.keyword.Bluemix_notm}} Developer Tools per l'IDE Jetbrains consiste nell'andare alla pagina dei [jetbrains del repository Github di {{site.data.keyword.Bluemix_notm}} Developer Tools](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) e attenersi alle istruzioni.

## Utilizzo
{: #usage}

Puoi iniziare con un'applicazione lato server esistente e abilitarla per {{site.data.keyword.Bluemix_notm}} o utilizzare la CLI {{site.data.keyword.dev_cli_notm}} per creare una nuova applicazione da uno StarterKit (ibmcloud dev create). Una volta che disponi del progetto della tua applicazione, aprilo nella tua IDE JetBrains.

Se hai un'applicazione lato server generica, seleziona Strumenti > IBM Cloud Developer Tools > Abilita applicazione per IBM Cloud. Questo controllerà tutti i file necessari e aggiungerà quelli mancanti, il che ti consentirà di creare l'applicazione localmente e di distribuirla a {{site.data.keyword.Bluemix_notm}} utilizzando un'applicazione Cloud Foundry oppure all'interno di un cluster Kubernetes.

Sviluppa la tua applicazione nativa cloud utilizzando le azioni di creazione/esecuzione/distribuzione di base dal menu degli strumenti per gli sviluppatori {{site.data.keyword.Bluemix_notm}}. Se devi eseguire delle azioni che non sono nel menu, apri semplicemente la scheda Terminale e immetti i comandi desiderati manualmente.
