---

copyright:

   years: 2017, 2018

lastupdated: "2018-06-21"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}  

# Comandi della CLI {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Versione: 1.2.0
Rilasciata: 8 marzo 2018

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.Bluemix_notm}} sono stati modificati da `bluemix` e `bx` a `ibmcloud`. Tuttavia, puoi ancora utilizzare i comandi della CLI `bluemix` e `bx` finché non vengono rimossi in una data successiva.
{: tip}

Utilizza i seguenti comandi della CLI {{site.data.keyword.dev_cli_notm}} (ibmcloud dev) per creare un progetto, distribuirlo, eseguirne il debug e verificarlo.

- [build](#build): crea il progetto in un contenitore locale
- [code](#code): scarica il codice da un progetto
- [console](#console): apre la console IBM Cloud per un progetto
- [create](#create): crea un nuovo progetto e ti fornisce l'opzione per aggiungere i servizi
- [debug](#debug): esegue il debug della tua applicazione in un contenitore locale
- [delete](#delete): elimina un progetto dal tuo spazio
- [deploy](#deploy): distribuisce un'applicazione a IBM Cloud
- [enable](#enable): aggiunge file IBM Cloud a un progetto esistente
- [get-credentials](#get-credentials): richiama le credenziali richieste dal progetto per abilitare l'utilizzo dei servizi collegati
- [help](#help): guida per gli argomenti e la sintassi IDT
- [list](#list): elenca tutti i progetti IBM Cloud in uno spazio
- [run](#run): esegue la tua applicazione in un contenitore locale
- [shell](#shell): apre una shell in un contenitore locale
- [status](#status): controlla lo stato dei contenitori utilizzati dalla CLI
- [stop](#stop): arresta un contenitore
- [test](#test): verifica la tua applicazione in un contenitore locale
- [view](#view): visualizza l'URL distribuito delle applicazioni per la verifica e la visualizzazione
- [compound commands](#compound): esegue più comandi in una istruzione della riga di comando



## build
{: #build}

Puoi creare la tua applicazione utilizzando il comando `build`. I comandi `test`, `debug` e `run` si aspettano di trovare un progetto compilato per cui devi prima eseguire un'operazione `build`.  

Viene utilizzato l'elemento di configurazione `build-cmd-debug` per creare l'applicazione per tutti gli utilizzi ad eccezione di `run`. Crea la tua applicazione per il debug specificando l'opzione della riga di comando `--debug`.  Viene utilizzato l'elemento di configurazione `build-cmd-run` quando stai creando l'applicazione per essere utilizzata con il comando `run`.

Per creare con più contenitori, il tuo progetto deve contenere un file [Compose](https://docs.docker.com/compose/overview/), specificato in `cli-config.yml` o puoi utilizzare il parametro del comando `dockerfile-tools` per fornirne uno. Consulta [File Compose](/docs/apps/projects/compose_file.html) per ulteriori informazioni.

Immetti il seguente comando nella tua directory del progetto corrente per creare la tua applicazione:  

```
ibmcloud dev build [--debug]
```
{: codeblock}


[Crea parametri del comando](#command-parameters)


## code
{: #code}

Utilizza il comando `code` per scaricare un progetto precedentemente creato con il codice del template dell'applicazione e i file di configurazione per {{site.data.keyword.Bluemix_notm}}.  Questo è utile quando devi estrarre una seconda copia di un progetto che hai creato.

Immetti il seguente comando per scaricare il codice da un progetto specificato.

```
ibmcloud dev code <projectName>
```
{: codeblock}


## console
{: #console}

Utilizza il comando `console` per aprire un browser web per la console web della tua applicazione su IBM Cloud.  Puoi eseguire il comando `ibmcloud dev console` dall'interno della cartella del tuo progetto e la CLI tenta di trovare un progetto corrispondente su IBM Cloud con lo stesso ID progetto della directory corrente. Se il sistema non è in grado di trovare un nome corrispondente, apre il dashboard web e mobile su IBM Cloud invece del progetto specificato.

Puoi fornire un nome progetto e la CLI ignora le corrispondenze basate sul nome cartella/applicazione. In questo caso, la CLI apre la console del progetto denominato in un browser web.  

Immetti il seguente comando per aprire un browser web per la console web della tua applicazione.

```
ibmcloud dev console [projectName]
```
{: codeblock}


## create
{: #create}

Crea un progetto richiedendo tutte le informazioni, tra cui tipo di risorsa, linguaggio, kit starter e le opzioni della toolchain DevOps. Il progetto viene creato nella directory corrente.

Per creare un progetto nella directory corrente e associare dei servizi ad esso, immetti il seguente comando:

```
ibmcloud dev create
```
{: codeblock}


## debug
{: #debug}

Puoi eseguire il debug della tua applicazione tramite il comando `debug`. Deve prima essere completata una build nel progetto utilizzando il comando di build con l'argomento `--debug`. Quando avvii il comando `debug` viene avviato un contenitore che fornisce una o più porte di debug come definito dal valore `container-port-map-debug` in cli-config.yml o specificato nella riga di comando. Collega il tuo strumento di debug preferito alla porta o alle porte e puoi eseguire il debug della tua applicazione normalmente.

Per prima cosa, compila il tuo progetto:

```
ibmcloud dev build --debug
```
{: codeblock}

Per iniziare, immetti il seguente comando nella tua directory del progetto corrente per eseguire il debug della tua applicazione:

```
ibmcloud dev debug
```
{: codeblock}

Per eseguire il debug, collega il tuo strumento di debug alla porta specificata.

Per uscire dalla sessione di debug, utilizza `CTRL-C`.


### parametri comando debug
{: #debug-parameters}

I seguenti parametri sono esclusivi per il comando `debug` e
a assistono con il debug di un'applicazione. Esistono [ulteriori parametri](#command-parameters) condivisi con altri comandi.

#### `container-port-map-debug`
{: #port-map-debug}

* Associazioni di porta per la porta di debug. Il primo valore è la porta da utilizzare nel SO host, il secondo è la porta nel contenitore [host-port:container-port].
* Utilizzo: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parametro che viene utilizzato per creare il codice per DEBUG.
* Utilizzo: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parametro che viene utilizzato per specificare un comando per richiamare il debug nel contenitore degli strumenti. Utilizza questo parametro se `build-cmd-debug` avvia la tua applicazione in debug.
* Utilizzo: `ibmcloud dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

Utilizza il comando `delete` per rimuovere i progetti dal tuo spazio {{site.data.keyword.Bluemix}}. Puoi eseguire il comando senza i parametri per elencare i progetti disponibili e selezionare il progetto da eliminare dall'elenco numerato. Le directory e il codice del progetto non vengono rimossi dal tuo spazio disco locale.

Immetti il seguente comando per eliminare il tuo progetto da {{site.data.keyword.Bluemix}}:

```
ibmcloud dev delete <projectName>
```
{: codeblock}


**Nota:** i servizi {{site.data.keyword.Bluemix}} **non** vengono rimossi.


## deploy
{: #deploy}

Puoi distribuire un'applicazione come applicazione Cloud Foundry o come un contenitore.

Per distribuire come applicazione Cloud Foundry a {{site.data.keyword.Bluemix}}, un file `manifest.yml` deve essere presente nella directory root del tuo progetto.

Per distribuire un'applicazione come un contenitore, devi installare localmente [Kubernetes](https://kubernetes.io/) e [Helm](https://github.com/kubernetes/helm). Assicurati che la versione del client Helm non è più recente della versione del server Helm. Puoi trovare entrambe eseguendo `helm version`. Consigliamo di utilizzare la versione v2.4.2 per il client.

In `cli-config.yml`, puoi scegliere di definire la posizione di un grafico Helm nella proprietà `chart-path`, impostare l'elemento `deploy-target` su `container` e configurare `deploy-image-target` come illustrato nell'esempio. L'elemento `deploy-image-target` in `cli-config.yml` viene utilizzato al posto degli elementi `repository` e `tag` nel file `chart/values.yml`. Per distribuire a {{site.data.keyword.Bluemix}} in particolare, imposta l'elemento di configurazione `ibm-cluster` sul nome del cluster Kubernetes che hai creato in {{site.data.keyword.Bluemix}} come descritto in [Esercitazione: Creazione dei cluster](/docs/containers/cs_tutorials.html#cs_cluster_tutorial).

Per ulteriori informazioni sul provisioning, sulla configurazione e sulla distribuzione a un cluster Kubernetes, vedi l'esercitazione [Deploy a scalable web application on Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes).

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

Se non definisce ciò in cli-config.yml, devi distribuire con il parametro `-t container` e ti verranno richiesti tutti gli altri valori.

Immetti il seguente comando nella tua directory del progetto corrente per creare la tua applicazione:  

```
ibmcloud dev build
```
{: codeblock}

Immetti il seguente comando nella tua directory del progetto corrente per distribuire il tuo progetto:

```
ibmcloud dev deploy
```
{: codeblock}


### parametri comando deploy
{: #deploy-parameters}

I seguenti parametri possono essere utilizzati con il comando `deploy` o aggiornando direttamente il file `cli-config.yml` del progetto. Esistono [ulteriori parametri](#command-parameters) condivisi con altri comandi.

#### `chart-path`
{: #chart-path}

* Parametro utilizzato per una distribuzione del contenitore per specificare l'ubicazione del grafico Helm utilizzato per la distribuzione.
* Utilizzo `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Parametro facoltativo utilizzato per indicare il tipo di distribuzione che deve essere completata.  Il tipo di distribuzione predefinito è pacchetto di build.
* Utilizzo `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parametro utilizzato con una distribuzione del contenitore come nome dell'immagine di destinazione per la distribuzione (ad esempio per contrassegnare un registro Docker).  Il valore non deve includere una versione, ad esempio: image-name:{version} perché la versione viene automaticamente incrementata e accodata da `deploy`.
* Utilizzo `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parametro facoltativo utilizzato per definire il nome del cluster Kubernetes per una distribuzione del contenitore a {{site.data.keyword.Bluemix}}
* Utilizzo `ibmcloud dev deploy --ibm-cluster [cluster-name]`


## enable
{: #enable}

Abilita un progetto esistente per la distribuzione a {{site.data.keyword.Bluemix_notm}}. Il comando `enable` tenta di rilevare automaticamente il linguaggio di un progetto esistente e poi richiede le ulteriori informazioni necessarie. Questo genera e aggiunge i file che possono essere utilizzati per i contenitori Docker locali, la distribuzione CloudFoundry o la distribuzione Kubernetes/Contenitore.

Immetti il seguente comando per abilitare un progetto esistente nella directory corrente per la distribuzione a {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud dev enable
```
{: codeblock}

La presenza dei file necessari fornisce il rilevamento del linguaggio del progetto per una struttura del progetto valida.  

* La presenza di un file `package.json` identifica un progetto Node.js.
* La presenza di un file `package.swift` identifica un progetto Swift.
* La presenza di un file `setup.py` o `requirements.txt` identifica un progetto Python.
* La presenza di un file `pom.xml` o `build.gradle` identifica un progetto Java.
	* La presenza di `pom.xml` identifica un progetto Maven.
	* La presenza di `build.gradle` identifica un progetto Gradle.

Facoltativamente, puoi anche sovrascrivere il linguaggio del progetto rilevato utilizzando l'argomento `--language`.  Tuttavia, sono supportati solo i progetti completi e validi. Il comando abilitato non modifica il codice sorgente.

Le opzioni del linguaggio includono:
* node
* swift
* python
* java-ee (interpretato come Java - Java EE)
* java-mp (interpretato come Java - Java MicroProfile)
* java-spring (interpretato come Java - Spring Framework)

I file creati utilizzando il comando `ibmcloud dev enable` che hanno conflitti di denominazione con i file esistenti nella cartella del progetto vengono salvati con l'estensione `.merge`.  

### parametri comando enable
{: #enable-parameters}

I seguenti parametri possono essere utilizzati con il comando `enable` o aggiornando direttamente il file `cli-config.yml` del progetto. Esistono [ulteriori parametri](#command-parameters) condivisi con altri comandi.

#### `language`
{: #enable-language}

* Parametro utilizzato per specificare il linguaggio del progetto che deve essere abilitato.
* Utilizzo `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parametro utilizzato per forzare la riabilitazione di un progetto già abilitato.
* Utilizzo `ibmcloud dev enable -f|--force`


## get-credentials
{: #get-credentials}

Richiama le credenziali richieste dal progetto per abilitare l'utilizzo dei servizi collegati.


## help
{: #help}

Per impostazione predefinita, se non viene trasmesso alcun argomento o azione o se viene fornita l'azione 'help', questo comando mostra un testo di "Aiuto" generale. La guida generale visualizzata include una descrizione degli argomenti di base così come un elenco di azioni disponibili.  

Immetti il seguente comando per visualizzare le informazioni della guida generale:

```
ibmcloud dev help
```
{: codeblock}


## list
{: #list}

Puoi elencare tutti i progetti {{site.data.keyword.Bluemix_notm}} in uno spazio.

Immetti il seguente comando per elencare i tuoi progetti:

```
ibmcloud dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
ibmcloud dev edit
```
{: codeblock}
-->


## run
{: #run}

Puoi eseguire la tua applicazione tramite il comando `run`. Deve prima essere completata una build nel progetto utilizzando il comando `build`. Quando richiami il comando `run`, viene avviato il contenitore di esecuzione che espone le porte come definito dal parametro `container-port-map`. Il parametro `run-cmd` può essere utilizzato per richiamare l'applicazione se il Dockerfile del contenitore di esecuzione non contiene un punto di ingresso per completare questa fase.

Per eseguire più contenitori, il tuo progetto deve contenere un file [Compose](https://docs.docker.com/compose/overview/), specificato in `cli-config.yml` o puoi utilizzare il parametro del comando `dockerfile-run` per fornirne uno. Consulta [File Compose](/docs/apps/projects/compose_file.html) per ulteriori informazioni.

Per prima cosa, compila il tuo progetto:

```
ibmcloud dev build
```
{: codeblock}

Immetti il seguente comando nella tua directory del progetto corrente per avviare la tua applicazione:

```
ibmcloud dev run
```
{: codeblock}

Per uscire dalla sessione utilizza `CTRL-C`.


### parametri comando run
{: #run-parameters}

I seguenti parametri sono esclusivi per il comando `run` e
assistono con la gestione della tua applicazione all'interno del contenitore in esecuzione.
Esistono [ulteriori parametri](#command-parameters) condivisi con altri comandi.

#### `container-name-run`
{: #container-name-run2}

* Il nome del contenitore di esecuzione.
* Utilizzo: `ibmcloud dev run --container-name-run [<projectName>]`

#### `container-path-run`
{: #container-path-run}

* Ubicazione nel contenitore da condividere all'esecuzione.
* Utilizzo: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* Ubicazione sul sistema host da condividere nel contenitore all'esecuzione.
* Utilizzo: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile del contenitore di esecuzione.
* Se intendi eseguire più contenitori, questo dovrebbe essere un file Compose.
* Per utilizzare più file di composizione, racchiudi tra virgolette un elenco delimitato da virgole dei nomi dei file.
* Utilizzo: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* Utilizzo: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* Immagine da creare da `dockerfile-run`.
* Utilizzo: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* Parametro che viene utilizzato per eseguire il codice nel contenitore di esecuzione. Utilizza questo parametro se la tua immagine avvia la tua applicazione.
* Utilizzo: `ibmcloud dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

Puoi aprire la shell all'interno del contenitore di esecuzione o degli strumenti con il comando `shell`.

Semplicemente eseguendo questo comando

```
ibmcloud dev shell
```

la CLI {{site.data.keyword.dev_cli_short}} aprirà una shell interattiva nel contenitore docker dell'applicazione. Il contenitore di destinazione predefinito per il comando shell è definito dal valore `container-shell-target` nel file `cli-config.yml`, dove i valori validi sono `run` o `tools`. Se questo valore non è definito o viene specificato un valore non valido, il comando `shell` indirizzerà al contenitore `tools` per impostazione predefinita. Il comando shell apre il contenitore nella directory specificata dall'istruzione `WORKDIR` nel Dockerfile corrispondente. Se `WORKDIR` non è elencato nel Dockerfile, viene utilizzata la root del contenitore come directory di lavoro. Per ulteriori informazioni, vedi [questo riferimento](https://docs.docker.com/engine/reference/builder/#workdir).

In alternativa, è possibile decidere di passare `run` o `tools` come un argomento al comando e questo contenitore sarà aggiornato e la shell verrà aperta per tale contenitore. Allo stesso modo, puoi utilizzare il parametro `container-name` per passare il nome del contenitore in cui vuoi utilizzare la shell. Tuttavia, questo indicatore dovrebbe essere riservato per quando non ci sono contenitori in esecuzione. Gli argomenti `run` e `tools` sono più flessibili e ti consentono di spostarti tra i contenitori quando uno di essi è al momento in esecuzione. Ad esempio, se il contenitore degli strumenti è in esecuzione ed esegui `ibmcloud dev shell run`, il contenitore `tools` verrà arrestato e il contenitore `run` verrà avviato e viceversa.

Se il contenitore `run` o `tools` di destinazione non è ancora in esecuzione quando esegui il comando `shell`, il contenitore di destinazione sarà avviato. Tuttavia, il valore predefinito `Cmd` o `Entrypoint` nel Dockerfile sarà sovrascritto per l'avvio diretto nella shell invece di avviare il processo del server. Questo ti consente di avviare il contenitore `run` o `tools` e avviare manualmente il server con i comandi personalizzati o quando preferisci.


Puoi anche specificare l'eseguibile della shell che vuoi aprire utilizzando il parametro `container-shell`. Per impostazione predefinita, viene utilizzato `/bin/sh`. Se preferisci usare la shell bash, specifica che il valore `container-shell` sia `/bin/bash`; tuttavia, tieni presente che bash non è disponibile automaticamente in tutte le varianti Linux.

Tutti gli argomenti aggiuntivi che passi al comando oltre agli indicatori saranno analizzati come il comando da eseguire quando la shell è aperta. Se fornisci un comando da eseguire, la shell all'interno del contenitore uscirà dopo l'esecuzione del comando e ritornerai al tuo terminale.

Ad esempio, puoi eseguire il comando Linux `ls` nella shell del contenitore degli strumenti richiamando `ibmcloud dev shell tools ls`.   Puoi anche specificare ulteriori indicatori da passare nell'esecuzione del comando della shell racchiudendo gli argomenti tra virgolette, come ad esempio `ibmcloud dev shell "ls -la"`.

### parametri comando shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nome del contenitore in cui vuoi eseguire la shell.
* Utilizzo: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Specifica quale shell eseguire all'interno del contenitore (il valore predefinito è /bin/sh)
* Utilizzo: `ibmcloud dev shell --container-shell [path/to/shell]`


## status
{: #status}

Puoi eseguire la query dello stato dei contenitori che sono utilizzati dalla CLI {{site.data.keyword.dev_cli_short}} come definito da `container-name-run` e `container-name-tools`.

Immetti il seguente comando nella tua directory del progetto corrente per controllare lo stato del contenitore:

```
ibmcloud dev status
```
{: codeblock}


[Parametri comando status](#command-parameters)


## stop
{: #stop}

Puoi arrestare i tuoi contenitori tramite il comando `stop`.

Per arrestare gli strumenti ed eseguire i contenitori come definito nel tuo file `cli-config.yml`, esegui:

```
ibmcloud dev stop
```
{: codeblock}

Per arrestare un contenitore non definito nel file `cli-config.yml`, puoi specificare un ulteriore parametro della riga di comando per sovrascriverlo.  Se non viene specificato alcun contenitore nel file `cli-config.yml` o nella riga di comando, il comando stop viene semplicemente restituito.

### parametri comando stop
{: #stop-parameters}

I seguenti parametri vengono utilizzati per il comando `stop`. Esistono [ulteriori parametri](#command-parameters) condivisi con altri comandi.

#### `container-name-run`
{: #container-name-run}

* Il nome del contenitore di esecuzione.
* Utilizzo: `ibmcloud dev stop --container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* Il nome del contenitore degli strumenti.
* Utilizzo: `ibmcloud dev stop --container-name-tools [<projectName>]`



## test
{: #test}

Puoi eseguire la tua applicazione tramite il comando `test`. Deve prima essere completata una build nel progetto utilizzando il comando `build --debug`. Il contenitore degli strumenti viene quindi utilizzato per richiamare `test-cmd` per l'applicazione.

Per prima cosa, compila il tuo progetto:

```
ibmcloud dev build --debug
```
{: codeblock}

Immetti il seguente comando per verificare la tua applicazione:

```
ibmcloud dev test
```
{: codeblock}


### parametri comando test
{: #test-parameters}

Il seguente parametro è esclusivo per il comando `test`.  Esistono [ulteriori parametri](#command-parameters) condivisi con altri comandi.

#### `test-cmd`
{: #test-cmd}

* Parametro che viene utilizzato per specificare un comando per verificare il codice nel contenitore degli strumenti.
* Utilizzo: `ibmcloud dev test --test-cmd /the/test/command`


## view
{: #view}

Puoi visualizzare l'URL a cui viene distribuita la tua applicazione tramite il comando `view`. Esegui questo comando nella directory root dell'applicazione che vuoi visualizzare. Anche il comando `view` aprirà l'URL nel tuo browser predefinito.

Per le applicazioni distribuite a Cloud Foundry, l'URL è composto dal nome host e dal dominio dell'applicazione.

Per le applicazioni distribuite a Kubernetes, l'URL è composto dall'indirizzo IP del nodo a cui viene eseguita la distribuzione e la porta pubblica. Se il comando determina che l'applicazione è stata distribuita a Kubernetes, lo strumento CLI richiederà conferma. Se specifichi che l'applicazione non è stata effettivamente distribuita a Kubernetes, viene visualizzato l'URL Cloud Foundry. Se presupponi che il comando mostri l'URL di un'applicazione distribuita a Kubernetes ma non è così, assicurati che `cli-config.yml` contenga una voce per `chart-path` o forniscila tramite la riga di comando come mostrato [qui](#chart-path).

Immetti il seguente comando per visualizzare la tua applicazione:

```
ibmcloud dev view
```
{: codeblock}

### parametri comando view
{: #view-parameters}

I seguenti parametri sono esclusivi per il comando `view`.

#### `deploy-target`

* Parametro facoltativo utilizzato per indicare al tipo di distribuzione di ignorare la richiesta
* Utilizzo `ibmcloud dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* Parametro che viene utilizzato per specificare di non aprire il browser.
* Utilizzo: `ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Root del progetto da aggiungere all'URL dell'applicazione Kubernetes
* Utilizzo: `ibmcloud dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster2}

* Parametro facoltativo utilizzato per definire il nome del cluster Kubernetes quando indirizzi una distribuzione del contenitore
* Utilizzo `ibmcloud dev view --ibm-cluster [cluster-name]`


## comandi composti
{: #compound}

Puoi eseguire più comandi in una istruzione della riga di comando separando i comandi IDT con il delimitatore `/`. Possono essere specificati ulteriori indicatori della riga di comando dopo aver specificato i comandi composti.  I seguenti comandi sono esempi di come puoi utilizzare i comandi composti:

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Tutti gli indicatori devono seguire il comando finale e saranno applicati a tutti i comandi a cui sono associati. Nell'esempio precedente, l'indicatore `--trace` è applicabile a tutti e 3 i comandi, ma `-t` è applicabile solo agli ultimi 2 comandi, per cui non sarà applicato al comando `build`.

Questi sono i comandi che possono essere utilizzati con questa funzione:
`build, debug, deploy, get-credentials, run, stop, test, view`

Se un comando ha esito negativo per un qualsiasi motivo, i comandi successivi non verranno eseguiti. Se tutti i comandi che seguono `debug` o `run`, l'esecuzione continuerà solo se `debug` o `run` vengono terminati, il che significa di terminare il processo dalla finestra di terminale corrente. `CTRL+C` terminerà il processo e non eseguirà i comandi successivi. Ad esempio, puoi eseguire `ibmcloud dev stop` da un'altra finestra di terminale per arrestare il contenitore in esecuzione e continuare l'esecuzione al comando successivo.


## Parametri per build, debug, run e test
{: #command-parameters}

I seguenti parametri possono essere utilizzati con i comandi `build|debug|run|test` o aggiornando direttamente il file `cli-config.yml` del progetto. Sono disponibili ulteriori parametri per i comandi [`debug`](#debug-parameters) e [`run`](#run-parameters).

**Nota**: i parametri di comando immessi sulla riga di comando hanno la precedenza sulla configurazione `cli-config.yml`.

#### `config-file`  
{: #config-file}

* Specifica un file cli-config.yml da utilizzare per un comando.
* Utilizzo: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Il nome del contenitore di esecuzione.
* Utilizzo: `ibmcloud dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Il nome del contenitore degli strumenti.
* Utilizzo: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

#### `host-path-tools`
{: #host-path-tools}

* Ubicazione sull'host da condividere per la creazione, il debug e la verifica.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* Ubicazione nel contenitore da condividere per la creazione, il debug e la verifica.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* Associazioni di porta per il contenitore. Il primo valore è la porta da utilizzare nel SO host, il secondo è la porta nel contenitore [host-port:container-port].
* Utilizzo: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile del contenitore degli strumenti.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* Immagine da creare da `dockerfile-tools`.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* Utilizza questa opzione per definire i montaggi tra il sistema host e il contenitore di esecuzione.
* I valori `host-path-run` e `container-path-run` vengono inseriti all'inizio di questo elenco.
* Come procedura ottimale e per evitare risultati imprevisti, devi creare ed eseguire utilizzando le stesse impostazioni di montaggio.
* Utilizzo: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilizza questa opzione per definire i montaggi tra il sistema host e il contenitore degli strumenti.
* I valori `host-path-run` e `container-path-run` vengono inseriti all'inizio di questo elenco.* Come procedura ottimale e per evitare risultati imprevisti, devi creare ed eseguire il debug utilizzando le stesse impostazioni di montaggio.
* Utilizzo: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parametro che viene utilizzato per specificare un comando per creare il codice per tutti gli utilizzi di DEBUG.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Utilizza questo parametro per fornire l'output dettagliato.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --trace`
