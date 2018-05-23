---
copyright:
  years: 2017, 2018
lastupdated: "2018-05-02"

---


{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:note:.deprecated}

# Risoluzione dei problemi relativi a IBM Cloud Developer Tools
{: #ts}

Sono documentati alcuni problemi noti con la {{site.data.keyword.dev_cli_notm}}, insieme alle loro soluzioni temporanee.
{:shortdesc}

<!-- Add a headings and paragraphs about troubleshooting for your service, or a list of known issues and workarounds. -->

## Problemi noti
{: #knownissues}

Le seguenti sezioni descrivono dei problemi noti e le possibili soluzioni.


### Errore di nome host già assegnato quando crei un progetto con un modello non mobile
{: #hostname}

Potresti visualizzare il seguente errore se utilizzi la {{site.data.keyword.dev_cli_short}} per creare un progetto dai modelli applicazione web, BFF, o microservizio:

```
The hostname <myHostname> is taken.
```
{: codeblock}


#### Causa
{: #hostname-cause}
   
Questo errore è dovuto ad un token di accesso scaduto.


#### Risoluzione
{: #hostname-resolution}

Accedi nuovamente.

```
bx login
```
{: codeblock}


### Errori generali con la {{site.data.keyword.dev_cli_short}}
{: #general}

Potresti vedere il seguente errore se usi i comandi create, delete, list o code della {{site.data.keyword.dev_cli_short}}:

```
Failed to <command> project.
```
{: codeblock}


#### Causa
{: #general-cause}
   
Questo errore è dovuto ad un token di accesso scaduto.


#### Risoluzione
{: #general-resolution}

Accedi nuovamente.

```
bx login
```
{: codeblock}


### Errore: Nessuna immagine quando esegui un nuovo progetto
{: #nosuchimage}

Potresti visualizzare il seguente errore quando esegui un progetto senza prima crearlo.

```
$ bx dev run testProject
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


#### Causa
{: #nosuchimage-cause}

Devi creare un progetto prima di eseguirlo. 


#### Risoluzione
{: #nosuchimage-resolution}

Immetti il seguente comando nella tua directory del progetto corrente per creare la tua applicazione:

```
bx dev build
```
{: codeblock}

Immetti il seguente comando nella tua directory del progetto corrente per avviare la tua applicazione:

```
bx dev run
```


### Errore con il broker di servizi quando aggiungi la funzionalità {{site.data.keyword.objectstorageshort}}
{: #os}

Potresti visualizzare il seguente errore se utilizzi la {{site.data.keyword.dev_cli_short}} per creare due progetti con la funzionalità {{site.data.keyword.objectstorageshort}}:

```
FAILED
Service broker error: {"description"=>"You can not create this Object Storage instance. Each organization using the Object Storage service is limited to one instance of the Free plan."}
```
{: codeblock}


#### Causa
{: #os-cause}
   
Questo errore è dovuto al servizio {{site.data.keyword.objectstorageshort}} che fornisce solo un'istanza del piano {{site.data.keyword.objectstorageshort}} gratuito.


#### Risoluzione
{: #os-resolution}

Per evitare questo errore ti viene richiesto di scegliere un piano diverso.


### Impossibile ottenere il codice durante la creazione del progetto
{: #code}

Potresti visualizzare il seguente errore se utilizzi la {{site.data.keyword.dev_cli_short}} per creare un progetto:
	
```
FAILED                            
Project created, but could not get code
https://console.ng.bluemix.net/developer/projects/b22165f3-cbc6-4f73-876f-e33cbec199d4/code
```
{: codeblock}
	

#### Causa
{: #code-cause}

Questo errore è dovuto a un timeout interno.
	

#### Risoluzione
{: #code-resolution}

Puoi ottenere il codice in uno dei seguenti modi:

* Immetti il seguente comando utilizzando la CLI:

   ```
   bx dev code <your-project-name>
   ```
   {: codeblock}

   Sostituisci `<your-project-name>` con il nome progetto che hai specificato durante la creazione del progetto.

* Utilizza la {{site.data.keyword.dev_console}}.

	1. Seleziona il tuo progetto [ ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://console.{DomainName}/developer/projects) nella {{site.data.keyword.dev_console}} e fai clic su **Ottieni codice**.

	2. Fai clic su **Genera codice**.

	3. Dopo aver generato il codice, fai clic su **Scarica codice**.


### Errore durante l'esecuzione di `bx dev run` per i progetti Node.js
{: #node}

Potresti visualizzare il seguente errore se stai eseguendo `bx dev run` con la {{site.data.keyword.dev_cli_short}} per i progetti Node.js Web o BFF:

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


#### Causa
{: #node-cause}
   
Questo errore si verifica quando il modulo `appmetrics` viene installato su un'architettura diversa. I moduli npm nativi installati su un'architettura non funzionano su un'altra. Le immagini Docker incluse si basano sul kernel Linux.


#### Risoluzione
{: #node-resolution}

Elimina la cartella `node_modules` ed esegui nuovamente `bx dev run`.


### Impossibile distribuire a Bluemix
{: #failuretodeploy}

Potresti tentare di eseguire una distribuzione a Bluemix con la {{site.data.keyword.dev_cli_short}} e appurare che non viene eseguita alcuna distribuzione a Bluemix ma non viene generato alcun errore.


#### Causa
{: #cause1}

Potresti non avere eseguito l'accesso al tuo account. 

#### Risoluzione
{: #resolution1}

Effettua l'accesso e riprova.

```
bx login
```


### Impossibile distribuire a Kubernetes su Bluemix
{: #failuretodeploytokube}

Puoi vedere questo errore dopo il prompt iniziale per il tuo nome cluster:

```
FAILED
Failed to execute the action:  exit status 1:

FAILED
Failed to configure deployment with cluster '<cluster-name>' due to: exit status 1
```


#### Causa
{: #cause2}

Molto probabilmente la causa è un nome cluster non valido, cosa che può essere confermata eseguendo lo stesso comando con `--trace`; nell'output dell'errore potresti vedere quanto segue:

```
Failing with error:  {"incidentID":"<id-number>","code":"E0008","description":"The specified cluster could not be found.","recoveryCLI":"Run 'bx cs clusters' to list all clusters you have access to.","type":"Provisioning"}
```


#### Risoluzione
{: #resolution2}

Assicurati che stai utilizzando il cluster corretto e che hai configurato il tuo cluster per la distribuzione eseguendo

```
bx cs cluster-config <cluster-name>
```


### Impossibile distribuire a Kubernetes su Bluemix

Puoi vedere questo errore dopo il prompt per la destinazione dell'immagine da distribuire:

```
FAILED
Failed to execute the action:  exit status 1:denied: requested access to the resource is denied


FAILED
Failed to push the Run image tagged 'registry.ng.bluemix.net/<namespace>/<project-name>:0.0.1' to the Docker registry due to: exit status 1
```


#### Causa
{: #cause3}

Molto probabilmente, ciò è dovuto a una destinazione dell'immagine da distribuire non valida. Nello specifico, potrebbe essere uno spazio dei nomi non valido, il valore intermedio nella destinazione dell'immagine da distribuire.


#### Risoluzione
{: #resolution3}

Assicurati che lo spazio dei nomi nella destinazione dell'immagine da distribuire corrisponda a uno degli spazi dei nomi trovati dall'esecuzione

```
bx cr namespaces
```



## APPENDICE
{: #appendix}

Tutti i prerequisiti verranno installati per la maggior parte degli utenti utilizzando i programmi di installazione della piattaforma nella parte superiore di questa pagina. Se devi installare manualmente qualche componente, ecco le istruzioni:

Per installare il plugin di sviluppo, è necessario che venga prima installata la [CLI IBM Cloud](../reference/bluemix_cli/get_started.md#getting-started).

Per utilizzare il plugin di sviluppo stesso, devi installarlo eseguendo questo comando: `bx plugin install dev -r Bluemix`

Per l'esecuzione e il debug di applicazioni in locale, devi anche installare [Docker ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](https://www.docker.com/get-docker).

Per la distribuzione di un'applicazione come un contenitore, devi anche installare Kubernetes, Helm e i seguenti plugin CLI IBM Cloud:

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

Per installare il plugin container-registry:
`bx plugin install container-registry`

Per installare il plugin container-service:
`bx plugin install container-service`


<!--
## Troubleshooting techniques
{: #tstechniques}
-->

<!-- Add a heading and content for how to get help and support. Use this template for beta and GA services:  -->


## Come ottenere aiuto e supporto
{: #gettinghelp}

Se hai problemi o domande sulla {{site.data.keyword.Bluemix_notm}} {{site.data.keyword.dev_console}} o sulla {{site.data.keyword.dev_cli_notm}}, ottieni assistenza cercando informazioni o facendo domande tramite un forum. Puoi anche aprire un ticket di supporto.

Quando pubblichi nei forum, puoi contrassegnare le tue domande con delle tag in modo che i team di sviluppo di {{site.data.keyword.Bluemix_notm}} ricevano una notifica.

<!--Insert the appropriate Stack Overflow tag for your service for <service_keyword> in URL and text below:  -->

Se hai domande tecniche sullo sviluppo o la distribuzione di un'applicazione con la {{site.data.keyword.dev_console}} o la {{site.data.keyword.dev_cli_notm}}:

* Pubblica la tua domanda in [Stack Overflow ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](http://stackoverflow.com/search?q=bluemix-dev-services+ibm-bluemix) e contrassegna la tua domanda con le tag `bluemix-dev-services` e `ibm-bluemix`.
* Pubblica la tua domanda in [Slack ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](http://ibm-cloud-tech.slack.com/) nel canale `bluemix-dev-services`. [Registrati ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](http://ibm.biz/IBMCloudNativeSlack) subito.


<!--Insert the appropriate dW Answers tag for your service for <service_keyword> in URL below:  -->
<!--
* For questions about the service and getting started instructions, use the [IBM developerWorks dW Answers ![External link icon](../icons/launch-glyph.svg "External link icon")](https://developer.ibm.com/answers/topics/bluemix-dev-services/?smartspace=bluemix) forum. Include the  "bluemix-dev-services" and "bluemix" tags.
* -->

Consulta la sezione relativa a [come ottenere supporto ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](/docs/support/index.html#getting-help) per ulteriori dettagli sull'utilizzo dei forum.

Per informazioni sull'apertura di un ticket di supporto {{site.data.keyword.IBM}} o sui livelli di supporto e le severità dei ticket, consulta la sezione relativa a [come contattare il supporto ![Icona link esterno](../icons/launch-glyph.svg "Icona link esterno")](/docs/support/index.html#contacting-support).

<!--Add a heading and content for how to get help. (Support not available for experimental.) Use this template for experimental services:  -->
