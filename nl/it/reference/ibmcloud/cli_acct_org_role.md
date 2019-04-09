---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: ibmcloud account, managing accounts, managing users, managing orgs, cloud foundry, account space, account, commands, account update, add certificate, remove certificate

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
   <dd>Visualizza il guid delle organizzazioni. Questa opzione è esclusiva con '--output'.</dd>
   <dt>--output FORMATO</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--guid'.</dd>
   <dt>-c ID_ACCOUNT</dt>
   <dd>ID account. Elenca le organizzazioni nell'account fornito. Se non specificato, il valore predefinito è l'account corrente. Se impostato su 'all', elenca le organizzazioni in tutti gli account. Questa opzione è esclusiva con '-u'.</dd>
   <dt>-u PROPRIETARIO_ACCOUNT</dt>
   <dd>Nome proprietario account. Elenca le organizzazioni negli account appartenenti all'utente fornito. Se non specificato, il valore predefinito è l'account corrente. Se impostato su 'all', elenca le organizzazioni in tutti gli account. Questa opzione è esclusiva con '-c'.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutte le organizzazioni della regione: `us-south` con il GUID visualizzato

```
ibmcloud account orgs -r us-south --guid
```

Elenca tutte le organizzazioni nel formato JSON

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
   <dd>Nome della regione. Se non specificato, il valore predefinito è la regione corrente. Se impostato su 'all', vengono elencate le organizzazioni con il nome indicato di tutte le regioni.</dd>
   <dt>--guid</dt>
   <dd>Richiama e visualizza il guid dell'organizzazione specificata. Tutti gli altri output per l'organizzazione vengono eliminati. Questa opzione è esclusiva con '--output'.</dd>
   <dt>--output REGIONE</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--guid'.</dd>
   </dl>

<strong>Esempi</strong>:

Mostra le informazioni dell'organizzazione `IBM` con il GUID visualizzato.

```
ibmcloud account org IBM --guid
```

## ibmcloud account org-create
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

## ibmcloud account org-replicate
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

## ibmcloud account org-rename
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

