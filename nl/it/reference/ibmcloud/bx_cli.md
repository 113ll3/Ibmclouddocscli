---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# Comandi generali della CLI (ibmcloud)
{: #ibmcloud_cli}

L'interfaccia di riga comando (CLI) {{site.data.keyword.cloud_notm}} fornisce una serie di comandi che vengono raggruppati in base allo spazio dei nomi per consentire agli utenti di interagire con {{site.data.keyword.cloud_notm}}.
{: shortdesc}

Il client riga di comando {{site.data.keyword.cloud_notm}} include un client riga di comando Cloud Foundry nella sua installazione. Se la tua CLI Cloud Foundry è installata, non utilizzare i comandi CLI {{site.data.keyword.cloud_notm}} e Cloud Foundry per la tua installazione nello stesso contesto. Utilizza invece **`ibmcloud cf [command]`** se vuoi utilizzare la CLI Cloud Foundry per gestire le risorse Cloud Foundry nel contesto CLI {{site.data.keyword.cloud_notm}}. **`ibmcloud cf api/login/logout/target`** non è consentito e devi utilizzare invece **`ibmcloud api/login/logout/target`**.

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.cloud_notm}} sono stati modificati da **`bluemix`** e **`bx`** a **`ibmcloud`**. Tuttavia, puoi ancora utilizzare i comandi della CLI **`bluemix`** e **`bx`** finché non vengono successivamente rimossi.
{: tip}

Di seguito sono riportati i comandi dettagliati supportati dalla CLI {{site.data.keyword.cloud_notm}}, inclusi nomi, argomenti, opzioni, prerequisiti, descrizioni ed esempi.

I prerequisiti elencano quali azioni sono necessarie prima di utilizzare il comando e potrebbero essere incluse una o più delle seguenti azioni:

<dl>
<dt>Docker</dt>
<dd>Installa la CLI Docker.</dd>
<dt>Endpoint</dt>
<dd>Utilizza il comando **`ibmcloud api`** per impostare un endpoint API.</dd>
<dt>Accedi</dt>
<dd>Utilizza il comando **`ibmcloud login`** per accedere. Se accedi con un ID federato, utilizza l'opzione **`--sso`** per l'autenticazione tramite un passcode monouso oppure l'opzione **`--apikey`** per l'autenticazione tramite una chiave API.</dd>
<dt>Destinazione</dt>
<dd>Utilizza il comando **`ibmcloud target`** per impostare un'organizzazione e uno spazio.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Visualizza la guida generale per gli spazi dei nomi supportati e i comandi integrati di primo livello della CLI {{site.data.keyword.cloud_notm}} o la guida per uno spazio dei nomi o un comando integrato specifico.

```
ibmcloud help [COMANDO|SPAZIONOMI]
```

