---

copyright:

  years: 2018, 2019


lastupdated: "2019-01-14"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione di risorse e gruppi di risorse
{: #ibmcloud_commands_resource}

Un gruppo di risorse è un modo per organizzare le risorse dell'account in raggruppamenti personalizzabili. Utilizza i seguenti comandi per gestire i gruppi di risorse {{site.data.keyword.Bluemix}} e le risorse in un gruppo di risorse.
{: shortdesc}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire i gruppi di risorse e le risorse.">
  <thead>
  </thead>
  <tbody>
    <tr>
      <td>[ibmcloud resource groups](cli_resource_group.html#ibmcloud_resource_groups)</td>
      <td>[ibmcloud resource group](cli_resource_group.html#ibmcloud_resource_group)</td>
      <td>[ibmcloud resource group-create](cli_resource_group.html#ibmcloud_resource_group_create)</td>
      <td>[ibmcloud resource group-update](cli_resource_group.html#ibmcloud_resource_group_update)</td>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quotas)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource quotas](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-instances](cli_resource_group.html#ibmcloud_resource_service_instances)</td>
      <td>[ibmcloud resource service-instance](cli_resource_group.html#ibmcloud_resource_service_instance)</td>
      <td>[ibmcloud resource service-instance-create](cli_resource_group.html#ibmcloud_resource_service_instance_create)
      <td>[ibmcloud resource service-instance-migrate](cli_resource_group.html#ibmcloud_resource_cf_service_instance_migrate)</td>
    </tr>  
    <tr>  
      <td>[ibmcloud resource service-instance-update](cli_resource_group.html#ibmcloud_resource_service_instance_update)</td>
      <td>[ibmcloud resource service-instance-delete](cli_resource_group.html#ibmcloud_resource_service_instance_delete)</td>
      <td>[ibmcloud resource service-bindings](cli_resource_group.html#ibmcloud_resource_service_bindings)</td>
      <td>[ibmcloud resource service-binding](cli_resource_group.html#ibmcloud_resource_service_binding)</td>
      <td>[ibmcloud resource service-binding-create](cli_resource_group.html#ibmcloud_resource_service_binding_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-binding-delete](cli_resource_group.html#ibmcloud_resource_service_binding_delete)</td>
      <td>[ibmcloud resource quota](cli_resource_group.html#ibmcloud_resource_quota)</td>
      <td>[ibmcloud resource service-keys](cli_resource_group.html#ibmcloud_resource_service_keys)</td>
      <td>[ibmcloud resource service-key](cli_resource_group.html#ibmcloud_resource_service_key)</td>
      <td>[ibmcloud resource service-key-create](cli_resource_group.html#ibmcloud_resource_service_key_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-key-update](cli_resource_group.html#ibmcloud_resource_service_key_update)</td>
      <td>[ibmcloud resource service-key-delete](cli_resource_group.html#ibmcloud_resource_service_key_delete)</td>
      <td>[ibmcloud resource service-aliases](cli_resource_group.html#ibmcloud_resource_service_aliases)</td>
      <td>[ibmcloud resource service-alias](cli_resource_group.html#ibmcloud_resource_service_alias)</td>
      <td>[ibmcloud resource service-alias-create](cli_resource_group.html#ibmcloud_resource_service_alias_create)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource service-alias-update](cli_resource_group.html#ibmcloud_resource_service_alias_update)</td>
      <td>[ibmcloud resource service-alias-delete](cli_resource_group.html#ibmcloud_resource_service_alias_delete)</td>
      <td>[ibmcloud resource search](cli_resource_group.html#ibmcloud_resource_search)</td>
      <td>[ibmcloud resource tags 
](cli_resource_group.html#ibmcloud_resource_tags)</td>
      <td>[ibmcloud resource tag](cli_resource_group.html#ibmcloud_resource_tag)</td>
    </tr>
    <tr>
      <td>[ibmcloud resource tag-create](cli_resource_group.html#ibmcloud_resource_tag_create)</td>
      <td>[ibmcloud resource tag-delete](cli_resource_group.html#ibmcloud_resource_tag_delete)</td>
      <td>[ibmcloud resource tag-attach](cli_resource_group.html#ibmcloud_resource_tag_attach)</td>
      <td>[ibmcloud resource tag-detach](cli_resource_group.html#ibmcloud_resource_tag_detach)</td>
      <td>[ibmcloud resource tag-update](cli_resource_group.html#ibmcloud_resource_tag_update)</td>
    </tr>
  </tbody>
</table>

## ibmcloud resource groups
{: #ibmcloud_resource_groups}

Elenca i gruppi di risorse.

```
ibmcloud resource groups [--default] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--default</dt>
  <dd>Richiama il gruppo predefinito dell'account corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i gruppi di risorse nell'account attualmente selezionato:

```
ibmcloud resource groups
```

Elenca il gruppo predefinito dell'account attualmente selezionato:

```
ibmcloud resource groups --default
```

## ibmcloud resource group
{: #ibmcloud_resource_group}

Mostra i dettagli di un gruppo di risorse

```
ibmcloud resource group NOME [--id] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse</dd>
  <dt>--id</dt>
  <dd>Mostra solo l'ID</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:

Mostra il gruppo di risorse `example-group`:

```
ibmcloud resource group example-group
```

Mostra solo l'ID del gruppo di risorse `example-group`:

```
ibmcloud resource group example-group --id
```

## ibmcloud resource group-create
{: #ibmcloud_resource_group_create}

Crea un gruppo di risorse

```
ibmcloud resource group-create NOME
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse</dd>
</dl>

<strong>Esempi</strong>:
Crea un gruppo di risorse `example-group`:

```
ibmcloud resource group-create example-group
```

## ibmcloud resource group-update
{: #ibmcloud_resource_group_update}

Aggiorna un gruppo di risorse esistente

```
ibmcloud resource group-update NOME [-n, --name NUOVO_NOME] [-q, --quota NOME_NUOVA_QUOTA]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse di destinazione</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del gruppo di risorse</dd>
  <dt>-q, --quota</dt>
  <dd>Nome della nuova definizione di quota</dd>
  <dt>-f</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina il gruppo di risorse `example-group` come `trial-group`:

```
ibmcloud resource group-update example-group -n trial-group
```

Modifica la quota del gruppo di risorse `example-group` come `free`:

```
ibmcloud resource group-update example-group -q free
```

## ibmcloud resource quotas
{: #ibmcloud_resource_quotas}

Elenca tutte le definizioni di quota

```
ibmcloud resource quotas
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Elenca tutte le definizioni di quota:

```
ibmcloud resource quotas
```

## ibmcloud resource quota
{: #ibmcloud_resource_quota}

Mostra i dettagli di una definizione di quota

```
ibmcloud resource quota NOME
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome della quota</dd>
</dl>

<strong>Esempi</strong>:
mostra i dettagli della quota `free`:

```
ibmcloud resource quota free
```

## ibmcloud resource cf-service-instance-migrate
{: #ibmcloud_resource_cf_service_instance_migrate}

Migra un'istanza del servizio Cloud Foundry nel gruppo di risorse

```
ibmcloud resource cf-service-instance-migrate (NOME_ISTANZA_SERVIZIO | ID_ISTANZA_SERVIZIO) [--resource-group-name NOME_GRUPPO_RISORSE | --resource-group-id ID_GRUPPO_RISORSE] [-f, --force]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ISTANZA_SERVIZIO o ID_ISTANZA_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o ID dell'istanza del servizio</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--resource-group-id'. Se non viene specificata alcuna di tali opzioni, viene utilizzato come valore predefinito il gruppo di risorse attualmente di destinazione.</dd>
  <dt>--resource-group-id</dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--resource-group-name'. Se non viene specificata alcuna di tali opzioni, viene utilizzato come valore predefinito il gruppo di risorse attualmente di destinazione.</dd>
  <dt>-f, --force</dt>
  <dd>Migra senza conferma</dd>
</dl>

## ibmcloud resource service-instances
{: #ibmcloud_resource_service_instances}

Elenca le istanze del servizio

```
ibmcloud resource service-instances [--service-name NOME_SERVIZIO] [--location UBICAZIONE] [--long] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--service-name</dt>
  <dd>Nome del servizio di appartenenza</dd>
  <dt>--location</dt>
  <dd>Filtra per ubicazione</dd>
  <dt>--long</dt>
  <dd>Mostra dei campi aggiuntivi nell'output</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:

Elenca le istanze del servizio `test-service`:

```
ibmcloud resource service-instances --service-name test-service
```

## ibmcloud resource service-instance
{: #ibmcloud_resource_service_instance}

Mostra di dettagli di un'istanza del servizio

```
ibmcloud resource service-instance (NOME|ID) [--location UBICAZIONE] [--id] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio), esclusivo con ID</dt>
  <dd>Nome dell'istanza del servizio</dd>
  <dt>ID (obbligatorio), esclusivo con NOME</dt>
  <dd>ID dell'istanza del servizio</dd>
  <dt>--location</dt>
  <dd>Filtra per ubicazione</dd>
  <dt>--id</dt>
  <dd>Visualizza l'ID dell'istanza del servizio</dd>
  <dt>--output</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--id'.</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli dell'istanza del servizio `my-service-instance`:

```
ibmcloud resource service-instance my-service-instance
```

## ibmcloud resource service-instance-create
{: #ibmcloud_resource_service_instance_create}

Crea un'istanza del servizio

```
ibmcloud resource service-instance-create NOME NOME_SERVIZIO|ID_SERVIZIO NOME_PIANO_SERVIZIO|ID_PIANO_SERVIZIO UBICAZIONE [[-d, --deployment NOME_DISTRIBUZIONE] [-p, --parameters @FILE_JSON | STRINGA_JSON ]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome dell'istanza del servizio</dd>
  <dt>NOME_SERVIZIO o ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o ID del servizio</dd>
  <dt>NOME_PIANO_SERVIZIO o ID_PIANO_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o ID del piano di servizio</dd>
  <dt>UBICAZIONE</dt>
  <dd>Ubicazione o ambiente di destinazione per creare l'istanza del servizio</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON di parametri per creare l'istanza del servizio</dd>
  <dt>-d, --deployment</dt>
  <dd>Nome della distribuzione</dd>
</dl>

<strong>Esempi</strong>:
Crea un'istanza del servizio denominata `my-service-instance` utilizzando il piano di servizio `test-service-plan` del servizio `test-service` nell'ubicazione `eu-gb`:

```
ibmcloud resource service-instance-create my-service-instance test-service test-service-plan eu-gb
```

## ibmcloud resource service-instance-update
{: #ibmcloud_resource_service_instance_update}

Aggiorna l'istanza del servizio

```
ibmcloud resource service-instance-update (NOME|ID) [-n, --name NUOVO_NOME] [--service-plan-id ID_PIANO_SERVIZIO] [--parameters @FILE_JSON | STRINGA_JSON] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>Nome (obbligatorio)</dt>
  <dd>Nome dell'istanza del servizio, esclusivo con ID</dd>
  <dt>ID (obbligatorio)</dt>
  <dd>ID dell'istanza del servizio, esclusivo con NOME</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome dell'istanza del servizio</dd>
  <dt>--service-plan-id</dt>
  <dd>Nuovo ID del piano di servizio</dd>
  <dt>--parameters @FILE_JSON | STRINGA_JSON</dt>
  <dd>File JSON o stringa JSON di parametri per creare l'istanza del servizio</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Aggiorna l'istanza del servizio `my-service-instance`, modifica il suo nome in `new-service-instance`:

```
ibmcloud resource service-instance-update my-service-instance -n new-service-instance
```

## ibmcloud resource service-instance-delete
{: #ibmcloud_resource_service_instance_delete}

Elimina l'istanza del servizio

```
ibmcloud resource service-instance-delete (NOME|ID) [-f, --force] [--recursive]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>Nome (obbligatorio)</dt>
  <dd>Nome dell'istanza del servizio, esclusivo con ID</dd>
  <dt>ID (obbligatorio)</dt>
  <dd>ID dell'istanza del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
  <dt>--recursive</dt>
  <dd>Elimina tutte le risorse di appartenenza</dd>
</dl>

<strong>Esempi</strong>:
Elimina la risorsa istanza-servizio `my-service-instance`:

```
ibmcloud resource service-instance-delete my-service-instance
```

## ibmcloud resource service-bindings
{: #ibmcloud_resource_service_bindings}

Mostra i bind all'alias del servizio

```
ibmcloud resource service-bindings ALIAS_SERVIZIO [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>ALIAS_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:
Mostra i bind della risorsa all'alias del servizio `my-service-alias`:

```
ibmcloud resource bindings my-service-alias
```

## ibmcloud resource service-binding
{: #ibmcloud_resource_service_binding}

Mostra i dettagli di un bind del servizio

```
ibmcloud resource service-binding NOME_ALIAS NOME_APPLICAZIONE [--id] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>NOME_APPLICAZIONE</dt>
  <dd>Nome applicazione CloudFoundry</dd>
  <dt>--id</dt>
  <dd>Visualizza solo l'ID. Tutto l'altro output per il bind del servizio viene eliminato. Questa opzione è esclusiva con '--output'.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--id'.</dd>
</dl>

<strong>Esempi</strong>:
Mostra i dettagli del bind del servizio tra l'alias di servizio `my-service-alias` e l'applicazione `my-app`:

```
ibmcloud resource bindings my-service-alias my-app
```

## ibmcloud resource service-binding-create
{: #ibmcloud_resource_service_binding_create}

Crea un bind del servizio

```
ibmcloud resource service-binding-create NOME_ALIAS_SERVIZIO NOME_APPLICAZIONE NOME_RUOLO [--service-id ID_SERVIZIO] [-p, --parameters @FILE_JSON | TESTO_JSON] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>NOME_APPLICAZIONE</dt>
  <dd>Nome applicazione CloudFoundry</dd>
  <dt>NOME_RUOLO</dt>
  <dd>Nome del ruolo utente</dd>
  <dt>--service-id</dt>
  <dd>Nome o UUID dell'ID servizio a cui appartiene il ruolo.</dd>
  <dt>-p, --parameter</dt>
  <dd>File JSON o stringa JSON dei parametri</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Crea un bind del servizio tra l'alias di servizio `my-service-alias` e l'applicazione `my-app` con il ruolo `Administrator`:

```
ibmcloud resource service-binding-create my-service-alias my-app Administrator
```

## ibmcloud resource service-binding-delete
{: #ibmcloud_resource_service_binding_delete}

Elimina un bind del servizio

```
ibmcloud resource service-binding-delete ALIAS_SERVIZIO NOME_APPLICAZIONE [-f, --force]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>NOME_APPLICAZIONE</dt>
  <dd>Nome applicazione CloudFoundry</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina il bind del servizio tra l'alias di servizio `my-service-alias` e l'applicazione `my-app`:

```
ibmcloud resource service-binding-delete my-service-alias my-app
```

## ibmcloud resource service-keys
{: #ibmcloud_resource_service_keys}

Elenca le chiavi dell'istanza o dell'alias del servizio

```
ibmcloud resource service-keys [ --instance-id ID | --instance-name NOME | --alias-id ID | --alias-name NOME ] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID istanza del servizio</dd>
  <dt>--instance-name</dt>
  <dd>Nome istanza del servizio</dd>
  <dt>--alias-id</dt>
  <dd>ID alias del servizio</dd>
  <dt>--alias-name</dt>
  <dd>Nome alias del servizio</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:
Elenca le chiavi dell'istanza del servizio `my-service-instance`:

```
ibmcloud resource service-keys --instance-name my-service-instance  [--output FORMATO]
```

## ibmcloud resource service-key
{: #ibmcloud_resource_service_key}

Visualizza i dettagli di qualsiasi numero di chiavi di servizio, dove i primi *n* caratteri del nome della chiave del servizio corrispondono al NOME_CHIAVE fornito.

```
ibmcloud resource service-key NOME_CHIAVE [--id]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE</dt>
  <dd>Nome della chiave</dd>
  <dt>--id</dt>
  <dd>Visualizza gli ID di qualsiasi chiave, dove i primi *n* caratteri del nome della chiave del servizio corrispondono al NOME_CHIAVE fornito e *n* è la lunghezza del NOME_CHIAVE fornito.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato dell'output. Attualmente è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:
Mostra i dettagli delle chiavi del servizio `my-service-key`:

```
ibmcloud resource service-key my-service-key
```

## ibmcloud resource service-key-create
{: #ibmcloud_resource_service_key_create}

Crea una chiave del servizio

```
ibmcloud resource service-key-create NOME NOME_RUOLO ( --instance-id ID_ISTANZA_SERVIZIO | --instance-name NOME_ISTANZA_SERVIZIO | --alias-id ID_ALIAS_SERVIZIO | --alias-name NOME_ALIAS_SERVIZIO ) [--service-id ID_SERVIZIO] [-p, --parameters @FILE_JSON | TESTO_JSON] [-f, --force]]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME</dt>
  <dd>Nome della chiave</dd>
  <dt>NOME_RUOLO</dt>
  <dd>Nome del ruolo utente</dd>
  <dt>--instance-id</dt>
  <dd>ID istanza del servizio</dd>
  <dt>--instance-name</dt>
  <dd>Nome istanza del servizio</dd>
  <dt>--alias-id</dt>
  <dd>ID alias del servizio</dd>
  <dt>--alias-name</dt>
  <dd>Nome alias del servizio</dd>
  <dt>--service-id</dt>
  <dd>Nome o UUID dell'ID servizio a cui appartiene il ruolo.</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON dei parametri</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Crea una chiave del servizio denominata `my-service-key` con il ruolo `Administrator` per l'istanza del servizio `my-service-instance`:

```
ibmcloud resource service-key-create my-service-key Administrator --instance-name my-service-instance
```

## ibmcloud resource service-key-update
{: #ibmcloud_resource_service_key_update}

Aggiorna una chiave del servizio

```
ibmcloud resource service-key-update ( NOME | ID ) [-n, --name NUOVO_NOME] [-g GRUPPO_RISORSE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME | ID</dt>
  <dd>Nome o ID della chiave</dd>
  <dt>-n, --name NUOVO_NOME</dt>
  <dd>Nuovo nome della chiave</dd>
  <dt>-g GRUPPO_RISORSE</dt>
  <dd>ID del gruppo di risorse a cui appartiene la chiave</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Aggiorna una chiave di servizio denominata `my-service-key`, dalle un nuovo nome `my-service-key-2`:

```
ibmcloud resource service-key-update my-service-key -n my-service-key-2
```

## ibmcloud resource service-key-delete
{: #ibmcloud_resource_service_key_delete}

Elimina una chiave del servizio

```
ibmcloud resource service-key-delete ( NOME_CHIAVE | ID_CHIAVE ) [-f, --forece]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_CHIAVE | ID_CHIAVE</dt>
  <dd>Nome della chiave o l'ID della chiave</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina la chiave del servizio `my-service-key`:

```
ibmcloud resource service-key-delete my-service-key
```

## ibmcloud resource service-aliases
{: #ibmcloud_resource_service_aliases}

Elenca gli alias per un'istanza del servizio

```
ibmcloud resource service-aliases [ --instance-id ID | --instance-name NOME ] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>--instance-id</dt>
  <dd>ID dell'istanza del servizio di appartenenza.</dd>
  <dt>--instance-name</dt>
  <dd>Nome dell'istanza del servizio di appartenenza.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:
Elenca gli alias per l'istanza del servizio `my-service-instance`:
```
ibmcloud resource service-aliases my-service-instance
```

## ibmcloud resource service-alias
{: #ibmcloud_resource_service_alias}

Mostra i dettagli di un alias del servizio

```
ibmcloud resource service-alias NOME_ALIAS [--id] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>--id</dt>
  <dd>Visualizza solo l'ID dell'alias del servizio fornito. Tutto l'altro output per l'alias viene eliminato. Questa opzione è esclusiva con '--output'.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>--output valore  Specifica il formato di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--id'.</dd>
</dl>

<strong>Esempi</strong>:
Mostra i dettagli dell'alias del servizio `my-service-alias`:
```
ibmcloud resource service-alias  my-service-alias
```

## ibmcloud resource service-alias-create
{: #ibmcloud_resource_service_alias_create}

Crea un alias di un'istanza del servizio

```
ibmcloud resource service-alias-create NOME_ALIAS ( --instance-id ID | --instance-name NOME ) [-s NOME_SPAZIO] [-t, --tags TAG] [-p, --parameters @FILE_JSON | TESTO_JSON]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>--instance-id</dt>
  <dd>ID dell'istanza del servizio di appartenenza.</dd>
  <dt>--instance-name</dt>
  <dd>Nome dell'istanza del servizio di appartenenza.</dd>
  <dt>-s</dt>
  <dd>Nome dello spazio in cui l'alias viene creato. Il valore predefinito è lo spazio corrente.</dd>
  <dt>-t, --tags</dt>
  <dd>Elenco delle tag.</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON dei parametri.</dd>
</dl>

<strong>Esempi</strong>:
Crea un alias del servizio denominato `my-service-alias` dell'istanza del servizio `my-service-instance`:
```
ibmcloud resource service-alias-create my-service-alias --instance-name my-service-instance
```

## ibmcloud resource service-alias-update
{: #ibmcloud_resource_service_alias_update}

Aggiorna un alias del servizio

```
ibmcloud resource service-alias-update NOME_ALIAS [-n, --name NUOVO_NOME] [-t, --tags TAG] [-p, --parameters @FILE_JSON | STRINGA_JSON ][-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome dell'alias del servizio.</dd>
  <dt>-t, --tags</dt>
  <dd>Elenco delle tag.</dd>
  <dt>-p, --parameters</dt>
  <dd>File JSON o stringa JSON dei parametri.</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'aggiornamento senza conferma dell'utente.</dd>
</dl>

<strong>Esempi</strong>:
Aggiorna l'alias del servizio `my-service-alias`, modifica il suo nome in `new-service-alias`:

```
ibmcloud resource service-alias-update my-service-alias -n new-service-alias
```

## ibmcloud resource service-alias-delete
{: #ibmcloud_resource_service_alias_delete}

Elimina un alias del servizio

```
ibmcloud resource service-alias-delete NOME_ALIAS [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni comando</strong>:
<dl>
  <dt>NOME_ALIAS (obbligatorio)</dt>
  <dd>Nome dell'alias del servizio</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina l'alias del servizio `my-service-alias`:

```
ibmcloud resource service-alias-delete my-service-alias
```

## ibmcloud resource search
{: #ibmcloud_resource_search}
Ricerca le risorse utilizzando la sintassi di query Lucene

```
ibmcloud search QUERY_LUCENE [-o, --offset OFFSET] [-l, --limit LIMITE] [-s, --sort-by (name, family, region, type, crn)]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>-o, -offset</dt>
  <dd>Avvio numero posizione risorsa</dd>
  <dt>-l, -limit</dt>
  <dd>Numero di risorse da restituire (massimo 10000)</dd>
  <dt>-s, --sort-by</dt>
  <dd>Proprietà in base a cui ordinare. Gli input accettati sono `name`, `family`, `region`, `type`, `crn`.</dd>
</dl>

<strong>Esempi</strong>:
Ricerca le applicazioni Cloud Foundry i cui nomi iniziano con un testo specifico:

```
ibmcloud resource search 'name:my* AND type:cf-application'
```

Ricerca le istanze del servizio Cloud Foundry del servizio del nome servizio specificato:

```
ibmcloud resource search 'service_name:messagehub AND type:cf-service-instance'
```

Ricerca i bind del servizio Cloud Foundry nell'organizzazione con l'ID specificato:

```
ibmcloud resource search 'organization_guid:5b82c134-afb3-4f69-b1e0-3cbe4a13a205 AND type:cf-service-binding'
```

Ricerca gli spazi Cloud Foundry con il nome specificato e ubicati in una delle due regioni specificate:

```
ibmcloud resource search 'name:dev AND type:cf-space AND region:(us-south OR eu-gb)'
```

Ricerca le risorse il cui nome contiene la parola dev nello spazio Cloud Foundry con l'ID specificato:

```            
ibmcloud resource search 'name:*dev* AND doc.space_guid:a07181ca-f917-4ee6-af22-b2c0c2a2d5d7'
```

Ricerca le risorse del controller delle risorse nell'ubicazione specificata (ad esempio la regione us-south):

```
ibmcloud resource search 'region:us-south AND family:resource_controller'
```

Ricerca le risorse o gli alias nel gruppo di risorse con l'ID specificato:

```
ibmcloud resource search '(type:resource-instance OR type:resource-alias) AND (doc.resource_group_id:c900d9671b235c00461c5e311a8aeced)'
```

Ricerca i gruppi di risorse con il nome predefinito:

```
ibmcloud resource search 'name:default AND type:resource-group'
```

Ricerca i bind della risorsa per il nome servizio specificato:

```
ibmcloud resource search 'service_name:cloud-object-storage AND type:resource-binding'
```

Ricerca una risorsa con il CRN (Cloud Resource Name) specificato:

```
ibmcloud resource search "crn:\"crn:v1:staging:public:cloudantnosqldb:us-south:s/4948af7e-cc78-4321-998a-e549dd5e9210:41a031cd-e9e5-4c46-975d-9e4a6391322e:cf-service-instance:\""
```

Ricerca una risorsa con la tag specificata:

```
ibmcloud resource search "tags:\"mykey:myvalue\""
```

## ibmcloud resource tags
{: #ibmcloud_resource_tags}

Elenca tutte le tag

```
ibmcloud resource tags [--tag-type TIPO_TAG] [-o, --offset OFFSET] [-l, --limit LIMITE]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-type</dt>
  <dd>Il tipo di tag (valori supportati: user, restricted)</dd>
  <dt>-o, --offset</dt>
  <dd>Numero posizione risorsa iniziale (valore predefinito: 0)</dd>
  <dt>-l, --limit</dt>
  <dd>Numero di risorse da restituire (massimo 10000) (valore predefinito: 10000)</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutte le tag

```
ibmcloud resource tags
```

Elenca tutte le tag limitate

```
ibmcloud resource tags --tag-type restricted
```

## ibmcloud resource tag
{: #ibmcloud_resource_tag}

Mostra i dettagli di una tag

```
ibmcloud resource tag (--tag-name NOME_TAG | --tag-crn CRN_TAG)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della tag "Ray Brown"

```
ibmcloud resource tag --tag-name "Ray Brown"
```

## ibmcloud resource tag-create
{: #ibmcloud_resource_tag_create}

Crea una tag

```
ibmcloud resource tag-create --tag-name NOME_TAG [--tag-type TIPO_TAG]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag</dd>
  <dt>--tag-type</dt>
  <dd>Tipo di tag (valori supportati: user, restricted; valore predefinito: user)</dd>
</dl>

<strong>Esempi</strong>:

Crea una tag utente con il nome think:2018

```
ibmcloud resource tag-create --tag-name think:2018
```

Crea una tag limitata con il nome department:marketing

```
ibmcloud resource tag-create --tag-name "department:marketing" --tag-type restricted
```

Crea una tag utente con il nome "Ray Brown"

```
ibmcloud resource tag-create --tag-name "Ray Brown"
```

Crea una tag limitata con il nome "environment:My Development"

```
ibmcloud resource tag-create --tag-name "environment:My Development" --tag-type restricted
```

## ibmcloud resource tag-delete
{: #ibmcloud_resource_tag_delete}

Elimina una tag

```
ibmcloud resource tag-delete (--tag-name NOME_TAG | --tag-crn CRN_TAG)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
</dl>

<strong>Esempi</strong>:

Elimina la tag "Ray Brown"

```
ibmcloud resource tag-delete --tag-name "Ray Brown"
```

## ibmcloud resource tag-attach
{: #ibmcloud_resource_tag_attach}

Aggiungi una tag a una risorsa

```
ibmcloud resource tag-attach (--tag-name NOME_TAG | --tag-crn CRN_TAG ) --resource-crn CRN_RISORSA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
  <dt>--resource-crn (obbligatorio)</dt>
  <dd>CRN risorsa</dd>
</dl>

<strong>Esempi</strong>:

Aggiungi la tag "Ray Brown" alla risorse il cui crn è resource_example_crn.

```
ibmcloud resource tag-attach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-detach
{: #ibmcloud_resource_tag_detach}

Rimuovi una tag da una risorsa

```
ibmcloud  tag-detach (--tag-name NOME_TAG | --tag-crn CRN_TAG) --resource-crn CRN_RISORSA
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
  <dt>--resource-crn (obbligatorio)</dt>
  <dd>CRN risorsa</dd>
</dl>

<strong>Esempi</strong>:

Rimuovi la tag "Ray Brown" dalla risorse il cui crn è resource_example_crn.

```
ibmcloud resource tag-detach --tag-name "Ray Brown" --resource-crn resource_example_crn
```

## ibmcloud resource tag-update
{: #ibmcloud_resource_tag_update}

Commuta la tag utente alla tag limitata e viceversa

```
ibmcloud tag-update (--tag-name NOME_TAG | --tag-crn CRN_TAG) --tag-type TIPO_TAG
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni comando</strong>:
<dl>
  <dt>--tag-name (obbligatorio)</dt>
  <dd>Nome tag, esclusivo con --tag-crn</dd>
  <dt>--tag-crn (obbligatorio)</dt>
  <dd>CRN tag, esclusivo con --tag-name</dd>
  <dt>--tag-type (obbligatorio)</dt>
  <dd>Tipo di tag</dd>
</dl>

<strong>Esempi</strong>:

Commuta la tag "Ray Brown" alla tag limitata

```
ibmcloud tag-update --tag-name "Ray Brown"  --tag-type restricted
```
