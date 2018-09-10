---

copyright:

  years: 2018


lastupdated: "2018-08-28"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi generali della CLI (ibmcloud)
{: #ibmcloud_cli}


L'interfaccia di riga comando (CLI) {{site.data.keyword.Bluemix_notm}} fornisce una serie di comandi che vengono raggruppati in base allo spazio dei nomi per consentire agli utenti di interagire con {{site.data.keyword.Bluemix_notm}}.

Il client riga di comando {{site.data.keyword.Bluemix_notm}} include un client riga di comando Cloud Foundry nella sua installazione. Se hai la tua propria CLI cf installata, non utilizzare i comandi della CLI {{site.data.keyword.Bluemix_notm}} `ibmcloud [comando]` e i comandi della CLI Cloud Foundry `cf [comando]` della tua propria installazione nello stesso contesto. Utilizza invece `ibmcloud cf [comando]` se vuoi utilizzare la CLI cf per gestire le risorse Cloud Foundry nel contesto della CLI {{site.data.keyword.Bluemix_notm}}.  Nota che `ibmcloud cf api/login/logout/target` non è consentito e devi utilizzare invece `ibmcloud api/login/logout/target`.

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.Bluemix_notm}} sono stati modificati da `bluemix` e `bx` a `ibmcloud`. Tuttavia, puoi ancora utilizzare i comandi della CLI `bluemix` e `bx` finché non vengono rimossi in una data successiva.
{: tip}

Di seguito sono elencati in dettaglio i comandi supportati dalla CLI {{site.data.keyword.Bluemix_notm}}, compresi i loro nomi, argomenti, opzioni, prerequisiti, descrizioni ed esempi.
{:shortdesc}

**Nota:** i *Prerequisiti* elencano quali azioni sono richieste prima di utilizzare il comando. I comandi che non hanno azioni prerequisite elencano **Nessuno**. Altrimenti, i prerequisiti possono includere una o più delle seguenti azioni:

<dl>
<dt>Endpoint</dt>
<dd>Un endpoint API deve essere impostato mediante <code>bluemix api</code> prima di utilizzare il comando.</dd>
<dt>Accesso</dt>
<dd>L'accesso utilizzando il comando <code>bluemix login</code> è richiesto prima di utilizzare questo comando.
Se stai eseguendo l'accesso con l'ID federato, utilizza l'opzione '--sso' per autenticarti con il passcode monouso o utilizza '--apikey' per autenticarti con la chiave API. Vai alla console {{site.data.keyword.Bluemix_notm}} e fai clic su **Gestisci ** &gt; **Sicurezza** &gt; **Chiavi API della piattaforma** per creare le chiavi API.
</dd>
<dt>Destinazione</dt>
<dd>Il comando <code>bluemix target</code> deve essere utilizzato per impostare un'organizzazione e uno spazio prima di utilizzare questo comando.</dd>
<dt>Docker</dt>
<dd>Per poter eseguire questo comando, è necessario che la CLI Docker (docker) sia installata.</dd>
</dl>


Utilizza gli indici nella seguente tabella per fare riferimento ai comandi ibmcloud usati di frequente.

