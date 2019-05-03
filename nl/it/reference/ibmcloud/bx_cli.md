---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

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

Il client riga di comando {{site.data.keyword.cloud_notm}} include un client riga di comando Cloud Foundry nella sua installazione. Se hai la tua propria CLI cf installata, non utilizzare sia i comandi della CLI {{site.data.keyword.cloud_notm}} `ibmcloud [comando]` sia i comandi della CLI Cloud Foundry `cf [comando]` della tua propria installazione nello stesso contesto. Utilizza invece `ibmcloud cf [comando]` se vuoi utilizzare la CLI cf per gestire le risorse Cloud Foundry nel contesto della CLI {{site.data.keyword.cloud_notm}}. Nota che `ibmcloud cf api/login/logout/target` non è consentito e devi utilizzare invece `ibmcloud api/login/logout/target`.

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.cloud_notm}} sono stati modificati da `bluemix` e `bx` a `ibmcloud`. Tuttavia, puoi ancora utilizzare i comandi della CLI `bluemix` e `bx` finché non vengono successivamente rimossi.
{: tip}

Di seguito sono elencati in dettaglio i comandi supportati dalla CLI {{site.data.keyword.cloud_notm}}, compresi i loro nomi, argomenti, opzioni, prerequisiti, descrizioni ed esempi.
{: shortdesc}

I *Prerequisiti* elencano quali azioni sono richieste prima di utilizzare il comando. I comandi che non hanno azioni prerequisite elencano **Nessuno**. Altrimenti, i prerequisiti possono includere una o più delle seguenti azioni:

<dl>
<dt>Endpoint</dt>
<dd>Un endpoint API deve essere impostato mediante <code>ibmcloud api</code> prima di utilizzare il comando.</dd>
<dt>Accesso</dt>
<dd>È necessario accedere mediante il comando <code>ibmcloud login</code> prima di utilizzare questo comando.
Se stai eseguendo l'accesso con l'ID federato, utilizza l'opzione '--sso' per autenticarti con il passcode monouso o utilizza '--apikey' per autenticarti con la chiave API.
</dd>
<dt>Destinazione</dt>
<dd>È necessario utilizzare il comando <code>ibmcloud target</code> per impostare un'organizzazione e uno spazio prima di utilizzare questo comando.</dd>
<dt>Docker</dt>
<dd>Per poter eseguire questo comando, è necessario che la CLI Docker (docker) sia installata.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

Visualizza la guida generale per i comandi integrati di primo livello e gli spazi dei nomi supportati della CLI {{site.data.keyword.cloud_notm}} oppure la guida per un comando o uno spazio dei nomi integrati specifici.

```
ibmcloud help [COMANDO|SPAZIONOMI]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>COMANDO|SPAZIONOMI (facoltativo)</dt>
   <dd>Il comando o lo spazio dei nomi per cui viene visualizzata la guida. Se non viene specificata, viene visualizzata la guida generale per la CLI {{site.data.keyword.Bluemix_notm}}.</dd>
   </dl>

<strong>Esempi</strong>:

Visualizza la guida generale per la CLI {{site.data.keyword.cloud_notm}}:
```
ibmcloud help
```
{: codeblock}

Visualizza la guida per il comando `info`:
```
ibmcloud help info
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

Imposta o visualizza l'endpoint API {{site.data.keyword.cloud_notm}}.
```
ibmcloud api [ENDPOINT_API] [--unset] [--skip-ssl-validation]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ENDPOINT_API (facoltativo)</dt>
   <dd>L'endpoint API di destinazione, ad esempio `https://cloud.ibm.com`. Se non vengono specificate entrambe le opzioni *ENDPOINT_API* e `--unset`, viene visualizzato l'endpoint API corrente.</dd>
   <dt>--unset (facoltativo)</dt>
   <dd>Rimuove l'impostazione di endpoint API.</dd>
   <dt>--skip-ssl-validation (facoltativo)</dt>
   <dd>Tralascia la convalida SSL delle richieste HTTP.</dd>
   </dl>
<strong>Esempi</strong>:

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

Annulla l'impostazione dell'endpoint API:
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

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDI</i></dt>
   <dd>Il valore di timeout per le richieste HTTP. Il valore predefinito è 60 secondi.</dd>
   <dt>--trace true|false|<i>percorso-al-file</i></dt>
   <dd>Traccia le richieste HTTP nel terminale o file specificato.</dd>
   <dt>--color true|false</dt>
   <dd>Abilita o disabilita l'output a colori. L'output a colori è abilitato per impostazione predefinita.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>Imposta una locale predefinita. Se LOCALE è <i>CLEAR</i>, la locale precedente viene eliminata.</dd>
   <dt>--check-version true|false</dt>
   <dd>Abilita o disabilita il controllo della versione della CLI.</dd>
   </dl>

