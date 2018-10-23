---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CFEE (Cloud Foundry Enterprise Environment)
{: #ibmcloud_commands_cfee}

Con CFEE ({{site.data.keyword.cfee_full}}) puoi istanziare più piattaforme Cloud Foundry isolate e di livello aziendale su richiesta. Le istanze del servizio IBM Cloud Foundry Enterprise vengono eseguite all'interno del tuo account in IBM Cloud. L'ambiente viene distribuito su hardware isolato (cluster Kubernetes). Hai un completo controllo sull'ambiente, compresi il controllo degli accessi, la capacità, gli aggiornamenti delle versioni e l'utilizzo e il monitoraggio delle risorse.

Utilizza i seguenti comandi per gestire i ruoli, gli utenti, gli spazi, le organizzazioni e gli ambienti CFEE.
{: shortdesc}

<table summary="Gestisci i Cloud Foundry Enterprise Environment (sperimentale)">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments
](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 <td>[ibmcloud cfee orgs](cli_cfee.html#ibmcloud_cfee_orgs)</td>
 <td>[ibmcloud cfee org](cli_cfee.html#ibmcloud_cfee_org)</td>
 <td>[ibmcloud cfee org-create](cli_cfee.html#ibmcloud_cfee_org_create)</td>
 </tr>
 <tr>
 <td>[ibmcloud cfee org-delete](cli_cfee.html#ibmcloud_cfee_org_delete)</td>
 <td>[ibmcloud cfee org-users](cli_cfee.html#ibmcloud_cfee_org_users)</td>
 <td>[ibmcloud cfee org-role-set](cli_cfee.html#ibmcloud_cfee_org_role_set)</td>
 <td>[ibmcloud cfee org-role-unset](cli_cfee.html#ibmcloud_cfee_org_role_unset)</td>
 <td>[ibmcloud cfee spaces](cli_cfee.html#ibmcloud_cfee_spaces)</td>
 </tr>
<tr>
 <td>[ibmcloud cfee space](cli_cfee.html#ibmcloud_cfee_space)</td>
 <td>[ibmcloud cfee space-create](cli_cfee.html#ibmcloud_cfee_space_create)</td>
 <td>[ibmcloud cfee space-rename](cli_cfee.html#ibmcloud_cfee_space_rename)</td>
 <td>[ibmcloud cfee space-delete](cli_cfee.html#ibmcloud_cfee_space_delete)</td>
 <td>[ibmcloud cfee space-role-set](cli_cfee.html#ibmcloud_cfee_space_role_set)</td>
 </tr>
 <tr>

 <td>[ibmcloud cfee space-role-unset](cli_cfee.html#ibmcloud_cfee_space_role_unset)</td>
 <td>[ibmcloud cfee space-roles](cli_cfee.html#ibmcloud_cfee_space_roles)</td>
 <td>[ibmcloud cfee space-users](cli_cfee.html#ibmcloud_cfee_space_users)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Elenca gli ambienti CFEE.

```
ibmcloud cfee environments
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostra i dettagli di un ambiente CFEE

```
ibmcloud cfee environment NOME [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME (obbligatorio)</dt>
   <dd>Il nome dell'ambiente da visualizzare.</dd>
   <dt>--id</dt>
   <dd>Mostra solo l'ID</dd>
  </dl>

<strong>Esempi</strong>:

Mostra i dettagli di un ambiente CFEE `env_example`:

```
ibmcloud cfee environment env_example
```

Mostra l'ID di un ambiente CFEE `env_example`:

```
ibmcloud cfee environment env_example --id
```

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Elenca tutte le organizzazioni

```
ibmcloud cfee orgs [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Elenca tutte le organizzazioni:

```
ibmcloud cfee orgs
```

Elenca tutte le organizzazioni dell'ambiente CFEE `env_example`:

```
ibmcloud cfee orgs --env env_example
```

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Visualizza i dettagli di un'organizzazione

```
ibmcloud cfee org ORG [--guid] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>--guid</dt>
   <dd>Visualizza solo il GUID dell'organizzazione, tutti gli altri output per l'organizzazione vengono eliminati</dd>
  </dl>

<strong>Esempi</strong>:

Mostra i dettagli di un'organizzazione CFEE `org_example`:

```
ibmcloud cfee org org_example
```

Visualizza i dettagli di un'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:

```
ibmcloud cfee org org_example --env env_example
```

Mostra il GUID di un'organizzazione CFEE `org_example`:

```
ibmcloud cfee org org_example --guid
```

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Crea un'organizzazione

```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione in fase di creazione.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>-q, --quota QUOTA</dt>
   <dd>La quota da assegnare all'organizzazione appena creata (utilizza la quota predefinita se non specificata)</dd>
  </dl>

<strong>Esempi</strong>:

Crea un'organizzazione CFEE `org_example`:

```
ibmcloud cfee org-create org_example
```

Crea un'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:

```
ibmcloud cfee org-create org_example --env env_example
```

Crea un'organizzazione CFEE `org_example` con la quota `quote_example`:

```
ibmcloud cfee org org-create org_example --quota quota_example
```

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Elimina un'organizzazione

```
ibmcloud cfee org-delete ORG [-f, --force] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione in fase di eliminazione.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'eliminazione senza conferma</dd>
  </dl>

<strong>Esempi</strong>:

Elimina un'organizzazione CFEE `org_example`:

```
ibmcloud cfee org-delete org_example
```

Elimina un'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:

```
ibmcloud cfee org-delete org_example --env env_example
```

Elimina un'organizzazione CFEE `org_example` senza conferma:

```
ibmcloud cfee org org-delete org_example -f
```

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Visualizza gli utenti nell'organizzazione specificata in base al ruolo

```
ibmcloud cfee org-users ORG [-a, --all] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>-a, --all</dt>
   <dd>Elenca tutti gli utenti nell'organizzazione specificata</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Visualizza gli utenti nell'organizzazione CFEE `org_example`:

```
ibmcloud cfee org-users org_example
```

Visualizza gli utenti nell'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:

```
ibmcloud cfee org-users org_example --env env_example
```

Elenca tutti gli utenti nell'organizzazione CFEE `org_example`:

```
ibmcloud cfee org-users org_example -a
```

## ibmcloud cfee org-role-set
{: #ibmcloud_cfee_org_role_set}

Assegna un ruolo dell'organizzazione a un utente (è richiesto un gestore organizzazione)

```
ibmcloud cfee org-role-set EMAIL_UTENTE ORG RUOLO [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'e-mail dell'utente che viene assegnata.</dd>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>RUOLO (obbligatorio)</dt>
   <dd>Il nome del ruolo organizzazione a cui viene assegnato l'utente. Ad esempio:
   <ul>
   <li>OrgManager: questo ruolo può invitare e gestire utenti, selezionare e modificare piani e impostare limiti di spesa.</li>
   <li>BillingManager: questo ruolo può creare e gestire l'account di fatturazione e le informazioni sul pagamento.</li>
   <li>OrgAuditor: questo ruolo dispone di un accesso in sola lettura a report e informazioni sull'organizzazione.</li>
   </ul>
   </dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Assegna il ruolo `BillingManager` all'utente `test@exmaple.com` nell'organizzazione `org_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager
```

Assegna il ruolo `BillingManager` all'utente `test@exmaple.com` nell'organizzazione `org_example` dell'ambiente CFEE `env_example`:

```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Rimuovi un ruolo organizzazione da un utente (gestore dell'organizzazione o solo l'utente)

```
ibmcloud cfee org-role-unset EMAIL_UTENTE ORG RUOLO [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'e-mail dell'utente che viene rimosso.</dd>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>RUOLO (obbligatorio)</dt>
   <dd>Il nome del ruolo organizzazione da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>OrgManager: questo ruolo può invitare e gestire utenti, selezionare e modificare piani e impostare limiti di spesa.</li>
   <li>BillingManager: questo ruolo può creare e gestire l'account di fatturazione e le informazioni sul pagamento.</li>
   <li>OrgAuditor: questo ruolo dispone di un accesso in sola lettura a report e informazioni sull'organizzazione.</li>
   </ul>
   </dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Rimuove il ruolo `BillingManager` dell'utente `test@exmaple.com` dall'organizzazione `org_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager
```

Rimuove il ruolo `BillingManager` dell'utente `test@exmaple.com` dall'organizzazione `org_example` dell'ambiente CFEE `env_example`:

```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Elenca tutti gli spazi

```
ibmcloud cfee spaces [-o,--org ORG] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Elenca tutti gli spazi

```
ibmcloud cfee spaces
```

Elenca tutti gli spazi dell'organizzazione `org_example` e dell'ambiente CFEE `env_example`

```
ibmcloud cfee spaces -o org_example --env env_example
```

## ibmcloud cfee space
{: #ibmcloud_cfee_space}

Mostra le informazioni dello spazio specificato

```
ibmcloud cfee space SPAZIO [--guid] [--security-group-rules] [-o,--org ORG] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Nome dello spazio da visualizzare.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>--guid</dt>
   <dd>Richiama e visualizza il guid dello spazio specificato. Tutti gli altri output per lo spazio vengono eliminati.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>--security-group-rules</dt>
   <dd>Richiama le regole di tutti i gruppi di sicurezza associati allo spazio.</dd>
  </dl>

<strong>Esempi</strong>:

Mostra le informazioni dello spazio `space_example`:

```
ibmcloud cfee space space_example
```

Richiama e visualizza il GUID dello spazio `space_example`:

```
ibmcloud cfee space space_example --guid
```

Mostra le regole di tutti i gruppi di sicurezza associati allo spazio `space_example`:

```
ibmcloud cfee space space_example --security-group-rules
```

Mostra le informazioni dello spazio `space_example` dell'organizzazione `org_example` e dell'ambiente CFEE `env_example`:

```
ibmcloud cfee space space_example -o org_example --env env_example
```

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Crea un nuovo spazio

```
ibmcloud cfee space-create SPAZIO [-o, --org ORG] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Nome dello spazio creato.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Crea un nuovo spazio `space_example`:

```
ibmcloud cfee space-create space_example
```

Crea un nuovo spazio `space_example` nell'organizzazione `org_example` e nell'ambiente CFEE `env_example`:

```
ibmcloud cfee space-create space_example -o org_example --env env_example
```

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Ridenomina uno spazio

```
ibmcloud cfee space-rename NOME_PRECEDENTE NUOVO_NOME [-o, --org ORG] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME_PRECEDENTE (obbligatorio)</dt>
   <dd>Il nome precedente dello spazio da rinominare.</dd>
   <dt>NUOVO_NOME (obbligatorio)</dt>
   <dd>Il nuovo nome con cui viene rinominato lo spazio.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Ridenomina lo spazio `space_example` con `new_pace_example`:

```
ibmcloud cfee space-rename space_example new_pace_example
```

Ridenomina lo spazio `space_example` con `new_pace_example` nell'organizzazione `org_example` e nell'ambiente CFEE `env_example`:

```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Elimina uno spazio

```
ibmcloud cfee space-delete SPAZIO [-f, --force] [-o, --org ORG] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Nome dello spazio da eliminare.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>-f, --force</dt>
   <dd>Forza l'eliminazione senza conferma.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Elimina lo spazio `space_example`:

```
ibmcloud cfee space-delete space_example
```

Elimina lo spazio `space_example` nell'organizzazione `org_example` e nell'ambiente CFEE `env_example` senza conferma:

```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```

## ibmcloud cfee space-role-set
{: #ibmcloud_cfee_space_role_set}

Assegna un ruolo dello spazio ad un utente

```
ibmcloud cfee space-role-set EMAIL_UTENTE ORG SPAZIO RUOLO [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'e-mail dell'utente che viene assegnata.</dd>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio a cui è assegnato l'utente.</dd>
   <dt>RUOLO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio a cui è assegnato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per un dato spazio.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Assegna l'utente `test@exmaple.com` all'organizzazione `org_example` e lo spazio `space_example` come ruolo `SpaceManager`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager
```

Assegna l'utente `test@exmaple.com` all'organizzazione `org_example` e lo spazio `space_example` come ruolo `SpaceManager` nell'ambiente `env_example`:

```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-role-unset
{: #ibmcloud_cfee_space_role_unset}

Rimuove un ruolo dello spazio da un utente

```
ibmcloud cfee space-role-unset EMAIL_UTENTE ORG SPAZIO RUOLO [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'e-mail dell'utente che viene rimosso.</dd>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio da cui viene eliminato l'utente.</dd>
   <dt>RUOLO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per un dato spazio.</li>
   <li>SpaceDeveloper: questo ruolo può creare e gestire applicazioni e servizi e visualizzare log e report.</li>
   <li>SpaceAuditor: questo ruolo può visualizzare log, report e impostazioni per lo spazio.</li>
   </ul></dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Rimuove l'utente `test@exmaple.com` dall'organizzazione `org_example` e dallo spazio `space_example` come ruolo `SpaceManager`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager
```

Rimuove l'utente `test@exmaple.com` dall'organizzazione `org_example` e dallo spazio `space_example` come ruolo `SpaceManager` nell'ambiente `env_example`:

```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```

## ibmcloud cfee space-roles
{: #ibmcloud_cfee_space_roles}

Ottiene tutti i ruoli dello spazio dell'utente corrente nell'organizzazione specifica

```
ibmcloud cfee space-roles ORG [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Ottiene tutti i ruoli dello spazio dell'utente corrente nell'organizzazione `org_example`:

```
ibmcloud cfee space-roles org_example
```

Ottiene tutti i ruoli dello spazio dell'utente corrente nell'organizzazione `org_example` e nell'ambiente `env_example`:

```
ibmcloud cfee space-roles org_example --env env_example
```

## ibmcloud cfee space-users
{: #ibmcloud_cfee_space_users}

Visualizza gli utenti nello spazio specificato in base al ruolo

```
ibmcloud cfee space-users ORG SPAZIO [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione.</dd>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Visualizza tutti gli utenti nello spazio `space_example` e nell'organizzazione `org_example`:

```
ibmcloud cfee space-users org_example space_example
```

Visualizza tutti gli utenti nello spazio `space_example`, nell'organizzazione `org_example` e nell'ambiente `env_example`:

```
ibmcloud cfee space-users org_example space_example --env env_example
```
