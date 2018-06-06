---

copyright:

  years: 2018

lastupdated: "2018-05-23"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools per le IDE Jetbrains
{: #ibm-dev-tools-for-jetbrains}

L'estensione IBM Developer per le IDE Jetbrains, che include IntelliJ, WebStorm, Android Studio e altro, fornisce nuove voci del menu per accedere direttamente ai comandi CLI IDT dall'interno dell'IDE. Ti consente di accedere rapidamente a un sottoinsieme di comandi `ibmcloud dev` sia per i flussi di lavoro Docker che Cloud Foundry, che includono la distribuzione dell'applicazione, l'avvio/arresto/riavvio di applicazioni su {{site.data.keyword.Bluemix_notm}}, la visualizzazione dei log di applicazioni remote e altro ancora, il tutto senza la necessità di uscire dal contesto dell'editor.
{:shortdesc}

![Acquisizione schermo di IBM Developer Tools in esecuzione nella IDE WebStorm.](jetbrains.png "Esempio del menu IDT in esecuzione nella IDE WebStorm")

## Dipendenze
{: #dependencies}

Per utilizzare l'estensione IBM Developer Tools per le IDE basate su Jetbrains, hai anche bisogno della [CLI di IBM Cloud Developer Tools](index.html) installata sul tuo sistema.

## Installazione
{: #installation}

Il modo più semplice per installare l'estensione IBM Developers Tools per l'IDE Jetbrains, è di andare alla pagina [IDT Github repo's jetbrains](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) e seguire le istruzioni.

## Utilizzo
{: #usage}

Puoi iniziare con un'applicazione lato server esistente e abilitarla per IBM Cloud o utilizzare la CLI IDT per creare una nuova applicazione da uno StarterKit  (ibmcloud dev create). Una volta che disponi del progetto delle tue applicazioni, aprilo nella tua IDE JetBrains.

Se hai un'applicazione lato server generica, seleziona Strumenti > IBM Cloud Developer Tools > Abilita applicazione per IBM Cloud. Questo controlla tutti i file necessari e li aggiunge dove mancano il che ti consente di creare l'applicazione localmente e distribuirla a IBM Cloud utilizzando un'applicazione Cloud Foundry o in un cluster Kubernetes.

Sviluppa la tua applicazione nativa cloud utilizzando le azioni di creazione/esecuzione/distribuzione di base dal menu IDT. Se hai bisogno di eseguire azioni che non sono nel menu, apri la scheda del terminale e immetti i comandi desiderati manualmente.