È possibile specificare solo una di queste opzioni alla volta.

<strong>Esempi</strong>:

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

Traccia le richieste HTTP in un file specificato */home/usera/my_trace*:
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

Il comando `ibmcloud info` non è più disponibile a partire dalla versione della CLI `0.14`. Per installare la versione della CLI più recente, vedi [Installazione della CLI {{site.data.keyword.cloud_notm}} autonoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud cf
{: #ibmcloud_cf}

Richiama la CLI CF integrata
```
ibmcloud [-q, --quiet] cf COMANDO...
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>Disattiva il messaggio "Richiamo di comando cf..."</dd>
</dl>

<strong>Esempi</strong>:

Elenca le applicazioni cf:

```
ibmcloud cf apps
```

Elenca i servizi cf senza messaggio "Richiamo di comando cf...":
```
ibmcloud -q cf services
```
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

Esegue l'accesso dell'utente.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u NOMEUTENTE] [-p PASSWORD] [--apikey CHIAVE | @FILE_CHIAVI] [--no-iam] [-c ID_ACCOUNT | --no-account] [-g GRUPPO_RISORSE] [-r REGIONE | --no-region] [-o ORG] [-s SPAZIO]
```

<strong>Prerequisiti</strong>:  Nessuno

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opzioni del comando</strong>:
<dl>
  <dt> -a <i>ENDPOINT_API</i> (facoltativo)</dt>
  <dd> Endpoint API (ad esempio: cloud.ibm.com)</dd>
  <dt> --apikey <i>CHIAVE_API o @PERCORSO_FILE_CHIAVI_API</i>
  <dd> Contenuto della chiave API o percorso del file della chiave API indicato da @</dd>
  <dt> --sso (facoltativo) </dt>
  <dd> Utilizza un passcode monouso per effettuare l'accesso </dd>
  <dt> -u <i>NOMEUTENTE</i> (facoltativo)</dt>
  <dd> Nome utente</dd>
  <dt> -p <i>PASSWORD</i> (facoltativo)</dt>
  <dd> Password</dd>
  <dt> -c <i>ID_ACCOUNT</i> (facoltativo) </dt>
  <dd> L'ID dell'account di destinazione. Questa opzione è esclusiva con --no-account</dd>
  <dt> --no-account (facoltativo) </dt>
  <dd> Forza l'accesso senza account. Questa opzione non è consigliata. Questa opzione è esclusiva con -c.</dd>
  <dt> -g <i>GRUPPO_RISORSE</i> (facoltativo) </dt>
  <dd> Nome del gruppo di risorse di destinazione</dd>
  <dt> -r REGIONE</dt>
  <dd> Il nome della regione, ad esempio 'us-south' o 'eu-gb'</dt>
  <dt> --no-region</dt>
  <dd> Forza l'accesso senza indicare come destinazione una regione.</dd>
  <dt> -o <i>ORGANIZZAZIONE</i> (facoltativo)</dt>
  <dd> Nome dell'organizzazione di destinazione (obsoleto, utilizza 'ibmcloud target -o ORGANIZZAZIONE')</dd>
  <dt> -s <i>SPAZIO</i> (facoltativo) </dt>
  <dd> Nome dello spazio di destinazione (obsoleto, utilizza 'ibmcloud target -s SPAZIO')</dd>
  <dt> --no-iam </dt>
  <dd> Forza l'autenticazione con il server di accesso invece di IAM pubblico</dd>
  <dt> --skip-ssl-validation (facoltativo) </dt>
  <dd> Tralascia la convalida SSL delle richieste HTTP. Questa opzione non è consigliata.</dd>
</dl>

<strong>Esempi</strong>:

### Accesso interattivo

```
ibmcloud login
```
{: codeblock}

Accedi con nome utente e password e imposta l'account, l'organizzazione e lo spazio di destinazione:
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Accedi con il passcode monouso e imposta l'account, l'organizzazione e lo spazio di destinazione
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### Per utilizzare i servizi Cloud Foundry

Per utilizzare i servizi Cloud Foundry, devi specificare un'organizzazione e uno spazio Cloud Foundry. Puoi immettere il seguente comando per scegliere in modo interattivo l'organizzazione e lo spazio:
```
ibmcloud target --cf
```
{: codeblock}

Facoltativamente, puoi utilizzare l'output del precedente comando per impostare manualmente la tua organizzazione e il tuo spazio con il seguente comando:
```
ibmcloud target -o <value> -s <value>
```
{: codeblock}

### La chiave API ha un account associato

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### La chiave API non ha un account associato

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> se la chiave API ha un account associato, il passaggio a un altro account non è consentito.

### Utilizza un passcode monouso
```
ibmcloud login -u UserID --sso
```
{: codeblock}

La CLI fornisce quindi un link dell'URL e richiede il passcode:
```
Codice monouso (Ottienine uno in https://Link_URL_per_ottenere_il_passcode):
```
{: screen}

Apri il link nel browser per ottenere un passcode. Digita il passcode fornito nella console e potrai accedere.

## ibmcloud logout
{: #ibmcloud_logout}

Disconnette l'utente.
```
ibmcloud logout
```
{: codeblock}

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud regions
{: #ibmcloud_regions}

Visualizza le informazioni per tutte le regioni su {{site.data.keyword.Bluemix_notm}}.
```
ibmcloud regions
```
{: codeblock}

<strong>Prerequisiti</strong>:  Endpoint

## ibmcloud target
{: #ibmcloud_target}


Imposta o visualizza l'account, la regione, l'organizzazione o lo spazio di destinazione.
```
ibmcloud target [-r NOME_REGIONE | --unset-region] [-c ID_ACCOUNT] [-g GRUPPO_RISORSE | --unset-resource-group] [--cf] [--cf-api ENDPOINT] [-o ORGANIZZAZIONE] [-s SPAZIO] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>-c <i>ID_ACCOUNT</i> (facoltativo)</dt>
   <dd>L'ID dell'account di destinazione.</dd>
   <dt>-r <i>NOME_REGIONE</i> (facoltativo)</dt>
   <dd>Nome della regione a cui essere passati, come 'us-south' o 'eu-gb'.</dd>
   <dt>-g <i>GRUPPO_RISORSE</i> (facoltativo)</dt>
   <dd>Nome del gruppo di risorse</dd>
   <dt>--cf</dt>
   <dd>Seleziona interattivamente l'organizzazione e lo spazio di destinazione</dd>
   <dt>--cf-api</dt>
   <dd>Endpoint API Cloud Foundry</dd>
   <dt>-o <i>NOME_ORGANIZZAZIONE</i> (facoltativo)</dt>
   <dd>Il nome dell'organizzazione di destinazione.</dd>
   <dt>-s <i>NOME_SPAZIO</i> (facoltativo)</dt>
   <dd>Il nome dello spazio di destinazione.</dd>
   <dt>--unset-region</dt>
   <dd>Annulla l'impostazione della regione indicata come destinazione</dd>
   <dt>--unset-resource-group</dt>
   <dd>Annulla l'impostazione del gruppo di risorse indicato come destinazione</dd>
   <dt>--output <i>FORMATO</i></dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>
Se nessuna delle opzioni viene specificata, vengono visualizzati l'account, la regione, l'organizzazione e lo spazio correnti.

<strong>Esempi</strong>:

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

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f</dt>
  <dd>Forza l'aggiornamento senza conferma. Il privilegio root è obbligatorio.</dd>
</dl>


## Comandi del servizio dell'infrastruttura classica generali
{: #softlayer_cli}

Utilizza i comandi dell'infrastruttura classica nella CLI (command line interface) {{site.data.keyword.cloud_notm}} per configurare e gestire i servizi dell'infrastruttura.

Esegui il comando `ibmcloud sl` per visualizzare l'elenco di comandi disponibili:
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Gen1 infrastructure Block Storage
   cdn             Gen1 infrastructure Content Delivery Network
   file            Gen1 infrastructure File Storage
   dns             Gen1 infrastructure Domain Name System
   globalip        Gen1 infrastructure Global IP addresses
   hardware        Gen1 infrastructure hardware servers
   image           Gen1 infrastructure Compute images
   ipsec           Gen1 infrastructure IPSEC VPN
   loadbal         Gen1 infrastructure Load balancers
   security        Gen1 infrastructure SSH Keys and SSL Certificates
   securitygroup   Gen1 infrastructure network security groups
   subnet          Gen1 infrastructure Network subnets
   ticket          Gen1 infrastructure Manage Tickets
   vlan            Gen1 infrastructure Network VLANs
   vs              Gen1 infrastructure Virtual Servers
   order           Gen1 infrastructure Orders
   user            Gen1 infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

Per visualizzare le informazioni di guida relative a un comando, esegui:
```
ibmcloud sl [command] -h
```

Il comando `ibmcloud sl init` non è più disponibile a partire dalla versione della CLI `0.14`. Per installare la versione della CLI più recente, vedi [Installazione della CLI {{site.data.keyword.cloud_notm}} autonoma](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli).
{: note}

## ibmcloud sl help
{: #sl_help}

Visualizza le informazioni di guida per tutti i comandi per gestire l'ambiente dell'infrastruttura classica.
```
ibmcloud sl help
```
{: codeblock}

