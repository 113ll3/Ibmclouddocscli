---

copyright:
  years: 2019
lastupdated: "2019-04-04"

keywords: cli, cli faq, debug cli, cli help, ibmcloud cli help, ibmcloud help

subcollection: cloud-cli

---

# Domande frequenti (FAQ)
{: #ibm-cli-faq}

## Qual è la struttura dei file per le applicazioni {{site.data.keyword.cloud_notm}}?
{: #cli-file-structure}

Le applicazioni create o abilitate dalla CLI sono fornite con impostazioni preconfigurate incapsulate nel file `cli-config.yml`. Il file `cli-config.yml` contiene le voci predefinite utilizzate dai comandi della CLI che possono essere sovrascritte dai valori passati attraverso la riga di comando.

Le applicazioni che sono state distribuite in una toolchain DevOps possono anche contenere file come `toolchain.yml` e `pipeline.yml`. Le applicazioni che vengono distribuite manualmente possono contenere un file `manifest.yml` e i file di grafico Helm (ad esempio, per le distribuzioni in Cloud Foundry o Kubernetes).

## Come vengono utilizzati i contenitori locali?
{: #cli-faq-containers}

Il plugin della CLI {{site.data.keyword.dev_cli_long}} utilizza due contenitori per facilitare la creazione e la verifica della tua applicazione. Il primo è il contenitore degli strumenti, che contiene i programmi di utilità necessari per creare e verificare la tua applicazione. Il `Dockerfile` per questo contenitore è definito dal parametro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Puoi pensare a esso come un contenitore di sviluppo poiché contiene gli strumenti utilizzati normalmente per lo sviluppo di uno specifico runtime.

Il secondo contenitore è il contenitore di esecuzione, che imita da vicino l'ambiente di runtime effettivo della tua applicazione una volta distribuita al cloud. Questo contenitore è di un formato adeguato per essere distribuito per l'utilizzo, ad esempio, in {{site.data.keyword.cloud_notm}}. Di conseguenza, viene definito un punto di ingresso che avvia la tua applicazione. Quando selezioni di eseguire la tua applicazione tramite il plugin CLI {{site.data.keyword.dev_cli_long}}, utilizza questo contenitore. Il `Dockerfile` per questo contenitore è definito dal parametro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run).

# Come posso distribuire il codice esistente?
Per distribuire una base di codice esistente, segui questa procedura per [abilitare la tua applicazione](/docs/apps?topic=creating-apps-create-deploy-app-cli#byoc-cli).

## Blog, video e documentazione di riferimento
{: #cli-faq-reference}

### Blog
{: #cli-blogs}

- [Deploying to {{site.data.keyword.cloud_notm}} Private with {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2018/05/deploying-to-ibm-cloud-private-2-1-0-2-with-ibm-cloud-developer-tools-cli/)
- [Deploying to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Enable existing projects for {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)

### Video
{: #cli-videos}

- [How to deploy to Kubernetes on {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=mh_XBn_eV_8&feature=youtu.be)
- [How to deploy existing projects to {{site.data.keyword.cloud_notm}} with the {{site.data.keyword.dev_cli_long}} CLI Plug-in](https://www.youtube.com/watch?v=-NP5ZEZE1dY&feature=youtu.be)
- [Create, debug, and deploy a Node.js app with the {{site.data.keyword.dev_cli_long}} CLI Plug-in and VSCode](https://www.youtube.com/watch?v=z-ByHuI41dU&feature=youtu.be)

### Documentazione ed esercitazioni
- [Distribuzione continua in Kubernetes](/docs/tutorials?topic=solution-tutorials-continuous-deployment-to-kubernetes)
- [Risoluzione dei problemi relativi al plugin della CLI {{site.data.keyword.dev_cli_long}}](/docs/cli?topic=cloud-cli-troubleshoot)
- [Comandi del plugin della CLI {{site.data.keyword.dev_cli_long}} (ibmcloud dev)](/docs/cli/idt?topic=cloud-cli-idt-cli)
- [Debug dell'applicazione locale per il plugin della CLI {{site.data.keyword.dev_cli_long}}](/docs/cli/idt?topic=cloud-cli-local-debug)

**Per segnalare problemi o fornire un feedback, puoi utilizzare il [canale {{site.data.keyword.cloud_notm}} Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com) - Richiedi l'accesso al team [qui](https://slack-invite-ibm-cloud-tech.mybluemix.net/).**