## Comandi ibmcloud generali
{: #ibmcloud_commands_index}

<table summary="Comandi ibmcloud generali.">
<caption>Tabella 1. Comandi ibmcloud generali</caption>
 <thead>
 <th colspan="5">Comandi ibmcloud generali</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help](bx_cli.html#ibmcloud_help)</td>
 <td>[ibmcloud api](bx_cli.html#ibmcloud_api)</td>
 <td>[ibmcloud config](bx_cli.html#ibmcloud_config)</td>
 <td>[ibmcloud info](bx_cli.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](bx_cli.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](bx_cli.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](bx_cli.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](bx_cli.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](bx_cli.html#ibmcloud_target)</td>
 <td>[ibmcloud update](bx_cli.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud help
{: #ibmcloud_help}
Visualizza la guida generale per i comandi integrati di primo livello e gli spazi dei nomi supportati della CLI {{site.data.keyword.Bluemix_notm}} oppure la guida per un comando o uno spazio dei nomi integrati specifici.

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

Visualizza la guida generale per la CLI {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud help
```

Visualizza la guida per il comando `info`:

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
Imposta o visualizza l'endpoint API {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud api [ENDPOINT_API] [--unset] [--skip-ssl-validation]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ENDPOINT_API (facoltativo)</dt>
   <dd>L'endpoint API di destinazione, ad esempio `https://api.chinabluemix.net`. Se non vengono specificate entrambe le opzioni *ENDPOINT_API* e `--unset`, viene visualizzato l'endpoint API corrente.</dd>
   <dt>--unset (facoltativo)</dt>
   <dd>Rimuove l'impostazione di endpoint API.</dd>
   <dt>--skip-ssl-validation (facoltativo)</dt>
   <dd>Tralascia la convalida SSL delle richieste HTTP.</dd>
   </dl>
<strong>Esempi</strong>:

Imposta l'endpoint API su api.chinabluemix.net:

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

Visualizza l'endpoint API corrente:

```
ibmcloud api
```

Annulla l'impostazione dell'endpoint API:

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


Scrive i valori predefiniti nel file di configurazione.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDI | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
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

Abilita l'output di traccia per le richieste HTTP:

```
ibmcloud config --trace true
```

Traccia le richieste HTTP in un file specificato */home/usera/my_trace*:

```
ibmcloud config --trace /home/usera/my_trace
```

Disabilita l'output a colori:

```
ibmcloud config --color false
```

Imposta la locale su zh_Hans:

```
ibmcloud config --locale zh_Hans
```

Cancella le impostazioni della locale:

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

Visualizza le informazioni su {{site.data.keyword.Bluemix_notm}} di base, compresi la regione corrente, la versione controller cloud e alcuni utili endpoint, quali gli endpoint per l'accesso e per lo scambio di token di accesso.

```
ibmcloud info
```

<strong>Prerequisiti</strong>:  Endpoint

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

## ibmcloud login
{: #ibmcloud_login}

Esegue l'accesso dell'utente.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u NOMEUTENTE] [-p PASSWORD] [--apikey CHIAVE | @FILE_CHIAVI] [--no-iam] [-c ID_ACCOUNT | --no-account] [-g GRUPPO_RISORSE] [-o ORG] [-s SPAZIO]
```

<strong>Prerequisiti</strong>:  Nessuno

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>Opzioni del comando</strong>:
<dl>
  <dt> -a <i>ENDPOINT_API</i> (facoltativo)</dt>
  <dd> Endpoint API (ad esempio: api.ng.bluemix.net)</dd>
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

Accesso con nome utente e password e imposta l'account, l'organizzazione e lo spazio di destinazione:

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

Accesso con il passcode monouso e imposta l'account, l'organizzazione e lo spazio di destinazione

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

Accesso con la chiave API e imposta le destinazioni:

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

La CLI fornirà un link all'URL e richiederà il passcode:
```
Codice monouso (Ottienine uno in https://Link_URL_per_ottenere_il_passcode):
```

Apri il link in un browser per ottenere il passcode. Digita il passcode fornito nella console e dovresti essere in grado di accedere.

## ibmcloud logout
{: #ibmcloud_logout}

Disconnette l'utente.

```
ibmcloud logout
```

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud regions
{: #ibmcloud_regions}

Visualizza le informazioni per tutte le regioni su {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud regions
```

<strong>Prerequisiti</strong>:  Endpoint

## ibmcloud target
{: #ibmcloud_target}


Imposta o visualizza l'account, la regione, l'organizzazione o lo spazio di destinazione.

```
ibmcloud target [-r NOME_REGIONE] [-c ID_ACCOUNT] [-g GRUPPO_RISORSE] [--cf] [-o ORGANIZZAZIONE] [-s SPAZIO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-r <i>NOME_REGIONE</i> (facoltativo)</dt>
   <dd>Nome della regione a cui essere passati, come 'us-south' o 'eu-gb'.</dd>
   <dt>-c <i>ID_ACCOUNT</i> (facoltativo)</dt>
   <dd>L'ID dell'account di destinazione.</dd>
   <dt>-g <i>GRUPPO_RISORSE</i> (facoltativo)</dt>
   <dd>Nome del gruppo di risorse</dd>
   <dt>--cf</dt>
   <dd>Seleziona interattivamente l'organizzazione e lo spazio di destinazione</dd>
   <dt>-o <i>NOME_ORGANIZZAZIONE</i> (facoltativo)</dt>
   <dd>Il nome dell'organizzazione di destinazione.</dd>
   <dt>-s <i>NOME_SPAZIO</i> (facoltativo)</dt>
   <dd>Il nome dello spazio di destinazione.</dd>
   </dl>
Se nessuna delle opzioni viene specificata, vengono visualizzati l'account, la regione, l'organizzazione e lo spazio correnti.

<strong>Esempi</strong>:

Imposta l'account, l'organizzazione e lo spazio correnti:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

Passa a una nuova regione:

```
ibmcloud target -r eu-gb
```

Visualizza l'account, la regione, l'organizzazione e lo spazio correnti:

```
ibmcloud target
```

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


## Comandi generali della CLI (ibmcloud sl)
{: #softlayer_cli}


Utilizza i comandi del servizio dell'infrastruttura nella CLI (command line interface) {{site.data.keyword.Bluemix_notm}} per configurare e gestire i servizi dell'infrastruttura.

Sono supportati i seguenti comandi. Utilizza il comando `ibmcloud sl` per visualizzare l'elenco di comandi disponibili:

<table summary="Comandi generali riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 1. Comandi del servizio dell'infrastruttura generali</caption>
 <thead>
 <th colspan="6">Comandi del servizio dell'infrastruttura generali </th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/ibmcloud/bx_cli.html#sl_init)</td>
 <td>[ibmcloud sl help
](/docs/cli/reference/ibmcloud/bx_cli.html#sl_help)</td>
   </tbody>
 </table>

 Per visualizzare le informazioni della guida per i comandi, esegui: `ibmcloud sl [command] -h`

 ## ibmcloud sl init
{: #sl_init}

Inizializza le impostazioni di configurazione utilizzate per connettersi all'ambiente dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}. La configurazione include nome utente, chiave API o password, account ed endpoint.
```
ibmcloud sl init [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL dell'endpoint API dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}, il valore predefinito è: https://api.softlayer.com/rest/v3.1 per l'autenticazione con chiave API, https://api.softlayer.com/mobile/v3.1 per l'autenticazione con ID IBM.</dd>
<dt>-u, --sl-user</dt>
<dd>Nome utente infrastruttura Gen1.</dd>
<dt>-p, --sl-password</dt>
<dd>Password o chiave API.</dd>
<dt>-c, --account-id</dt>
<dd>ID account.</dd>
<dt>-q, --security-question-id</dt>
<dd>ID della domanda di sicurezza utilizzato per l'autenticazione; chiedi al tuo proprietario dell'account se non lo conosci.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Risposta alla domanda di sicurezza utilizzata per l'autenticazione; chiedi al tuo proprietario dell'account se non la conosci.</dd>
<dt>-s, --security-code</dt>
<dd>Codice di sicurezza generato dal fornitore della sicurezza quando è abilitata l'autenticazione a 2 fattori.</dd>
<dt>-v, --security-vendor</dt>
<dd>Fornitore della sicurezza che fornisce il codice di sicurezza per l'autenticazione; le opzioni sono: VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Token di autenticazione quando è abilitata l'autenticazione tramite telefono.</dd>
</dl>

Ad esempio, accedi con nome utente e password o chiave API dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}
```
$ ibmcloud sl init
Scegli come configurare l'autenticazione dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}:
1. Accedi con nome utente e password/chiave API dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}
2. Utilizza SSO (Single-Sign-On) {{site.data.keyword.Bluemix_notm}}
Immetti un numero>1
URL endpoint API Softlayer: [https://api.softlayer.com/rest/v3.1]>
Nome utente: []> user@example.com
Chiave API o password: []> abcd

Endpoint API:    https://api.softlayer.com/rest/v3.1
Nome utente:       user@example.com
Chiave API:         xxxxxxxxxx
```
Ad esempio, utilizza SSO (Single-Sign-On) {{site.data.keyword.Bluemix_notm}} per accedere a Softlayer
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
Endpoint API: api.ng.bluemix.net
Autenticazione in corso...
OK

Account utente di esempio con account specificato (65ce8074c6c62b5)

Endpoint API:   https://api.ng.bluemix.net (API version: 2.54.0)   
Regione:         us-south
Utente:           user@example.com
Account:        Account utente di esempio (65ce8074c6c62b5)   
Nessuna organizzazione o nessuno spazio di destinazione; usa 'ibmcloud target --cf oppure ibmcloud target -o ORGANIZZAZIONE -s SPAZIO'


$ ibmcloud sl init
Scegli come configurare l'autenticazione dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}:

1. Accedi con nome utente e password/chiave API Softlayer
2. Utilizza SSO (Single-Sign-On) IBM Cloud
Immetti un numero> 2
URL endpoint API dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}: [https://api.softlayer.com/mobile/v3.1]>
Impostazione dell'account su: 123456
OK

Endpoint API dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}} :    https://api.softlayer.com/mobile/v3.1   

ID account:                123456
ID utente:                   user@example.com
Token IMS:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

Visualizza le informazioni della guida per tutti i comandi per gestire l'ambiente dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}.
```
ibmcloud sl help
```
