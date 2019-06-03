---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools per gli IDE JetBrains
{: #ibm-dev-tools-for-jetbrains}

L'estensione {{site.data.keyword.cloud}} Developer Tools per gli IDE JetBrains, che includono `IntelliJ`, `WebStorm`, `Android Studio` e altro, fornisce nuove voci di menu per accedere direttamente ai comandi della CLI {{site.data.keyword.dev_cli_notm}} dall'interno dell'IDE. Puoi accedere rapidamente a un sottoinsieme di comandi `ibmcloud dev` sia per i flussi di lavoro Docker che per quelli Cloud Foundry, che includono la distribuzione dell'applicazione, l'avvio/arresto/riavvio di applicazioni su {{site.data.keyword.cloud_notm}}, la visualizzazione dei log di applicazioni remote e altro ancora. Il tutto senza la necessità di uscire dal contesto dell'editor.
{: shortdesc}

![Acquisizione di schermo di IBM Cloud Developer Tools in esecuzione nell'IDE WebStorm.](jetbrains.png "{{site.data.keyword.cloud_notm}} Developer Tools - menu di esempio in esecuzione nell'IDE WebStorm")


## Dipendenze
{: #jetbrains-dependencies}

Per utilizzare l'estensione {{site.data.keyword.cloud_notm}} Developer Tools per le IDE basate su JetBrains, hai bisogno della [CLI {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) installata sul tuo sistema.

## Installazione
{: #jetbrains-installation}

Il modo migliore per installare l'estensione {{site.data.keyword.cloud_notm}} Developer Tools per l'IDE JetBrains consiste nell'andare alla pagina del [JetBrains del repository GitHub di {{site.data.keyword.cloud_notm}} Developer Tools](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") e attenerti alle istruzioni.

## Utilizzo
{: #jetbrains-usage}

Puoi iniziare con un'applicazione lato server esistente e abilitarla per il cloud o utilizzare la CLI {{site.data.keyword.dev_cli_notm}} per creare una nuova applicazione da un kit starter (`ibmcloud dev create`). Una volta che disponi del progetto della tua applicazione, aprilo nella tua IDE JetBrains.

Per abilitare per il cloud un'applicazione lato server esistente, seleziona **Tools** > **IBM Cloud Developer Tools** > **Enable app for {{site.data.keyword.cloud_notm}}**. Tutti i file necessari vengono selezionati e aggiunti (se necessario) per la distribuzione a {{site.data.keyword.cloud_notm}} utilizzando un'applicazione Cloud Foundry o all'interno di un cluster Kubernetes.

Sviluppa la tua applicazione nativa cloud utilizzando le azioni di creazione, esecuzione e distribuzione di base dal menu di {{site.data.keyword.cloud_notm}} Developer Tools. Se devi eseguire delle azioni che non sono nel menu, apri semplicemente una scheda del terminale e immetti i comandi manualmente.
