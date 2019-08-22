---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-05"

keywords: cli, ibmcloud account cli, managing accounts cli, managing users cli, managing orgs, cloud foundry user cli, account space cli, account, account orgs, account update command, add certificate cli, remove certificate command, manage cf users cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}

# Gestione di account, utenti e organizzazioni Cloud Foundry
{: #ibmcloud_commands_account}

Utilizza i seguenti comandi per gestire gli account, gli utenti in un account e l'organizzazione, lo spazio e i ruoli degli ambienti Cloud Foundry pubblici.
{: shortdesc}

## ibmcloud account orgs
{: #ibmcloud_account_orgs}

Elenca tutte le organizzazioni.
```
ibmcloud account orgs [-r NOME_REGIONE] [--guid | --output FORMATO] [-c ID_ACCOUNT] [-u PROPRIETARIO_ACCOUNT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-r NOME_REGIONE</dt>
   <dd>Nome della regione. Elenca le organizzazioni nella regione specificata. Se non specificato, il valore predefinito è la regione corrente. Se impostato su 'all', elenca le organizzazioni in tutte le regioni.</dd>
   <dt>--guid</dt>
   <dd>Visualizza il guid delle organizzazioni. Questa opzione è esclusiva con `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con `--guid`.</dd>
   <dt>-c ID_ACCOUNT</dt>
   <dd>ID account. Elenca le organizzazioni nell'account. Se non specificato, il valore predefinito è l'account corrente. Se impostato su `all`, elenca le organizzazioni in tutti gli account. Questa opzione è esclusiva con `-u`.</dd>
   <dt>-u PROPRIETARIO_ACCOUNT</dt>
   <dd>Nome proprietario account. Elenca le organizzazioni negli account appartenenti all'utente. Se non specificato, il valore predefinito è l'account corrente. Se impostato su 'all', elenca le organizzazioni in tutti gli account. Questa opzione è esclusiva con `-c`.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutte le organizzazioni nella regione `us-south` con il GUID visualizzato:
```
ibmcloud account orgs -r us-south --guid
```

Elenca tutte le organizzazioni nel formato JSON:
```
ibmcloud account orgs --output JSON
```

## ibmcloud account org
{: #ibmcloud_account_org}

Mostra le informazioni dell'organizzazione specificata
```
ibmcloud account org NOME_ORGANIZZAZIONE [-r REGIONE] [--guid | --output REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>-r REGIONE</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente. Se impostato su `all`, vengono elencate le organizzazioni con il nome indicato in tutte le regioni.</dd>
   <dt>--guid</dt>
   <dd>Richiama e visualizza il guid dell'organizzazione. Tutti gli altri output per l'organizzazione vengono eliminati. Questa opzione è esclusiva con `--output`.</dd>
   <dt>--output REGIONE</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con `--guid`.</dd>
   </dl>

<strong>Esempi</strong>:

Mostra le informazioni dell'organizzazione `IBM` con il GUID visualizzato.
```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crea un'organizzazione. Questa operazione può essere eseguita solo dal proprietario dell'account.
```
ibmcloud account org-create NOME_ORGANIZZAZIONE [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da creare.</dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

<strong>Esempi</strong>:

Crea un'organizzazione denominata `IBM`.
```
ibmcloud account org-create IBM 
```

## ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replica un'organizzazione dalla regione corrente in un'altra regione.
```
ibmcloud account org-replicate NOME_ORGANIZZAZIONE NOME_REGIONE [-r, --region REGIONE_ORIGINE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione esistente che deve essere replicata.</dd>
   <dt>NOME_REGIONE (obbligatorio)</dt>
   <dd>Il nome della regione che ospita l'organizzazione replicata.</dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

<strong>Esempi</strong>:

Replica l'organizzazione `myorg` nella regione `eu-gb`:
```
ibmcloud account org-replicate myorg eu-gb
```

## ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Rinomina un'organizzazione. Questa operazione può essere eseguita solo da un gestore organizzazione.
```
ibmcloud account org-rename NOME_ORGANIZZAZIONE_PRECEDENTE NUOVO_NOME_ORGANIZZAZIONE [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE_PRECEDENTE (obbligatorio)</dt>
   <dd>Il vecchio nome dell'organizzazione da rinominare.</dd>
   <dt>NUOVO_NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nuovo nome dell'organizzazione da rinominare.</dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Elenca tutti gli spazi di account.
```
ibmcloud account spaces [-o NOME_ORGANIZZAZIONE] [-r NOME-REGIONE] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-o NOME_ORGANIZZAZIONE (facoltativo)</dt>
   <dd>Nome dell'organizzazione. Elenca gli spazi nell'organizzazione specificata. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>-r NOME-REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Elenca gli spazi nella regione specificata. Se non specificato, il valore predefinito è la regione corrente.</dd>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutti gli spazi:
```
ibmcloud account spaces
```

Elenca tutti gli spazi dell'organizzazione `org_example` nel formato JSON:
```
ibmcloud account spaces -o org_example --output JSON
```

## ibmcloud account space
{: #ibmcloud_account_space}

Mostra le informazioni di uno specifico spazio.
```
ibmcloud account space NOME_SPAZIO [-o NOME_ORGANIZZAZIONE] [--guid | --output FORMATO] [--security-group-rules]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Nome dello spazio da visualizzare.</dd>
   <dt>-o NOME_ORGANIZZAZIONE</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>--guid</dt>
   <dd>Richiama e visualizza il guid dello spazio. Tutti gli altri output per lo spazio vengono eliminati. Questa opzione è esclusiva con `--output`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON. Tutti gli altri output per lo spazio vengono eliminati. Questa opzione è esclusiva con `--guid`.</dd>
   <dt>--security-group-rules</dt>
   <dd>Richiama le regole di tutti i gruppi di sicurezza associati allo spazio.</dd>
   </dl>

<strong>Esempi</strong>:

Mostra le informazioni dello spazio `space_example`:
```
ibmcloud account space space_example
```

Mostra Il GUID dello spazio `space_example`:
```
ibmcloud account space space_example --guid
```

Mostra le informazioni dello spazio `space_example` nel formato JSON:
```
ibmcloud account space space_example --output JSON
```

Mostra le regole del gruppo di sicurezza dello spazio `space_example`:
```
ibmcloud account space space_example --security-group-rules
```

## ibmcloud account space-create
{: #ibmcloud_account_space_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [`cf create-space`](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}

Questo comando ha la stessa funzione e le stesse opzioni del comando [`cf rename-space`](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}

Questo comando ha la stessa funzione e le stesse opzioni del comando [`cf delete-space`](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Visualizza gli utenti nell'organizzazione specificata per il ruolo.

```
ibmcloud account org-users NOME_ORGANIZZAZIONE [-r, --region REGIONE] [-a, --all]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
<dd>Il nome dell'organizzazione.</dd>
<dt>-a, -all (facoltativo)</dt>
<dd>Elenca tutti gli utenti dell'organizzazione specificata, non raggruppati per ruolo.</dd>
<dt>-r, --region REGIONE (facoltativo)</dt>
<dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
</dl> 

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Aggiunge un utente nell'organizzazione (è richiesto il gestore organizzazione).
```
 ibmcloud account org-user-add NOME_UTENTE ORGANIZZAZIONE [-r, --region REGIONE]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Il nome dell'utente.</dd>
<dt>ORGANIZZAZIONE (obbligatorio)</dt>
<dd>Il nome dell'organizzazione.</dd>
<dt>-r, --region REGIONE (facoltativo)</dt>
<dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
</dl>  

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Rimuove un utente dall'organizzazione (solo il gestore organizzazione o l'utente).
```
ibmcloud account org-user-remove NOME_UTENTE ORGANIZZAZIONE [-f, --force]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Ottiene tutti i ruoli organizzazione dell'utente corrente.
```
ibmcloud account org-roles [-r, --region REGIONE] [-u ID_UTENTE] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID utente. Se non specificato, il valore predefinito è l'utente corrente.</dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assegna un ruolo dell'organizzazione a un utente. Questa operazione deve essere eseguita da un gestore organizzazione.
```
ibmcloud account org-role-set NOME_UTENTE NOME_ORGANIZZAZIONE RUOLO_ORGANIZZAZIONE [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente da assegnare.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>RUOLO_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome del ruolo organizzazione a cui viene assegnato l'utente. Ad esempio:
   <ul>
   <li>OrgManager: questo ruolo può invitare e gestire utenti, selezionare e modificare piani e impostare limiti di spesa.</li>
   <li>BillingManager: questo ruolo può creare e gestire l'account di fatturazione e le informazioni sul pagamento.</li>
   <li>OrgAuditor: questo ruolo dispone di un accesso in sola lettura a report e informazioni sull'organizzazione.</li>
   </ul>
   </dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Assegna l'utente `Mary` all'organizzazione `IBM` con il ruolo `OrgManager`:
```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
Puoi impostare i ruoli organizzazione e spazio utilizzando la CLI ma, se vuoi impostare le altre autorizzazioni, devi utilizzare l'IU. Per ulteriori informazioni, vedi [Gestione dell'accesso alle risorse](/docs/iam?topic=iam-iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Rimuove un ruolo dell'organizzazione da un utente. Questa operazione può essere eseguita solo da un gestore organizzazione.
```
ibmcloud account org-role-unset NOME_UTENTE NOME_ORGANIZZAZIONE RUOLO_ORGANIZZAZIONE [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente da rimuovere.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>RUOLO_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome del ruolo organizzazione da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>OrgManager: questo ruolo può invitare e gestire utenti, selezionare e modificare piani e impostare limiti di spesa.</li>
   <li>BillingManager: questo ruolo può creare e gestire l'account di fatturazione e le informazioni sul pagamento.</li>
   <li>OrgAuditor: questo ruolo dispone di un accesso in sola lettura a report e informazioni sull'organizzazione.</li>
   </ul>
   </dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

<strong>Esempi</strong>:

Rimuove l'utente `Mary` dall'organizzazione `IBM` con il ruolo `OrgManager`:
```
ibmcloud account org-role-unset Mary IBM OrgManager
```

## ibmcloud account space-users
{: #ibmcloud_account_space_users}

Visualizza gli utenti nello spazio specificato per il ruolo.
```
ibmcloud account space-users NOME_ORGANIZZAZIONE NOME_SPAZIO [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio.</dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

## ibmcloud account space-roles
{: #ibmcloud_account_space_roles}

Ottiene tutti i ruoli dello spazio dell'utente corrente nell'organizzazione specifica

```
ibmcloud account space-roles ORGANIZZAZIONE [-r, --region REGIONE] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>-r (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
   </dl>

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assegna un ruolo dello spazio a un utente. Questa operazione può essere eseguita solo da un gestore spazio.
```
ibmcloud account space-role-set NOME_UTENTE NOME_ORGANIZZAZIONE NOME_SPAZIO RUOLO_SPAZIO [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente da assegnare.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio a cui è assegnato l'utente.</dd>
   <dt>RUOLO_SPAZIO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio a cui è assegnato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul>
   </dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

<strong>Esempi</strong>:

Assegna l'utente `Mary` all'organizzazione `IBM` e allo spazio `Cloud` con il ruolo `SpaceManager`:
```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

## ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Rimuove un ruolo dello spazio da un utente. Questa operazione può essere eseguita solo da un gestore spazio.
```
ibmcloud account space-role-unset NOME_UTENTE NOME_ORGANIZZAZIONE NOME_SPAZIO RUOLO_SPAZIO [-r, --region REGIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente da rimuovere.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio da cui viene eliminato l'utente.</dd>
   <dt>RUOLO_SPAZIO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
   <dt>-r, --region REGIONE (facoltativo)</dt>
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
    </dl>


<strong>Esempi</strong>:

Rimuove l'utente `Mary` dall'organizzazione `IBM` e dall spazio `Cloud` con il ruolo `SpaceManager`:
```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

## ibmcloud account list
{: #ibmcloud_account_list}

Elenca tutti gli account dell'utente corrente:
```
ibmcloud account list [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Visualizza l'account dell'organizzazione specificata (utente dell'organizzazione obbligatorio).
```
ibmcloud account org-account NOME_ORGANIZZAZIONE [-r, --region REGIONE] [--guid | --output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-r (facoltativo)</dt>
  <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente.</dd>
  <dt>--guid (facoltativo)</dt>
  <dd>Visualizza solo l'ID account</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Mostra i dettagli dell'account.
```
ibmcloud account show
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli dell'account attualmente indicato come destinazione:
```
ibmcloud account show
```

## ibmcloud account update
{: #ibmcloud_account_update}

Aggiorna uno specifico account:
```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Abilita o disabilita la connettività agli endpoint del servizio per un account SoftLayer.</dd>
</dl>

<strong>Esempi</strong>:

Abilita la connettività agli endpoint del servizio per l'account corrente:
```
ibmcloud account update --service-endpoint-enable true
```

## Classic infrastructure account audit-logs
{: #classic_account_audit_logs}

Elenca i log di controllo dell'account SoftLayer:
```
account audit-logs [-u, --user-name NOME_UTENTE] [-t, --object-type TIPO_OGGETTO] [-o, --object OGGETTO] [-a, --action AZIONE] [-s, --start-date DATA_INIZIO] [-e, --end-date DATA_FINE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-a, --action <i>AZIONE</i></dt>
  <dd>Azione. Elenca i log di controllo con l'azione.</dd>
  <dt>-e, --end-date <i>DATA_FINE</i></dt>
  <dd>Data di fine. Elenca i log di controllo prima della data di fine. I formati supportati sono yyyy-MM-ddTHH:mm:ss.</dd>
  <dt>-o, --object <i>OGGETTO</i></dt>
  <dd>Oggetto. Elenca i log di controllo con l'oggetto.</dd>
  <dt>-t, --object-type <i>TIPO_OGGETTO</i></dt>
  <dd>Tipo di oggetto. Elenca i log di controllo con il tipo di oggetto.</dd>
  <dt>-s, --start-date <i>DATA_INIZIO</i></dt>
  <dd>Data di inizio. Elenca i log di controllo dopo la data di inizio. I formati supportati sono yyyy-MM-ddTHH:mm:ss.</dd>
  <dt>-u, --user-name <i>NOME_UTENTE</i></dt>
  <dd>Nome utente. Elenca i log di controllo con il nome utente.</dd>
</dl>

<strong>Esempi</strong>:

Elenca i log di controllo:
```
ibmcloud account audit-logs
```

## ibmcloud account audit-logs
{: #ibmcloud_account_audit_logs}

Elenca i log di controllo dell'account

```
ibmcloud account audit-logs [--user-name NOME_UTENTE] [--object-type TIPO_OGGETTO] [--object OGGETTO] [--action AZIONE] [--start-date DATA_INIZIO] [--end-date DATA_FINE] [--output FORMATO]
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>--user-name <i>NOME_UTENTE</i> (facoltativo)</dt>
   <dd>Elenca i log di controllo con il nome utente.</dd>
   <dt>--object-type <i>TIPO_OGGETTO</i> (facoltativo)</dt>
   <dd>Elenca i log di controllo con il tipo di oggetto.</dd>
   <dt>--object <i>OGGETTO</i> (facoltativo)</dt>
   <dd>Elenca i log di controllo con l'oggetto.</dd>
   <dt>--action <i>AZIONE</i> (facoltativo)</dt>
   <dd>Elenca i log di controllo con l'azione.</dd>
   <dt>--start-date <i>DATA_INIZIO</i> (facoltativo)</dt>
   <dd>Elenca i log di controllo dopo la data di inizio. I formati supportati sono yyyy-MM-ddTHH:mm:ss.</dd>
   <dt>--end-date <i>DATA_FINE</i> (facoltativo)</dt>
   <dd>Elenca i log di controllo prima della data di fine. I formati supportati sono yyyy-MM-ddTHH:mm:ss.</dd>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account users
{: #ibmcloud_account_users}

Visualizza gli utenti associati all'account. Questa operazione deve essere eseguita dal proprietario dell'account.
```
ibmcloud account users [-c, --account-id ID_ACCOUNT] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>-c (facoltativo)</dt>
<dd>ID account. Se non specificato, il valore predefinito è l'account corrente.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Rimuove un utente da un account (solo il proprietario dell'account).
```
ibmcloud account user-remove ID_UTENTE [-c ID_ACCOUNT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>ID_UTENTE (obbligatorio)</dt>
<dd>ID utente</dd>
<dt>-c ID_ACCOUNT</dt>
<dd>ID account. Se non specificato, il valore predefinito è l'account corrente.</dd>
<dt>-f, --force</dt>
<dd>Forza la rimozione senza conferma.</dd>
</dl>

## ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invita un utente nell'account:
```
ibmcloud account user-invite EMAIL_UTENTE [-o ORG [--org-role RUOLO_ORG] [-s SPAZIO, --space-role RUOLO_SPAZIO]]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'email dell'utente da invitare.</dd>
   <dt>-o ORG</dt>
   <dd>Organizzazione a cui invitare l'utente</dd>
   <dt>--org-role RUOLO_ORG</dt>
   <dd>Ruolo organizzazione. Gli input validi sono: OrgManager, BillingManager, OrgAuditor e OrgUser. Se omesso, viene impostato il ruolo OrgUser.</dd>
   <dt>-s SPAZIO</dt>
   <dd>Spazio a cui invitare l'utente</dd>
   <dt>--space-role RUOLO_SPAZIO</dt>
   <dd>Ruolo spazio. Gli input validi sono: SpaceManager, SpaceDeveloper e SpaceAuditor.</dd>
</dl>

Se non sei pronto ad assegnare l'accesso o vuoi assegnare una politica IAM invece dell'accesso Cloud Foundry, puoi invitare un utente senza accesso e assegnarlo successivamente. Per ulteriori informazioni sull'assegnazione dell'accesso agli utenti, vedi [Gestione dell'accesso alle risorse](/docs/iam?topic=iam-iammanidaccser#assign_new_access).
{: tip}

## ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Invia di nuovo l'invito a un utente (amministratore dell'account).
```
ibmcloud account user-reinvite EMAIL_UTENTE
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'email dell'utente da invitare di nuovo.</dd>
</dl>

## ibmcloud account user-preference
{: #ibmcloud_account_user_preference}

Mostra i dettagli della preferenza utente

```
ibmcloud account user-preference [--output FORMATO]
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account user-preference-update
{: #ibmcloud_account_user_preference_update}

Aggiorna la preferenza utente

```
ibmcloud account user-preference-update (--position NUOVA_POSIZIONE) [--output FORMATO]
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>--position <i>NUOVA_POSIZIONE</i> (facoltativo)</dt>
   <dd>Imposta la posizione di un utente, come ad esempio 'gestore' o 'studente'.</dd>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account platform-notification-subscribe
{: #ibmcloud_account_platform_notification_subscribe}

Sottoscrivi notifica della piattaforma:
```
ibmcloud account platform-notification-subscribe (--type TIPO)
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>--type <i>TIPO</i> (facoltativo)</dt>
   <dd>Tipo di notifica, uno di 'unplanned_events', 'planned_maintenance'.</dd>
</dl>

## ibmcloud account platform-notification-unsubscribe
{: #ibmcloud_account_platform_notification_unsubscribe}

Annulla sottoscrizione notifica della piattaforma:
```
ibmcloud account platform-notification-unsubscribe (--type TIPO)
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>--type <i>TIPO</i> (facoltativo)</dt>
   <dd>Tipo di notifica, uno di 'unplanned_events', 'planned_maintenance'.</dd>
</dl>

## ibmcloud account domain-cert
{: #ibmcloud_account_domain_cert}

Elenca le informazioni sul certificato di un dominio:
```
ibmcloud account domain-cert NOME_DOMINIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_DOMINIO (obbligatorio)</dt>
<dd>Il dominio che ospita il certificato.</dd>
</dl>


<strong>Esempi</strong>:

Visualizza le informazioni sul certificato del dominio `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert ibmcxo-eventconnect.com
```

## ibmcloud account domain-cert-add
{: #ibmcloud_account_domain_cert_add}

Aggiunge un certificato al dominio specificato nell'organizzazione corrente.
```
ibmcloud account domain-cert-add DOMINIO -k FILE_CHIAVE PRIVATA -c FILE_CERTIFICATO [-p PASSWORD] [-i FILE_CERTIFICATO_INTERMEDIO] [-t FILE_TRUSTSTORE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio a cui viene aggiunto il certificato.</dd>
   <dt>-k <i>FILE_CHIAVE PRIVATA</i> (obbligatorio)</dt>
   <dd>Il percorso del file della chiave privata.</dd>
   <dt>-c <i>FILE_CERTIFICATO</i> (obbligatorio)</dt>
   <dd>Il percorso del file del certificato.</dd>
   <dt>-p <i>PASSWORD</i> (facoltativo)</dt>
   <dd>La password per il certificato.</dd>
   <dt>-i <i>FILE_CERTIFICATO_INTERMEDIO</i> (facoltativo)</dt>
   <dd>Il percorso del file di certificato intermedio.</dd>
   <dt>-t <i>FILE_TRUSTSTORE</i> (facoltativo)</dt>
   <dd>Il file truststore.</dd>
   </dl>


<strong>Esempi</strong>:

Aggiunge un certificato al dominio `ibmcxo-eventconnect.com`:
```
ibmcloud account domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud account domain-cert-remove
{: #ibmcloud_account_domain_cert_remove}

Rimuove un certificato dal dominio specificato nell'organizzazione corrente.
```
ibmcloud account domain-cert-remove DOMINIO [-f]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio da cui rimuovere il certificato.</dd>
   <dt>-f (facoltativo)</dt>
   <dd>Forza l'eliminazione senza conferma.</dd>
   </dl>