### Prerequisiti
{: #help-prereqs}

Nessuno.

### Opzioni del comando
{: #help-options}

<dl>
<dt>COMMAND|NAMESPACE</dt>
<dd>Il comando o lo spazio dei nomi per cui viene visualizzata la guida. Se non viene specificata, viene visualizzata la guida generale per la CLI {{site.data.keyword.cloud_notm}}. Facoltativo.</dd>
</dl>

### Esempi
{: #help-examples}

Visualizza la guida generale per la CLI {{site.data.keyword.cloud_notm}}:
```
ibmcloud help
```
{: codeblock}

Visualizza la guida per il comando **`dev`**:
```
ibmcloud help dev
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Imposta o visualizza l'endpoint API {{site.data.keyword.cloud_notm}}.
```
ibmcloud api [ENDPOINT_API] [--unset] [--skip-ssl-validation]
```

### Prerequisiti
{: #api-prereqs}

Nessuno.

### Opzioni del comando
{: #api-options}

<dl>
<dt>API_ENDPOINT</dt>
<dd>L'endpoint API di destinazione, ad esempio `https://cloud.ibm.com`. Se non vengono specificate le opzioni **`API_ENDPOINT`** e **`--unset`**, viene visualizzato l'endpoint API corrente. Facoltativo.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Tralascia la convalida SSL delle richieste HTTP. Facoltativo.</dd>
<dt>--unset</dt>
<dd>Rimuove l'impostazione di endpoint API.</dd>
</dl>

### Esempi
{: #api-examples}

Imposta l'endpoint API su cloud.ibm.com:
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

Visualizza l'endpoint API corrente:
```
ibmcloud api
```
{: codeblock}

Rimuove l'endpoint API.
```
ibmcloud api --unset
```
{: codeblock}

## ibmcloud config
{: #ibmcloud_config}

Scrive i valori predefiniti nel file di configurazione.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDI | --trace (true|false|percorso/a/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

### Prerequisiti
{: #config-prereqs}

Nessuno.

### Opzioni del comando
{: #config-options}

<dl>
<dt>--check-version</dt>
<dd>Abilita o disabilita il controllo della versione della CLI. I valori validi sono `true` o `false`.</dd>
<dt>--color</dt>
<dd>Abilita o disabilita l'output a colori. Questa opzione è disabilitata per impostazione predefinita. I valori validi sono `true` o `false`.</dd>
<dt>--http-timeout</dt>
<dd>Il valore di timeout per le richieste HTTP in secondi. Il valore predefinito è 60 secondi.</dd>
<dt>--locale</dt>
<dd>Imposta una locale predefinita. Se non viene specificato alcun valore, la locale precedente viene eliminata. </dd>
<dt>--trace</dt>
<dd>Traccia le richieste HTTP nel terminale o file specificato. I valori validi sono `true` o `false`.</dd>
</dl>

Puoi specificare solo una delle opzioni alla volta.
{: tip}

### Esempi
{: #config-examples}

Imposta il timeout della richiesta HTTP su 30 secondi:
```
ibmcloud config --http-timeout 30
```
{: codeblock}

Abilita l'output di traccia per le richieste HTTP:
```
ibmcloud config --trace true
```
{: codeblock}

Traccia le richieste HTTP nel file `/home/usera/my_trace`:
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

Disabilita l'output a colori:
```
ibmcloud config --color false
```
{: codeblock}

Imposta la locale su zh_Hans:
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

Cancella le impostazioni della locale:
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

Il comando **`ibmcloud info`** non è più disponibile a partire dalla versione della CLI 0.14. Per installare la versione della CLI più recente, vedi [Installazione della CLI {{site.data.keyword.cloud_notm}} autonoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).

## ibmcloud cf
{: #ibmcloud_cf}

Richiama la CLI Cloud Foundry integrata.
```
ibmcloud [-q, --quiet] cf COMANDO...
```

### Prerequisiti
{: #info-prereqs}

Nessuno.

### Opzioni del comando
{: #info-options}

<dl>
  <dt>-q, --quiet</dt>
  <dd>Non visualizza il messaggio richiamato.</dd>
</dl>

### Esempi
{: #info-examples}

Elenca le applicazioni Cloud Foundry:

```
ibmcloud cf apps
```

Elenca i servizi Cloud Foundry senza visualizzare il messaggio `Invoking cf command...`:
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud cf install
{: #ibmcloud_cf_install}

Installa una CLI Cloud Foundry per la CLI IBM Cloud
```
ibmcloud cf install [-v, --version VERSION] [--restore] [-f, --force]
```

### Prerequisiti
{: #cfinstall-prereqs}

Nessuno.

### Opzioni del comando
{: #cfinstall-options}

<dl>
  <dt>-v, --version</dt>
  <dd>Specifica la versione della CLI Cloud Foundry da installare</dd>
  <dt>--restore</dt>
  <dd>Ripristina la versione predefinita della CLI Cloud Foundry</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'installazione senza conferma</dd>
</dl>

### Esempi
{: #cfinstall-examples}

Installa la CLI Cloud Foundry `6.44.1`:

```
ibmcloud cf install -v 6.44.1
```

Installa l'ultima versione della CLI Cloud Foundry senza conferma:

```
ibmcloud cf install -f
```

Ripristina la CLI Cloud Foundry in bundle predefinita:

```
ibmcloud cf install --restore
```

## ibmcloud login
{: #ibmcloud_login}

Accedi alla CLI {{site.data.keyword.cloud_notm}}.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u NOMEUTENTE] [-p PASSWORD] [--apikey CHIAVE | @FILE_CHIAVI] [--no-iam] [-c ID_ACCOUNT | --no-account] [-g GRUPPO_RISORSE] [-r REGIONE | --no-region] [-o ORG] [-s SPAZIO]
```
### Prerequisiti
{: #login-prereqs}

Nessuno.

### Opzioni del comando
{: #login-options}

<dl>
<dt>-a API_ENDPOINT</dt>
<dd>L'endpoint API, ad esempio, `cloud.ibm.com`. </dd>
<dt>--apikey API_KEY or @API_KEY_FILE_PATH</dt>
<dd>Il contenuto della chiave API o il percorso di un file della chiave API indicato dal simbolo @.</dd>
<dt>-u USER_NAME</dt>
<dd>Il nome utente. Facoltativo.</dd>
<dt>-p PASS_WORD</dt>
<dd>La password dell'utente. Facoltativo.</dd>
<dt>-c ID_ACCOUNT</dt>
<dd>L'ID dell'account di destinazione. Questa opzione è esclusiva con **`--no account`**.</dd>
<dt>--no-account</dt>
<dd>Accesso forzato senza l'account. Questa opzione non è consigliata ed è esclusiva con l'opzione **`-c`**.</dd>
<dt>-g GRUPPO_RISORSE</dt>
<dd>Il nome del gruppo di risorse di destinazione. Facoltativo.</dd>
<dt>-r REGIONE</dt>
<dd>Il nome della regione di destinazione, ad esempio, us-south o eu-gb.</dd>
<dt>--no-region</dt>
<dd>Accesso forzato senza selezionare una regione.</dd>
<dt>-o ORG</dt>
<dd>Il nome dell'organizzazione di destinazione. Questa opzione è obsoleta. Utilizza invece **`ibmcloud target -o org_name`**. Facoltativo.</dd>
<dt>-s SPAZIO</dt>
<dd>Il nome dello spazio di destinazione. Questa opzione è obsoleta. Utilizza invece **`ibmcloud target -s space_name`**. Facoltativo.</dd>
<dt>--no-iam</dt>
<dd>Forza l'autenticazione con il server di accesso invece dell'IAM pubblica.</dd>
<dt>--skip-ssl-validation</dt>
<dd>Tralascia la convalida SSL delle richieste HTTP. Questa opzione non è consigliata.</dd>
</dl>

### Esempi
{: #login-examples}

Accedi in modo interattivo.

```
ibmcloud login
```
{: codeblock}

Accedi con un nome utente e una password e imposta lo spazio, l'organizzazione e l'account di destinazione:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Accedi con un passcode monouso e imposta lo spazio, l'organizzazione e l'account di destinazione:
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Imposta i tuoi organizzazione e spazio Cloud Found. Puoi immettere il seguente comando per identificare in modo interattivo l'organizzazione e lo spazio:

```
ibmcloud target --cf
```
{: codeblock}

Oppure, se sai a quale organizzazione e spazio appartiene il servizio, puoi utilizzare il seguente comando:

```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

Utilizza una chiave API con un account associato.

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

Utilizza una chiave API senza un account associato.

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

Se la chiave API ha un account associato, il passaggio a un altro account non è supportato.
{: note}

Utilizza un passcode monouso:

```
ibmcloud login -u UserID --sso
```
{: codeblock}

Successivamente, la CLI fornisce un link URL e ti richiede il passcode:

```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

Apre il link in un browser e ottiene un passcode. Immette il passcode fornito nella console e accede.

## ibmcloud logout
{: #ibmcloud_logout}

Scollega dalla CLI.

```
ibmcloud logout
```
{: codeblock}

### Prerequisiti
{: #logout-prereqs}

Nessuno.

## ibmcloud regions
{: #ibmcloud_regions}

Visualizza le informazioni per tutte le regioni su {{site.data.keyword.cloud_notm}}.

```
ibmcloud regions
```
{: codeblock}

### Prerequisiti
{: #regions-prereqs}

Utilizza il comando **`ibmcloud api`** per impostare un endpoint API.

## ibmcloud target
{: #ibmcloud_target}

Imposta o visualizza l'account, la regione, l'organizzazione o lo spazio di destinazione.

```
ibmcloud target [-r NOME_REGIONE | --unset-region] [-c ID_ACCOUNT] [-g GRUPPO_RISORSE | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORGANIZZAZIONE] [-s SPAZIO] [--output FORMATO]
```

### Prerequisiti
{: #target-prereqs}

* Utilizza il comando **`ibmcloud api`** per impostare un endpoint API.
* Utilizza il comando **`ibmcloud login`** per accedere. Se stai eseguendo l'accesso un ID federato, utilizza l'opzione **`--sso`** per l'autenticazione tramite un passcode monouso oppure l'opzione **`--apikey`** per l'autenticazione tramite una chiave API.

### Opzioni del comando
{: #target-options}

<dl>
<dt>-c ID_ACCOUNT</dt>
<dd>L'ID dell'account di destinazione. Facoltativo.</dd>
<dt>-r REGIONE</dt>
<dd>Il nome della regione di destinazione, ad esempio, us-south o eu-gb. Facoltativo.</dd>
<dt>-g GRUPPO_RISORSE</dt>
<dd>Il nome del gruppo di risorse di destinazione. Facoltativo.</dd>
<dt>--cf</dt>
<dd>Specifica in modo interattivo lo spazio e l'organizzazione di destinazione.</dd>
<dt>--cf-api</dt>
<dd>L'endpoint API Cloud Foundry.</dd>
<dt>-o ORG</dt>
<dd>Il nome dell'organizzazione di destinazione. Facoltativo.</dd>
<dt>-s SPAZIO</dt>
<dd>Il nome dello spazio di destinazione. Facoltativo.</dd>
<dt>--unset-region</dt>
<dd>Cancella la regione selezionata.</dd>
<dt>--unset-resource-group</dt>
<dd>Cancella il gruppo di risorse selezionato.</dd>
<dt>--output FORMATO</dt>
<dd>Il formato di output specificato. JSON è l'unico formato supportato.</dd>
</dl>

Se nessuna delle opzioni viene specificata, vengono visualizzati l'account, la regione, l'organizzazione e lo spazio correnti.
{: note}

### Esempi
{: #target-examples}

Imposta l'account, l'organizzazione e lo spazio correnti:
```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```
{: codeblock}

Passa a una nuova regione:
```
ibmcloud target -r eu-gb
```
{: codeblock}

Visualizza l'account, la regione, l'organizzazione e lo spazio correnti:
```
ibmcloud target
```
{: codeblock}

## ibmcloud update
{: #ibmcloud_update}

Aggiorna la CLI alla versione più recente.

```
ibmcloud update [-f]
```
### Prerequisiti
{: #update-prereqs}

### Opzioni del comando
{: #update-options}

<dl>
  <dt>-f</dt>
  <dd>Forza un aggiornamento senza conferma. Il privilegio root è obbligatorio.</dd>
</dl>

## Comandi del servizio dell'infrastruttura classica generali
{: #classic-service-commands}

Utilizza i comandi dell'infrastruttura classica nella CLI {{site.data.keyword.cloud_notm}} per configurare e gestire i servizi dell'infrastruttura.

Esegui il comando **`ibmcloud sl`** per visualizzare l'elenco di comandi disponibili:
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Classic infrastructure Block Storage
   file            Classic infrastructure File Storage
   dns             Classic infrastructure Domain Name System
   globalip        Classic infrastructure Global IP addresses
   hardware        Classic infrastructure hardware servers
   image           Classic infrastructure Compute images
   ipsec           Classic infrastructure IPSEC VPN
   loadbal         Classic infrastructure Load balancers
   security        Classic infrastructure SSH Keys and SSL Certificates
   securitygroup   Classic infrastructure network security groups
   subnet          Classic infrastructure Network subnets
   ticket          Classic infrastructure Manage Tickets
   vlan            Classic infrastructure Network VLANs
   vs              Classic infrastructure Virtual Servers
   order           Classic infrastructure Orders
   user            Classic infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

Per visualizzare le informazioni della guida su un comando, immetti il seguente comando:
```
ibmcloud sl [command] -h
```

Il comando **`ibmcloud sl init`** non è più disponibile a partire dalla versione della CLI `0.14`. Per installare la versione della CLI più recente, vedi [Installazione della CLI {{site.data.keyword.cloud_notm}} autonoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Visualizza le informazioni di guida per tutti i comandi per gestire l'ambiente dell'infrastruttura classica.
```
ibmcloud sl help
```
{: codeblock}

