---



copyright:

  years: 2017, 2018

lastupdated: "2018-04-17"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong_notm}}CLI
{: #containerregcli}

La CLI {{site.data.keyword.registrylong}} è un plug-in per la gestione del tuo registro e delle relative risorse per il tuo account {{site.data.keyword.Bluemix_notm}}.
{: shortdesc}

**Prerequisiti**
* Prima di eseguire i comandi del registro, accedi a {{site.data.keyword.Bluemix_notm}}
 con il comando `bx login` per generare un token di accesso e autenticare la tua sessione.

Per scoprire come utilizzare la CLI {{site.data.keyword.registrylong_notm}}, vedi [Introduzione a {{site.data.keyword.registrylong_notm}}](../../../services/Registry/index.html).

<table summary="Gestisci {{site.data.keyword.registrylong_notm}}">
<caption>Tabella 1. Comandi per la gestione di {{site.data.keyword.registrylong_notm}}
</caption>
 <thead>
 <th colspan="5">Comandi per la gestione del registro</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr build](#bx_cr_build)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (bx cr images)](#bx_cr_image_list)</td>
 </tr>
 <tr>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 <td>[bx cr login](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (bx cr namespaces)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 </tr>
 <tr>
 <td>[bx cr plan](#bx_cr_plan)</td>
 <td>[bx cr plan-upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr quota](#bx_cr_quota)</td>
 <td>[bx cr quota-set](#bx_cr_quota_set)</td>
 <td>[bx cr region](#bx_cr_region)</td>
 </tr>
 <tr>
 <td>[bx cr region-set](#bx_cr_region_set)</td>
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 <td>[bx cr token-get](#bx_cr_token_get)</td>
 <td>[bx cr token-list (bx cr tokens)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>
 </tr><tr>
 <td>[bx cr vulnerability-assessment (bx cr va)](#bx_cr_va)</td>
 </tr>
 </tbody></table>



## bx cr api
{: #bx_cr_api}

Restituisce i dettagli sull'endpoint dell'API del registro per cui vengono eseguiti i comandi.

```
bx cr api
```
{: codeblock}


## bx cr build
{: #bx_cr_build}

Crea un'immagine Docker in {{site.data.keyword.registrylong_notm}}.

```
bx cr build [--no-cache] [--pull] [--quiet | -q] [--build-arg KEY=VALUE ...] [--file FILE | -f FILE] --tag TAG DIRECTORY
```
{: codeblock}

**Parametri**
<dl>
<dt>DIRECTORY</dt>
<dd>L'ubicazione del tuo contesto di build, che contiene i tuoi file Dockerfile e prerequisiti.</dd>
<dt>--no-cache</dt>
<dd>(Facoltativo)  Se specificato, i livelli di immagine memorizzati in cache dalle build precedenti non vengono utilizzati in questa build.</dd>
<dt>--pull</dt>
<dd>(Facoltativo) Se specificato, le immagini di base vengono estratte anche se sull'host di build esiste già un'immagine con una tag corrispondente.</dd>
<dt>--quiet, -q</dt>
<dd>(Facoltativo) Se specificato, l'output di build viene eliminato a meno che non si verifichi un errore.</dd>
<dt> --build-arg KEY=VALUE</dt>
<dd>(Facoltativo) Specificare un argomento di build aggiuntivo nel formato 'CHIAVE=VALORE'. È possibile specificare più argomenti di build includendo questo parametro più volte. Il valore di ogni argomento di build è disponibile come variabile di ambiente quando specifichi una riga ARG che corrisponde alla chiave nel tuo Dockerfile.</dd>
<dt>--file FILE, -f FILE</dt>
<dd>(Facoltativo)  Se utilizzi gli stessi file per più build, puoi scegliere un percorso di un Dockerfile diverso. Specifica la posizione del Dockerfile in relazione al contesto di build. Se non specificato, il valore predefinito è `PATH/Dockerfile`, dove PATH è la root del contesto di build.</dd>
<dt>--tag TAG, -t TAG</dt>
<dd>Il nome completo dell'immagine di cui vuoi eseguire la build, che include l'URL del registro e lo spazio dei nomi.</dd>
</dl>


## bx cr info
{: #bx_cr_info}

Visualizza il nome e l'account del registro a cui sei collegato.

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
{: #bx_cr_image_inspect}

Visualizza i dettagli di una specifica immagine.

```
bx cr image-inspect [--format FORMATO] IMMAGINE [IMMAGINE...]
```
{: codeblock}

**Parametri**
<dl>
<dt>--format FORMATO</dt>
<dd>(Facoltativo) Formatta gli elementi di output utilizzando un modello Go. 

Per ulteriori informazioni, vedi [Formattazione e filtro dell'output della CLI per i comandi {{site.data.keyword.registrylong_notm}}](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>IMAGE</dt>
<dd>Il nome dell'immagine per cui vuoi ottenere un report. Puoi analizzare più immagini elencando ogni immagine nel comando con uno spazio tra ciascun nome.

<p>Per trovare i nomi delle tue immagini, esegui `bx cr image-list`. Combina il contenuto delle colonne Repository e Tag per creare il nome dell'immagine nel formato `repository:tag`. Se nel nome immagine non è specificata una tag, viene analizzata l'immagine contrassegnata con `latest`. </p> 

</dd>
</dl>


## bx cr image-list (bx cr images)
{: #bx_cr_image_list}

Visualizza tutte le immagini nel tuo account {{site.data.keyword.Bluemix_notm}}.

<p>**Nota:** il nome dell'immagine è la combinazione del contenuto delle colonne Repository e Tag nel formato `repository:tag`. </p> 

```
 bx cr image-list [--no-trunc] [--format FORMATO] [-q, --quiet] [--restrict LIMITAZIONE] [--include-ibm] 
```
{: codeblock}

**Parametri**
<dl>
<dt>--no-trunc</dt>
<dd>(Facoltativo) Non troncare i digest immagine.</dd>
<dt>--format FORMATO</dt>
<dd>(Facoltativo) Formatta gli elementi di output utilizzando un modello Go. 

Per ulteriori informazioni, vedi [Formattazione e filtro dell'output della CLI per i comandi {{site.data.keyword.registrylong_notm}}](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
<dt>-q, --quiet</dt>
<dd>(Facoltativo) Ogni immagine viene elencata nel formato: `repository:tag`</dd>
<dt>--restrict LIMITAZIONE</dt>
<dd>(Facoltativo) Limita l'output per visualizzare solo le immagini nello spazio dei nomi o nello spazio dei nomi e nel repository specificati. </dd>
<dt>--include-ibm</dt>
<dd>(Facoltativo) Include le immagini pubbliche fornite da {{site.data.keyword.IBM_notm}} nell'output. Senza questa opzione, vengono elencate solo le immagini private per impostazione predefinita.</dd>
</dl>



## bx cr image-rm
{: #bx_cr_image_rm}

Elimina una o più immagini specificate dal tuo registro.

```
bx cr image-rm IMMAGINE [IMMAGINE...]
```
{: codeblock}

**Parametri**
<dl>
<dt>IMMAGINE</dt>
<dd>Il nome dell'immagine per cui vuoi ottenere un report. Puoi eliminare più immagini contemporaneamente elencando ogni immagine nel comando con uno spazio tra ciascun nome.

<p>Per trovare i nomi delle tue immagini, esegui `bx cr image-list`. Combina il contenuto delle colonne Repository e Tag per creare il nome dell'immagine nel formato `repository:tag`. Se nel nome immagine non è specificata una tag, per impostazione predefinita viene eliminata l'immagine contrassegnata con `latest`.</p> 

</dd>
</dl>


## bx cr login
{: #bx_cr_login}

Questo comando esegue il comando `docker login` sul registro. Il comando `docker login` è obbligatorio per abilitare l'esecuzione dei comandi `docker push` o `docker pull` per il registro. Questo comando non è obbligatorio per eseguire altri comandi `bx cr`. Se Docker non è installato, questo comando restituisce un messaggio di errore.

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
{: #bx_cr_namespace_add}

Aggiunge uno spazio dei nomi al tuo account {{site.data.keyword.Bluemix_notm}}.

```
bx cr namespace-add SPAZIONOMI
```
{: codeblock}

**Parametri**
<dl>
<dt>SPAZIONOMI</dt>
<dd>Lo spazio dei nomi che desideri aggiungere. Lo spazio dei nomi deve essere univoco tra tutti gli account {{site.data.keyword.Bluemix_notm}} nella stessa regione.</dd>
</dl>


## bx cr namespace-list (bx cr namespaces)
{: #bx_cr_namespace_list}

Visualizza tutti gli spazi dei nomi che appartengono al tuo account {{site.data.keyword.Bluemix_notm}}.

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
{: #bx_cr_namespace_rm}

Rimuove uno spazio dei nomi dal tuo account {{site.data.keyword.Bluemix_notm}}. Le immagini in questo spazio dei nomi vengono eliminate quando si rimuove lo spazio dei nomi.

```
bx cr namespace-rm SPAZIONOMI
```
{: codeblock}

**Parametri**
<dl>
<dt>SPAZIONOMI</dt>
<dd>Lo spazio dei nomi che desideri rimuovere.</dd>
</dl>


## bx cr plan
{: #bx_cr_plan}

Visualizza il piano dei prezzi.

```
bx cr plan
```
{: codeblock}


## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

Esegue il tuo upgrade al piano standard.

Per informazioni sui piani, vedi [Piani del registro](../../../services/Registry/registry_overview.html#registry_plans).

```
bx cr plan-upgrade [PIANO]
```
{: codeblock}

**Parametri**
<dl>
<dt>PIANO</dt>
<dd>Il nome del piano di prezzi che si desidera aggiornare. Se PIANO non viene specificato, il valore predefinito è `standard`.</dd>
</dl>


## bx cr quota
{: #bx_cr_quota}

Visualizza le tue quote correnti per traffico e archiviazione e le informazioni di utilizzo rispetto a tali quote.

```
bx cr quota
```
{: codeblock}


## bx cr quota-set
{: #bx_cr_quota_set}

Modifica la quota specificata.

```
bx cr quota-set [--traffic TRAFFICO] [--storage ARCHIVIAZIONE]
```
{: codeblock}

**Parametri**
<dl>
<dt>--traffic TRAFFICO</dt>
<dd>(Facoltativo) Modifica la tua quota di traffico al valore specificato, in megabyte. L'operazione non riesce se non sei autorizzato a impostare il traffico o se imposti un valore che supera il tuo piano dei prezzi corrente.</dd>
<dt>--storage ARCHIVIAZIONE</dt>
<dd>(Facoltativo) Modifica la tua quota di archiviazione al valore specificato, in megabyte. L'operazione non riesce se non sei autorizzato a impostare le quote di archiviazione o se imposti un valore che supera il tuo piano dei prezzi corrente.</dd>
</dl>


## bx cr region
{: #bx_cr_region}

Visualizza la regione di destinazione e il registro.

```
bx cr region
```
{: codeblock}

Per ulteriori informazioni, vedi [Regioni](../../../services/Registry/registry_overview.html#registry_regions).


## bx cr region-set
{: #bx_cr_region_set}

Imposta una regione di destinazione per i comandi {{site.data.keyword.registrylong_notm}}. Per elencare le regioni disponibili, esegui il comando senza parametri.

```
bx cr region-set [REGIONE]
```
{: codeblock}

**Parametri**
<dl>
<dt>REGIONE</dt>
<dd>(Facoltativo) Il nome della tua regione di destinazione, ad esempio, `us-south`. 

Per ulteriori informazioni, vedi [Regioni](../../../services/Registry/registry_overview.html#registry_regions).

</dd>
</dl>


## bx cr token-add
{: #bx_cr_token_add}

Aggiunge un token che puoi utilizzare per controllare l'accesso a un registro.

```
bx cr token-add [--description DESCRIZIONE] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**Parametri**
<dl>
<dt>--description DESCRIZIONE</dt>
<dd>(Facoltativo) Specifica il valore come descrizione per il token, che viene visualizzata quando esegui `bx cr token-list`. Se il tuo token viene creato automaticamente da {{site.data.keyword.containerlong_notm}}, la descrizione viene impostata sul nome del tuo cluster Kubernetes. In questo caso, il token viene rimosso automaticamente alla rimozione del cluster.</dd>
<dt>-q, --quiet</dt>
<dd>(Facoltativo) Visualizza solo il token, senza alcun testo circostante.</dd>
<dt>--non-expiring</dt>
<dd>(Facoltativo) Crea un token con l'accesso che non scade. Se questo parametro non è impostato, l'accesso da un token scade dopo 24 ore per impostazione predefinita.</dd>
<dt>--readwrite</dt>
<dd>(Facoltativo) Crea un token che concede l'accesso di lettura e scrittura. Senza questa opzione, l'accesso è di sola lettura per impostazione predefinita.</dd>
</dl>


## bx cr token-get
{: #bx_cr_token_get}

Richiama il token specificato dal registro.

```
bx cr token-get TOKEN
```

{: codeblock}

**Parametri**
<dl>
<dt>TOKEN</dt>
<dd>(Facoltativo) L'identificativo univoco del token che desideri richiamare.</dd>
</dl>


## bx cr token-list (bx cr tokens)
{: #bx_cr_token_list}

Visualizza tutti i token esistenti per il tuo account {{site.data.keyword.Bluemix_notm}}.

```
bx cr token-list --format FORMATO
```
{: codeblock}

**Parametri**
<dl>
<dt>--format FORMATO</dt>
<dd>(Facoltativo) Formatta gli elementi di output utilizzando un modello Go. 

Per ulteriori informazioni, vedi [Formattazione e filtro dell'output della CLI per i comandi {{site.data.keyword.registrylong_notm}}](../../../services/Registry/registry_cli_reference.html#registry_cli_listing).

</dd>
</dl>


## bx cr token-rm
{: #bx_cr_token_rm}

Rimuove uno o più token specificati.

```
bx cr token-rm TOKEN [TOKEN...]
```
{: codeblock}

**Parametri**
<dl>
<dt>TOKEN</dt>
<dd>(Facoltativo) TOKEN può essere il token stesso o l'identificativo univoco del token, come mostrato in `bx cr token-list`. È possibile specificare più token e devono essere separati da uno spazio.</dd>
</dl>


## bx cr vulnerability-assessment (bx cr va)
{: #bx_cr_va}

Visualizza un report di valutazione delle vulnerabilità per le tue immagini.

```
bx cr vulnerability-assessment [--extended | -e] [--vulnerabilities | -v] [--configuration-issues | -c] [--output FORMATO | -o FORMATO] IMMAGINE [IMMAGINE...] 
```
{: codeblock}

**Parametri**
<dl>
<dt>IMMAGINE</dt>
<dd>Il nome dell'immagine per cui vuoi ottenere un report. Il report ti informa se l'immagine ha delle vulnerabilità di pacchetto note. Puoi richiedere report per più immagini contemporaneamente elencando ogni immagine nel comando con uno spazio tra ciascun nome.

<p>Per trovare i nomi delle tue immagini, esegui `bx cr image-list`. Combina il contenuto delle colonne Repository e Tag per creare il nome dell'immagine nel formato `repository:tag`. Se nel nome immagine non è specificata una tag, il report valuta l'immagine contrassegnata con `latest`. </p> 

<p>Sono supportati i seguenti sistemi operativi:

<ul>

<li>Alpine</li>
<li>CentOS</li>
<li>Debian</li>
<li>RHEL (Red Hat Enterprise Linux)</li>
<li>Ubuntu</li>
</ul>

</p>

Per ulteriori informazioni, vedi [Gestione della sicurezza delle immagini con il Controllo vulnerabilità](../../../services/va/va_index.html).

</dd>
<dt>--output FORMATO, -o FORMATO</dt>
<dd>(Facoltativo) L'output del comando viene restituito nel formato scelto. Il formato predefinito è `text`. Sono supportati i seguenti formati:

<ul>

<li>`text`</li>
<li>`json`</li>
</ul>

</dd>
<dt>--vulnerabilities, -v</dt>
<dd>(Facoltativo) L'output del comando è limitato per mostrare solo le vulnerabilità.</dd>
<dt>--configuration-issues, -c</dt>
<dd>(Facoltativo) L'output del comando è limitato per mostrare solo problemi di configurazione.</dd>
<dt>--extended, -e </dt>
<dd>(Facoltativo) L'output del comando mostra informazioni aggiuntive sulle correzioni per i pacchetti vulnerabili.</dd>

</dl>

