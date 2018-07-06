---

copyright:
  years: 2015, 2018
lastupdated: "2018-06-21"

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

# Risoluzione dei problemi relativi a {{site.data.keyword.Bluemix_notm}} Developer Tools
{: #troubleshoot}

I problemi generali quando si utilizza la CLI {{site.data.keyword.dev_cli_short}} per creare le applicazioni potrebbero includere degli errori di distribuzione oppure l'impossibilità di richiamare il codice quando si crea un'applicazione. In molti casi, puoi risolvere questi problemi seguendo pochi semplici passi.
{:shortdesc}

## Errore nel nome host quando crei un'applicazione con un modello non mobile
{: #hostname-error}

Potresti visualizzare il seguente errore se utilizzi la CLI {{site.data.keyword.dev_cli_short}} per distribuire un'applicazione a Cloud Foundry. Se immetti un nome host che ritieni sia univoco, potresti ancora visualizzare questo messaggio.

```
The hostname <myHostname> is taken.
```
{: codeblock}
{: tsSymptoms}

Questo errore è causato da un token di accesso scaduto.
{: tsCauses}

Accedi nuovamente.

```
bx login
```
{: codeblock}
{: tsResolve}

## Errori generali con la CLI {{site.data.keyword.dev_cli_short}}
{: #general}

Potresti visualizzare il seguente errore se utilizzi i comandi `create`, `delete`, `list` o `code` della CLI {{site.data.keyword.dev_cli_short}}:

```
Failed to <command> application.
```
{: codeblock}
{: tsSymptoms}

Questo errore è causato da un token di accesso scaduto.
{: tsCauses}

Accedi nuovamente.

```
bx login
```
{: codeblock}
{: tsResolve}

## Errore: Nessuna immagine quando esegui una nuova applicazione
{: #nosuchimage}

Potresti visualizzare il seguente errore quando esegui un'applicazione senza prima crearla.

```
$ bx dev run
The run-cmd option was not specified
Stopping the 'testProject' container...
The 'testProject' container was not found
Creating image bx-dev-testProject based on Dockerfile...
OK
Creating a container named 'testProject' from that image...
FAILED
Container 'testProject' could not be created:
Error: No such image: bx-dev-testProject
```
{: tsSymptoms}

Devi creare un'applicazione prima di eseguirla.
{: tsCauses}

Esegui il seguente comando nella tua directory dell'applicazione corrente per creare la tua applicazione:

```
bx dev build
```
{: codeblock}

Esegui il seguente comando nella tua directory dell'applicazione corrente per avviare la tua applicazione:

```
bx dev run
```
{: tsResolve}

## Errore con il broker di servizi quando aggiungi la funzionalità {{site.data.keyword.objectstorageshort}}
{: #os}

Potresti visualizzare il seguente errore se utilizzi la CLI {{site.data.keyword.dev_cli_short}} per creare due applicazioni con la funzionalità {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}
{: tsSymptoms}

Questo errore è dovuto al servizio {{site.data.keyword.objectstorageshort}} che fornisce solo un'istanza del piano {{site.data.keyword.objectstorageshort}} gratuito.
{: tsCauses}

Per evitare questo errore ti viene richiesto di scegliere un piano diverso.
{: tsResolve}

## Errore durante il richiamo del codice durante la creazione di un'applicazione
{: #code}

Potresti visualizzare il seguente errore se utilizzi la CLI {{site.data.keyword.dev_cli_short}} per creare un'applicazione:

```
FAILED
Application created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
{: tsSymptoms}

Questo errore è dovuto a un timeout interno.
{: tsCauses}

Puoi ottenere il codice in uno dei seguenti modi:

* Immetti il seguente comando utilizzando la CLI:

   ```
   bx dev code <your-app-name>
   ```
   {: codeblock}

   Sostituisci `<your-app-name>` con il nome applicazione che hai specificato durante la creazione dell'applicazione.

* Utilizza la {{site.data.keyword.dev_console}}.

	1. Seleziona la tua applicazione [ ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://console.bluemix.net/developer/appservice/apps) nella {{site.data.keyword.dev_console}}.

	2. Fai clic su **Download Code**.

{: tsResolve}

## Errore di esecuzione di `bx dev run` per le applicazioni Node.js
{: #node}

Potresti visualizzare il seguente errore se stai eseguendo `bx dev run` con la CLI {{site.data.keyword.dev_cli_short}} per le applicazioni Node.js Web o BFF:

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
{: codeblock}
{: tsSymptoms}

Questo errore si verifica quando il modulo `appmetrics` viene installato su un'architettura diversa. I moduli npm nativi installati su un'architettura non funzionano su un'altra. Le immagini Docker incluse si basano sul kernel Linux.
{: tsCauses}

Elimina la cartella `node_modules` ed esegui nuovamente il comando `bx dev run`.
{: tsResolve}

## Impossibile distribuire a {{site.data.keyword.Bluemix_notm}}

Si verifica un errore quando tenti la distribuzione a {{site.data.keyword.Bluemix_notm}} con la CLI {{site.data.keyword.dev_cli_short}}, ma non viene visualizzato alcun errore.
{: tsSymptoms}

Potresti non essere collegato al tuo account.
{: tsCauses}

Effettua l'accesso e riprova.

```
bx login
```
{: tsResolve}

## Impossibile distribuire a Kubernetes in {{site.data.keyword.Bluemix_notm}}

Il seguente errore potrebbe essere visualizzato dopo che ti viene richiesto il tuo nome del cluster:

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```
{: tsSymptoms}

Molto probabilmente è causato da un nome del cluster non valido. Puoi confermare la causa eseguendo lo stesso comando con `--trace` e i seguenti dettagli potrebbero essere inclusi nell'output dell'errore:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'bx cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```
{: tsCauses}

Assicurati di stare utilizzando il cluster corretto e di aver configurato il tuo cluster per la distribuzione eseguendo:

```
bx cs cluster-config <cluster-name>
```
{: tsResolve}

## Impossibile distribuire a una destinazione dell'immagine

Il seguente errore potrebbe essere visualizzato dopo che ti viene richiesta la destinazione dell'immagine da distribuire:

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<app-name>:0.0.1' to the Docker registry due to: exit status 1
```
{: tsSymptoms}

Molto probabilmente è causato da una destinazione dell'immagine da distribuire non valida. Nello specifico, lo spazio dei nomi, che è il valore intermedio nella destinazione dell'immagine da distribuire, potrebbe non essere valido.

Assicurati che lo spazio dei nomi nella destinazione dell'immagine da distribuire corrisponda a uno degli spazi dei nomi trovati dall'esecuzione:

```
bx cr namespaces
```
{: tsResolve}

## Reinstallazione degli strumenti
{: #appendix}

Tutti i prerequisiti vengono installati per la maggior parte degli utenti utilizzando i programmi di installazione della piattaforma. Se devi installare manualmente qualche componente, ecco le istruzioni:

Per installare il plug-in di sviluppo, devi prima installare la [CLI IBM Cloud](https://console.bluemix.net/docs/cli/reference/bluemix_cli/get_started.html#getting-started).

Per utilizzare il plug-in di sviluppo stesso, devi installarlo eseguendo questo comando: `bx plugin install dev -r Bluemix`

Per l'esecuzione e il debug di applicazioni in locale, devi anche installare [Docker](https://www.docker.com/get-docker).

Per la distribuzione di un'applicazione come contenitore, devi anche installare Kubernetes, Helm e i seguenti plug-in della IBM Cloud:

Per installare Kubernetes:
* Utenti Mac:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl`

* Utenti Linux:
`curl --progress-bar -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`

* Utenti Windows:
`curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.7.0/bin/windows/amd64/kubectl.exe`

Per installare Helm:
* Utenti Mac e Linux:
`export DESIRED_VERSION=v2.6.0`
`curl -sL https://raw.githubusercontent.com/kubernetes/helm/master/scripts/get | bash`

* Utenti Windows:
Scarica e installa il file binario all'indirizzo https://github.com/kubernetes/helm/releases/tag/v2.6.0

Per installare il plug-in container-registry:
`bx plugin install container-registry`

Per installare il plug-in container-service:
`bx plugin install container-service`
