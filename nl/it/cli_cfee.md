---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-05"

keywords: cli, cloud foundry enterprise environment, cfee, ibmcloud cfee, cfee environment, cfee instance, target user, list cfee

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestione del servizio Cloud Foundry Enterprise Environment
{: #ibmcloud_commands_cfee}

Con CFEE ({{site.data.keyword.cfee_full}}) puoi istanziare più piattaforme Cloud Foundry isolate e di livello aziendale su richiesta. Le istanze del servizio IBM Cloud Foundry Enterprise vengono eseguite all'interno del tuo account in {{site.data.keyword.cloud_notm}}. L'ambiente viene distribuito su hardware isolato (cluster Kubernetes). Hai un completo controllo sull'ambiente, compresi il controllo degli accessi, la capacità, gli aggiornamenti delle versioni e l'utilizzo e il monitoraggio delle risorse.

Utilizza i seguenti comandi per gestire i ruoli, gli utenti, gli spazi, le organizzazioni e gli ambienti CFEE.
{: shortdesc}

## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

Elenca gli ambienti CFEE:
```
ibmcloud cfee environments
```
{: codeblock}

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

Mostra i dettagli di un ambiente CFEE:
```
ibmcloud cfee environment NOME [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NAME (obbligatorio)</dt>
   <dd>Il nome dell'ambiente da visualizzare.</dd>
   <dt>--id</dt>
   <dd>Mostra solo l'ID</dd>
  </dl>

<strong>Esempi</strong>:

Mostra i dettagli di un ambiente CFEE `env_example`:
```
ibmcloud cfee environment env_example
```
{: codeblock}

Mostra l'ID di un ambiente CFEE `env_example`:
```
ibmcloud cfee environment env_example --id
```
{: codeblock}

## ibmcloud cfee orgs
{: #ibmcloud_cfee_orgs}

Elenca tutte le organizzazioni:
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
{: codeblock}

Elenca tutte le organizzazioni dell'ambiente CFEE `env_example`:
```
ibmcloud cfee orgs --env env_example
```
{: codeblock}

## ibmcloud cfee org
{: #ibmcloud_cfee_org}

Visualizza i dettagli di un'organizzazione:
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
{: codeblock}

Visualizza i dettagli di un'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:
```
ibmcloud cfee org org_example --env env_example
```
{: codeblock}

Mostra il GUID di un'organizzazione CFEE `org_example`:
```
ibmcloud cfee org org_example --guid
```
{: codeblock}

## ibmcloud cfee org-create
{: #ibmcloud_cfee_org_create}

Crea un'organizzazione:
```
ibmcloud cfee org-create ORG [-q, --quota QUOTA] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da creare.</dd>
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
{: codeblock}

Crea un'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:
```
ibmcloud cfee org-create org_example --env env_example
```
{: codeblock}

Crea un'organizzazione CFEE `org_example` con la quota `quote_example`:
```
ibmcloud cfee org org-create org_example --quota quota_example
```
{: codeblock}

## ibmcloud cfee org-delete
{: #ibmcloud_cfee_org_delete}

Elimina un'organizzazione:
```
ibmcloud cfee org-delete ORG [-f, --force] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da eliminare.</dd>
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
{: codeblock}

Elimina un'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:
```
ibmcloud cfee org-delete org_example --env env_example
```
{: codeblock}

Elimina un'organizzazione CFEE `org_example` senza conferma:
```
ibmcloud cfee org org-delete org_example -f
```
{: codeblock}

## ibmcloud cfee org-users
{: #ibmcloud_cfee_org_users}

Visualizza gli utenti nell'organizzazione specificata in base al ruolo:
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
{: codeblock}

Visualizza gli utenti nell'organizzazione CFEE `org_example` dell'ambiente CFEE `env_example`:
```
ibmcloud cfee org-users org_example --env env_example
```
{: codeblock}

Elenca tutti gli utenti nell'organizzazione CFEE `org_example`:
```
ibmcloud cfee org-users org_example -a
```
{: codeblock}

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
   <dd>L'email dell'utente da assegnare.</dd>
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
{: codeblock}

Assegna il ruolo `BillingManager` all'utente `test@exmaple.com` nell'organizzazione `org_example` dell'ambiente CFEE `env_example`:
```
ibmcloud cfee org-role-set tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee org-role-unset
{: #ibmcloud_cfee_org_role_unset}

Rimuove un ruolo organizzazione da un utente (gestore dell'organizzazione o solo l'utente):
```
ibmcloud cfee org-role-unset EMAIL_UTENTE ORG RUOLO [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>EMAIL_UTENTE (obbligatorio)</dt>
   <dd>L'email dell'utente da rimuovere.</dd>
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
{: codeblock}

Rimuove il ruolo `BillingManager` dell'utente `test@exmaple.com` dall'organizzazione `org_example` dell'ambiente CFEE `env_example`:
```
ibmcloud cfee org-role-unset tes@example.com org_example BillingManager --env env_example
```
{: codeblock}

## ibmcloud cfee spaces
{: #ibmcloud_cfee_spaces}

Elenca tutti gli spazi:
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

Elenca tutti gli spazi:
```
ibmcloud cfee spaces
```
{: codeblock}

Elenca tutti gli spazi dell'organizzazione `org_example` e dell'ambiente CFEE `env_example`
```
ibmcloud cfee spaces -o org_example --env env_example
```
{: codeblock}

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
   <dd>Richiama e visualizza il guid dello spazio. Tutti gli altri output per lo spazio vengono eliminati.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
   <dt>--security-group-rules</dt>
   <dd>Richiama le regole di tutti i gruppi di sicurezza associati allo spazio.</dd>
  </dl>

<strong>Esempi</strong>:

Mostra i dettagli di uno spazio denominato `space_example`:
```
ibmcloud cfee space space_example
```
{: codeblock}

Richiama e visualizza il GUID dello spazio `space_example`:
```
ibmcloud cfee space space_example --guid
```
{: codeblock}

Mostra le regole di tutti i gruppi di sicurezza associati allo spazio `space_example`:
```
ibmcloud cfee space space_example --security-group-rules
```
{: codeblock}

Mostra i dettagli dello spazio `space_example`, dell'organizzazione `org_example` e dell'ambiente CFEE `env_example`:
```
ibmcloud cfee space space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-create
{: #ibmcloud_cfee_space_create}

Crea uno spazio:
```
ibmcloud cfee space-create SPAZIO [-o, --org ORG] [--env AMBIENTE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Nome dello spazio da creare.</dd>
   <dt>--env AMBIENTE</dt>
   <dd>Nome ambiente CFEE. Se non specificato, il valore predefinito è l'ambiente CFEE corrente.</dd>
   <dt>-o, --org ORG</dt>
   <dd>Nome dell'organizzazione. Se non specificato, il valore predefinito è l'organizzazione corrente.</dd>
  </dl>

<strong>Esempi</strong>:

Crea uno spazio denominato `space_example`:
```
ibmcloud cfee space-create space_example
```
{: codeblock}

Crea uno spazio denominato `space_example`, nell'organizzazione `org_example` e nell'ambiente CFEE `env_example`:
```
ibmcloud cfee space-create space_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-rename
{: #ibmcloud_cfee_space_rename}

Rinomina uno spazio:
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
{: codeblock}

Ridenomina lo spazio `space_example` con `new_pace_example` nell'organizzazione `org_example` e nell'ambiente CFEE `env_example`:
```
ibmcloud cfee space-rename space_example new_pace_example -o org_example --env env_example
```
{: codeblock}

## ibmcloud cfee space-delete
{: #ibmcloud_cfee_space_delete}

Elimina uno spazio:
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
{: codeblock}

Elimina lo spazio `space_example` nell'organizzazione `org_example` e nell'ambiente CFEE `env_example` senza conferma:
```
ibmcloud cfee space-delete space_example new_pace_example -f -o org_example --env env_example
```
{: codeblock}

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
   <dd>L'email dell'utente da assegnare.</dd>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione a cui viene assegnato l'utente.</dd>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio a cui è assegnato l'utente.</dd>
   <dt>RUOLO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio a cui è assegnato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per uno spazio.</li>
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
{: codeblock}

Assegna l'utente `test@exmaple.com` all'organizzazione `org_example` e lo spazio `space_example` come ruolo `SpaceManager` nell'ambiente `env_example`:
```
ibmcloud cfee space-role-set tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
   <dd>L'email dell'utente da rimuovere.</dd>
   <dt>ORGANIZZAZIONE (obbligatorio)</dt>
   <dd>Il nome dell'organizzazione da cui viene eliminato l'utente.</dd>
   <dt>SPAZIO (obbligatorio)</dt>
   <dd>Il nome dello spazio da cui viene eliminato l'utente.</dd>
   <dt>RUOLO (obbligatorio)</dt>
   <dd>Il nome del ruolo spazio da cui viene eliminato l'utente. Ad esempio:
   <ul>
   <li>SpaceManager: questo ruolo può invitare e gestire utenti e attivare funzioni per uno spazio.</li>
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
{: codeblock}

Rimuove l'utente `test@exmaple.com` dall'organizzazione `org_example` e dallo spazio `space_example` come ruolo `SpaceManager` nell'ambiente `env_example`:
```
ibmcloud cfee space-role-unset tes@example.com org_example space_example SpaceManager --env env_example
```
{: codeblock}

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
{: codeblock}

Ottiene tutti i ruoli dello spazio dell'utente corrente nell'organizzazione `org_example` e nell'ambiente `env_example`:
```
ibmcloud cfee space-roles org_example --env env_example
```
{: codeblock}

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
{: codeblock}

Visualizza tutti gli utenti nello spazio `space_example`, nell'organizzazione `org_example` e nell'ambiente `env_example`:
```
ibmcloud cfee space-users org_example space_example --env env_example
```
{: codeblock}

## ibmcloud cfee create
{: #ibmcloud_cfee_create}

Fai una richiesta per creare un'istanza di Cloud Foundry Enterprise Environment:
```
ibmcloud cfee create [-n, --name NAME] [--location LOCATION] [--cells CELLS] [--virtual-dedicated-hardware] [--private-access] [--private-vlan ID, --public-vlan ID] [--plan ID] [-c PARAMETERS_AS_JSON]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-n, --name NOME (obbligatorio)</dt>
  <dd>Specifica il nome del CFEE. Il nome deve essere di massimo 24 caratteri, iniziare con una lettera e contenere solo caratteri alfanumerici, `-`, `_` e `.`.</dd>
  <dt>--location LOCATION (required)</dt>
  <dd>Specifica il data center in cui eseguire il provisioning di questo CFEE (ad esempio, dal10). Per trovare i data center disponibili, esegui `ibmcloud cfee create-locations`.</dd>
  <dt>--cells CELLS</dt>
  <dd>Specifica il numero di celle per questo CFEE. Il valore predefinito è 2 e il minimo è 1. In un CFEE a una cella non può esserci l'alta disponibilità.</dd>
  <dt>--private-access</dt>
  <dd>Specifica il tipo di accesso di rete per il database PostgreSQL di cui viene eseguito il provisioning come parte di CFEE. Imposta l'indicatore solo se l'account è abilitato per VRF e l'endpoint del servizio. Se questo indicatore è impostato, viene utilizzato l'endpoint di accesso privato.</dd>
  <dt>--virtual-dedicated-hardware</dt>
  <dd>Con l'hardware dedicato, i tuoi nodi di lavoro sono ospitati su un'infrastruttura dedicata al tuo account. Con l'hardware condiviso, le risorse dell'infrastruttura, ad esempio l'hypervisor e l'hardware fisico, sono condivise con altri clienti IBM, ma ogni nodo di lavoro è a singolo tenant dedicato a te. `Shared` è il valore predefinito se l'indicatore NON è impostato. L'utilizzo di un nodo di lavoro `dedicated` ha degli ulteriori costi.</dd>
  <dt>--private-vlan ID</dt>
  <dd>Specifica l'ID della VLAN privata. Per impostazione predefinita, viene utilizzata una serie di VLAN disponibili o ne viene creata una coppia per tuo conto.</dd>
  <dt>--public-vlan ID</dt>
  <dd>Specifica l'ID della VLAN pubblica. Per impostazione predefinita, viene utilizzata una serie di VLAN disponibili o ne viene creata una coppia per tuo conto.</dd>
  <dt>--plan ID</dt>
  <dd>Specifica l'ID del piano. Per impostazione predefinita, viene utilizzato un piano Standard.</dd>
  <dt>-c PARAMETERS_AS_JSON</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per l'API, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, vedi https://cloud.ibm.com/apidocs/cfaas#provision-new-cfee-environment per la specifica voce di catalogo. Questo è necessario per il provisioning di CFEE multizona. Nota: tutti gli altri indicatori vengono ignorati e i campi resource_group_id, access_token e refresh_token vengono gestiti dal comando della CLI.</dd>
</dl>

<strong>Esempi</strong>:

Crea un'istanza denominata `test-cfee` in `dal10`:
```
ibmcloud cfee create test-cfee dal10
```

Crea un'istanza `dedicated` denominata `test-cfee` in `dal10` con `4` celle:
```
ibmcloud cfee create test-cfee dal10 --cells 4 --isolation dedicated
```

## ibmcloud cfee create-locations
{: #ibmcloud_cfee_create_locations}

Effettua una richiesta per ottenere un elenco dei data center disponibili per le regioni di destinazione
```
ibmcloud cfee create-locations [--output FORMAT]
```
{: codeblock}

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud cfee create-permission-get
{: #ibmcloud_cfee_create_permission_get}

Controlla se un utente dispone di tutte le autorizzazioni richieste per creare un'istanza CFEE. Il comando controlla le seguenti politiche di accesso per l'utente di destinazione: editor per i servizi CFEE, ruolo di amministratore per il servizio Kubernetes, editor per il ruolo di piattaforma e gestore per il ruolo di accesso al servizio per il servizio Cloud Object Storage e il ruolo di sviluppatore per lo spazio corrente nell'organizzazione attuale per il provisioning di Compose for PostgreSQL

```
ibmcloud cfee create-permission-get USER_NAME [-ag, --access-group GROUP_NAME] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>Il nome del gruppo di accesso in cui controllare le autorizzazioni. Il gruppo di accesso predefinito è `cfee-provision-access-group`.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specifica il formato di output delle autorizzazioni; al momento è supportato solo JSON.</dd>
  </dl>
  
<strong>Esempi</strong>:

Controlla le autorizzazioni di creazione CFEE per l'utente `name@example.com`:
```
ibmcloud cfee create-permission-get name@example.com
```
{: codeblock}

Controlla le autorizzazioni di creazione CFEE per l'utente `name@example.com` e nel gruppo di accesso `test-access-group`:
```
ibmcloud cfee create-permission-get name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-permission-set
{: #ibmcloud_cfee_create_permission_set}

Assegna all'utente tutte le autorizzazioni necessarie per creare un'istanza CFEE. Il comando crea le seguenti politiche di accesso per l'utente di destinazione: ruolo di editor per il servizio CFEE, ruolo di amministratore per il servizio Kubernetes, editor per il ruolo di piattaforma e gestore per il ruolo di accesso al servizio per il servizio Cloud Object Storage e il ruolo di sviluppatore per lo spazio corrente nell'organizzazione attuale per il provisioning di Compose for PostgreSQL

```
ibmcloud cfee create-permission-set USER_NAME [-ag, --access-group GROUP_NAME]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NOME_UTENTE (obbligatorio)</dt>
   <dd>Il nome dell'utente.</dd>
   <dt>--access-group GROUP_NAME</dt>
   <dd>Il nome del gruppo di accesso in cui assegnare le autorizzazioni. Il gruppo di accesso predefinito è `cfee-provision-access-group`.</dd>
  </dl>
  
<strong>Esempi</strong>:

Assegna le autorizzazioni di creazione CFEE all'utente `name@example.com` tramite il gruppo di accesso predefinito:
```
ibmcloud cfee create-permission-set name@example.com
```
{: codeblock}

Assegna le autorizzazioni di creazione CFEE all'utente `name@example.com` tramite il gruppo di accesso `test-access-group`:
```
ibmcloud cfee create-permission-set name@example.com -ag test-access-group
```
{: codeblock}

## ibmcloud cfee create-status
{: #ibmcloud_cfee_create_status}

Controlla lo stato di provisioning di un'istanza CFEE:
```
ibmcloud cfee create-status NAME or ID [--poll] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>NAME o ID (obbligatorio)</dt>
   <dd>Il nome o l'ID dell'istanza CFEE.</dd>
   <dt>--poll</dt>
   <dd>Specifica se vuoi rendere questa chiamata ricorrente, di cui eseguire il polling finché lo stato non è stabile.</dd>
   <dt>--output FORMAT</dt>
   <dd>Specifica il formato di output dello stato; al momento è supportato solo JSON.</dd>
  </dl>

## ibmcloud cfee monitoring-enable
{: #ibmcloud_cfee_monitoring-enable}

Abilita il monitoraggio sull'ambiente CFEE di destinazione:
```
ibmcloud cfee monitoring-enable
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-disable
{: #ibmcloud_cfee_monitoring-disable}

Disabilita il monitoraggio sull'ambiente CFEE di destinazione:
```
ibmcloud cfee monitoring-disable
```
{: codeblock}

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
  </dl>

## ibmcloud cfee monitoring-status
{: #ibmcloud_cfee_monitoring-status}

Controlla lo stato dell'operazione di abilitazione/disabilitazione del monitoraggio più recente nell'ambiente CFEE di destinazione.
```
ibmcloud cfee monitoring-status [--poll]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
  <dl>
   <dt>--poll</dt>
   <dd>Specifica se vuoi rendere questa chiamata ricorrente, di cui eseguire il polling finché lo stato non è stabile</dd>
  </dl>