## ibmcloud account spaces
{: #ibmcloud_account_spaces}

Elenca tutti gli spazi di account.

```
ibmcloud account spaces [-o NOME_ORGANIZZAZIONE] [-r NOME-REGIONE] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>-o NOME_ORGANIZZAZIONE</dt>
   <dd>Nome dell'organizzazione. Elenca gli spazi nell'organizzazione specificata. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>-r NOME-REGIONE</dt>
   <dd>Nome della regione. Elenca gli spazi nella regione specificata. Se non specificato, il valore predefinito è la regione corrente.</dd>
   <dt>--output FORMATO</dt>
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
   <dd>Richiama e visualizza il guid dello spazio specificato. Tutti gli altri output per lo spazio vengono eliminati. Questa opzione è esclusiva con '--output'.</dd>
   <dt>--output FORMATO</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON. Tutti gli altri output per lo spazio vengono eliminati. Questa opzione è esclusiva con '--guid'.</dd>
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

Questo comando ha la stessa funzione e le stesse opzioni del comando [cf create-space](http://cli.cloudfoundry.org/en-US/cf/create-space.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## ibmcloud account space-rename
{: #ibmcloud_account_space_rename}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf rename-space](http://cli.cloudfoundry.org/en-US/cf/rename-space.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## ibmcloud account space-delete
{: #ibmcloud_account_space_delete}


Questo comando ha la stessa funzione e le stesse opzioni del comando [cf delete-space](http://cli.cloudfoundry.org/en-US/cf/delete-space.html){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").

## ibmcloud account org-users
{: #ibmcloud_account_org_users}

Visualizza gli utenti nell'organizzazione specificata per il ruolo.

```
ibmcloud account org-users ORG_NAME [-a] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
<dd>Il nome dell'organizzazione.</dd>
<dt>-a (facoltativo)</dt>
<dd>Elenca tutti gli utenti dell'organizzazione specificata, non raggruppati per ruolo.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud account org-user-add
{: #ibmcloud_account_org_user_add}

Aggiunge un utente nell'organizzazione (è richiesto il gestore organizzazione).

```
 ibmcloud account org-user-add NOME_UTENTE ORGANIZZAZIONE
```

## ibmcloud account org-user-remove
{: #ibmcloud_account_org_user_remove}

Rimuove un utente dall'organizzazione (gestore organizzazione o solo l'utente).

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
ibmcloud account org-roles [-u ID_UTENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>-u</dt>
   <dd>ID utente. Se non specificato, il valore predefinito è l'utente corrente.</dd>
  </dl>

## ibmcloud account org-role-set
{: #ibmcloud_account_org_role_set}

Assegna un ruolo dell'organizzazione a un utente. Questa operazione può essere eseguita solo da un gestore organizzazione.

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
Puoi impostare i ruoli organizzazione/spazio utilizzando la CLI ma, se vuoi impostare le altre autorizzazioni, devi utilizzare l'IU. Per ulteriori dettagli, vedi [Gestione dell'accesso alle risorse](/docs/iam/mngiam.html#iammanidaccser).
{: note}
<!-- Begin Staging URL vs Prod URL -->

## ibmcloud account org-role-unset
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

## ibmcloud account space-users
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

## ibmcloud account space-role-set
{: #ibmcloud_account_space_role_set}

Assegna un ruolo dello spazio a un utente. Questa operazione può essere eseguita solo da un gestore spazio.

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

## ibmcloud account space-role-unset
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

## ibmcloud account list
{: #ibmcloud_account_list}

Elenca tutti gli account dell'utente corrente

```
ibmcloud account list
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

## ibmcloud account org-account
{: #ibmcloud_account_org_account}

Visualizza l'account dell'organizzazione specificata (utente dell'organizzazione obbligatorio).

```
ibmcloud account org-account NOME_ORGANIZZAZIONE [--guid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--guid (facoltativo)</dt>
  <dd>Visualizza solo l'ID account</dd>
</dl>

## ibmcloud account show
{: #ibmcloud_account_show}

Mostra i dettagli dell'account

```
ibmcloud account show
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

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

Aggiorna uno specifico account.

```
ibmcloud account update (--service-endpoint-enable true | false)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--service-endpoint-enable true | false</dt>
  <dd>Abilita o disabilita la connettività agli endpoint del servizio per un account Softlayer.</dd>
</dl>

<strong>Esempi</strong>:

Abilita la connettività agli endpoint del servizio per l'account corrente:

```
ibmcloud account update --service-endpoint-enable true
```

## ibmcloud account users
{: #ibmcloud_account_users}

Visualizza gli utenti associati all'account. Questa operazione può essere eseguita solo dal proprietario dell'account.

```
ibmcloud account users
```

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
   <dd>Ruolo organizzazione. Gli input validi sono: OrgManager, BillingManager, OrgAuditor e OrgUser. Se omesso, viene impostato il ruolo OrgUser.</dd>
   <dt>-s SPAZIO</dt>
   <dd>Spazio a cui invitare l'utente</dd>
   <dt>--space-role RUOLO_SPAZIO</dt>
   <dd>Ruolo spazio. Gli input validi sono: SpaceManager, SpaceDeveloper e SpaceAuditor.</dd>
</dl>

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
   <dd>L'email dell'utente invitato nuovamente.</dd>
</dl>

## ibmcloud app domain-cert
{: #accounts-list-domain-cert}

Elenca le informazioni sul certificato di un dominio.

```
ibmcloud app domain-cert NOME_DOMINIO
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
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #accounts-add-domain-cert}

Aggiunge un certificato al dominio specificato nell'organizzazione corrente.

```
ibmcloud app domain-cert-add DOMINIO -k FILE_CHIAVE PRIVATA -c FILE_CERTIFICATO [-p PASSWORD] [-i FILE_CERTIFICATO_INTERMEDIO] [-t FILE_TRUSTSTORE]
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
   <dt>-i <i>FILE_CERTIFICATO_INTERMEDIO</i> (optional)</dt>
   <dd>Il percorso del file di certificato intermedio.</dd>
   <dt>-t <i>FILE_TRUSTSTORE</i> (facoltativo)</dt>
   <dd>Il file truststore.</dd>
   </dl>


<strong>Esempi</strong>:

Aggiunge un certificato al dominio `ibmcxo-eventconnect.com`:

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #accounts-remove-domain-cert}

Rimuove un certificato dal dominio specificato nell'organizzazione corrente.

```
ibmcloud app domain-cert-remove DOMINIO [-f]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>DOMINIO (obbligatorio)</dt>
   <dd>Il dominio da cui rimuovere il certificato.</dd>
   <dt>-f (facoltativo)</dt>
   <dd>Forza l'eliminazione senza conferma.</dd>
   </dl>
