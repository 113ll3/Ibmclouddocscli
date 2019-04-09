---

copyright:
   years: 2017, 2019
lastupdated: "2019-02-14"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}
{:note: .note}

# Comandi del plugin CLI {{site.data.keyword.dev_cli_notm}} (ibmcloud dev)
{: #idt-cli}

Versione: 2.1.4
Rilasciata: 31 agosto 2018

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.cloud}} `bluemix` e `bx` sono ora `ibmcloud`. Tuttavia, puoi ancora utilizzare i comandi della CLI `bluemix` e `bx` finché non vengono successivamente rimossi.
{: tip}

Utilizza i seguenti comandi della CLI {{site.data.keyword.dev_cli_notm}} (`ibmcloud dev`) per creare un'applicazione, gestirla, distribuirla, eseguirne il debug e verificarla.

- [build](#build): crea l'applicazione in un contenitore locale.
- [code](#code): scarica il codice per un'applicazione.
- [console](#console): apre la console {{site.data.keyword.cloud_notm}} per un'applicazione.
- [create](#create): crea una nuova applicazione e ti fornisce l'opzione per aggiungere i servizi.
- [debug](#debug): esegue il debug della tua applicazione in un contenitore locale.
- [delete](#delete): elimina un'applicazione dal tuo spazio.
- [deploy](#deploy): distribuisce un'applicazione a {{site.data.keyword.cloud_notm}}.
- [diag](#diag): visualizza le informazioni sulle dipendenze installate.
- [edit](#edit): aggiunge o rimuove servizi da un'applicazione esistente.
- [enable](#enable): aggiorna un'applicazione esistente per l'utilizzo con {{site.data.keyword.cloud_notm}} Developer Tools.
- [get-credentials](#get-credentials): ottiene le credenziali richieste dall'applicazione per abilitare l'uso di servizi {{site.data.keyword.cloud_notm}} connessi.
- [help](#help): guida sulla sintassi e gli argomenti della CLI.
- [list](#list): elenca tutte le applicazioni {{site.data.keyword.cloud_notm}} in un gruppo di risorse.
- [run](#run): esegue la tua applicazione in un contenitore locale.
- [shell](#shell): apre una shell in un contenitore locale.
- [status](#status): controlla lo stato dei contenitori utilizzati dalla CLI.
- [stop](#stop): arresta un contenitore.
- [test](#test): verifica la tua applicazione in un contenitore locale.
- [view](#view): visualizza l'URL distribuito dell'applicazione per la verifica e la visualizzazione.
- [comandi composti](#compound): esegui più comandi in una singola istruzione della riga di comando.

## build
{: #build}

Se stai utilizzando Windows&trade;, devi utilizzare Windows&trade; 10 Pro o versioni successive.

Puoi creare la tua applicazione utilizzando il comando `build`. I comandi `test`, `debug` e `run` si aspettano di trovare un'applicazione compilata, per cui devi prima eseguire un'operazione `build`.

Viene utilizzato l'elemento di configurazione `build-cmd-debug` per creare l'applicazione per tutti gli utilizzi ad eccezione di `run`. Crea la tua applicazione per il debug specificando l'opzione della riga di comando `--debug`. Viene utilizzato l'elemento di configurazione `build-cmd-run` quando stai creando l'applicazione per l'utilizzo con il comando `run`.

Per eseguire la creazione con più contenitori, la tua applicazione deve avere un file [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno"), che è specificato in `cli-config.yml`, oppure puoi utilizzare il parametro del comando `dockerfile-tools` per fornirne uno.

Esegui il seguente comando nella tua directory dell'applicazione corrente per creare la tua applicazione:  
```
ibmcloud dev build [--debug]
```
{: codeblock}

## code
{: #code}

Utilizza il comando `code` per scaricare un'applicazione precedentemente creata con il codice del template dell'applicazione e i file di configurazione per {{site.data.keyword.cloud_notm}}. Puoi utilizzare questo comando quando devi estrarre una seconda copia di un'applicazione.

Esegui il seguente comando per scaricare il codice da una specifica applicazione.
```
ibmcloud dev code <applicationName>
```
{: codeblock}

## console
{: #console}

Utilizza il comando `console` per aprire un browser web per la console web della tua applicazione su {{site.data.keyword.cloud_notm}}.  Puoi eseguire il comando `ibmcloud dev console` dall'interno della cartella della tua applicazione. La CLI prova a trovare un'applicazione corrispondente in {{site.data.keyword.cloud_notm}} che abbia lo stesso ID applicazione della directory corrente. Se non è in grado di trovare un nome corrispondente, il sistema apre il dashboard Web e mobile su {{site.data.keyword.cloud_notm}} invece dell'applicazione specifica.

Puoi fornire un nome applicazione e la CLI ignora la messa in corrispondenza basata sul nome della cartella o dell'applicazione. In questo caso, la CLI apre la console dell'applicazione denominata in un browser web.  

Immetti il seguente comando per aprire un browser web per la console web della tua applicazione.
```
ibmcloud dev console [applicationName]
```
{: codeblock}

## create
{: #create}

Crea un'applicazione richiedendo tutte le informazioni, compresi il tipo di risorsa, il linguaggio, il kit starter e le opzioni della toolchain DevOps, compresi IBM Cloud Foundry o Cloud Foundry Enterprise Environment e Kubernetes. L'applicazione viene creata nella directory corrente.

Per creare un'applicazione nella directory corrente e associare dei servizi ad essa, immetti il seguente comando:
```
ibmcloud dev create
```
{: codeblock}

## debug
{: #debug}

Se stai utilizzando Windows&trade;, devi eseguire Windows&trade; 10 Pro o versioni successive.

Puoi eseguire il debug della tua applicazione tramite il comando `debug`. Deve prima essere completata una build nell'applicazione utilizzando il comando di build con l'argomento `--debug`. Quando avvii il comando `debug` viene avviato un contenitore che fornisce una o più porte di debug come definito dal valore `container-port-map-debug` in cli-config.yml o specificato nella riga di comando. Collega il tuo strumento di debug preferito alla porta o alle porte e puoi eseguire il debug della tua applicazione normalmente.

Per prima cosa, compila la tua applicazione:
```
ibmcloud dev build --debug
```
{: codeblock}

Per iniziare, immetti il seguente comando nella tua directory dell'applicazione corrente per eseguire il debug della tua applicazione:
```
ibmcloud dev debug
```
{: codeblock}

Per eseguire il debug, collega il tuo strumento di debug alla porta specificata.

Per uscire dalla sessione di debug, utilizza `CTRL-C`.

### parametri comando debug
{: #debug-parameters}

I seguenti parametri sono esclusivi per il comando `debug` e
a assistono con il debug di un'applicazione. Ci sono dei [parametri aggiuntivi](#command-parameters) che sono condivisi con altri comandi.

#### `container-port-map-debug`
{: #port-map-debug}

* Associazioni di porta per la porta di debug. Il primo valore è la porta da utilizzare nel SO host, il secondo è la porta nel contenitore [porta-host:porta-contenitore].
* Utilizzo: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* Parametro che viene utilizzato per creare il codice per DEBUG.
* Utilizzo: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* Parametro che viene utilizzato per specificare un comando per avviare il debug nel contenitore degli strumenti. Utilizza questo parametro se `build-cmd-debug` avvia la tua applicazione in debug.
* Utilizzo: `ibmcloud dev debug --debug-cmd /the/debug/command`

## delete
{: #delete}

Utilizza il comando `delete` per rimuovere le applicazioni dal tuo spazio {{site.data.keyword.cloud_notm}}. Puoi eseguire il comando senza parametri per elencare le applicazioni disponibili e selezionare l'applicazione da eliminare dall'elenco numerato. Le directory e il codice dell'applicazione non vengono rimossi dal tuo spazio su disco locale.

Esegui il seguente comando per eliminare la tua applicazione da {{site.data.keyword.cloud_notm}}:
```
ibmcloud dev delete <applicationName>
```
{: codeblock}

I servizi {{site.data.keyword.cloud_notm}} non vengono rimossi.
{: note}

## deploy
{: #deploy}

Puoi distribuire un'applicazione come applicazione Cloud Foundry o come un contenitore.

Prima di distribuire un'applicazione Cloud Foundry a {{site.data.keyword.cloud_notm}}, un file `manifest.yml` deve essere presente nella directory root della tua applicazione.

Prima di distribuire un'applicazione come un contenitore, devi installare localmente [Kubernetes](https://kubernetes.io/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno") e [Helm](https://github.com/kubernetes/helm){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno"). La versione del client Helm non deve essere più recente della versione del server Helm. Puoi trovare entrambe eseguendo `helm version`. Si consiglia l'utilizzo della v2.4.2 per la versione client.

Per distribuire la tua applicazione su Kubernetes, devi specificare `deploy-target` come `container` in `cli-config.yml` oppure utilizzare il parametro `-t container`.

In `cli-config.yml` è anche possibile specificare altri parametri necessari per configurare la distribuzione Kubernetes utilizzando gli argomenti della riga di comando. Se non definisci questi parametri in `cli-config.yml`, devi eseguire la distribuzione con il parametro `-t container`. Ti vengono quindi richiesti tutti gli altri valori.

```yaml
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

In `cli-config.yml`, puoi scegliere di definire la posizione di un grafico Helm nella proprietà `chart-path` e configurare `deploy-image-target` come illustrato nell'esempio. L'elemento `deploy-image-target` in `cli-config.yml` viene utilizzato al posto degli elementi `repository` e `tag` nel file `chart/values.yml`. Per eseguire la distribuzione specificamente a {{site.data.keyword.cloud_notm}}, imposta l'elemento di configurazione `ibm-cluster` sul nome del cluster Kubernetes che hai creato in {{site.data.keyword.cloud_notm}}.

Esegui il seguente comando nella tua directory dell'applicazione corrente per creare la tua applicazione:  
```
ibmcloud dev build
```
{: codeblock}

Esegui il seguente comando nella tua directory dell'applicazione corrente per distribuire la tua applicazione:
```
ibmcloud dev deploy
```
{: codeblock}

### Esegui la distribuzione a {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment 
{: #deploy-cfee}

Puoi eseguire la distribuzione a un {{site.data.keyword.cloud_notm}} Foundry Enterprise Environment. Per eseguire questa operazione, configura il tuo ambiente locale per questo ambiente utilizzando `ibmcloud target --cf` e scegli quindi l'ambiente corretto da tale elenco. Puoi quindi utilizzare il comando `deploy` come faresti per {{site.data.keyword.cloud_notm}} Public Cloud Foundry.

### parametri comando deploy
{: #deploy-parameters}

I seguenti parametri possono essere utilizzati con il comando `deploy` o aggiornando direttamente il file `cli-config.yml` dell'applicazione. Ci sono dei [parametri aggiuntivi](#command-parameters) che sono condivisi con altri comandi.

#### `chart-path`
{: #chart-path}

* Parametro utilizzato per una distribuzione del contenitore per specificare l'ubicazione del grafico Helm utilizzato per la distribuzione.
* Utilizzo `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* Parametro facoltativo utilizzato per indicare il tipo di distribuzione che deve essere completata. Il tipo di distribuzione predefinito è pacchetto di build.
* Utilizzo `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* Parametro utilizzato con una distribuzione del contenitore come nome immagine di destinazione per la distribuzione. Il valore non deve includere una versione. Ad esempio: nome-immagine:{version} perché la versione viene automaticamente incrementata e accodata da `deploy`.
* Utilizzo `ibmcloud dev deploy --deploy-image-target [nome-immagine]`

#### `ibm-cluster`
{: #ibm-cluster}

* Parametro facoltativo utilizzato per definire il nome del cluster Kubernetes per una distribuzione del contenitore a {{site.data.keyword.Bluemix_notm}}
* Utilizzo `ibmcloud dev deploy --ibm-cluster [nome-cluster]`

#### `host`
{: #host}

* Parametro utilizzato facoltativamente per definire il nome host dell'applicazione quando esegui la distribuzione a Cloud Foundry
* Utilizzo `ibmcloud dev deploy --host [nome host]`

#### `domain`
{: #domain}

* Parametro utilizzato facoltativamente per definire il dominio dell'applicazione quando esegui la distribuzione a Cloud Foundry
* Utilizzo `ibmcloud dev deploy --domain [dominio]`

## diag
{: #diag}

Questo comando viene utilizzato come diagnostica per visualizzare le informazioni sulle dipendenze installate della CLI {{site.data.keyword.dev_cli_notm}}. Questa operazione è utile per determinare se ti manca qualche dipendenza o come ausilio nell'esecuzione del debug dei problemi.

Immetti il seguente comando per visualizzare le versioni delle tue dipendenze installate:
```
ibmcloud dev diag
```
{: codeblock}

## edit
{: #edit}

Modifica la tua applicazione con opzioni quali la sua connessione a un'applicazione già in {{site.data.keyword.cloud_notm}}, la gestione dei servizi {{site.data.keyword.cloud_notm}} dell'applicazione e la sua toolchain {{site.data.keyword.cloud_notm}} che esegue la distribuzione a IBM Cloud Kubernetes, Cloud Foundry o Cloud Foundry Enterprise Environment. Con un'applicazione locale connessa a un'applicazione in {{site.data.keyword.cloud_notm}}, usa `edit` per aggiungere nuovi servizi, connettere e disconnettere servizi esistenti o rimuovere servizi esistenti dal tuo account. Inoltre, puoi creare o visualizzare una toolchain {{site.data.keyword.cloud_notm}} per l'applicazione. Esegui il seguente comando nella root della tua directory dell'applicazione:
```
ibmcloud dev edit
```
{: codeblock}

Se non disponi di servizi esistenti sul tuo account, questo comando ti mostra un elenco dei gruppi di servizi da cui puoi selezionare un servizio da connettere alla tua applicazione.

Tuttavia, se hai dei servizi esistenti sul tuo account, questo comando ti mostra un elenco di questi servizi e se ciascun servizio è connesso all'applicazione o meno.

* Un servizio connesso ti offre le opzioni per disconnettere il servizio dalla tua applicazione o eliminare il servizio dal tuo account, disconnettendolo da tutte le applicazioni a cui è connesso.

* Un servizio disconnesso ti offre le opzioni per connettere tale servizio alla tua applicazione o eliminare il servizio dal tuo account. La connessione di un servizio esistente scarica anche i file, quali le credenziali o il codice sorgente per iniziare a utilizzare tale servizio.

Puoi anche aggiungere un nuovo servizio alla tua applicazione, dove vieni guidato nei prompt di selezione di servizio, e scaricare ulteriori file quali i file di credenziali o il codice sorgente per iniziare a utilizzare il nuovo servizio.

## enable
{: #enable}

Abilita un'applicazione esistente per la distribuzione a {{site.data.keyword.cloud_notm}}. Il comando `enable` tenta di rilevare automaticamente il linguaggio di un'applicazione esistente e poi richiede le ulteriori informazioni necessarie. Questo genera e aggiunge i file che possono essere utilizzati per i contenitori Docker locali, la distribuzione Cloud Foundry, la distribuzione Cloud Foundry Enterprise Environment o la distribuzione del contenitore Kubernetes. Tutti gli ambienti di distribuzione possono essere utilizzati mediante una distribuzione (`deploy`) manuale oppure utilizzando una toolchain DevOps.

Dopo che hai eseguito l'accesso a {{site.data.keyword.cloud_notm}}, puoi scegliere di connettere questa applicazione locale a un'applicazione che è già in {{site.data.keyword.cloud_notm}} oppure creare una nuova applicazione {{site.data.keyword.cloud_notm}}. Per avvalerti delle funzioni di {{site.data.keyword.cloud_notm}} quali i servizi e le toolchain DevOps, è necessaria un'applicazione in {{site.data.keyword.cloud_notm}}. Quando viene creata un'applicazione {{site.data.keyword.cloud_notm}} per un'applicazione clonata da un repository Git, l'applicazione {{site.data.keyword.cloud_notm}} include questo repository nella sua configurazione. 

`enable` è una funzione Beta. Se hai problemi ad abilitare la tua applicazione, la nostra [pagina dedicata alla risoluzione dei problemi](/docs/cli/ts_createapps.html#troubleshoot) ti offre assistenza. In particolare, `enable` non è progettata per i framework o le applicazioni mobili. Per applicazioni complesse che producono diversi asset distribuibili, è necessario abilitare ciascun componente dell'applicazione singolarmente. 

Esegui il seguente comando per abilitare un'applicazione esistente nella directory corrente:
```
ibmcloud dev enable
```
{: codeblock}

La presenza dei file necessari fornisce il rilevamento del linguaggio dell'applicazione per una struttura del progetto valida.  

* La presenza di un file `package.json` identifica un'applicazione Node.js.
* La presenza di un file `package.swift` identifica un'applicazione Swift.
* La presenza di un file `setup.py` o `requirements.txt` identifica un'applicazione Python.
* La presenza di un file `pom.xml` o `build.gradle` identifica un'applicazione Java.
	* La presenza di un `pom.xml` identifica un'applicazione Maven.
	* La presenza di un `build.gradle` identifica un'applicazione Gradle.

Facoltativamente, puoi anche sovrascrivere il linguaggio dell'applicazione rilevato utilizzando l'argomento `--language`.  Sono supportate solo le applicazioni complete e valide. Il comando enable non modifica il tuo codice sorgente.

### Opzioni di linguaggio di enable
{: #enable-language-options}

Le opzioni del linguaggio includono:
* node
* swift
* python
* java-ee (interpretato come Java&trade; - Java&trade; EE)
* java-mp (interpretato come Java&trade; - Java&trade; MicroProfile)
* java-spring (interpretato come Java&trade; - Spring Framework)

I file creati utilizzando il comando `ibmcloud dev enable`, e che hanno dei conflitti di denominazione con i file esistenti nella cartella dell'applicazione, vengono salvati con un'estensione file `.merge`.  

### Parametri del comando enable
{: #enable-parameters}

I seguenti parametri possono essere utilizzati con il comando `enable` o aggiornando direttamente il file `cli-config.yml` dell'applicazione. Ci sono dei [parametri aggiuntivi](#command-parameters) che sono condivisi con altri comandi.

#### `language`
{: #enable-language}

* Parametro utilizzato per specificare il linguaggio dell'applicazione da abilitare.
* Utilizzo `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* Parametro utilizzato per forzare la riabilitazione di un'applicazione già abilitata.
* Utilizzo `ibmcloud dev enable -f|--force`

#### `no-create`
{: #enable-no-create}

* Parametro per impedire la creazione di un'applicazione in {{site.data.keyword.Bluemix_notm}} durante la creazione dei file di abilitazione localmente.
* Utilizzo: `ibmcloud dev enable --no-create`

## get-credentials
{: #get-credentials}

Ottiene le credenziali richieste dall'applicazione per abilitare l'utilizzo di servizi connessi.

## help
{: #help}

Per impostazione predefinita, se non viene trasmesso alcun argomento o azione o se viene fornita l'azione 'help', questo comando mostra un testo di "Aiuto" generale. La guida generale visualizzata include una descrizione degli argomenti di base e un elenco delle azioni disponibili.  

Immetti il seguente comando per visualizzare le informazioni della guida generale:
```
ibmcloud dev help
```
{: codeblock}

## list
{: #list}

Puoi elencare tutte le applicazioni {{site.data.keyword.cloud_notm}} in un gruppo di risorse.

Esegui il seguente comando per elencare le tue applicazioni:
```
ibmcloud dev list
```
{: codeblock}

## run
{: #run}

Se stai utilizzando Windows&trade;, devi eseguire Windows&trade; 10 Pro o versioni successive.

Puoi eseguire la tua applicazione tramite il comando `run`. Deve prima essere completata una build sull'applicazione utilizzando il comando `build`. Quando esegui il comando `run`, viene avviato il contenitore di esecuzione che espone le porte come definito dal parametro `container-port-map`. Il parametro `run-cmd` viene utilizzato per richiamare l'applicazione se il `Dockerfile` del contenitore di esecuzione non contiene un punto di ingresso per completare questa fase.

Per l'esecuzione con più contenitori, la tua applicazione deve contenere un file [Compose](https://docs.docker.com/compose/overview/){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno"), specificato in `cli-config.yml`, oppure puoi utilizzare il parametro del comando `dockerfile-run` per fornirne uno.

Per prima cosa, compila la tua applicazione:
```
ibmcloud dev build
```
{: codeblock}

Esegui il seguente comando nella tua directory dell'applicazione corrente per avviare la tua applicazione:
```
ibmcloud dev run
```
{: codeblock}

Per uscire dalla sessione utilizza `CTRL-C`.

### parametri comando run
{: #run-parameters}

I seguenti parametri sono esclusivi per il comando `run` e
assistono con la gestione della tua applicazione all'interno del contenitore in esecuzione.
Ci sono dei [parametri aggiuntivi](#command-parameters) che sono condivisi con altri comandi.

#### `container-name-run`
{: #container-name-run2}

* Il nome del contenitore di esecuzione.
* Utilizzo: `ibmcloud dev run --container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* Ubicazione nel contenitore da condividere all'esecuzione.
* Utilizzo: `ibmcloud dev run --container-path-run [/percorso/ad/applicazione]`

#### `host-path-run`
{: #host-path-run}

* Ubicazione sul sistema host da condividere nel contenitore all'esecuzione.
* Utilizzo: `ibmcloud dev run --host-path-run [/percorso/a/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* Dockerfile del contenitore di esecuzione.
* Se prevedi un'esecuzione con diversi contenitori, questo deve essere un file Compose.
* Per utilizzare più file di composizione, racchiudi tra virgolette un elenco delimitato da virgole dei nomi dei file.
* Utilizzo: `ibmcloud dev run --dockerfile-run [/percorso/a/Dockerfile]`
* Utilizzo: `ibmcloud dev run --dockerfile-run "/percorso/a/file/compose, /percorso/a/un/altro/file/compose, ..."`

#### `image-name-run`
{: #image-name-run}

* Immagine da creare da `dockerfile-run`.
* Utilizzo: `ibmcloud dev run --image-name-run [/percorso/a/nome-immagine]`

#### `run-cmd`
{: #run-cmd}

* Parametro che viene utilizzato per eseguire il codice nel contenitore di esecuzione. Utilizza questo parametro se la tua immagine avvia la tua applicazione.
* Utilizzo: `ibmcloud dev run --run-cmd [/the/run/command]`

## shell
{: #shell}

Se stai utilizzando Windows&trade;, devi eseguire Windows&trade; 10 Pro o versioni successive.

Puoi aprire la shell all'interno del contenitore di esecuzione o degli strumenti con il comando `shell`.

Eseguendo il seguente comando:
```
ibmcloud dev shell
```
{: codeblock}

La CLI {{site.data.keyword.dev_cli_short}} apre una shell interattiva nel contenitore docker dell'applicazione. Il contenitore di destinazione predefinito per il comando shell è definito dal valore `container-shell-target` nel file `cli-config.yml`, dove i valori validi sono `run` o `tools`. Se questo valore non è definito o viene specificato un valore non valido, il comando `shell` punta al contenitore `tools` per impostazione predefinita. Il comando shell apre il contenitore nella directory specificata dall'istruzione `WORKDIR` nel Dockerfile corrispondente. Se `WORKDIR` non è elencato nel Dockerfile, viene utilizzata la root del contenitore come directory di lavoro. Per ulteriori informazioni, vedi [questo riferimento](https://docs.docker.com/engine/reference/builder/#workdir){: new_window} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno").

In alternativa, puoi decidere di passare `run` o `tools` come un argomento al comando; tale contenitore viene attivato e la shell viene aperta per tale contenitore. Allo stesso modo, puoi utilizzare il parametro `container-name` per passare il nome del contenitore in cui vuoi utilizzare la shell. Tuttavia, questo indicatore dovrebbe essere riservato per quando non ci sono contenitori in esecuzione. Gli argomenti `run` e `tools` sono più flessibili e ti consentono di passare da un contenitore all'altro quando uno di essi è in esecuzione. Ad esempio, se il contenitore degli strumenti è in esecuzione ed esegui `ibmcloud dev shell run`, il contenitore `tools` viene arrestato e il contenitore `run` viene avviato e viceversa.

Se il contenitore `run` o `tools` di destinazione non è ancora in esecuzione quando esegui il comando `shell`, il contenitore di destinazione viene avviato. Tuttavia, il valore predefinito `Cmd` o `Entrypoint` nel Dockerfile viene sovrascritto per l'avvio direttamente nella shell invece di avviare il processo del server. Questo ti consente di avviare il contenitore `run` o `tools` e avviare manualmente il server con i comandi personalizzati o quando preferisci.

Puoi anche specificare l'eseguibile della shell che vuoi aprire utilizzando il parametro `container-shell`. Per impostazione predefinita, viene utilizzato `/bin/sh`. Se preferisci usare la shell bash, specifica che il valore `container-shell` sia `/bin/bash`; tuttavia, tieni presente che bash non è disponibile automaticamente in tutte le varianti Linux&trade;.

Tutti gli argomenti aggiuntivi che passi al comando oltre agli indicatori sono analizzati come il comando da eseguire quando la shell è aperta. Se fornisci un comando, la shell all'interno del contenitore si chiude dopo l'esecuzione del comando e ti riporta al tuo terminale.

Ad esempio, puoi eseguire il comando Linux &trade; `ls` nella shell del contenitore degli strumenti richiamando `ibmcloud dev shell tools ls`. Puoi anche specificare ulteriori indicatori da passare nell'esecuzione del comando della shell racchiudendo gli argomenti tra virgolette, come ad esempio `ibmcloud dev shell "ls -la"`.

### parametri comando shell
{: #shell-parameters}

#### `container-name`
{: #container-name}

* Nome del contenitore in cui vuoi eseguire la shell.
* Utilizzo: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* Specifica quale shell eseguire all'interno del contenitore (il valore predefinito è /bin/sh).
* Utilizzo: `ibmcloud dev shell --container-shell [percorso/alla/shell]`

## status
{: #status}

Se stai utilizzando Windows&trade;, devi utilizzare Windows&trade; 10 Pro o versioni successive.

Puoi eseguire la query dello stato dei contenitori che sono utilizzati dalla CLI {{site.data.keyword.dev_cli_short}} come definito da `container-name-run` e `container-name-tools`.

Esegui il seguente comando nella tua directory dell'applicazione corrente per controllare lo stato del contenitore:
```
ibmcloud dev status
```
{: codeblock}

[Parametri comando status](#command-parameters)

## stop
{: #stop}

Se stai utilizzando Windows&trade;, devi eseguire Windows&trade; 10 Pro o versioni successive.

Puoi arrestare i tuoi contenitori tramite il comando `stop`.

Per arrestare gli strumenti ed eseguire i contenitori come definito nel tuo file `cli-config.yml`, esegui:
```
ibmcloud dev stop
```
{: codeblock}

Per arrestare un contenitore che non è definito nel file `cli-config.yml`, puoi specificare un ulteriore parametro della riga di comando per sovrascriverlo. Se non viene specificato alcun contenitore nel file `cli-config.yml` o nella riga di comando, il comando stop viene semplicemente restituito.

### parametri comando stop
{: #stop-parameters}

I seguenti parametri vengono utilizzati per il comando `stop`. Ci sono dei [parametri aggiuntivi](#command-parameters) che sono condivisi con altri comandi.

#### `container-name-run`
{: #container-name-run}

* Il nome del contenitore di esecuzione.
* Utilizzo: `ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* Il nome del contenitore degli strumenti.
* Utilizzo: `ibmcloud dev stop --container-name-tools [<applicationName>]`

## test
{: #test}

Se stai utilizzando Windows&trade;, devi eseguire Windows&trade; 10 Pro o versioni successive.

Puoi eseguire la tua applicazione tramite il comando `test`. Deve prima essere completata una build sull'applicazione utilizzando il comando `build --debug`. Il contenitore degli strumenti viene quindi utilizzato per avviare il `test-cmd` per l'applicazione.

Per prima cosa, compila la tua applicazione:
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

Il seguente parametro è esclusivo per il comando `test`. Ci sono dei [parametri aggiuntivi](#command-parameters) che sono condivisi con altri comandi.

#### `test-cmd`
{: #test-cmd}

* Parametro che viene utilizzato per specificare un comando per verificare il codice nel contenitore degli strumenti.
* Utilizzo: `ibmcloud dev test --test-cmd /the/test/command`

## view
{: #view}

Puoi visualizzare l'URL a cui viene distribuita la tua applicazione tramite il comando `view`. Esegui questo comando nella directory root dell'applicazione che vuoi visualizzare. Anche il comando `view` apre l'URL nel tuo browser predefinito.

Per le applicazioni distribuite a Cloud Foundry, l'URL è composto dal nome host e dal dominio dell'applicazione.

Per le applicazioni distribuite a Kubernetes, l'URL è composto dall'indirizzo IP del nodo a cui viene eseguita la distribuzione e la porta pubblica. Se il comando determina che l'applicazione è stata distribuita a Kubernetes, lo strumento CLI richiede conferma. Se specifichi che l'applicazione non è stata distribuita a Kubernetes, viene visualizzato l'URL Cloud Foundry. Se prevedevi che il comando visualizzasse l'URL per un'applicazione distribuita a Kubernetes, assicurati che `cli-config.yml` contenga una voce per `chart-path` oppure forniscila tramite la riga di comando come mostrato [qui](#chart-path).

Immetti il seguente comando per visualizzare la tua applicazione:
```
ibmcloud dev view
```
{: codeblock}

### parametri comando view
{: #view-parameters}

I seguenti parametri sono esclusivi per il comando `view`.

#### `deploy-target`

* Parametro facoltativo utilizzato per indicare il tipo di distribuzione per ignorare il prompt.
* Utilizzo `ibmcloud dev view -t|--target buildpack|container`

#### `no-open`
{: #no-open}

* Parametro che viene utilizzato per specificare di non aprire il browser.
* Utilizzo: `ibmcloud dev view --no-open`

#### `web-app-root`
{: #web-app-root}

* Root del progetto da aggiungere all'URL dell'applicazione Kubernetes e Cloud Foundry.
* Utilizzo: `ibmcloud dev view --web-app-root [root]`

#### `ibm-cluster`
{: #ibm-cluster2}

* Parametro facoltativo utilizzato per definire il nome del cluster Kubernetes quando indichi come destinazione una distribuzione del contenitore.
* Utilizzo `ibmcloud dev view --ibm-cluster [cluster-name]`

## comandi composti
{: #compound}

Puoi eseguire diversi comandi in una istruzione della riga di comando separando i comandi di {{site.data.keyword.cloud_notm}} Developer Tools con il delimitatore `/`. Possono essere utilizzati ulteriori indicatori della riga di comando dopo aver specificato i comandi composti.  I seguenti comandi sono esempi di come puoi utilizzare i comandi composti:
```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

Tutti gli indicatori devono seguire il comando finale ed essere applicati a tutti i comandi a cui sono associati. Utilizzando `ibmcloud dev build/deploy/view -t container --trace` come un esempio, l'indicatore `--trace` viene applicato a tutti e tre i comandi, ma `-t` è applicabile solo ai due comandi finali e non sarà applicato al comando `build`.

Con questa funzione possono essere utilizzati i seguenti comandi:
`build, debug, deploy, get-credentials, run, stop, test, view`

Se un comando ha esito negativo per un qualsiasi motivo, i comandi successivi non vengono eseguiti.

Se qualche comando segue a `debug` o `run`, l'esecuzione continua se `debug` o `run` vengono terminati utilizzando un metodo diverso dal terminare il processo dalla finestra di terminale corrente. `CTRL+C` termina il processo e non esegue i comandi successivi. Ad esempio, puoi eseguire `ibmcloud dev stop` da un'altra finestra di terminale per arrestare il contenitore in esecuzione e continuare l'esecuzione al comando successivo.

## Parametri per build, debug, run e test
{: #command-parameters}

I seguenti parametri possono essere utilizzati con i comandi `build|debug|run|test` o aggiornando direttamente il file `cli-config.yml` dell'applicazione. Sono disponibili ulteriori parametri per i comandi [`debug`](#debug-parameters) e [`run`](#run-parameters).

I parametri di comando immessi sulla riga di comando hanno la precedenza sulla configurazione `cli-config.yml`.
{: note}

#### `config-file`  
{: #config-file}

* Specifica un file cli-config.yml da utilizzare per un comando.
* Utilizzo: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* Il nome del contenitore di esecuzione.
* Utilizzo: `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* Il nome del contenitore degli strumenti.
* Utilizzo: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* Ubicazione sull'host da condividere per la creazione, il debug e la verifica.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --host-path-tools [/percorso/per/strumenti/build]`

#### `container-path-tools`
{: #container-path-tools}

* Ubicazione nel contenitore da condividere per la creazione, il debug e la verifica.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --container-path-tools [/percorso/per/build]`

#### `container-port-map`
{: #container-port-map}

* Associazioni di porta per il contenitore. Il primo valore è la porta da utilizzare nel SO host, il secondo è la porta nel contenitore [porta-host:porta-contenitore].
* Utilizzo: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* Dockerfile del contenitore degli strumenti.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [percorso/al/filedocker]`

#### `image-name-tools`
{: #image-name-tools}

* Immagine da creare da `dockerfile-tools`.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --image-name-tools [percorso/al/nome-immagine]`

#### `container-mounts-run`
{: #container-mounts-run}

* Utilizza questa opzione per definire i montaggi tra il sistema host e il contenitore di esecuzione.
* I valori `host-path-run` e `container-path-run` vengono inseriti all'inizio di questo elenco.
* Come procedura ottimale e per evitare risultati imprevisti, puoi creare ed eseguire utilizzando le stesse impostazioni di montaggio.
* Utilizzo: `ibmcloud dev <build|run|test> --container-mounts-run [/percorso/relativo/a/dir/host:/percorso/assoluto/a/dir/contenitore ecc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* Utilizza questa opzione per definire i montaggi tra il sistema host e il contenitore degli strumenti.
* I valori `host-path-tools` e `container-path-tools` vengono inseriti all'inizio di questo elenco * Come procedura ottimale e per evitare risultati imprevisti, puoi creare ed eseguire il debug utilizzando le stesse impostazioni di montaggio.
* Utilizzo: `ibmcloud dev <build|debug|test> --container-mounts-tools [/percorso/relativo/a/dir/host:/percorso/assoluto/a/dir/contenitore ecc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* Parametro che viene utilizzato per specificare un comando per creare il codice per tutti gli utilizzi di DEBUG.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* Utilizza questo parametro per fornire l'output dettagliato.
* Utilizzo: `ibmcloud dev <build|debug|run|test> --trace`
