---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Sviluppo e distribuzione delle tue applicazioni
{: #developing}

Lo sviluppo di applicazioni native cloud con la CLI {{site.data.keyword.dev_cli_notm}} segue un flusso abbastanza semplice:

1. [Crea o abilita un'applicazione per la distribuzione](#idt-create).
2. [Codifica, crea ed esegui](#code-build-run) la tua applicazione localmente utilizzando i contenitori.
3. [Distribuisci](#cli-deploy) la tua applicazione a {{site.data.keyword.cloud_notm}}.

## Crea o abilita un'applicazione per la distribuzione cloud
{: #idt-create}

Puoi creare un'applicazione in diversi modi.
- [Console web dei servizi dell'applicazione](https://cloud.ibm.com/developer/appservice/dashboard) per i microservizi e le applicazioni web generici
- [Dashboard Watson](https://cloud.ibm.com/developer/watson/dashboard) per la creazione di applicazioni starter abilitate alle funzionalità basate su Watson.
    - Altri dashboard basati sull'industria e la tecnologia sono disponibili dal menu "Hamburger" nella homepage {{site.data.keyword.cloud_notm}}. Hanno tutti un approccio simile all'utilizzo dei kit starter per creare nuove applicazioni.
- Il comando [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) delle CLI {{site.data.keyword.dev_cli_notm}} permette di creare una nuova applicazione.
- Il comando [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) delle CLI {{site.data.keyword.dev_cli_notm}} permette di abilitare velocemente il cloud per un'applicazione lato server esistente.

Per ognuno dei metodi di creazione precedenti, il flusso è simile. Seleziona il tipo di progetto, il linguaggio di implementazione e il modello dell'applicazione da utilizzare. Puoi anche scegliere di aggiungere servizi alla tua applicazione, come l'autenticazione o la persistenza. Infine puoi aggiungere la funzionalità DevOps all'applicazione che fornisce una toolchain completa del controllo di origine e le comunicazioni con il team. Inclusa una pipeline che viene attivata ad ogni commit per convalidare, creare e distribuire la tua applicazione a {{site.data.keyword.cloud_notm}}.

![Flusso di creazione di esempio che utilizza la CLI {{site.data.keyword.dev_cli_notm}} ](create_flow.png "Flusso di creazione di esempio che utilizza la CLI {{site.data.keyword.dev_cli_notm}} ")

La CLI {{site.data.keyword.dev_cli_notm}} lavora a stretto contatto per fornire un'esperienza ottimale durante lo sviluppo. I progetti creati dalle console web forniscono un pulsante **Download code** per scaricare il codice sorgente generato sulla tua workstation per un ulteriore sviluppo.

### Comandi CLI utili
{: #helpful}

I seguenti comandi CLI `ibmcloud dev` consentono di lavorare con il tuo progetto e le console web:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) Utilizzato per scaricare un codice di origine delle applicazioni sulla tua workstation.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) Apre il tuo browser alla pagina del progetto dell'applicazione corrente in {{site.data.keyword.cloud_notm}}.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) Il comando per creare una nuova applicazione.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) Utilizzato per eliminare l'applicazione corrente dall'area del progetto {{site.data.keyword.cloud_notm}}.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) Il comando per abilitare nel cloud un'applicazione lato server esistente.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) Per ottenere le credenziali richieste dal progetto per abilitare l'utilizzo di servizi associati.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) Per elencare tutte le applicazioni che vengono create nell'organizzazione o spazio attualmente selezionati, dalla CLI o dalle console.

### Esplorazione della struttura del progetto dell'applicazione
{: #exploring-project}

I progetti creati o abilitati per l'utilizzo con gli strumenti per gli sviluppatori sono forniti con le impostazioni preconfigurate incapsulate nel file `cli-config.yml`. `cli-config.yml` ha delle voci predefinite utilizzate dai comandi `ibmcloud dev` che puoi sovrascrivere con dei valori passati attraverso la riga di comando.

### Video e blog di riferimento
{: #ref1}

- Video: [Installazione di {{site.data.keyword.cloud_notm}} Developer Tools su Ubuntu Linux&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")
- Blog: [Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")

## Codifica, crea ed esegui
{: #code-build-run}

Una volta che il tuo progetto è stato creato, tocca a te farlo diventare qualcosa di utile. Il flusso generale consiste nel modificare il codice sorgente e quindi eseguire un comando [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) per compilare l'applicazione in un contenitore locale specifico per il linguaggio e la configurazione della tua applicazione. A seconda del linguaggio e del generatore delle tue applicazioni utilizzati, ci sono uno o più contenitori predefiniti per supportare la creazione e l'esecuzione localmente. Di solito, c'è un contenitore "degli strumenti" per le build e il debug locale. Questo contenitore ha ulteriori strumenti e funzionalità per aiutarti nello sviluppo. Esiste inoltre un contenitore "di esecuzione" che simula l'ambiente di runtime della tua applicazione dopo che è stata distribuita nel cloud, in Cloud Foundry o in un ambiente del contenitore basato su Kubernetes di IBM.

Sei libero di utilizzare qualsiasi IDE o editor preferisci per codificare la tua applicazione. {{site.data.keyword.IBM_notm}} offre un'estensione per l'editor Microsoft&trade; Visual Studio Code (VSCode) che ti consente di accedere a tutti i comandi IDE direttamente nell'editor.

Dopo che il progetto è stato creato, esegui la tua applicazione utilizzando [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) o [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug). L'applicazione viene eseguita all'interno del contenitore appropriato. Alcuni modelli delle applicazioni supportano più contenitori esterni alle tue applicazioni. Le applicazioni vengono avviate e configurate automaticamente durante l'esecuzione o il debug. Esiste anche un comando [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) che esegue gli eventuali scenari di test associati all'applicazione.

### Come vengono utilizzati i contenitori locali
{: #local-containers}

La CLI {{site.data.keyword.dev_cli_long}} utilizza due contenitori per la creazione e la verifica della tua applicazione. Il primo è il contenitore degli strumenti, che contiene i programmi di utilità necessari per creare e verificare la tua applicazione. Il Dockerfile per questo contenitore è definito dal parametro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Puoi pensare a esso come un contenitore di sviluppo poiché contiene gli strumenti utilizzati normalmente per lo sviluppo di uno specifico runtime.

Il secondo contenitore è il contenitore di esecuzione. Questo contenitore è di un formato adeguato per essere distribuito per l'utilizzo, ad esempio, in {{site.data.keyword.cloud}}. Di conseguenza, viene definito un punto di ingresso che avvia la tua applicazione. Quando selezioni di eseguire la tua applicazione tramite la CLI {{site.data.keyword.dev_cli_short}}, utilizza questo contenitore. Il Dockerfile per questo contenitore è definito dal parametro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

### Comandi CLI utili
{: #helpful2}

I seguenti comandi CLI ti consentono di eseguire il debug del tuo progetto:
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) Crea il progetto in un contenitore locale.
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) Esegue il debug della tua applicazione in un contenitore locale.
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) Esegue la tua applicazione in un contenitore locale.
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) Apre una shell in un contenitore locale.
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) Controlla lo stato dei contenitori utilizzati dalla CLI {{site.data.keyword.dev_cli_notm}}.
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) Arresta un contenitore
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) Verifica la tua applicazione in un contenitore locale.

### Debug delle applicazioni locali
{: #ref2}

- [Debug delle applicazioni locali](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## Distribuisci
{: #cli-deploy}

In un ambiente nativo cloud appropriato, utilizzi una pipeline DevOps completamente funzionale per gestire tutte le distribuzioni e un gran numero di altre funzionalità. Durante il flusso di creazione, puoi configurare la tua applicazione per l'utilizzo di DevOps di IBM Cloud. Se non sei pronto a utilizzare il DevOps integrato, puoi eseguire manualmente [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) per distribuire la tua applicazione o utilizzare il comando `deploy` nella tua pipeline DevOps.

### Comandi CLI utili
{: #helpful3}

I seguenti comandi CLI consentono di lavorare con il tuo progetto durante il processo di distribuzione:
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) Apre la console {{site.data.keyword.cloud_notm}} per un progetto.
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) Distribuisce un'applicazione a {{site.data.keyword.cloud_notm}}.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) Visualizza l'URL del tuo progetto.

### Video e blog di riferimento
{: #ref3}

- Blog: [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")
- Blog: [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.cloud_notm}} Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")
