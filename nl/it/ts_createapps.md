---

copyright:
  years: 2015, 2019
lastupdated: "2019-01-30"

---

{:tsSymptoms: .tsSymptoms}
{:tsCauses: .tsCauses}
{:tsResolve: .tsResolve}
{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note: .deprecated}
{:troubleshoot: data-hd-content-type='troubleshoot'}

# Risoluzione dei problemi relativi al plugin della CLI {{site.data.keyword.cloud_notm}} Developer Tools
{: #troubleshoot}

I problemi generali quando si utilizza l'interfaccia riga di comando (CLI) {{site.data.keyword.dev_cli_short}} per creare le applicazioni potrebbero includere degli errori di distribuzione oppure l'impossibilità di richiamare il codice. In molti casi, puoi risolvere questi problemi seguendo pochi semplici passi.
{: shortdesc}

## Perché ricevo un errore di nome host quando creo un'applicazione con un modello non mobile?
{: #hostname-error}
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato se utilizzi la CLI {{site.data.keyword.dev_cli_short}} per distribuire un'applicazione a Cloud Foundry. Se immetti un nome host univoco, potresti ancora visualizzare questo messaggio.

```
The hostname <myHostname> is taken.
```
{: screen}
{: tsSymptoms}

Questo errore è causato da un token di accesso scaduto.
{: tsCauses}

Accedi nuovamente eseguendo il seguente comando:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Perché ricevo errori di comandi generali?
{: #general}
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato quando utilizzi i comandi `create`, `delete`, `list` o `code`:

```
Failed to <command> application.
```
{: screen}
{: tsSymptoms}

Questo errore è causato da un token di accesso scaduto.
{: tsCauses}

Accedi nuovamente eseguendo il seguente comando:
```
ibmcloud login
```
{: codeblock}
{: tsResolve}

## Perché l'immagine per la mia nuova applicazione non viene riconosciuta?
{: #nosuchimage}
{: troubleshoot}

Quando tenti di eseguire `ibmcloud dev run` per un'applicazione senza prima crearla, potrebbe essere visualizzato il seguente errore.

```
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image ibmcloud-dev-testProject based on Dockerfile...
OK                    
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: ibmcloud-dev-testProject
```
{: screen}
{: tsSymptoms}

Devi creare un'applicazione prima di eseguirla. Esegui il seguente comando nella tua directory dell'applicazione corrente:
```
ibmcloud dev build
```
{: codeblock}
{: tsCauses}

Esegui il seguente comando nella tua directory dell'applicazione corrente per avviare la tua applicazione:
```
ibmcloud dev run
```
{: tsResolve}

## Perché ricevo un errore del broker di servizi quando aggiungo la funzionalità {{site.data.keyword.objectstorageshort}}?
{: #os}
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato se utilizzi la CLI per creare due applicazioni con la funzionalità {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: screen}
{: tsSymptoms}

Questo errore è dovuto al servizio {{site.data.keyword.objectstorageshort}} che fornisce solo un'istanza del piano {{site.data.keyword.objectstorageshort}} gratuito.
{: tsCauses}

Seleziona un altro piano.
{: tsResolve}

## Perché il mio codice non viene richiamato quando creo un'applicazione?
{: #code}
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato quando utilizzi la CLI per creare un'applicazione:

```
FAILED
Application created, but could not get code
https://cloud.ibm.com/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: screen}
{: tsSymptoms}

Questo errore è dovuto a un timeout interno.
{: tsCauses}

Per ottenere il codice utilizza uno dei seguenti modi:

* Immetti il seguente comando:

   ```
   ibmcloud dev code <your-app-name>
   ```
   {: codeblock}

   Sostituisci `<your-app-name>` con il nome applicazione che hai specificato durante la creazione dell'applicazione.

* Utilizza la {{site.data.keyword.dev_console}}.

	1. Seleziona la tua applicazione [ ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://console.bluemix.net/developer/appservice/apps) nella {{site.data.keyword.dev_console}}.

	2. Fai clic su **Download Code**.
{: tsResolve}

## Perché non posso eseguire il comando `ibmcloud dev run` per le applicazioni Node.js?
{: #node}
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato se esegui il comando `ibmcloud dev run` per le applicazioni BFF o web Node.js:

```
module.js:597
  return process.dlopen(module, path._makeLong(filename));
                 ^

Error: /app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/appmetrics.node: invalid ELF header
    at Error (native)
    at Object.Module._extensions..node (module.js:597:18)
    at Module.load (module.js:487:32)
    at tryModuleLoad (module.js:446:12)

    at Function.Module._load (module.js:438:3)
    at Module.require (module.js:497:17)
    at require (internal/module.js:20:19)
    at Object.<anonymous> (/app/node_modules/bluemix-autoscaling-agent/node_modules/appmetrics/index.js:25:13)
    at Module._compile (module.js:570:32)
    at Object.Module._extensions..js (module.js:579:10)
```
{: screen}
{: tsSymptoms}

Questo errore si verifica quando il modulo `appmetrics` viene installato su un'architettura diversa. I moduli npm nativi installati su un'architettura non funzionano su un'altra. Le immagini Docker incluse si basano sul kernel Linux.
{: tsCauses}

Elimina la cartella `node_modules` ed esegui nuovamente il comando `ibmcloud dev run`.
{: tsResolve}

## Perché non posso distribuire a {{site.data.keyword.cloud_notm}}?
{: troubleshoot}

Si è verificato un errore durante la distribuzione a {{site.data.keyword.cloud_notm}} ma non viene visualizzato alcun errore.
{: tsSymptoms}

Potresti non essere collegato al tuo account.
{: tsCauses}

Immetti il seguente comando per accedere e riprova.
```
ibmcloud login
```
{: tsResolve}

## Perché non posso distribuire a Kubernetes su {{site.data.keyword.cloud_notm}}?
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato dopo che ti viene richiesto il tuo nome del cluster:
```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: screen}
{: tsSymptoms}

Molto probabilmente è causato da un nome del cluster non valido. Puoi confermare la causa eseguendo lo stesso comando con `--trace` e i seguenti dettagli potrebbero essere inclusi nell'output dell'errore:
```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'ibmcloud cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: screen}
{: tsCauses}

Assicurati di stare utilizzando il cluster corretto e di averlo configurato per la distribuzione eseguendo:
```
ibmcloud cs cluster-config <cluster-name>
```
{: codeblock}
{: tsResolve}

## Perché non posso distribuire una destinazione dell'immagine?
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato dopo che ti viene richiesta la destinazione dell'immagine da distribuire:
```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: screen}
{: tsSymptoms}

Molto probabilmente è causato da una destinazione dell'immagine da distribuire non valida. Nello specifico, lo spazio dei nomi, che è il valore intermedio nella destinazione dell'immagine da distribuire, potrebbe non essere valido.
{: tsCauses}

Assicurati che lo spazio dei nomi nella destinazione dell'immagine da distribuire corrisponda a uno degli spazi dei nomi visualizzati quando immetti il seguente comando:
```
ibmcloud cr namespaces
```
{: codeblock}
{: tsResolve}

## Perché non posso determinare la lingua per la mia applicazione?
{: troubleshoot}

Il seguente errore potrebbe essere visualizzato quando tenti di avviare la tua applicazione:
```
FAILED
Could not determine the language of your application.

Try using the --language flag to specify the language of your application 
directly. 
```
{: screen}
{: tsSymptoms}

Questo errore potrebbe essere dovuto a una delle seguenti cause:
- Esecuzione del comando [enable](/docs/cli/idt/commands.html#enable) da una directory che non è la directory di origine della tua applicazione.
- Esecuzione del comando [enable](/docs/cli/idt/commands.html#enable) per un'applicazione di una lingua che non è riconosciuta.
{: tsCauses}

Assicurati di eseguire il comando dalla directory dell'applicazione che contiene il codice sorgente dell'applicazione. Se questo non risolve il problema e il linguaggio è uno dei [linguaggi supportati](/docs/cli/idt/commands.html#enable-language-options), utilizza il parametro `--language` per specificare il linguaggio.
{: tsResolve}

## Perché non posso creare o eseguire un'applicazione che è stata abilitata per la distribuzione cloud?
{: troubleshoot}

Potresti riscontrare diversi errori durante il tentativo di [creare](/docs/cli/idt/commands.html#build) o [eseguire](/docs/cli/idt/commands.html#run) un'applicazione abilitata.
{: tsSymptoms}


Le molte possibili cause differenti possono essere trovate in ognuno dei seguenti link.
{: tsCauses}

- Per ulteriori informazioni sulla risoluzione di tali problemi con un'applicazione Spring, consulta [Abilitazione delle applicazioni Spring Boot esistenti per la distribuzione cloud](/docs/java-spring/enable_existing.html#enable_existing).
- Per ulteriori informazioni sulla risoluzione di tali problemi con un'applicazione `Node.js`, consulta [Abilitazione delle applicazioni Node.js esistenti per la distribuzione cloud](/docs/node/enable_existing.html#enable_existing).
{: tsResolve}

## Come installo {{site.data.keyword.Bluemix_notm}} Developer Tools manualmente?
{: #appendix}
Tutti i prerequisiti vengono installati per la maggior parte degli utenti utilizzando i programmi di installazione della piattaforma. Se devi installare manualmente qualche componente, sono qui riportate le istruzioni per ciascuno di essi.
Per installare il plug-in di sviluppo, devi prima installare la [CLI IBM Cloud](https://console.bluemix.net/docs/cli/reference/ibmcloud/download_cli.html#install_use).
Per utilizzare il plug-in di sviluppo stesso, devi installarlo eseguendo questo comando: 
```
ibmcloud plugin install dev
```
{: codeblock}
 
Per l'esecuzione e il debug di applicazioni in locale, devi anche installare [Docker](https://www.docker.com/get-docker).
 
Per distribuire un'applicazione come un contenitore, devi anche installare Kubernetes, Helm e i seguenti plug-in della CLI di IBM Cloud.
 
### Per installare Kubernetes:
Utenti Mac:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl
```
{: codeblock}

Utenti Linux:
```
curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl
```
{: codeblock}

Utenti Windows:
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe
```
{: codeblock}

### Per installare Helm:
Utenti Mac e Linux:
```
export DESIRED_VERSION=v2.7.2
curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash
```
{: codeblock}

Utenti Windows:
scarica e installa il [file binario](https://github.com/kubernetes/helm/releases/tag/v2.7.2).

### Per installare il plug-in container-registry:
```
ibmcloud plugin install container-registry
```
{: codeblock}

### Per installare il plug-in container-service:
```
ibmcloud plugin install container-service
```
{: codeblock}
