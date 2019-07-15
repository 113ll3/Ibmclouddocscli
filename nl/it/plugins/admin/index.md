---

copyright:
  years: 2015, 2019
lastupdated: "2019-06-10"

keywords: cli, ibmcloud admin cli, admin cli plugin, admin plugin, cloud foundry admin cli plugin, adding users, buildpack, security groups, cf ba

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}
{:note: .note}
{:important: .important}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} Admin CLI
{: #ibmcloud-admincli}

Puoi gestire il tuo ambiente {{site.data.keyword.cloud_notm}} locale o {{site.data.keyword.cloud_notm}} dedicato utilizzando l'interfaccia riga di comando (CLI) Cloud Foundry con il plugin {{site.data.keyword.cloud_notm}} Admin CLI. Ad
esempio, puoi aggiungere utenti da un registro LDAP.

Prima di iniziare, installa la CLI Cloud Foundry. Il plugin {{site.data.keyword.cloud_notm}} Admin CLI
richiede `cf` versione 6.11.2 o successiva. [Scarica interfaccia riga di comando Cloud Foundry](https://github.com/cloudfoundry/cli/releases){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

La CLI Cloud Foundry non è supportata da Cygwin. Utilizza la CLI Cloud Foundry in una finestra della riga di comando diversa da quella di Cygwin.

{{site.data.keyword.cloud_notm}} Admin CLI è utilizzato solo per gli ambienti {{site.data.keyword.cloud_notm}} locale e {{site.data.keyword.cloud_notm}} dedicato. Non è supportato in {{site.data.keyword.cloud_notm}} pubblico.
{: note}

## Aggiunta del plugin {{site.data.keyword.cloud_notm}} Admin CLI
{: #add-admin-cli}

Dopo aver installato la CLI Cloud Foundry, puoi aggiungere il plugin {{site.data.keyword.cloud_notm}} Admin CLI.

Se hai precedentemente installato il plugin {{site.data.keyword.cloud_notm}} Admin, per ottenere gli aggiornamenti più recenti potresti dover disinstallare il plugin, eliminare il repository ed eseguire quindi la reinstallazione.
{: tip}

Completa la seguente procedura per aggiungere il repository e installare il plug-in:

1. Per aggiungere il repository del plug-in Gestione {{site.data.keyword.cloud_notm}}, immetti il seguente comando:
  ```
  cf add-plugin-repo IBMCloudAdmin https://<customer_console_endpoint>.bluemix.net/cli
  ```
  {: codeblock}

  Puoi trovare lo stesso comando con l'endpoint effettivo nella pagina della CLI della console di gestione: `https://<customer_console_endpoint>.bluemix.net/cli`.
  {: note}

2. Per installare il plug-in {{site.data.keyword.cloud_notm}} Admin CLI, immetti il seguente comando:
  ```
  cf install-plugin IBMCloudAdminCLI -r IBMCloudAdmin
```
  {: codeblock}

## Disinstallazione del plugin {{site.data.keyword.cloud_notm}} Admin CLI
{: #remove-admin-cli}

Completa la seguente procedura per disinstallare il plugin. 

1. Disinstalla il plugin:
  ```
  cf uninstall-plugin IBMCloudAdminCLI
  ```
  {: codeblock}

2. Rimuovi il repository di plugin:
  ```
  cf remove-plugin-repo IBMCloudAdmin
  ```
  {: codeblock}

Puoi quindi aggiungere il repository aggiornato e installare l'ultimo plugin.

## Utilizzo del plug-in {{site.data.keyword.cloud_notm}} Admin CLI
{: #using-admin-cli}

Puoi utilizzare il plug-in {{site.data.keyword.cloud_notm}} Admin CLI per aggiungere o rimuovere utenti, assegnare o annullare l'assegnazione degli utenti dalle organizzazioni ed effettuare altre attività di gestione.

Per visualizzare un elenco di comandi, immetti il seguente
comando:
```
cf plugins
```
{: codeblock}

Per ulteriore assistenza per un comando, utilizza l'opzione `-help`.

### Connessione e accesso a {{site.data.keyword.cloud_notm}}
{: #connecting-ibm-cloud}

1. Per connetterti all'endpoint dell'API {{site.data.keyword.cloud_notm}}, immetti il seguente comando:
  ```
  cf api api.us-south.cf.cloud.ibm.com
  ```
  {: codeblock}
  
  Anche se gli endpoint API Cloud Foundry legacy `api.*.bluemix.net` sono ancora disponibili, puoi aggiornare gli script e l'automazione dell'infrastruttura per utilizzare i seguenti endpoint API Cloud Foundry aggiornati per la tua regione:

  * api.us-south.cf.cloud.ibm.com (in precedenza api.ng.bluemix.net)
  * api.eu-gb.cf.cloud.ibm.com (in precedenza api.eu-gb.bluemix.net)
  * api.us-east.cf.cloud.ibm.com (in precedenza api.us-east.bluemix.net)
  * api.eu-de.cf.cloud.ibm.com (in precedenza api.eu-de.bluemix.net)
  * api.au-syd.cf.cloud.ibm.com (in precedenza api.au-syd.bluemix.net)

  Puoi controllare l'URL corretto nella pagina delle informazioni e delle risorse della console di gestione. L'URL viene mostrato nella sezione delle informazioni API nel campo
**URL API**.

2. Accedi a {{site.data.keyword.cloud_notm}} immettendo il seguente comando:
  ```
  cf login
  ```
  {: codeblock}

## Gestione degli utenti
{: #admin_users}

### Aggiunta di un utente
{: #admin_add_user}

Per aggiungere un utente al tuo ambiente {{site.data.keyword.cloud_notm}} dal registro
utenti dell'ambiente, utilizza il seguente comando:
```
cf ba add-user user_name organization first_name last_name
```
{: codeblock}

Per aggiungere un utente a un'organizzazione specifica, devi essere un amministratore con autorizzazione users.write (o Superuser). Se sei un gestore organizzazione, ti può essere data la possibilità di aggiungere utenti alla tua organizzazione da un Superuser che esegue il comando **`enable-managers-add-users`**. Per ulteriori informazioni, vedi [Abilitazione dei gestori all'aggiunta di utenti](#clius_emau).

<dl>
<dt>user_name</dt>
<dd>Il nome dell'utente nel registro LDAP.</dd>
<dt>organization</dt>
<dd>Il nome o GUID dell'organizzazione {{site.data.keyword.cloud_notm}} a cui aggiungere l'utente.</dd>
<dt>first_name</dt>
<dd>Il nome dell'utente da aggiungere all'organizzazione.</dd>
<dt>last_name</dt>
<dd>Il cognome dell'utente da aggiungere all'organizzazione.</dd>
</dl>

Puoi anche utilizzare **`ba au`** come un alias per il nome del comando **`ba add-user`** più lungo.
{: tip}

### Invito di un utente da {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_invite_public}

Ogni ambiente {{site.data.keyword.Bluemix_dedicated_notm}} ha un account aziendale pubblico di proprietà del client in {{site.data.keyword.cloud_notm}}. Affinché gli utenti nell'ambiente dedicato possano creare cluster con il {{site.data.keyword.containershort}}, l'amministratore deve aggiungere gli utenti a questo account aziendale pubblico. Una volta aggiunti gli utenti all'account aziendale pubblico, i loro account dedicati e pubblici sono collegati tra loro. Gli utenti possono quindi utilizzare il proprio ID IBM per accedere contemporaneamente all'ambiente dedicato e pubblico e possono creare risorse nell'account pubblico dall'interfaccia dedicata. Per ulteriori informazioni, vedi [Setting up IBM Cloud Container Service on Dedicated](/docs/containers?topic=containers-dedicated#dedicated_setup). Per invitare gli utenti dell'ambiente dedicato all'account pubblico:
```
cf ba invite-users-to-public -userid=user_email -organization=dedicated_org_id -apikey=public_api_key -public_org_id=public_org_id
```
{: pre}

Per aggiungere utenti dell'ambiente dedicato al tuo account pubblico {{site.data.keyword.cloud_notm}}, devi essere un amministratore dell'account dedicato.

<dl>
<dt>user_email</dt>
<dd>Se inviti un singolo utente, l'e-mail dell'utente.</dd>
<dt>dedicated_org_id</dt>
<dd>Se inviti tutti gli utenti attualmente in un'organizzazione dell'account dedicato, l'ID organizzazione dell'account dedicato.</dd>
<dt>public_api_key</dt>
<dd>Una chiave API per invitare gli utenti all'account pubblico. Questo deve essere generato dall'amministratore dell'account pubblico.</dd>
<dt>public_org_id</dt>
<dd>L'ID dell'organizzazione dell'account pubblico a cui inviti gli utenti.</dd>
</dl>

### Elenco degli utenti invitati da {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_list}

Se hai invitato utenti dell'ambiente dedicato al tuo account {{site.data.keyword.cloud_notm}} con il [comando **`invite-users-to-public`**](#admin_dedicated_invite_public), puoi elencare gli utenti nel tuo account per vedere il loro stato di invito. Gli utenti invitati che hanno un ID IBM esistente avranno uno stato di ATTIVO. Gli utenti invitati che non hanno un ID IBM esistente hanno lo stato IN SOSPESO o ATTIVO a seconda che abbiano già accettato o meno l'invito all'account. Per elencare gli utenti nel tuo account {{site.data.keyword.cloud_notm}}:

```
cf ba invite-users-status -apikey=public_api_key
```
{: pre}

Per aggiungere utenti dell'ambiente dedicato al tuo account pubblico {{site.data.keyword.cloud_notm}}, devi essere un amministratore dell'account dedicato.

<dl>
<dt>public_api_key</dt>
<dd>La chiave API utilizzata per invitare gli utenti all'account. Questo deve essere generato dall'amministratore dell'account pubblico.</dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### Ricerca di un utente
{: #admin_search_user}

Per ricercare un utente, utilizza il seguente comando con i parametri del filtro di ricerca facoltativi
(nome, autorizzazione, organizzazione e ruolo):

```
cf ba search-users -name=user_name -permission=permission_value -organization=organization_value -role=role_value
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Il nome dell'utente.</dd>
<dt>permission_value</dt>
<dd>L'autorizzazione assegnata all'utente. Le autorizzazioni disponibili sono admin (o superuser), login (o basic), catalog.read, catalog.write, reports.read, reports.write, users.read o users.write. Non puoi utilizzare questo parametro insieme al parametro organizzazione nella stessa query.</dd>
<dt>organization_value</dt>
<dd>Il nome dell'organizzazione a cui appartiene l'utente. Non puoi utilizzare questo parametro insieme al parametro autorizzazione nella stessa query.</dd>
<dt>role_value</dt>
<dd>Il ruolo dell'organizzazione assegnato all'utente. I ruoli disponibili sono auditors, managers e billing_managers. Con questo parametro devi specificare l'organizzazione.</dd>
</dl>

Puoi anche utilizzare **`ba su`** come un alias per il nome del comando **`ba search-users`** più lungo.
{: tip}

### Impostazione di autorizzazioni per un utente
{: #admin_setperm_user}

Puoi impostare una sola autorizzazione alla volta. Per impostare le autorizzazioni per uno specifico utente, utilizza il seguente comando:
```
cf ba set-permissions user_name permission access
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Il nome dell'utente.</dd>
<dt>permission</dt>
<dd>Imposta l'autorizzazione assegnata all'utente. Le autorizzazioni disponibili sono admin (o superuser), login (o basic), catalog.read, catalog.write, reports.read, reports.write, users.read o users.write. Non puoi utilizzare questo parametro insieme al parametro organizzazione nella stessa query.</dd>
<dt>access</dt>
<dd>Per il catalogo, i report o le autorizzazioni utente, devi anche impostare il livello di accesso come `read` o `write`.</dd>
</dl>

Puoi anche utilizzare **`ba sp`** come un alias per il nome del comando **`ba set-permissions`** più lungo.
{: tip}

<!-- staging-only commands end -->

### Rimozione di un utente
{: #admin_remov_user}

Per rimuovere un utente dal tuo ambiente {{site.data.keyword.cloud_notm}}, utilizza il seguente comando:

```
cf ba remove-user user_name
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Il nome dell'utente in {{site.data.keyword.cloud_notm}}.</dd>
</dl>

Puoi anche utilizzare **`ba ru`** come un alias per il nome del comando **`ba remove-user`** più lungo.
{: tip}

### Abilitazione dei gestori all'aggiunta di utenti
{: #clius_emau}

Se disponi dell'autorizzazione Superuser nel tuo ambiente {{site.data.keyword.cloud_notm}}, puoi abilitare i gestori organizzazione ad aggiungere utenti alle organizzazioni che essi gestiscono. Per abilitare i gestori ad aggiungere utenti, utilizza il seguente comando:

```
cf ba enable-managers-add-users
```
{: codeblock}

Puoi anche utilizzare **`ba emau`** come un alias per il nome del comando **`ba enable-managers-add-users`** più lungo.
{: tip}

### Disabilitazione dei gestori all'aggiunta di utenti
{: #clius_dmau}

Se i gestori dell'organizzazione sono abilitati ad aggiungere utenti alle organizzazioni che gestiscono nel tuo ambiente {{site.data.keyword.cloud_notm}} con il comando **`enable-managers-add-users`** e disponi dell'autorizzazione Superuser, puoi rimuovere questa impostazione. Per disabilitare i gestori all'aggiunta di utenti, utilizza il seguente comando:

```
cf ba disable-managers-add-users
```
{: codeblock}

Puoi anche utilizzare il comando **`ba dmau`** come un alias per il nome del comando **`ba disable-managers-add-users`** più lungo.
{: tip}

## Amministrazione delle organizzazioni
{: #admin_orgs}

### Aggiunta di un'organizzazione
{: #admin_add_org}

Per aggiungere un'organizzazione, utilizza il seguente comando:

```
cf ba create-org organization manager
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} da aggiungere.</dd>
<dt>manager</dt>
<dd>Il nome utente del gestore per l'organizzazione.</dd>
</dl>

Puoi anche utilizzare **`ba co`** come un alias per il nome del comando **`ba create-org`** più lungo.
{: tip}

### Eliminazione di un'organizzazione
{: #admin_delete_org}

Per eliminare un'organizzazione, utilizza il seguente comando:

```
cf ba delete-org organization
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} da eliminare.</dd>
</dl>

Puoi anche utilizzare **`ba do`** come un alias per il nome del comando **`ba delete-org`** più lungo.
{: tip}

### Assegnazione di un utente a un'organizzazione
{: #admin_ass_user_org}

Per assegnare un utente del tuo ambiente {{site.data.keyword.cloud_notm}} a
una specifica organizzazione, utilizza il seguente comando:

```
cf ba set-org user_name organization [role]
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Il nome dell'utente.</dd>
<dt>organization</dt>
<dd>Il nome o GUID dell'organizzazione {{site.data.keyword.cloud_notm}} a cui assegnare l'utente.</dd>
<dt>role</dt>
<dd>Il ruolo dell'utente. I valori validi sono OrgManager, BillingManager, OrgAuditor. Vedi [Ruoli](/docs/iam?topic=iam-userroles#userroles) per le descrizioni dei ruoli.</dd>
</dl>

Puoi anche utilizzare **`ba so`** come un alias per il nome del comando **`ba set-org`** più lungo.
{: tip}

### Annullamento dell'assegnazione di un utente da un'organizzazione
{: #admin_unass_user_org}

Per annullare l'assegnazione di un utente del tuo ambiente {{site.data.keyword.cloud_notm}} da
una specifica organizzazione, utilizza il seguente comando:

```
cf ba unset-org user_name organization [role]
```
{: codeblock}

<dl>
<dt>user_name</dt>
<dd>Il nome dell'utente.</dd>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}}.</dd>
<dt>role</dt>
<dd>Il ruolo dell'utente. I valori validi sono OrgManager, BillingManager, OrgAuditor. Vedi [Ruoli](/docs/iam?topic=iam-userroles#userroles) per le descrizioni dei ruoli.</dd>
</dl>

Puoi anche utilizzare **`ba uo`** come un alias per il nome del comando **`ba unset-org`** più lungo.
{: tip}

### Impostazione di una quota per un'organizzazione
{: #admin_set_org_quota}

Per impostare la quota di utilizzo per una specifica organizzazione, utilizza il seguente comando:

```
cf ba set-quota organization plan
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} per cui impostare la quota.</dd>
<dt>plan</dt>
<dd>Il piano di quota per un'organizzazione.</dd>
</dl>

Puoi anche utilizzare **`ba sq`** come un alias per il nome del comando **`ba set-quota`** più lungo.
{: tip}


### Ricerca di quote contenitore per un'organizzazione
{: #admin_find_containquotas}

Per trovare la quota per i contenitori di un'organizzazione, utilizza il seguente comando:

```
cf ibmcloud-admin containers-quota organization
```
{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o l'ID dell'organizzazione in IBM Cloud. Questo parametro è obbligatorio.</dd>
</dl>

Puoi anche utilizzare **`ba cq`** come un alias per il nome del comando **`ibmcloud-admin containers-quota`** più lungo.
{: tip}

### Impostazione di quote contenitore per un'organizzazione
{: #admin_set_containquotas}

Per impostare la quota per i contenitori di un'organizzazione, utilizza il seguente comando con almeno una delle opzioni incluse:

```
cf ibmcloud-admin set-containers-quota organization options
```
{: codeblock}

Puoi includere più opzioni, ma ne devi includere almeno una.
{: note}

<dl>
<dt>organization</dt>
<dd>Il nome o l'ID dell'organizzazione {{site.data.keyword.cloud_notm}} per cui impostare la quota.</dd>
<dt>options</dt>
<dd>Le scelte sono floating-ips-max value (nome breve fim), memory-max value (nome breve mm), memory-space-default value (nome breve msd)o image-limit value (nome breve il). Il valore deve essere un numero intero.</dd>
</dl>

Facoltativamente, puoi fornire un file che contenga parametri di configurazione specifici in un oggetto JSON valido. Se utilizzi l'opzione **`-file`**, ha la precedenza e le altre opzioni vengono ignorate. Per fornire un file anziché impostare le opzioni, utilizza il seguente comando:

```
cf ibmcloud-admin set-containers-quota organization -file path_to_JSON_file
```
{: codeblock}

Il file JSON deve avere il formato mostrato nel seguente esempio:

```
{
  "floating_ips_max": 10,
  "floating_ips_space_default": 0,
  "ram_max": 4096,
  "ram_space_default": 0,
  "image_limit": 10
}
```
{: codeblock}

Puoi anche utilizzare **`ba scq`** come un alias per il nome del comando **`ibmcloud-admin set-containers-quota`** più lungo.
{: tip}

## Amministrazione di spazi
{: #admin_spaces}

### Aggiunta di uno spazio all'organizzazione

Per aggiungere uno spazio nell'organizzazione, utilizza il seguente comando:

```
cf ibmcloud-admin create-space organization space_name
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione a cui aggiungere lo spazio.</dd>
<dt>space_name</dt>
<dd>Il nome dello spazio che stai aggiungendo all'organizzazione.</dd>
</dl>

Puoi anche utilizzare **`ba cs`** come un alias per il nome del comando **`ba create-space`** più lungo.
{: tip}

### Eliminazione di un spazio dall'organizzazione

Per rimuovere uno spazio dall'organizzazione, utilizza il seguente comando:

```
cf ibmcloud-admin delete-space organization space_name
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione da cui deve essere rimosso lo spazio.</dd>
<dt>space_name</dt>
<dd>Il nome dello spazio che stai rimuovendo dall'organizzazione.</dd>
</dl>

Puoi anche utilizzare **`ba cs`** come un alias per il nome del comando **`ba delete-space`** più lungo.
{: tip}

### Aggiunta di un utente a uno spazio con un ruolo

Per creare un utente in uno spazio con un ruolo specificato, utilizza il seguente comando:

```
cf ibmcloud-admin set-space organization space_name user_name role
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione a cui sta venendo aggiunto l'utente.</dd>
<dt>space_name</dt>
<dd>Il nome dello spazio a cui sta venendo aggiunto l'utente.</dd>
<dt>user_name</dt>
<dd>Il nome dell'utente.</dd>
<dt>role</dt>
<dd>Il ruolo dell'utente. I valori validi sono Manager, Developer o Auditor.</dd>
</dl>

Puoi anche utilizzare **`ba ss`** come un alias per il nome del comando **`ba set-space`** più lungo.
{: tip}


### Rimozione del ruolo di un utente in uno spazio

Per rimuovere il ruolo di un utente in uno spazio, utilizza il seguente comando:

```
cf ibmcloud-admin unset-space organization space_name user_name role
```

{: codeblock}

<dl>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione a cui appartiene l'utente.</dd>
<dt>space_name</dt>
<dd>Il nome dello spazio a cui appartiene l'utente.</dd>
<dt>user_name</dt>
<dd>Il nome dell'utente.</dd>
<dt>role</dt>
<dd>Il ruolo dell'utente. I valori validi sono Manager, Developer o Auditor.</dd>
</dl>

Puoi anche utilizzare **`ba us`** come un alias per il nome del comando **`ba unset-space`** più lungo.
{: tip}

## Gestione del catalogo
{: #admin_catalog}

### Abilitazione dei servizi per tutte le organizzazioni
{: #admin_ena_service_org}

Per abilitare la visualizzazione di un servizio nel
catalogo {{site.data.keyword.cloud_notm}} per tutte le
organizzazioni, utilizza il seguente comando:

```
cf ba enable-service-plan plan_identifier
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di selezionare un piano di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona <b>Aggiungi</b> per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio. </dd>
</dl>

Puoi anche utilizzare **`ba esp`** come un alias per il nome del comando **`ba enable-service-plan`** più lungo.
{: tip}

### Disabilitazione dei servizi per tutte le organizzazioni
{: #admin_dis_service_org}

Per disabilitare la visualizzazione di un servizio nel catalogo {{site.data.keyword.cloud_notm}} per tutte le
organizzazioni, utilizza il seguente comando:

```
cf ba disable-service-plan plan_identifier
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di selezionare un piano di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona <b>Aggiungi</b> per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio.</dd>
</dl>

Puoi anche utilizzare **`ba dsp`** come un alias per il nome del comando **`ba disable-service-plan`** più lungo.
{: tip}

### Aggiunta della visibilità dei servizi per le organizzazioni
{: #admin_addvis_service_org}

Puoi aggiungere un'organizzazione dall'elenco di organizzazioni che possono vedere uno specifico servizio nel catalogo {{site.data.keyword.cloud_notm}}. Per consentire a un'organizzazione di visualizzare uno specifico servizio nel catalogo, utilizza il seguente comando:

```
cf ba add-service-plan-visibility plan_identifier organization
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di selezionare un piano di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona <b>Aggiungi</b> per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio.</dd>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione da aggiungere all'elenco di visibilità del servizio.</dd>
</dl>

Puoi anche utilizzare **`ba aspv`** come un alias per il nome del comando **`ba add-service-plan-visibility`** più lungo.
{: tip}

### Rimozione della visibilità dei servizi per le organizzazioni
{: #admin_remvis_service_org}

Puoi rimuovere un'organizzazione dall'elenco di organizzazioni che possono vedere
uno specifico servizio nel catalogo {{site.data.keyword.cloud_notm}}. Per rimuovere la visibilità di un servizio nel catalogo per un'organizzazione, utilizza il seguente comando:

```
cf ba remove-service-plan-visibility plan_identifier organization
```
{: codeblock}

<dl>
<dt>plan_identifier</dt>
<dd>Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di selezionare un piano di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona <b>Aggiungi</b> per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio.</dd>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione da rimuovere dall'elenco di visibilità del servizio.</dd>
</dl>

Puoi anche utilizzare **`ba rspv`** come un alias per il nome del comando **`ba remove-service-plan-visibility`** più lungo.
{: tip}

### Modifica della visibilità dei servizi per le organizzazioni
{: #admin_editvis_service_org}

Puoi modificare e sostituire l'elenco di servizi che specifiche
organizzazioni possono vedere nel catalogo {{site.data.keyword.cloud_notm}}. Per sostituire tutti i servizi visibili esistenti per un'organizzazione o più organizzazioni, utilizza questo comando.

```
cf ba edit-service-plan-visibilities plan_identifier organization_1 optional_organization_2
```
{: codeblock}

Questo
comando sostituisce i servizi visibili esistenti per le organizzazioni specificate con il servizio
da te specificato nel comando.

<dl>
<dt>plan_identifier</dt>
<dd>Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di selezionare un piano di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona <b>Aggiungi</b> per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio.</dd>
<dt>organization</dt>
<dd>Il nome o il GUID dell'organizzazione a cui aggiungere la visibilità. Puoi abilitare la visibilità del servizio per più di
un'organizzazione immettendo altri nomi o GUID di organizzazione nel comando.</dd>
</dl>

Puoi anche utilizzare **`ba espv`** come un alias per il nome del comando **`ba edit-service-plan-visibility`** più lungo.
{: tip}

## Gestione dei report
{: #admin_add_report}

### Aggiunta di report
{: #admin_adding_report}

Per aggiungere un report di sicurezza, utilizza il seguente comando:

```
cf ba add-report category date PDF|TXT|LOG RTF
```
{: codeblock}

Se hai accesso in scrittura per l'autorizzazione dei report, puoi creare una nuova categoria e aggiungere un report in uno qualsiasi dei formati accettati per i tuoi utenti. Immetti il nome della nuova categoria per il parametro **`categoria`** o aggiungi il nuovo report a una categoria esistente.

<dl>
<dt>category</dt>
<dd>La categoria per il report. Se nel nome è presente uno spazio, utilizza le virgolette.</dd>
<dt>data</dt>
<dd>La data del report nel formato YYYYMMDD.</dd>
<dt>PDF|TXT|LOG</dt>
<dd>Il percorso del PDF, file di testo o file di log del report da caricare.</dd>
<dt>RTF</dt>
<dd>Un'opzione per includere una versione RTF (Rich Text Format) del PDF. Questa opzione si applica solo se includi un percorso al PDF del report. La versione RTF è utilizzata per l'indicizzazione e la ricerca.</dd>
</dl>

Puoi anche utilizzare **`ba ar`** come un alias per il nome del comando **`ba add-report`** più lungo.
{: tip}

### Eliminazione di report
{: #admin_del_report}

Per eliminare un report di sicurezza, utilizza il seguente comando:

```
cf ba delete-report category date name
```
{: codeblock}

<dl>
<dt>category</dt>
<dd>La categoria per il report. Se nel nome è presente uno spazio, utilizza le virgolette.</dd>
<dt>data</dt>
<dd>La data del report nel formato YYYYMMDD.</dd>
<dt>name</dt>
<dd>Il nome del report.</dd>
</dl>

Puoi anche utilizzare **`ba d`r** come un alias per il nome del comando **`ba delete-report`** più lungo.
{: tip}

### Recupero di report
{: #admin_retr_report}

Per recuperare un report di sicurezza, utilizza il seguente comando:

```
cf ba retrieve-report search
```
{: codeblock}

<dl>
<dt>search</dt>
<dd>Il nome file del report. Se nel nome è presente uno spazio, racchiudi il nome
tra virgolette.</dd>
</dl>

Puoi anche utilizzare **`ba rr`** come un alias per il nome del comando **`ba retrieve-report`** più lungo.
{: tip}

## Visualizzazione delle informazioni sulle metriche della risorsa
{: #cliresourceusage}

Puoi visualizzare le informazioni sulle metriche della risorsa, compresi l'utilizzo di memoria, disco e CPU. Oltre all'utilizzo di tali risorse, puoi vedere un riepilogo delle risorse fisiche e riservate disponibili. Inoltre, puoi visualizzare i dati di utilizzo dei DEA (droplet execution agent) e delle celle (architettura Diego). Per visualizzare le informazioni sulle metriche della risorsa, utilizza il seguente comando:

```
cf ba resource-metrics
```

Puoi anche utilizzare **`ba rsm`** come un alias per il nome del comando **`ba resource-metrics`** più lungo.
{: tip}

## Visualizzazione della cronologia delle metriche di risorse
{: #cliresourceusagehistory}

Puoi richiamare la cronologia delle metriche di risorse relativa all'utilizzo di memoria e disco. Le metriche restituite includono la quantità di risorse utilizzate rispetto al totale disponibile, sia per risorse fisiche che riservate. I dati cronologici per l'utilizzo di memoria e disco possono essere visualizzati su base oraria, giornaliera o mensile. Puoi specificare le date di inizio e di fine per richiamare i dati in un intervallo di date specifico. Se non si specificano delle date, i dati cronologici predefiniti sono i dati della memoria su base oraria per le ultime 48 ore. I dati vengono visualizzati in ordine decrescente, con le date più recenti mostrate per prime. Per visualizzare le informazioni sulla cronologia delle metriche di risorse, utilizza il seguente comando:

```
cf ba resource-metrics-history hourly|daily|monthly  memory|disk   start|end
```
{: codeblock}

<dl>
<dt>--hourly</dt>
<dd>Visualizza i dati cronologici per le ultime 48 ore. Questo è il valore predefinito.</dd>
<dt>--daily</dt>
<dd>Visualizza la media giornaliera dei dati cronologici per gli ultimi 30 giorni.</dd>
<dt>--monthly</dt>
<dd>Visualizza la media mensile dei dati cronologici per gli ultimi 6 mesi.</dd>
<dt>--memory</dt>
<dd>Visualizza la quantità totale e utilizzata per la memoria riservata e fisica. </dd>
<dt>--disk</dt>
<dd>Visualizza la quantità totale e utilizzata per il disco riservato e fisico.</dd>
<dt>--start</dt>
<dd>Specifica una data di inizio per la base giornaliera o mensile nel formato mm-dd-yyyy o una data e ora di inizio per la base oraria nel formato mm-dd-yyyy hh:mm:ss fuso orario. </dd>
<dt>--end</dt>
<dd>Specifica una data di fine per la base giornaliera o mensile nel formato mm-dd-yyyy o una data e ora di fine per la base oraria nel formato mm-dd-yyyy hh:mm:ss fuso orario. </dd>
</dl>

### Esempi
{: #cliresourceusagehistoryex}

```
cf ibmcloud-admin resource-metrics-history
cf ibmcloud-admin resource-metrics-history --daily --disk --start=07-04-2017
cf ibmcloud-admin resource-metrics-history --monthly --memory
cf ibmcloud-admin resource-metrics-history --hourly --start="06-01-2017 00:00:00 EDT" --end="06-30-2017 23:59:00 EDT
```
{: codeblock}

Puoi visualizzare l'elenco precedente di parametri ed esempi di comando utilizzando il seguente comando:

```
cf ba resource-metrics-history -help
```

Puoi anche utilizzare **`ba rsmh`** come un alias per il nome del comando **`ba resource-metrics-history`** più lungo.
{: tip}

## Gestione dei broker dei servizi
{: #admin_servbro}

### Elenco dei broker dei servizi
{: #clilistservbro}

Per elencare i broker dei servizi, utilizza il seguente comando:

```
cf ba service-brokers broker_name
```
{: codeblock}

Per elencare tutti i broker dei servizi, immetti il comando omettendo il parametro **`nome_broker`**.

<dl>
<dt>broker_name</dt>
<dd>Nome del broker dei servizi personalizzato. Utilizza questo parametro per ottenere informazioni per un broker dei servizi specifico. Facoltativo.</dd>
</dl>

Puoi anche utilizzare **`ba sb`** come un alias per il nome del comando **`ba service-brokers`** più lungo.
{: tip}

### Aggiunta di un broker dei servizi
{: #cliaddservbro}

Per aggiungere un broker dei servizi in modo tale da poter aggiungere un servizio personalizzato nel catalogo {{site.data.keyword.cloud_notm}}, utilizza il seguente comando:

```
cf ba add-service-broker broker_name user_name password broker_url
```
{: codeblock}

<dl>
<dt>broker_name</dt>
<dd>Nome del broker dei servizi personalizzato.</dd>
<dt>user_name</dt>
<dd>Nome utente per l'account con accesso al broker dei servizi.</dd>
<dt>password</dt>
<dd>Password per l'account con accesso al broker dei servizi.</dd>
<dt>broker_url</dt>
<dd>URL per il broker dei servizi.</dd>
</dl>

Puoi anche utilizzare **`ba asb`** come un alias per il nome del comando **`ba add-service-broker`** più lungo.
{: tip}

### Eliminazione di un broker dei servizi
{: #clidelservbro}

Per eliminare un broker dei servizi che rimuove il servizio personalizzato dal catalogo
{{site.data.keyword.cloud_notm}}, utilizza il seguente comando:

```
cf ba delete-service-broker service_broker
```
{: codeblock}

<dl>
<dt>service_broker</dt>
<dd>Il nome o il GUID del broker dei servizi personalizzato.</dd>
</dl>

Puoi anche utilizzare **`ba dsb`** come un alias per il nome del comando **`ba delete-service-broker`** più lungo.
{: tip}

### Aggiornamento di un broker dei servizi
{: #cliupdservbro}

Per aggiornare un broker dei servizi, utilizza il seguente comando:

```
cf ba update-service-broker broker_name user_name password broker_url
```
{: codeblock}

<dl>
<dt>broker_name</dt>
<dd>Nome del broker dei servizi personalizzato.</dd>
<dt>user_name</dt>
<dd>Nome utente per l'account con accesso al broker dei servizi.</dd>
<dt>password</dt>
<dd>Password per l'account con accesso al broker dei servizi.</dd>
<dt>broker_url</dt>
<dd>URL per il broker dei servizi.</dd>
</dl>

Puoi anche utilizzare **`ba usb`** come un alias per il nome del comando **`ba update-service-broker`** più lungo.
{: tip}

## Gestione dei gruppi di sicurezza dell'applicazione
{: #admin_secgro}

Per gestire i gruppi di sicurezza dell'applicazione (ASG), devi essere un amministratore con accesso completo all'ambiente locale o dedicato. Tutti gli utenti dell'ambiente possono elencare gli ASG disponibili per l'organizzazione a cui si fa riferimento con il comando. Tuttavia, per creare, aggiornare o associare gli ASG, devi essere l'amministratore dell'ambiente {{site.data.keyword.cloud_notm}}.

I gruppi ASG funzionano come firewall virtuali che controllano il traffico in uscita dalle applicazioni presenti nel tuo ambiente {{site.data.keyword.cloud_notm}}. Ogni ASG è costituito da un elenco di regole che consentono un traffico specifico e la comunicazione da e verso la rete esterna. Puoi associare uno o più ASG a una specifica serie di gruppi di sicurezza, ad esempio a una serie di gruppi utilizzata per applicare l'accesso globale, oppure associarli agli spazi all'interno di un'organizzazione nel tuo ambiente {{site.data.keyword.cloud_notm}}.

{{site.data.keyword.cloud_notm}} è inizialmente impostato con limitazioni a tutti gli accessi alla rete esterna. Due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, abilitano l'accesso globale alla rete esterna quando esegui il bind di tali gruppi alla serie di gruppi di sicurezza Cloud Foundry predefinita. Le due serie di gruppi di sicurezza in Cloud Foundry utilizzate per applicare l'accesso globale sono **Preparazione predefinita** ed **Esecuzione predefinita**. Queste serie di gruppi applicano le regole per consentire il traffico a tutte le applicazioni in esecuzione o a tutte le applicazioni in fase di preparazione. Se non vuoi eseguire il bind a queste due serie di gruppi di sicurezza, puoi annullare il bind alle serie di gruppi Cloud Foundry e quindi associare il gruppo a uno specifico spazio. Per ulteriori informazioni, vedi il documento relativo all'[associazione mediante bind dei gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

L'annullamento del bind delle serie di gruppi **Preparazione predefinita** o **Esecuzione predefinita** dai due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, disabilita l'accesso globale alla rete esterna. Utilizza l'annullamento del bind con cautela e consapevolezza del suo potenziale impatto sulle applicazioni in esecuzione e in fase di preparazione nel tuo ambiente.
{: important}

I seguenti comandi che consentono di gestire i gruppi di sicurezza si basano su Cloud Foundry versione 1.6. Per ulteriori informazioni, compresi i campi obbligatori e facoltativi, vedi le informazioni di Cloud Foundry relative alla [creazione di gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

### Elenco dei gruppi di sicurezza
{: #clilissecgro}

Per elencare tutti i gruppi di sicurezza, utilizza il seguente comando:

```
cf ba security-groups
```
{: codeblock}

Per visualizzare i dettagli di uno specifico gruppo di sicurezza, utilizza il seguente comando:

```
cf ba security-groups security-group
```
{: codeblock}

<dl>
<dt>Gruppo di sicurezza</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
</dl>

Puoi anche utilizzare **`ba sg`** come un alias per il nome del comando **`ba security-groups`** più lungo.
{: tip}

### Creazione di un gruppo di sicurezza
{: #clicreasecgro}

Per creare un gruppo di sicurezza, utilizza il seguente comando:
```
cf ba create-security-group security-group path-to-rules-file
```
{: codeblock}

Al nome di ciascun gruppo di sicurezza creato, viene aggiunto il prefisso `adminconsole_` per distinguerlo dai gruppi di sicurezza creati da IBM.

<dl>
<dt>security-group</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
<dt>path-to-rules-file</dt>
<dd>Il percorso assoluto o relativo a un file di regole.</dd>
</dl>

Puoi anche utilizzare **`ba csg`** come un alias per il nome del comando **`ba create-security-group`** più lungo.
{: tip}

Per ulteriori informazioni sulla creazione di gruppi di sicurezza e le regole che definiscono il traffico in uscita, vedi il documento relativo alla [creazione di gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

### Aggiornamento di un gruppo di sicurezza
{: #cliupdsecgro}

Per aggiornare un gruppo di sicurezza, utilizza il seguente comando:

```
cf ba update-security-group security-group path-to-rules-file
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
<dt>path-to-rules-file</dt>
<dd>Il percorso assoluto o relativo a un file di regole.</dd>
</dl>

Puoi anche utilizzare **`ba usg`** come un alias per il nome del comando **`ba update-security-group`** più lungo.
{: tip}

### Eliminazione di un gruppo di sicurezza
{: #clidelsecgro}

Per eliminare un gruppo di sicurezza, utilizza il seguente comando:
```
cf ba delete-security-group security-group
```
{: codeblock}

<dl>
<dt>Gruppo di sicurezza</dt>
<dd>Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba dsg`** come un alias per il nome del comando **`ba delete-security-group`** più lungo.
{: tip}

### Esecuzione del bind dei gruppi di sicurezza
{: #clibindsecgro}

Per eseguire il bind alla serie di gruppi di sicurezza Preparazione predefinita, utilizza il seguente comando:

```
cf ba bind-staging-security-group security-group
```
{: codeblock}

<dl>
<dt>Gruppo di sicurezza</dt>
<dd>Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba bssg`** come un alias per il nome del comando **`ba bind-staging-security-group`** più lungo.
{: tip}

Per eseguire il bind alla serie di gruppi di sicurezza Esecuzione predefinita, utilizza il seguente comando:

```
cf ba bind-running-security-group security-group
```
{: codeblock}

<dl>
<dt>Gruppo di sicurezza</dt>
<dd class="pd">Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba brsg`** come un alias per il nome del comando **`ba bind-running-security-group`** più lungo.
{: tip}

Per eseguire il bind di un gruppo di sicurezza a uno spazio, utilizza il seguente comando:

```
cf ba bind-security-group security-group org space
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
<dt>org</dt>
<dd>Il nome dell'organizzazione a cui associare il gruppo di sicurezza.</dd>
<dt>spazio</dt>
<dd>Il nome dello spazio all'interno dell'organizzazione a cui associare il gruppo di sicurezza.</dd>
</dl>

Puoi anche utilizzare **`ba bsg`** come un alias per il nome del comando **`ba bind-security-group`** più lungo.
{: tip}

Per ulteriori informazioni sull'associazione mediante bind dei gruppi di sicurezza, vedi il documento relativo all'[associazione mediante bind dei gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

### Annullamento del bind dei gruppi di sicurezza
{: #cliunbindsecgro}

L'annullamento del bind della serie di gruppi Preparazione predefinita dai due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, disabilita l'accesso globale alla rete esterna e deve essere utilizzato con cautela e comprensione delle implicazioni che ha su tutte le applicazioni in fase di preparazione nel tuo ambiente. Per annullare il bind dalla serie di gruppi di sicurezza Preparazione predefinita, utilizza il seguente comando:

```
cf ba unbind-staging-security-group security-group
```
{: codeblock}

<dl>
<dt>Gruppo di sicurezza</dt>
<dd>Il nome del tuo gruppo di sicurezza.</dd>
</dl>

Puoi anche utilizzare **`ba ussg`** come un alias per il nome del comando **`ba unbind-staging-security-group`** più lungo.
{: tip}

L'annullamento del bind della serie di gruppi Esecuzione predefinita dai due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, disabilita l'accesso globale alla rete esterna e deve essere utilizzato con cautela e comprensione delle implicazioni che ha su tutte le applicazioni in esecuzione nel tuo ambiente. Per annullare il bind dalla serie di gruppi di sicurezza Esecuzione predefinita, utilizza il seguente comando:

```
cf ba unbind-running-security-group security-group
```
{: codeblock}

<dl>
<dt>Gruppo di sicurezza</dt>
<dd>Il nome del tuo gruppo di sicurezza.</dd>
</dl>

Puoi anche utilizzare **`ba brsg`** come un alias per il nome del comando **`ba unbind-running-security-group`** più lungo.
{: tip}

Per annullare il bind di un gruppo di sicurezza a uno spazio, utilizza il seguente comando:

```
cf ba unbind-security-group security-group org space
```
{: codeblock}

<dl>
<dt>security-group</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
<dt>org</dt>
<dd>Il nome dell'organizzazione da cui annullare l'associazione al gruppo di sicurezza.</dd>
<dt>spazio</dt>
<dd>Il nome dello spazio all'interno dell'organizzazione da cui annullare l'associazione al gruppo di sicurezza.</dd>
</dl>

Puoi anche utilizzare **`ba usg`** come un alias per il nome del comando **`ba unbind-security-group`** più lungo.
{: tip}

Per ulteriori informazioni sull'annullamento dell'associazione mediante bind di gruppi di sicurezza, vedi il documento relativo all'[annullamento dell'associazione mediante bind di gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## Gestione dei pacchetti di build
{: #admin_buildpack}

### Elenco dei pacchetti di build
{: #clilistbuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi elencare i pacchetti di build. Per elencare tutti i pacchetti di build o visualizzarne uno specifico, utilizza il seguente comando:

```
cf ba buildpacks buildpack_name
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Un parametro facoltativo per specificare un determinato pacchetto di build da visualizzare.</dd>
</dl>

Puoi anche utilizzare **`ba lb`** come un alias per il nome del comando **`ba buildpacks`** più lungo.
{: tip}

### Creazione e caricamento di un pacchetto di build
{: #clicreupbuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi creare e caricare un pacchetto di build. Puoi caricare qualsiasi file compresso che presenta un tipo di file `.zip`. Per caricare un pacchetto di build, utilizza il seguente comando:

```
cf ba create-buildpack buildpack_name file_path position
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Il nome del pacchetto di build da caricare.</dd>
<dt>file_path</dt>
<dd>Il percorso del file compresso del pacchetto di build.</dd>
<dt>position</dt>
<dd>L'ordine in cui vengono controllati i pacchetti di build durante il rilevamento automatico.</dd>
</dl>

Puoi anche utilizzare **`ba cb`** come un alias per il nome del comando **`ba create-buildpack`** più lungo.
{: tip}

### Aggiornamento di un pacchetto di build
{: #cliupdabuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi aggiornare un pacchetto di build esistente. Per aggiornare un pacchetto di build, utilizza il seguente comando:
```
cf ba update-buildpack buildpack_name position enabled locked
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Il nome del pacchetto di build da aggiornare.</dd>
<dt>position</dt>
<dd>L'ordine in cui vengono controllati i pacchetti di build durante il rilevamento automatico.</dd>
<dt>enabled</dt>
<dd>Indica se il pacchetto di build è utilizzato per la fase di preparazione.</dd>
<dt>locked</dt>
<dd>Indica se il pacchetto di build è bloccato per impedire gli aggiornamenti.</dd>
</dl>

Puoi anche utilizzare **`ba ub`** come un alias per il nome del comando **`ba update-buildpack`** più lungo.
{: tip}

### Eliminazione di un pacchetto di build
{: #clidelbuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi eliminare un pacchetto di build esistente. Per eliminare un pacchetto di build, utilizza il seguente comando:
```
cf ba delete-buildpack buildpack_name
```
{: codeblock}

<dl>
<dt>buildpack_name</dt>
<dd>Il nome del pacchetto di build da eliminare.</dd>
</dl>

Puoi anche utilizzare **`ba db`** come un alias per il nome del comando **`ba delete-buildpack`** più lungo.
{: tip}
