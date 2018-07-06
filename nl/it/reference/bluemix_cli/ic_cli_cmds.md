---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi generali della CLI (ibmcloud)
{: #ibmcloud_cli}

Versione: 0.7.1

L'interfaccia di riga comando (CLI) {{site.data.keyword.Bluemix_notm}} fornisce una serie di comandi che vengono raggruppati in base allo spazio dei nomi per consentire agli utenti di interagire con {{site.data.keyword.Bluemix_notm}}.

A partire dalla versione 0.5.0, il client riga di comando {{site.data.keyword.Bluemix_notm}} include un client riga di comando Cloud Foundry nella sua installazione. Se hai la tua propria CLI cf installata, non utilizzare i comandi della CLI {{site.data.keyword.Bluemix_notm}} `ibmcloud [comando]` e i comandi della CLI Cloud Foundry `cf [comando]` della tua propria installazione nello stesso contesto. Utilizza invece `ibmcloud cf [comando]` se vuoi utilizzare la CLI cf per gestire le risorse Cloud Foundry nel contesto della CLI {{site.data.keyword.Bluemix_notm}}.  Nota che `ibmcloud cf api/login/logout/target` non è consentito e devi utilizzare invece `ibmcloud api/login/logout/target`.

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
 <td>[ibmcloud help](ic_cli_cmds.html#ibmcloud_help)</td>
 <td>[ibmcloud api](ic_cli_cmds.html#ibmcloud_api)</td>
 <td>[ibmcloud config](ic_cli_cmds.html#ibmcloud_config)</td>
 <td>[ibmcloud info](ic_cli_cmds.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](ic_cli_cmds.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](ic_cli_cmds.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](ic_cli_cmds.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions](ic_cli_cmds.html#ibmcloud_regions)</td>
 <td>[ibmcloud target](ic_cli_cmds.html#ibmcloud_target)</td>
 <td>[ibmcloud update](ic_cli_cmds.html#ibmcloud_update)</td>
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
ibmcloud login [-a ENDPOINT_API] [--sso] [-u NOMEUTENTE] [-p PASSWORD] [--apikey CHIAVE | @FILE_CHIAVI] [--no-iam] [-c ID_ACCOUNT] [-g GRUPPO_RISORSE] [-o ORGANIZZAZIONE] [-s SPAZIO]
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
  <dd> ID dell'account di destinazione</dd>
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

#### Accesso interattivo

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

#### La chiave API ha un account associato

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### La chiave API non ha un account associato

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>Nota:</strong> se la chiave API ha un account associato, il passaggio a un altro account non è consentito.

#### Utilizza un passcode monouso

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
