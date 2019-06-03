---

copyright:
  years: 2015, 2019
lastupdated: "2019-05-21"

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
{: #bluemixadmincli}

Puoi gestire il tuo ambiente {{site.data.keyword.cloud_notm}} locale o {{site.data.keyword.cloud_notm}} dedicato utilizzando l'interfaccia riga di comando (CLI) Cloud Foundry con il plugin {{site.data.keyword.cloud_notm}} Admin CLI. Ad
esempio, puoi aggiungere utenti da un registro LDAP.

Prima di iniziare, installa la CLI Cloud Foundry. Il plugin {{site.data.keyword.cloud_notm}} Admin CLI
richiede `cf` versione 6.11.2 o successiva. [Scarica interfaccia riga di comando Cloud Foundry](https://github.com/cloudfoundry/cli/releases){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno")

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
cf ba add-user <nome_utente> <organizzazione> <nome> <cognome>
```
{: codeblock}

Per aggiungere un utente a un'organizzazione specifica, devi essere un amministratore con autorizzazione users.write (o Superuser). Se sei un gestore organizzazione, ti può essere data la possibilità di aggiungere utenti alla tua organizzazione da un Superuser che esegue il comando **`enable-managers-add-users`**. Per ulteriori informazioni, vedi [Abilitazione dei gestori all'aggiunta di utenti](#clius_emau).

| Opzione | Descrizione | 
| -------| ------------|
| _userName_ | Il nome dell'utente nel registro LDAP. |
| _organization_ | Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} a cui aggiungere l'utente. |
| _firstName_ | Il nome dell'utente da aggiungere all'organizzazione. | 
| _lastName_ | Il cognome dell'utente da aggiungere all'organizzazione. | 
{: caption="Tabella 1. Opzioni del comando cf ba add-user" caption-side="top"}

Puoi anche utilizzare **`ba au`** come un alias per il nome del comando **`ba add-user`** più lungo.
{: tip}

### Invito di un utente da {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_invite_public}

Ogni ambiente {{site.data.keyword.Bluemix_dedicated_notm}} ha un account aziendale pubblico di proprietà del client in {{site.data.keyword.cloud_notm}}. Affinché gli utenti nell'ambiente dedicato possano creare cluster con il {{site.data.keyword.containershort}}, l'amministratore deve aggiungere gli utenti a questo account aziendale pubblico. Una volta aggiunti gli utenti all'account aziendale pubblico, i loro account dedicati e pubblici sono collegati tra loro. Gli utenti possono quindi utilizzare il proprio ID IBM per accedere contemporaneamente all'ambiente dedicato e pubblico e possono creare risorse nell'account pubblico dall'interfaccia dedicata. Per ulteriori informazioni, vedi [Setting up IBM Cloud Container Service on Dedicated](/docs/containers?topic=containers-dedicated#dedicated_setup). Per invitare gli utenti dell'ambiente dedicato all'account pubblico:
```
cf ba invite-users-to-public -userid=<email_utente> -organization=<id_organizzazione_dedicato> -apikey=<chiave_api_pubblica> -public_org_id=<id_organizzazione_pubblico>
```
{: pre}

Per aggiungere utenti dell'ambiente dedicato al tuo account pubblico {{site.data.keyword.cloud_notm}}, devi essere un amministratore dell'account dedicato. 

| Opzione | Descrizione | 
| -------| ------------|
| -userid | Se inviti un singolo utente, l'e-mail dell'utente. |
| -organization | Se inviti tutti gli utenti attualmente in un'organizzazione dell'account dedicato, l'ID organizzazione dell'account dedicato. |
| -apikey | Una chiave API per invitare gli utenti all'account pubblico. Questo deve essere generato dall'amministratore dell'account pubblico. | 
| -public_org_id | L'ID dell'organizzazione dell'account pubblico a cui inviti gli utenti. | 
{: caption="Tabella 2. Opzioni del comando cf ba invite-users-to-public" caption-side="top"}

### Elenco degli utenti invitati da {{site.data.keyword.Bluemix_dedicated_notm}}
{: #admin_dedicated_list}

Se hai invitato utenti dell'ambiente dedicato al tuo account {{site.data.keyword.Bluemix_notm}} con il [comando **`invite-users-to-public`**](#admin_dedicated_invite_public), puoi elencare gli utenti nel tuo account per vedere il loro stato di invito. Gli utenti invitati che hanno un ID IBM esistente avranno uno stato di ATTIVO. Gli utenti invitati che non hanno un ID IBM esistente hanno lo stato IN SOSPESO o ATTIVO a seconda che abbiano già accettato o meno l'invito all'account. Per elencare gli utenti nel tuo account {{site.data.keyword.Bluemix_notm}}:

```
cf ba invite-users-status -apikey=<chiave_api_pubblica>
```
{: pre}

Per aggiungere utenti dell'ambiente dedicato al tuo account pubblico {{site.data.keyword.Bluemix_notm}}, devi essere un amministratore dell'account dedicato. 

<dl class="parml">
<dt class="pt dlterm">&lt;chiave_api_pubblica&gt;</dt>
<dd class="pd">La chiave API utilizzata per invitare gli utenti all'account. Questo deve essere generato dall'amministratore dell'account pubblico. </dd>
</dl>

<!-- staging-only commands start. Live for interconnect -->

### Ricerca di un utente
{: #admin_search_user}

Per ricercare un utente, utilizza il seguente comando con i parametri del filtro di ricerca facoltativi
(nome, autorizzazione, organizzazione e ruolo):

```
cf ba search-users -name=<valore_nome_utente> -permission=<valore_autorizzazione> -organization=<valore_organizzazione> -role=<valore_ruolo>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| -name | Il nome dell'utente. |
| -permission | L'autorizzazione assegnata all'utente. Le autorizzazioni disponibili sono admin (o superuser), login (o basic), catalog.read, catalog.write, reports.read, reports.write, users.read o users.write. Non puoi utilizzare questo parametro insieme al parametro organizzazione nella stessa query. |
| -organization | Il nome dell'organizzazione a cui appartiene l'utente. Non puoi utilizzare questo parametro insieme al parametro autorizzazione nella stessa query. | 
| -role | Il ruolo dell'organizzazione assegnato all'utente. I ruoli disponibili sono auditors, managers e billing_managers. Con questo parametro devi specificare l'organizzazione. | 
{: caption="Tabella 3. Opzioni del comando cf ba search-users" caption-side="top"}

Puoi anche utilizzare **`ba su`** come un alias per il nome del comando **`ba search-users`** più lungo.
{: tip}

### Impostazione di autorizzazioni per un utente
{: #admin_setperm_user}

Per impostare le autorizzazioni per uno specifico utente, utilizza il seguente comando:
```
cf ba set-permissions <nome_utente> <autorizzazione> <accesso>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _userName_ | Il nome dell'utente. |
| _permission_ | Imposta l'autorizzazione assegnata all'utente. Le autorizzazioni disponibili sono admin (o superuser), login (o basic), catalog.read, catalog.write, reports.read, reports.write, users.read o users.write. Non puoi utilizzare questo parametro insieme al parametro organizzazione nella stessa query. |
| _access_ | Per il catalogo, i report o le autorizzazioni utente, devi anche impostare il livello di accesso come `read` o `write`. |  
{: caption="Tabella 4. Opzioni del comando cf ba set-permissions" caption-side="top"}

Puoi impostare una sola autorizzazione alla volta.

Puoi anche utilizzare **`ba sp`** come un alias per il nome del comando **`ba set-permissions`** più lungo.
{: tip}

<!-- staging-only commands end -->

### Rimozione di un utente
{: #admin_remov_user}

Per rimuovere un utente dal tuo ambiente {{site.data.keyword.Bluemix_notm}}, utilizza il seguente comando:

```
cf ba remove-user <nome_utente>
```
{: codeblock}

<dl class="parml">

<dt class="pt dlterm">&lt;user_name&gt;</dt>
<dd class="pd">Il nome dell'utente in {{site.data.keyword.Bluemix_notm}}.</dd>

</dl>

Puoi anche utilizzare **`ba ru`** come un alias per il nome del comando **`ba remove-user`** più lungo.
{: tip}

### Abilitazione dei gestori all'aggiunta di utenti
{: #clius_emau}

Se disponi dell'autorizzazione Superuser nel tuo ambiente {{site.data.keyword.Bluemix_notm}}, puoi abilitare i gestori organizzazione ad aggiungere utenti alle organizzazioni che essi gestiscono. Per abilitare i gestori ad aggiungere utenti, utilizza il seguente comando:

```
cf ba enable-managers-add-users
```
{: codeblock}

Puoi anche utilizzare **`ba emau`** come un alias per il nome del comando **`ba enable-managers-add-users`** più lungo.
{: tip}

### Disabilitazione dei gestori all'aggiunta di utenti
{: #clius_dmau}

Se i gestori dell'organizzazione sono abilitati ad aggiungere utenti alle organizzazioni che gestiscono nel tuo ambiente {{site.data.keyword.Bluemix_notm}} con il comando **`enable-managers-add-users`** e disponi dell'autorizzazione Superuser, puoi rimuovere questa impostazione. Per disabilitare i gestori all'aggiunta di utenti, utilizza il seguente comando:

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
cf ba create-org <organizzazione> <manager>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ |Il nome o il GUID dell'organizzazione {{site.data.keyword.Bluemix_notm}} da aggiungere.|
| _manager_ | Il nome utente del gestore per l'organizzazione. |
{: caption="Tabella 5. Opzioni del comando cf ba create-org" caption-side="top"}

Puoi anche utilizzare **`ba co`** come un alias per il nome del comando **`ba create-org`** più lungo.
{: tip}

### Eliminazione di un'organizzazione
{: #admin_delete_org}

Per eliminare un'organizzazione, utilizza il seguente comando:

```
cf ba delete-org <organizzazione>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organization&gt;</dt>
<dd class="pd">Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} da eliminare.</dd>
</dl>

Puoi anche utilizzare **`ba do`** come un alias per il nome del comando **`ba delete-org`** più lungo.
{: tip}

### Assegnazione di un utente a un'organizzazione
{: #admin_ass_user_org}

Per assegnare un utente del tuo ambiente {{site.data.keyword.cloud_notm}} a
una specifica organizzazione, utilizza il seguente comando:

```
cf ba set-org <nome_utente> <organizzazione> [<ruolo>]
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _userName_ | Il nome dell'utente. |
| _organization_ | Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} a cui assegnare l'utente. |
| _role_ |Il ruolo dell'utente. I valori validi sono `OrgManager`, `BillingManager`, `OrgAuditor`. Vedi [Ruoli](/docs/iam?topic=iam-userroles#userroles) per le descrizioni dei ruoli. |  
{: caption="Tabella 6. Opzioni del comando cf ba set-org" caption-side="top"}

Puoi anche utilizzare **`ba so`** come un alias per il nome del comando **`ba set-org`** più lungo.
{: tip}

### Annullamento dell'assegnazione di un utente da un'organizzazione
{: #admin_unass_user_org}

Per annullare l'assegnazione di un utente del tuo ambiente {{site.data.keyword.cloud_notm}} da
una specifica organizzazione, utilizza il seguente comando:

```
cf ba unset-org <nome_utente> <organizzazione> [<ruolo>]
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _userName_ | Il nome dell'utente. |
| _organization_ |Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}}.|
| _role_ |Il ruolo dell'utente. I valori validi sono `OrgManager`, `BillingManager`, `OrgAuditor`. Vedi [Ruoli](/docs/iam?topic=iam-userroles#userroles) per le descrizioni dei ruoli. |  
{: caption="Tabella 7. Opzioni del comando cf ba unset-org" caption-side="top"}

Puoi anche utilizzare **`ba uo`** come un alias per il nome del comando **`ba unset-org`** più lungo.
{: tip}

### Impostazione di una quota per un'organizzazione
{: #admin_set_org_quota}

Per impostare la quota di utilizzo per una specifica organizzazione, utilizza il seguente comando:

```
cf ba set-quota <organizzazione> <piano>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ | Il nome o il GUID dell'organizzazione {{site.data.keyword.cloud_notm}} per cui impostare la quota. |
| _plan_ | Il piano di quota per un'organizzazione. |  
{: caption="Tabella 8. Opzioni del comando cf ba set-quota" caption-side="top"}

Puoi anche utilizzare **`ba sq`** come un alias per il nome del comando **`ba set-quota`** più lungo.
{: tip}


### Ricerca di quote contenitore per un'organizzazione
{: #admin_find_containquotas}

Per trovare la quota per i contenitori di un'organizzazione, utilizza il seguente comando:

```
cf ibmcloud-admin containers-quota <organizzazione>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;organizzazione&gt;</dt>
<dd class="pd">Il nome o l'ID dell'organizzazione in IBM Cloud. Questo parametro è obbligatorio.</dd>
</dl>

Puoi anche utilizzare **`ba cq`** come un alias per il nome del comando **`ibmcloud-admin containers-quota`** più lungo.
{: tip}

### Impostazione di quote contenitore per un'organizzazione
{: #admin_set_containquotas}

Per impostare la quota per i contenitori di un'organizzazione, utilizza il seguente comando con almeno una delle opzioni incluse:

```
cf ibmcloud-admin set-containers-quota <organizzazione> <options>
```
{: codeblock}

Puoi includere più opzioni, ma ne devi includere almeno una.
{: note}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ | Il nome o l'ID dell'organizzazione {{site.data.keyword.cloud_notm}} per cui impostare la quota. |
| _options_ | Le scelte sono **`floating-ips-max value`** (nome breve **`fim`**), **`floating-ips-space-default value`** (nome breve **`fisd`**), **`memory-max value`** (nome breve **`mm`**), **`memory-space-default value`** (nome breve **`msd`**) o **`image-limit value`** (nome breve **`il`**). Il valore deve essere un numero intero. |  
{: caption="Tabella 9. Opzioni del comando cf ibmcloud-admin set-containers-quota" caption-side="top"}

Facoltativamente, puoi fornire un file che contenga parametri di configurazione specifici in un oggetto JSON valido. Se utilizzi l'opzione **`-file`**, ha la precedenza e le altre opzioni vengono ignorate. Per fornire un file anziché impostare le opzioni, utilizza il seguente comando:

```
cf ibmcloud-admin set-containers-quota <organizzazione> <-file percorso_al_file_JSON>
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
cf ibmcloud-admin create-space <organizzazione> <nome_spazio>
```

{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ | Il nome o il GUID dell'organizzazione a cui aggiungere lo spazio. |
| _spaceName_ | Il nome dello spazio che stai aggiungendo all'organizzazione. |  
{: caption="Tabella 10. Opzioni del comando cf ibmcloud-admin create-space" caption-side="top"}

Puoi anche utilizzare **`ba cs`** come un alias per il nome del comando **`ba create-space`** più lungo.
{: tip}

### Eliminazione di un spazio dall'organizzazione

Per rimuovere uno spazio dall'organizzazione, utilizza il seguente comando:

```
cf ibmcloud-admin delete-space <organizzazione> <nome_spazio>
```

{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ | Il nome o il GUID dell'organizzazione da cui deve essere rimosso lo spazio. |
| _spaceName_ | Il nome dello spazio che stai rimuovendo dall'organizzazione. |  
{: caption="Tabella 11. Opzioni del comando cf ibmcloud-admin delete-space" caption-side="top"}

Puoi anche utilizzare **`ba cs`** come un alias per il nome del comando **`ba delete-space`** più lungo.
{: tip}

### Aggiunta di un utente a uno spazio con un ruolo

Per creare un utente in uno spazio con un ruolo specificato, utilizza il seguente comando:

```
cf ibmcloud-admin set-space <organizzazione> <nome_spazio> <nome_utente> <ruolo>
```

{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ | Il nome o il GUID dell'organizzazione a cui sta venendo aggiunto l'utente. |
| _spaceName_ | Il nome dello spazio a cui sta venendo aggiunto l'utente. |
| _userName_ | Il nome dell'utente. |
| _role_ |Il ruolo dell'utente. I valori validi sono `Manager`, `Developer` o `Auditor`. |  
{: caption="Tabella 12. Opzioni del comando cf ibmcloud-admin set-space" caption-side="top"}

Puoi anche utilizzare **`ba ss`** come un alias per il nome del comando **`ba set-space`** più lungo.
{: tip}


### Rimozione del ruolo di un utente in uno spazio

Per rimuovere il ruolo di un utente in uno spazio, utilizza il seguente comando:

```
cf ibmcloud-admin unset-space <organizzazione> <nome_spazio> <nome_utente> <ruolo>
```

{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _organization_ | Il nome o il GUID dell'organizzazione a cui appartiene l'utente. |
| _spaceName_ | Il nome dello spazio a cui appartiene l'utente. |
| _userName_ | Il nome dell'utente. |
| _role_ |Il ruolo dell'utente. I valori validi sono `Manager`, `Developer` o `Auditor`. |  
{: caption="Tabella 13. Opzioni del comando cf ibmcloud-admin unset-space" caption-side="top"}

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
cf ba enable-service-plan <identificativo_piano>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;identificativo_piano&gt;</dt>
<dd class="pd">Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di scegliere tra dei piani di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona **Aggiungi** per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio. </dd>
</dl>

Puoi anche utilizzare **`ba esp`** come un alias per il nome del comando **`ba enable-service-plan`** più lungo.
{: tip}

### Disabilitazione dei servizi per tutte le organizzazioni
{: #admin_dis_service_org}

Per disabilitare la visualizzazione di un servizio nel catalogo {{site.data.keyword.Bluemix_notm}} per tutte le
organizzazioni, utilizza il seguente comando:

```
cf ba disable-service-plan <identificativo_piano>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;identificativo_piano&gt;</dt>
<dd class="pd">Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di scegliere tra dei piani di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona **Aggiungi** per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio.</dd>
</dl>

Puoi anche utilizzare **`ba dsp`** come un alias per il nome del comando **`ba disable-service-plan`** più lungo.
{: tip}

### Aggiunta della visibilità dei servizi per le organizzazioni
{: #admin_addvis_service_org}

Puoi aggiungere un'organizzazione dall'elenco di organizzazioni che possono vedere uno specifico servizio nel catalogo {{site.data.keyword.Bluemix_notm}}. Per consentire a un'organizzazione di visualizzare uno specifico servizio nel catalogo, utilizza il seguente comando: 

```
cf ba add-service-plan-visibility <identificativo_piano> <organizzazione>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _planIdentifier_ | Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di scegliere tra dei piani di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona **Aggiungi** per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio. |
| _organization_ | Il nome o il GUID dell'organizzazione da aggiungere all'elenco di visibilità del servizio. |  
{: caption="Tabella 14. Opzioni del comando cf ba add-service-plan-visibility" caption-side="top"}

Puoi anche utilizzare **`ba aspv`** come un alias per il nome del comando **`ba add-service-plan-visibility`** più lungo.
{: tip}

### Rimozione della visibilità dei servizi per le organizzazioni
{: #admin_remvis_service_org}

Puoi rimuovere un'organizzazione dall'elenco di organizzazioni che possono vedere
uno specifico servizio nel catalogo {{site.data.keyword.Bluemix_notm}}. Per rimuovere la visibilità di un servizio nel catalogo per un'organizzazione, utilizza il seguente comando: 

```
cf ba remove-service-plan-visibility <identificativo_piano> <organizzazione>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _planIdentifier_ | Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di scegliere tra dei piani di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona **Aggiungi** per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio. |
| _organization_ | Il nome o il GUID dell'organizzazione da rimuovere dall'elenco di visibilità del servizio. |  
{: caption="Tabella 15. Opzioni del comando cf ba remove-service-plan-visibility" caption-side="top"}

Puoi anche utilizzare **`ba rspv`** come un alias per il nome del comando **`ba remove-service-plan-visibility`** più lungo.
{: tip}

### Modifica della visibilità dei servizi per le organizzazioni
{: #admin_editvis_service_org}

Puoi modificare e sostituire l'elenco di servizi che specifiche
organizzazioni possono vedere nel catalogo {{site.data.keyword.Bluemix_notm}}. Per sostituire tutti i servizi visibili esistenti per un'organizzazione o più organizzazioni, utilizza questo comando.

```
cf ba edit-service-plan-visibilities <identificativo_piano> <organizzazione_1> <organizzazione_facoltativa_2>
```
{: codeblock}

Questo
comando sostituisce i servizi visibili esistenti per le organizzazioni specificate con il servizio
da te specificato nel comando.

| Opzione | Descrizione | 
| -------| ------------|
| _planIdentifier_ | Il nome o il GUID del piano di servizio che desideri abilitare. Se immetti un nome del piano di servizio non univoco, ad esempio "Standard" o "Di base," ti verrà richiesto di scegliere tra dei piani di servizio. Per identificare il nome di un piano di servizio, seleziona la categoria di servizio dalla home page, quindi seleziona **Aggiungi** per visualizzare i servizi per quella categoria. Fai clic sul nome del servizio per aprire la vista Dettagli, da cui puoi visualizzare i nomi dei piani di servizi disponibili per il servizio. |
| _organization_ | Il nome o il GUID dell'organizzazione a cui aggiungere la visibilità. Puoi abilitare la visibilità del servizio per più di
un'organizzazione immettendo altri nomi o GUID di organizzazione nel comando. |  
{: caption="Tabella 16. Opzioni del comando cf ba edit-service-plan-visibilities" caption-side="top"}

Puoi anche utilizzare **`ba espv`** come un alias per il nome del comando **`ba edit-service-plan-visibility`** più lungo.
{: tip}

## Gestione dei report
{: #admin_add_report}

### Aggiunta di report
{: #admin_adding_report}

Per aggiungere un report di sicurezza, utilizza il seguente comando:

```
cf ba add-report <categoria> <date> <PDF|TXT|LOG> <RTF>
```
{: codeblock}

Se hai accesso in scrittura per l'autorizzazione dei report, puoi creare una nuova categoria e aggiungere un report in uno qualsiasi dei formati accettati per i tuoi utenti. Immetti il nome della nuova categoria per il parametro **`categoria`** o aggiungi il nuovo report a una categoria esistente.

| Opzione | Descrizione | 
| -------| ------------|
| _category_ | La categoria per il report. Se nel nome è presente uno spazio, utilizza le virgolette. |
| _date_ | La data del report nel formato YYYYMMDD. |  
| _filePath_ | Il percorso del PDF, file di testo o file di log del report da caricare. |
| _RTF_ | Un'opzione per includere una versione RTF (Rich Text Format) del PDF. Questa opzione si applica solo se includi un percorso al PDF del report. La versione RTF è utilizzata per l'indicizzazione e la ricerca. |
{: caption="Tabella 17. Opzioni del comando cf ba add-report" caption-side="top"}

Puoi anche utilizzare **`ba ar`** come un alias per il nome del comando **`ba add-report`** più lungo.
{: tip}

### Eliminazione di report
{: #admin_del_report}

Per eliminare un report di sicurezza, utilizza il seguente comando:

```
cf ba delete-report <categoria> <data> <nome>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _category_ | La categoria per il report. Se nel nome è presente uno spazio, utilizza le virgolette. |
| _date_ | La data del report nel formato YYYYMMDD. |  
| _name_ | Il nome del report. |
{: caption="Tabella 18. Opzioni del comando cf ba delete-report" caption-side="top"}

Puoi anche utilizzare **`ba d`r** come un alias per il nome del comando **`ba delete-report`** più lungo.
{: tip}

### Recupero di report
{: #admin_retr_report}

Per recuperare un report di sicurezza, utilizza il seguente comando:

```
cf ba retrieve-report <search>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;search&gt;</dt>
<dd class="pd">Il nome file del report. Se nel nome è presente uno spazio, racchiudi il nome
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
cf ba resource-metrics-history <hourly|daily|monthly>  <memory|disk >  <start|end>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| --hourly | View the historical data for the last 48 hours. This is the default value. |
| --daily | View the historical data daily average for the last 30 days. |  
| --monthly | View the historical data monthly average for the last 6 months. |
| --memory | View the used and total reserved and physical memory. |
| --disk | View the used and total reserved and physical disk. | 
| --start | Specify a start date for daily or monthly in the format of mm-dd-yyyy, or start date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
| --end | Specify an end date for daily or monthly in the format of mm-dd-yyyy, or end date and time for hourly in the format of mm-dd-yyyy hh:mm:ss time zone. |
{: caption="Tabella 19. Opzioni del comando cf ba resource-metrics-history" caption-side="top"}

**Esempi**

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
cf ba service-brokers <nome_broker>
```
{: codeblock}

Per elencare tutti i broker dei servizi, immetti il comando omettendo il parametro **`nome_broker`**.

<dl class="parml">
<dt class="pt dlterm">&lt;nome_broker&gt;</dt>
<dd class="pd">Nome del broker dei servizi personalizzato. Utilizza questo parametro per ottenere informazioni per un broker dei servizi specifico. Facoltativo.</dd>
</dl>

Puoi anche utilizzare **`ba sb`** come un alias per il nome del comando **`ba service-brokers`** più lungo.
{: tip}

### Aggiunta di un broker dei servizi
{: #cliaddservbro}

Per aggiungere un broker dei servizi in modo tale da poter aggiungere un servizio personalizzato nel catalogo {{site.data.keyword.Bluemix_notm}}, utilizza il seguente comando:

```
cf ba add-service-broker <nome_broker> <nome_utente> <password> <url_broker>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _brokerName_ | Nome del broker dei servizi personalizzato. |
| _userName_ | Nome utente per l'account con accesso al broker dei servizi. |  
| _password_ | Password per l'account con accesso al broker dei servizi. |
| _brokerURL_ | URL per il broker dei servizi. |
{: caption="Tabella 20. Opzioni del comando cf ba add-service-broker" caption-side="top"}

Puoi anche utilizzare **`ba asb`** come un alias per il nome del comando **`ba add-service-broker`** più lungo.
{: tip}

### Eliminazione di un broker dei servizi
{: #clidelservbro}

Per eliminare un broker dei servizi che rimuove il servizio personalizzato dal catalogo
{{site.data.keyword.Bluemix_notm}}, utilizza il seguente comando:

```
cf ba delete-service-broker <broker_servizi>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;broker_servizi&gt;</dt>
<dd class="pd">Il nome o il GUID del broker dei servizi personalizzato. </dd>
</dl>

Puoi anche utilizzare **`ba dsb`** come un alias per il nome del comando **`ba delete-service-broker`** più lungo.
{: tip}

### Aggiornamento di un broker dei servizi
{: #cliupdservbro}

Per aggiornare un broker dei servizi, utilizza il seguente comando:

```
cf ba update-service-broker <nome_broker> <nome_utente> <password> <url_broker>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _brokerName_ | Nome del broker dei servizi personalizzato. |
| _userName_ | Nome utente per l'account con accesso al broker dei servizi. |  
| _password_ | Password per l'account con accesso al broker dei servizi. |
| _brokerURL_ | URL per il broker dei servizi. |
{: caption=" Tabella 21. Opzioni del comando cf ba update-service-broker" caption-side="top"}

Puoi anche utilizzare **`ba usb`** come un alias per il nome del comando **`ba update-service-broker`** più lungo.
{: tip}

## Gestione dei gruppi di sicurezza dell'applicazione
{: #admin_secgro}

Per gestire i gruppi di sicurezza dell'applicazione (ASG), devi essere un amministratore con accesso completo all'ambiente locale o dedicato. Tutti gli utenti dell'ambiente possono elencare gli ASG disponibili per l'organizzazione a cui si fa riferimento con il comando. Tuttavia, per creare, aggiornare o associare gli ASG, devi essere l'amministratore dell'ambiente {{site.data.keyword.Bluemix_notm}}.

I gruppi ASG funzionano come firewall virtuali che controllano il traffico in uscita dalle applicazioni presenti nel tuo ambiente {{site.data.keyword.cloud_notm}}. Ogni ASG è costituito da un elenco di regole che consentono un traffico specifico e la comunicazione da e verso la rete esterna. Puoi associare uno o più ASG a una specifica serie di gruppi di sicurezza, ad esempio a una serie di gruppi utilizzata per applicare l'accesso globale, oppure associarli agli spazi all'interno di un'organizzazione nel tuo ambiente {{site.data.keyword.Bluemix_notm}}.

{{site.data.keyword.Bluemix_notm}} è inizialmente impostato con limitazioni a tutti gli accessi alla rete esterna. Due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, abilitano l'accesso globale alla rete esterna quando esegui il bind di tali gruppi alla serie di gruppi di sicurezza Cloud Foundry predefinita. Le due serie di gruppi di sicurezza in Cloud Foundry utilizzate per applicare l'accesso globale sono **Preparazione predefinita** ed **Esecuzione predefinita**. Queste serie di gruppi applicano le regole per consentire il traffico a tutte le applicazioni in esecuzione o a tutte le applicazioni in fase di preparazione. Se non vuoi eseguire il bind a queste due serie di gruppi di sicurezza, puoi annullare il bind alle serie di gruppi Cloud Foundry e quindi associare il gruppo a uno specifico spazio. Per ulteriori informazioni, vedi il documento relativo all'[associazione mediante bind dei gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

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
cf ba security-groups <gruppo-di-sicurezza>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Gruppo di sicurezza&gt;</dt>
<dd class="pd">Nome del gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba sg`** come un alias per il nome del comando **`ba security-groups`** più lungo.
{: tip}

### Creazione di un gruppo di sicurezza
{: #clicreasecgro}

Per creare un gruppo di sicurezza, utilizza il seguente comando:
```
cf ba create-security-group <gruppo-di-sicurezza> <percorso-del-file-di-regole>
```
{: codeblock}

Al nome di ciascun gruppo di sicurezza creato, viene aggiunto il prefisso `adminconsole_` per distinguerlo dai gruppi di sicurezza creati da IBM.

| Opzione | Descrizione | 
| -------| ------------|
| _groupName_ | Il nome del gruppo di sicurezza. |
| _filePath_ | Il percorso assoluto o relativo a un file di regole. |  
{: caption="Tabella 22. Opzioni del comando cf ba create-security-group" caption-side="top"}

Puoi anche utilizzare **`ba csg`** come un alias per il nome del comando **`ba create-security-group`** più lungo.
{: tip}

Per ulteriori informazioni sulla creazione di gruppi di sicurezza e le regole che definiscono il traffico in uscita, vedi il documento relativo alla [creazione di gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#creating-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

### Aggiornamento di un gruppo di sicurezza
{: #cliupdsecgro}

Per aggiornare un gruppo di sicurezza, utilizza il seguente comando:

```
cf ba update-security-group <gruppo-di-sicurezza> <percorso-del-file-di-regole>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _groupName_ | Il nome del gruppo di sicurezza. |
| _filePath_ | Il percorso assoluto o relativo a un file di regole. |  
{: caption="Tabella 23. Opzioni del comando cf ba update-security-group" caption-side="top"}

Puoi anche utilizzare **`ba usg`** come un alias per il nome del comando **`ba update-security-group`** più lungo.
{: tip}

### Eliminazione di un gruppo di sicurezza
{: #clidelsecgro}

Per eliminare un gruppo di sicurezza, utilizza il seguente comando:
```
cf ba delete-security-group <gruppo-di-sicurezza>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Gruppo di sicurezza&gt;</dt>
<dd class="pd">Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba dsg`** come un alias per il nome del comando **`ba delete-security-group`** più lungo.
{: tip}

### Esecuzione del bind dei gruppi di sicurezza
{: #clibindsecgro}

Per eseguire il bind alla serie di gruppi di sicurezza Preparazione predefinita, utilizza il seguente comando:

```
cf ba bind-staging-security-group <gruppo-di-sicurezza>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Gruppo di sicurezza&gt;</dt>
<dd class="pd">Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba bssg`** come un alias per il nome del comando **`ba bind-staging-security-group`** più lungo.
{: tip}

Per eseguire il bind alla serie di gruppi di sicurezza Esecuzione predefinita, utilizza il seguente comando:

```
cf ba bind-running-security-group <gruppo-di-sicurezza>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Gruppo di sicurezza&gt;</dt>
<dd class="pd">Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba brsg`** come un alias per il nome del comando **`ba bind-running-security-group`** più lungo.
{: tip}

Per eseguire il bind di un gruppo di sicurezza a uno spazio, utilizza il seguente comando:

```
cf ba bind-security-group <gruppo-di-sicurezza> <organizzazione> <spazio>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _groupName_ | Il nome del gruppo di sicurezza. |
| _org_ | Il nome dell'organizzazione a cui associare il gruppo di sicurezza. |
| _space_ | Il nome dello spazio all'interno dell'organizzazione a cui associare il gruppo di sicurezza. |
{: caption="Tabella 24. Opzioni del comando cf ba bind-security-group" caption-side="top"}

Puoi anche utilizzare **`ba bsg`** come un alias per il nome del comando **`ba bind-security-group`** più lungo.
{: tip}

Per ulteriori informazioni sull'associazione mediante bind dei gruppi di sicurezza, vedi il documento relativo all'[associazione mediante bind dei gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#binding-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

### Annullamento del bind dei gruppi di sicurezza
{: #cliunbindsecgro}

L'annullamento del bind della serie di gruppi Preparazione predefinita dai due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, disabilita l'accesso globale alla rete esterna e deve essere utilizzato con cautela e comprensione delle implicazioni che ha su tutte le applicazioni in fase di preparazione nel tuo ambiente. Per annullare il bind dalla serie di gruppi di sicurezza Preparazione predefinita, utilizza il seguente comando:

```
cf ba unbind-staging-security-group <gruppo-di-sicurezza>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Gruppo di sicurezza&gt;</dt>
<dd class="pd">Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba ussg`** come un alias per il nome del comando **`ba unbind-staging-security-group`** più lungo.
{: tip}

L'annullamento del bind della serie di gruppi Esecuzione predefinita dai due gruppi di sicurezza creati da IBM, `public_networks` e `dns`, disabilita l'accesso globale alla rete esterna e deve essere utilizzato con cautela e comprensione delle implicazioni che ha su tutte le applicazioni in esecuzione nel tuo ambiente. Per annullare il bind dalla serie di gruppi di sicurezza Esecuzione predefinita, utilizza il seguente comando:

```
cf ba unbind-running-security-group <gruppo-di-sicurezza>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;Gruppo di sicurezza&gt;</dt>
<dd class="pd">Nome del tuo gruppo di sicurezza</dd>
</dl>

Puoi anche utilizzare **`ba brsg`** come un alias per il nome del comando **`ba unbind-running-security-group`** più lungo.
{: tip}

Per annullare il bind di un gruppo di sicurezza a uno spazio, utilizza il seguente comando:

```
cf ba unbind-security-group <gruppo-di-sicurezza> <organizzazione> <spazio>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _groupName_ | Il nome del gruppo di sicurezza. |
| _org_ | Il nome dell'organizzazione da cui annullare l'associazione al gruppo di sicurezza. |
| _space_ | Il nome dello spazio all'interno dell'organizzazione da cui annullare l'associazione al gruppo di sicurezza. |
{: caption="Tabella 25. Opzioni del comando cf ba unbind-security-group" caption-side="top"}

Puoi anche utilizzare **`ba usg`** come un alias per il nome del comando **`ba unbind-security-group`** più lungo.
{: tip}

Per ulteriori informazioni sull'annullamento dell'associazione mediante bind di gruppi di sicurezza, vedi il documento relativo all'[annullamento dell'associazione mediante bind di gruppi di sicurezza dell'applicazione](https://docs.cloudfoundry.org/concepts/asg.html#unbinding-groups){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## Gestione dei pacchetti di build
{: #admin_buildpack}

### Elenco dei pacchetti di build
{: #clilistbuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi elencare i pacchetti di build. Per elencare tutti i pacchetti di build o visualizzarne uno specifico, utilizza il seguente comando:

```
cf ba buildpacks <nome_pacchettodibuild>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;nome_pacchettodibuild&gt;</dt>
<dd class="pd">Un parametro facoltativo per specificare un determinato pacchetto di build da visualizzare.</dd>
</dl>

Puoi anche utilizzare **`ba lb`** come un alias per il nome del comando **`ba buildpacks`** più lungo.
{: tip}

### Creazione e caricamento di un pacchetto di build
{: #clicreupbuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi creare e caricare un pacchetto di build. Puoi caricare qualsiasi file compresso che presenta un tipo di file `.zip`. Per caricare un pacchetto di build, utilizza il seguente comando:

```
cf ba create-buildpack <nome_pacchettodibuild> <percorso_file> <posizione>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _name_ | Il nome del pacchetto di build da caricare. |
| _filePath_ | Il percorso del file compresso del pacchetto di build. |
| _position_ | L'ordine in cui vengono controllati i pacchetti di build durante il rilevamento automatico. |
{: caption="Tabella 26. Opzioni del comando cf ba create-buildpack" caption-side="top"}

Puoi anche utilizzare **`ba cb`** come un alias per il nome del comando **`ba create-buildpack`** più lungo.
{: tip}

### Aggiornamento di un pacchetto di build
{: #cliupdabuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi aggiornare un pacchetto di build esistente. Per aggiornare un pacchetto di build, utilizza il seguente comando:
```
cf ba update-buildpack <nome_pacchettodibuild> <posizione> <abilitato> <bloccato>
```
{: codeblock}

| Opzione | Descrizione | 
| -------| ------------|
| _name_ | Il nome del pacchetto di build da aggiornare. |
| _position_ | L'ordine in cui vengono controllati i pacchetti di build durante il rilevamento automatico. |
| _enabled_ | Indica se il pacchetto di build è utilizzato per la fase di preparazione. |
| _locked_ | Indica se il pacchetto di build è bloccato per impedire gli aggiornamenti. | 
{: caption="Tabella 27. Opzioni del comando cf ba update-buildpack" caption-side="top"}

Puoi anche utilizzare **`ba ub`** come un alias per il nome del comando **`ba update-buildpack`** più lungo.
{: tip}

### Eliminazione di un pacchetto di build
{: #clidelbuildpack}

Se disponi di autorizzazioni di scrittura nel catalogo di applicazioni, puoi eliminare un pacchetto di build esistente. Per eliminare un pacchetto di build, utilizza il seguente comando:
```
cf ba delete-buildpack <nome_pacchettodibuild>
```
{: codeblock}

<dl class="parml">
<dt class="pt dlterm">&lt;nome_pacchettodibuild&gt;</dt>
<dd class="pd">Il nome del pacchetto di build da eliminare.</dd>
</dl>

Puoi anche utilizzare **`ba db`** come un alias per il nome del comando **`ba delete-buildpack`** più lungo.
{: tip}
