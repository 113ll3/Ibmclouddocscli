---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi generali della CLI (ibmcloud sl)
{: #softlayer_cli}

Il plug-in {{site.data.keyword.BluSoftlayer}} è stato inglobato nella CLI {{site.data.keyword.Bluemix_notm}} e non devi più installarlo.
{: tip}

Utilizza i comandi dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}} nella CLI (command line interface) {{site.data.keyword.Bluemix_notm}} per configurare e gestire i servizi SoftLayer.

A partire da maggio 2018, i comandi della CLI {{site.data.keyword.Bluemix_notm}} sono stati modificati da `bluemix` e `bx` a `ibmcloud`. Tuttavia, puoi ancora utilizzare i comandi della CLI `bluemix` e `bx` finché non vengono rimossi in una data successiva.
{: tip}

Per iniziare, installa la CLI {{site.data.keyword.Bluemix_notm}}. Per i dettagli,
vedi [CLI IBM Cloud ![Icona link esterno](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}.

Per un elenco completo dei comandi della CLI {{site.data.keyword.Bluemix_notm}}, vedi: [Comandi {{site.data.keyword.Bluemix_notm}} (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli).

Sono supportati i seguenti comandi. Utilizza il comando `ibmcloud sl` per visualizzare l'elenco di comandi disponibili:

<table summary="Comandi generali riportati in ordine alfabetico con dei link a ulteriori informazioni sul comando">
<caption>Tabella 1. Comandi generali dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandi generali dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
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
