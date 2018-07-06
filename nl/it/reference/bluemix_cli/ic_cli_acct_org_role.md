---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi della CLI per gestire account, organizzazioni e ruoli
 {: #ibmcloud_commands_account}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire account, organizzazioni, spazi e ruoli.">
<caption>Tabella 1. Comandi per gestire account, organizzazioni, spazi e ruoli</caption>
 <thead>
 <th colspan="5">Comandi per gestire account, organizzazioni, spazi e ruoli</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud account orgs](ic_cli_acct_org_role.html#ibmcloud_account_orgs)</td>
 <td>[ibmcloud account org](ic_cli_acct_org_role.html#ibmcloud_account_org)</td>
 <td>[ibmcloud account org-create](ic_cli_acct_org_role.html#ibmcloud_account_org_create)</td>
 <td>[ibmcloud account org-replicate](ic_cli_acct_org_role.html#ibmcloud_account_org_replicate)</td>
 <td>[ibmcloud account org-rename](ic_cli_acct_org_role.html#ibmcloud_account_org_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud account spaces](ic_cli_acct_org_role.html#ibmcloud_account_spaces)</td>
 <td>[ibmcloud account space](ic_cli_acct_org_role.html#ibmcloud_account_space)</td>
 <td>[ibmcloud account space-create](ic_cli_acct_org_role.html#ibmcloud_account_space_create)</td>
 <td>[ibmcloud account space-rename](ic_cli_acct_org_role.html#ibmcloud_account_space_rename)</td>
 <td>[ibmcloud account space-delete](ic_cli_acct_org_role.html#ibmcloud_account_space_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-users](ic_cli_acct_org_role.html#ibmcloud_account_org_users)</td>
 <td>[ibmcloud account org-user-add](ic_cli_acct_org_role.html#ibmcloud_account_org_user_add)</td>
 <td>[ibmcloud account org-user-remove](ic_cli_acct_org_role.html#ibmcloud_account_org_user_remove)</td>
 <td>[ibmcloud account org-roles](ic_cli_acct_org_role.html#ibmcloud_account_org_roles)</td>
 <td>[ibmcloud account org-role-set](ic_cli_acct_org_role.html#ibmcloud_account_org_role_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud account org-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_org_role_unset)</td>
 <td>[ibmcloud account space-users](ic_cli_acct_org_role.html#ibmcloud_account_space_users)</td>
 <td>[ibmcloud account space-roles](ic_cli_acct_org_role.html#ibmcloud_account_space_roles)</td>
 <td>[ibmcloud account space-role-set](ic_cli_acct_org_role.html#ibmcloud_account_space_role_set)</td>
 <td>[ibmcloud account space-role-unset](ic_cli_acct_org_role.html#ibmcloud_account_space_role_unset)</td>
</tr>
 <td>[ibmcloud account list](ic_cli_acct_org_role.html#ibmcloud_account_list)</td>
 <td>[ibmcloud account org-account](ic_cli_acct_org_role.html#ibmcloud_account_org_account)</td>
 <td>[ibmcloud account users](ic_cli_acct_org_role.html#ibmcloud_account_users)</td>
 <td>[ibmcloud account user-remove](ic_cli_acct_org_role.html#ibmcloud_account_user_remove)</td>
 <td>[ibmcloud account user-invite](ic_cli_acct_org_role.html#ibmcloud_account_user_invite)</td>
 </tr>
 <tr>
  <td>[ibmcloud account user-reinvite](ic_cli_acct_org_role.html#ibmcloud_account_user_reinvite)</td>
  <td>[ibmcloud iam access-groups](ic_cli_acct_org_role.html#ibmcloud_iam_access-groups)</td>
  <td>[ibmcloud iam access-group](ic_cli_acct_org_role.html#ibmcloud_iam_access-group)</td>
  <td>[ibmcloud iam access-group-create](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-create)</td>
  <td>[ibmcloud iam access-group-update](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-update)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-delete)</td>
  <td>[ibmcloud iam access-group-users](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-users)</td>
  <td>[ibmcloud iam access-group-user-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-add)</td>
  <td>[ibmcloud iam access-group-user-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-remove)</td>
  <td>[ibmcloud iam access-group-user-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-user-purge)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-service-ids](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-ids)</td>
  <td>[ibmcloud iam access-group-service-id-add](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-add)</td>
  <td>[ibmcloud iam access-group-service-id-remove](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-remove)</td>
  <td>[ibmcloud iam access-group-service-id-purge](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-service-id-purge)</td>
  <td>[ibmcloud iam access-group-policies](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policies)</td>
</tr>
<tr>
  <td>[ibmcloud iam access-group-policy](ic_cli_acct_org_role.html#ibmcloud_iam_access-group-policy)</td>
  <td>[ibmcloud iam access-group-policy-create](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_create)</td>
  <td>[ibmcloud iam access-group-policy-update](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_update)</td>
  <td>[ibmcloud iam access-group-policy-delete](ic_cli_acct_org_role.html#ibmcloud_iam_access_group_policy_delete)</td>
 </tr>
 </tbody>
 </table>
 
 ### ibmcloud account orgs
{: #ibmcloud_account_orgs}

Elenca tutte le organizzazioni

```
ibmcloud account orgs [-r REGIONE] [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-r <i>REGIONE</i> (facoltativo)</dt>
   <dd>Regione per cui vengono visualizzare le informazioni sull'organizzazione. Se impostato su 'all', vengono elencate tutte le organizzazioni in tutte le regioni.</dd>
   <dt>--guid (facoltativo)</dt>
   <dd>Visualizza il GUID delle organizzazioni.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutte le organizzazioni della regione: `us-south` con il GUID visualizzato

```
ibmcloud account orgs -r us-south --guid
```

### ibmcloud account org
{: #ibmcloud_account_org}

Visualizza le informazioni per l'organizzazione specificata.

```
ibmcloud account org NOME_ORGANIZZAZIONE [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>--guid (facoltativo)</dt>
   <dd>Visualizza il GUID dell'organizzazione.</dd>
   </dl>

<strong>Esempi</strong>:

Mostra le informazioni dell'organizzazione `IBM` con il GUID visualizzato

```
ibmcloud account org IBM --guid
```

### ibmcloud account org-create
{: #ibmcloud_account_org_create}

Crea una nuova organizzazione. Questa operazione può essere eseguita solo dal proprietario dell'account.

```
ibmcloud account org-create NOME_ORGANIZZAZIONE [-f]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione in fase di creazione.</dd>
   <dt>-f</dt>
   <dd>Forza la creazione senza conferma.</dd>
   </dl>

<strong>Esempi</strong>:

Crea un'organizzazione denominata `IBM`.

```
ibmcloud account org-create IBM
```

### ibmcloud account org-replicate
{: #ibmcloud_account_org_replicate}

Replica un'organizzazione dalla regione corrente in un'altra regione.

```
ibmcloud account org-replicate NOME_ORGANIZZAZIONE NOME_REGIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione esistente che deve essere replicata.</dd>
   <dt>NOME_REGIONE (obbligatorio)</dt>
   <dd>Il nome della regione che ospita l'organizzazione replicata.</dd>
   </dl>

<strong>Esempi</strong>:

Replica l'organizzazione `myorg` nella regione `eu-gb`:

```
ibmcloud account org-replicate myorg eu-gb
```

### ibmcloud account org-rename
{: #ibmcloud_account_org_rename}

Rinomina un'organizzazione. Questa operazione può essere eseguita solo da un gestore organizzazione.

```
ibmcloud account org-rename VECCHIO_NOME_ORGANIZZAZIONE NUOVO_NOME_ORGANIZZAZIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE_PRECEDENTE (obbligatorio)</dt>
   <dd>Il vecchio nome dell'organizzazione da rinominare.</dd>
   <dt>NUOVO_NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nuovo nome con cui viene rinominata l'organizzazione.</dd>
   </dl>

### ibmcloud account spaces
{: #ibmcloud_account_spaces}

Elenca tutti gli spazi

```
ibmcloud account spaces [-o NOME_ORGANIZZAZIONE] [-r NOME-REGIONE]
```

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-o</dt>
   <dd>Nome dell'organizzazione. Elenca gli spazi nell'organizzazione specificata. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>-r</dt>
   <dd>Nome della regione. Elenca gli spazi nella regione specificata. Se non specificato, il valore predefinito è la regione corrente.</dd>
   </dl>

### ibmcloud account space
{: #ibmcloud_account_space}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/space.html){: new_window}.

### ibmcloud account space-create
{: #ibmcloud_account_space_create}

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window}.

### ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf rename-space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window}.

### ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-space ![Icona link esterno](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window}.

### ibmcloud account org-users
{: #ibmcloud_account_org_users}

Visualizza gli utenti nell'organizzazione specificata per il ruolo.

```
ibmcloud account org-users NOME_ORGANIZZAZIONE [-a]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
<dd>Il nome dell'organizzazione.</dd>
<dt>-a (facoltativo)</dt>
<dd>Elenca tutti gli utenti dell'organizzazione specificata, non raggruppati per ruolo.</dd>
</dl>

### ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Aggiunge un utente nell'organizzazione (è richiesto il gestore organizzazione).

```
 ibmcloud account org-user-add NOME_UTENTE ORGANIZZAZIONE
```

### ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Rimuove un utente dall'organizzazione (gestore organizzazione o solo l'utente)

```
   ibmcloud account org-user-remove NOME_UTENTE ORGANIZZAZIONE [-f, --force]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--force, -f</dt>
<dd>Forza l'eliminazione senza conferma.</dd>
</dl>

### ibmcloud account org-roles
{: #ibmcloud_account_org_roles}

Ottiene tutti i ruoli organizzazione dell'utente corrente

```
ibmcloud account org-roles [-u ID_UTENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID utente. Se non specificato, il valore predefinito è l'utente corrente.</dd>
  </dl>

### ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assegna un ruolo dell'organizzazione ad un utente. Questa operazione può essere eseguita solo da un gestore organizzazione.

```
ibmcloud account org-role-set NOME_UTENTE NOME_ORGANIZZAZIONE RUOLO_ORGANIZZAZIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di assegnazione.</dd>
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
  </dl>

<strong>Esempi</strong>:

Assegna l'utente `Mary` all'organizzazione `IBM` con il ruolo `OrgManager`:

```
ibmcloud account org-role-set Mary IBM OrgManager
```
<!-- Begin Staging URL vs Prod URL -->
**Nota**: puoi impostare i ruoli org/space utilizzando la CLI ma, se vuoi impostare le altre autorizzazioni, devi utilizzare l'IU. Per ulteriori dettagli, vedi [Assegnazione dell'accesso utente](/docs/iam/assignaccess.html#assignaccess).
<!-- Begin Staging URL vs Prod URL -->

### ibmcloud account org-role-unset
{: #ibmcloud_account_org_role_unset}

Rimuove un ruolo dell'organizzazione da un utente. Questa operazione può essere eseguita solo da un gestore organizzazione.

```
ibmcloud account org-role-unset NOME_UTENTE NOME_ORGANIZZAZIONE RUOLO_ORGANIZZAZIONE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di eliminazione.</dd>
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
    </dl>

<strong>Esempi</strong>:

Rimuove l'utente `Mary` dall'organizzazione `IBM` con il ruolo `OrgManager`:

```
ibmcloud account org-role-unset Mary IBM OrgManager
```

### ibmcloud account space-users
{: #ibmcloud_account_space_users}

Visualizza gli utenti nello spazio specificato per il ruolo.

```
ibmcloud account space-users NOME_ORGANIZZAZIONE NOME_SPAZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio.</dd>
   </dl>

### ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assegna un ruolo dello spazio ad un utente. Questa operazione può essere eseguita solo da un gestore spazio.

```
ibmcloud account space-role-set NOME_UTENTE NOME_ORGANIZZAZIONE NOME_SPAZIO RUOLO_SPAZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di assegnazione.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio a cui è assegnato l'utente.</dd>
   <dt>RUOLO_SPAZIO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio a cui è assegnato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per un dato spazio.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
    </dl>

<strong>Esempi</strong>:

Assegna l'utente `Mary` all'organizzazione `IBM` e allo spazio `Cloud` con il ruolo `SpaceManager`:

```
ibmcloud account space-role-set Mary IBM Cloud SpaceManager
```

### ibmcloud account space-role-unset
{: #ibmcloud_account_space_role_unset}

Rimuove un ruolo dello spazio da un utente. Questa operazione può essere eseguita solo da un gestore spazio.

```
ibmcloud account space-role-unset NOME_UTENTE NOME_ORGANIZZAZIONE NOME_SPAZIO RUOLO_SPAZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente in fase di eliminazione.</dd>
   <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>NOME_SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio da cui viene eliminato l'utente.</dd>
   <dt>RUOLO_SPAZIO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per un dato spazio.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
    </dl>


<strong>Esempi</strong>:

Rimuove l'utente `Mary` dall'organizzazione `IBM` e dall spazio `Cloud` con il ruolo `SpaceManager`:

```
ibmcloud account space-role-unset Mary IBM Cloud SpaceManager
```

### ibmcloud account list
{: #ibmcloud_account_list}

Elenca tutti gli account dell'utente corrente

```
ibmcloud account list
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

### ibmcloud account org-account
{: #ibmcloud_account_org_account}

Visualizza l'account dell'organizzazione specificata (utente dell'organizzazione obbligatorio)

```
ibmcloud account org-account NOME_ORGANIZZAZIONE [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--guid (facoltativo)</dt>
  <dd>Visualizza solo l'ID account</dd>
</dl>

### ibmcloud account users
{: #ibmcloud_account_users}

Visualizza gli utenti associati con l'account. Questa operazione può essere eseguita solo dal proprietario dell'account.

```
ibmcloud account users
```

### ibmcloud account user-remove
{: #ibmcloud_account_user_remove}

Rimuovi un utente da un account (solo il proprietario dell'account)

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

### ibmcloud account user-invite
{: #ibmcloud_account_user_invite}

Invita un utente nell'account

```
ibmcloud account user-invite EMAIL_UTENTE [-o ORG [--org-role RUOLO_ORG] [-s SPAZIO, --space-role RUOLO_SPAZIO]]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'email dell'utente invitato.</dd>
   <dt>-o ORG</dt>
   <dd>Organizzazione a cui invitare l'utente</dd>
   <dt>--org-role RUOLO_ORG</dt>
   <dd>Ruolo organizzazione. Gli input validi sono: OrgManager, BillingManager, OrgAuditor e OrgUser. Se omesso, verrà impostato il ruolo OrgUser.</dd>
   <dt>-s SPAZIO</dt>
   <dd>Spazio a cui invitare l'utente</dd>
   <dt>--space-role RUOLO_SPAZIO</dt>
   <dd>Ruolo spazio. Gli input validi sono: SpaceManager, SpaceDeveloper e SpaceAuditor.</dd>
</dl>

### ibmcloud account user-reinvite
{: #ibmcloud_account_user_reinvite}

Invia di nuovo l'invito a un utente (amministratore dell'account)

```
ibmcloud account user-reinvite EMAIL_UTENTE
```
<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'e-mail dell'utente che viene nuovamente invitato.</dd>
</dl>

### ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Elenca i gruppi di accesso nell'account corrente

```
ibmcloud iam access-groups [-u NOME_UTENTE | -s NOME_ID_SERVIZIO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-u</dt>
  <dd>Elenca i gruppi di accesso a cui appartiene l'utente. Questo indicatore è esclusivo per '-s'.</dd>
  <dt>-s</dt>
  <dd>Elenca i gruppi di accesso a cui appartienel'ID del servizio. Questo indicatore è esclusivo per '-u'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i gruppi di accesso:

```
ibmcloud iam access-groups
```

### ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Mostra i dettagli di un gruppo di accesso

```
ibmcloud iam access-group NOME_GRUPPO [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-id</dt>
  <dd>Mostra solo l'ID</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli del gruppo di accesso `example_group`:

```
ibmcloud iam access-group example_group
```

### ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Crea un gruppo di accesso

```
ibmcloud iam access-group-create NOME_GRUPPO [-d, --description DESCRIZIONE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Descrizione del gruppo di accesso</dd>
</dl>

<strong>Esempi</strong>:

Crea un gruppo di accesso `example_group`:

```
ibmcloud iam access-group-create example_group -d "example access group"
```

### ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Aggiorna un gruppo di accesso

```
ibmcloud iam access-group-update NOME_GRUPPO [-n, --name NUOVO_NOME] [-d, --description NUOVA_DESCRIZIONE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del gruppo di accesso</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Ridenomina il gruppo di accesso `example_group` con `hello_world_group`:

```
ibmcloud iam access-group-update example_group --name "hello_world_group"
```

### ibmcloud iam access-group-delete
{: #ibmcloud_iam_access_group_delete}

Elimina un gruppo di accesso

```
ibmcloud iam access-group-delete NOME_GRUPPO [-f, --force] [-r, --recursive]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
  <dt>-r, --recursive</dt>
  <dd>Elimina il gruppo di accesso e i relativi membri</dd>
</dl>

<strong>Esempi</strong>:

Elimina il gruppo di accesso `example_group`:

```
ibmcloud iam access-group-delete example_group --force
```

### ibmcloud iam access-group-users
{: #ibmcloud_iam_access_group_users}

Elenca gli utenti in un gruppo di accesso

```
ibmcloud iam access-group-users NOME_GRUPPO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutti gli utenti nel gruppo di accesso `example_group`:

```
ibmcloud iam access-group-users example_group
```

### ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Aggiunge gli utenti a un gruppo di accesso

```
ibmcloud iam access-group-user-add NOME_GRUPPO NOME_UTENTE [NOME_UTENTE2...]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiunge l'utente `name@example.com` al gruppo di accesso `example_group`:

```
ibmcloud iam access group-user-add example_group name@example.com
```

### ibmcloud iam access-group-user-remove
{: #ibmcloud_iam_access_group_user_remove}

Rimuove un utente da un gruppo di accesso

```
ibmcloud iam access-group-user-remove NOME_GRUPPO NOME_UTENTE
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Rimuove l'utente `name@example.com` dal gruppo di accesso `example_group`:

```
ibmcloud iam access-group-user-remove example_group name@example.com
```

### ibmcloud iam access-group-user-purge
{: #ibmcloud_iam_access_group_user_purge}

Rimuove l'utente da tutti i gruppi di accesso

```
ibmcloud iam access-group-user-purge NOME_UTENTE [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rimuove l'utente `name@example.com` da tutti i gruppi di accesso:

```
ibmcloud iam access-group-user-purge name@example.com -f
```

### ibmcloud iam access-group-service-ids
{: #ibmcloud_iam_access_group_service_ids}

Elenca gli ID del servizio in un gruppo di accesso

```
ibmcloud iam access-group-service-ids NOME_GRUPPO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutti gli ID del servizio nel gruppo di accesso `example_group`:

```
ibmcloud iam access-group-service-ids example_group
```

### ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Aggiungi l'ID del servizio a un gruppo di accesso

```
ibmcloud iam access-group-service-id-add NOME_GRUPPO NOME_ID_SERVIZIO [NOME_ID_SERVIZIO2...]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiunge l'ID del servizio `example-service` al gruppo di accesso `example_group`:

```
ibmcloud iam access-group-service-id-add example_group example-service
```

### ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Rimuove un utente da un ID del servizio di accesso

```
ibmcloud iam access-group-service-id-remove NOME_GRUPPO NOME_ID_SERVIZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Rimuove l'ID del servizio `example-service` dal gruppo di accesso `example_group`:

```
ibmcloud iam access-group-service-id-remove example_group example-service
```

### ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Rimuove l'ID del servizio da tutti i gruppi di accesso

```
ibmcloud iam access-group-service-id-purge NOME_ID_SERVIZIO [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rimuove l'ID del servizio `example-service` da tutti i gruppi di accesso:

```
ibmcloud iam access-group-service-id-purge example --force
```

### ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Elenca le politiche di un gruppo di accesso

```
ibmcloud iam access-group-policies NOME_GRUPPO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutte le politiche del gruppo di accesso `example_group`:

```
ibmcloud iam access-group-policies example_group
```

### ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Mostra i dettagli di una politica del gruppo di accesso

```
ibmcloud iam access-group-policy NOME_GRUPPO ID_POLITICA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della politica `51b9717e-76b0-4f6a-bda7-b8132431f926` del gruppo di accesso `example_group`:

```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

### ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Crea una politica del gruppo di accesso

```
ibmcloud iam access-group-policy-create NOME_GRUPPO {--file @FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica</dd>
  <dt>-roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Crea una politica del gruppo di accesso da un file JSON:

```
ibmcloud iam access-group-policy-create example_group -f @policy.json
```

Assegna a `example_group` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`:
```
ibmcloud iam access-group-policy-create example_group --roles Administrator --service-name sample-service
```

Assegna a `example_group` il ruolo `Editor` per la risorsa `key123` dell'istanza `sample-service` con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`:
```
ibmcloud iam access-group-policy-create example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Assegna a `example_group` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Assegna a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-name sample-resource-group
```

Assegna a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-create example_group --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-update
{: #ibmcloud_iam_access_group_policy_update}

Aggiorna una politica del gruppo di accesso

```
ibmcloud iam access-group-policy-update ID_POLITICA_NOME_GRUPPO {--file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica</dd>
  <dt>--roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica del gruppo di accesso con quella nel file JSON della politica:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 -f @policy.json
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Administrator --service-name sample-service
```

Aggiorna la politica del gruppo di accesso per assegnare a `example_group` il ruolo `Editor` per la risorsa `key123` dell'istanza `sample-service` con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`.
```
ibmcloud iam access-group-policy-update example_group --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-name sample-resource-group
```

Aggiorna la politica del gruppo di accesso per fornire a `example_group` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:
```
ibmcloud iam access-group-policy-update example_group b8638ceb-5c4d-4d58-ae06-7ad95a10c4d4 --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

### ibmcloud iam access-group-policy-delete
{: #ibmcloud_iam_access_group_policy_delete}

Elimina a una politica del gruppo di accesso

```
ibmcloud iam access-group-policy-delete NOME_GRUPPO ID_POLITICA [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina la politica `51b9717e-76b0-4f6a-bda7-b8132431f926` del gruppo di accesso `example_group`:
```
ibmcloud iam access-group-policy-delete example_group 51b9717e-76b0-4f6a-bda7-b8132431f926 -f
```
