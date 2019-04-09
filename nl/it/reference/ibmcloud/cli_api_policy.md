---

copyright:

  years: 2018, 2019


lastupdated: "2019-01-03"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione dell'accesso IAM, delle chiavi API, degli ID servizio e dei gruppi di accesso
{: #ibmcloud_commands_iam}

Utilizza i seguenti comandi per gestire le chiavi API, gli ID servizio, i gruppi di accesso e le politiche di accesso/autorizzazione per utenti, servizi e gruppi di accesso.
{: shortdesc}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire le politiche e le chiavi API.">
  <thead>
  </thead>
  <tbody>
  <tr>
   <td>[ibmcloud iam service-ids](cli_api_policy.html#ibmcloud_iam_service_ids)</td>
   <td>[ibmcloud iam service-id](cli_api_policy.html#ibmcloud_iam_service_id)</td>
   <td>[ibmcloud iam service-id-create](cli_api_policy.html#ibmcloud_iam_service_id_create)</td>
   <td>[ibmcloud iam service-id-update](cli_api_policy.html#ibmcloud_iam_service_id_update)</td>
   <td>[ibmcloud iam service-id-delete](cli_api_policy.html#ibmcloud_iam_service_id_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-id-lock](cli_api_policy.html#ibmcloud_iam_service_id_lock)</td>
   <td>[ibmcloud iam service-id-unlock](cli_api_policy.html#ibmcloud_iam_service_id_unlock)</td>
   <td>[ibmcloud iam api-keys
](cli_api_policy.html#ibmcloud_iam_api_keys)</td>
   <td>[ibmcloud iam api-key-create](cli_api_policy.html#ibmcloud_iam_api_key_create)</td>
   <td>[ibmcloud iam api-key-delete](cli_api_policy.html#ibmcloud_iam_api_key_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam api-key-update](cli_api_policy.html#ibmcloud_iam_api_key_update)</td>
   <td>[ibmcloud iam api-key-lock](cli_api_policy.html#ibmcloud_iam_api_key_lock)</td>
   <td>[ibmcloud iam api-key-unlock](cli_api_policy.html#ibmcloud_iam_api_key_unlock)</td>
   <td>[ibmcloud iam service-api-keys](cli_api_policy.html#ibmcloud_iam_service_api_keys)</td>
   <td>[ibmcloud iam service-api-key](cli_api_policy.html#ibmcloud_iam_service_api_key)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-api-key-create](cli_api_policy.html#ibmcloud_iam_service_api_key_create)</td>
   <td>[ibmcloud iam service-api-key-update](cli_api_policy.html#ibmcloud_iam_service_api_key_update)</td>
   <td>[ibmcloud iam service-api-key-delete](cli_api_policy.html#ibmcloud_iam_service_api_key_delete)</td>
   <td>[ibmcloud iam service-api-key-lock](cli_api_policy.html#ibmcloud_iam_service_api_key_lock)</td>
   <td>[ibmcloud iam service-api-key-unlock](cli_api_policy.html#ibmcloud_iam_service_api_key_unlock)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam service-policies](cli_api_policy.html#ibmcloud_iam_service_policies)</td>
   <td>[ibmcloud iam service-policy](cli_api_policy.html#ibmcloud_iam_service_policy)</td>
   <td>[ibmcloud iam service-policy-create](cli_api_policy.html#ibmcloud_iam_service_policy_create)</td>
   <td>[ibmcloud iam service-policy-update](cli_api_policy.html#ibmcloud_iam_service_policy_update)</td>
   <td>[ibmcloud iam service-policy-delete](cli_api_policy.html#ibmcloud_iam_service_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam user-policies](cli_api_policy.html#ibmcloud_iam_user_policies)</td>
   <td>[ibmcloud iam user-policy](cli_api_policy.html#ibmcloud_iam_user_policy)</td>
   <td>[ibmcloud iam user-policy-create](cli_api_policy.html#ibmcloud_iam_user_policy_create)</td>
   <td>[ibmcloud iam user-policy-update](cli_api_policy.html#ibmcloud_iam_user_policy_update)</td>
   <td>[ibmcloud iam user-policy-delete](cli_api_policy.html#ibmcloud_iam_user_policy_delete)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam oauth-tokens
](cli_api_policy.html#ibmcloud_iam_oauth_tokens)</td>
   <td>[ibmcloud iam dedicated-id-disconnect](cli_api_policy.html#ibmcloud_iam_dedicated_id_disconnect)</td>
   <td>[ibmcloud iam authorization-policy-create](cli_api_policy.html#ibmcloud_iam_authorization_policy_create)</td>
   <td>[ibmcloud iam authorization-policy-delete](cli_api_policy.html#ibmcloud_iam_authorization_policy_delete)</td>
   <td>[ibmcloud iam authorization-policy](cli_api_policy.html#ibmcloud_iam_authorization_policy)</td>
  </tr>
  <tr>
   <td>[ibmcloud iam authorization-policies
](cli_api_policy.html#ibmcloud_iam_authorization_policies)</td>
   <td>[ibmcloud iam access-groups](cli_api_policy.html#ibmcloud_iam_access_groups)</td>
   <td>[ibmcloud iam access-group](cli_api_policy.html#ibmcloud_iam_access_group)</td>
   <td>[ibmcloud iam access-group-create](cli_api_policy.html#ibmcloud_iam_access_group_create)</td>
   <td>[ibmcloud iam access-group-update](cli_api_policy.html#ibmcloud_iam_access_group_update)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-delete](cli_api_policy.html#ibmcloud_iam_access_group_delete)</td>
   <td>[ibmcloud iam access-group-users](cli_api_policy.html#ibmcloud_iam_access_group_users)</td>
   <td>[ibmcloud iam access-group-user-add](cli_api_policy.html#ibmcloud_iam_access_group_user_add)</td>
   <td>[ibmcloud iam access-group-user-remove](cli_api_policy.html#ibmcloud_iam_access_group_user_remove)</td>
   <td>[ibmcloud iam access-group-user-purge](cli_api_policy.html#ibmcloud_iam_access_group_user_purge)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-service-ids](cli_api_policy.html#ibmcloud_iam_access_group_service_ids)</td>
   <td>[ibmcloud iam access-group-service-id-add](cli_api_policy.html#ibmcloud_iam_access_group_service_id_add)</td>
   <td>[ibmcloud iam access-group-service-id-remove](cli_api_policy.html#ibmcloud_iam_access_group_service_id_remove)</td>
   <td>[ibmcloud iam access-group-service-id-purge](cli_api_policy.html#ibmcloud_iam_access_group_service_id_purge)</td>
   <td>[ibmcloud iam access-group-policies](cli_api_policy.html#ibmcloud_iam_access_group_policies)</td>
</tr>
<tr>
   <td>[ibmcloud iam access-group-policy](cli_api_policy.html#ibmcloud_iam_access_group_policy)</td>
   <td>[ibmcloud iam access-group-policy-create](cli_api_policy.html#ibmcloud_iam_access_group_policy_create)</td>
   <td>[ibmcloud iam access-group-policy-update](cli_api_policy.html#ibmcloud_iam_access_group_policy_update)</td>
   <td>[ibmcloud iam access-group-policy-delete](cli_api_policy.html#ibmcloud_iam_access_group_policy_delete)</td>
  </tr>
  </tbody>
  </table>

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Elenca tutti gli ID servizio

```
ibmcloud iam service-ids [--uuid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Mostra l'UUID solo degli ID servizio</dd>
</dl>

<strong>Esempi</strong>:
elenca l'UUID di tutti gli ID servizio sotto l'account corrente

```
ibmcloud iam service-ids --uuid
```

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Visualizza i dettagli di un ID servizio

```
ibmcloud iam service-id (NOME|UUID) [--uuid]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>--uuid</dt>
  <dd>Visualizza l'UUID dell'ID servizio</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli dell'ID servizio `sample-test`

```
ibmcloud iam service-id sample-test
```
Mostra i dettagli dell'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Crea un ID servizio

```
ibmcloud iam service-id-create NOME [-d, --description DESCRIZIONE] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio</dd>
  <dt>-d, --description</dt>
  <dd>Descrizione dell'ID servizio</dd>
  <dt>--lock</dt>
  <dd>Blocca l'ID servizio quando è in fase di creazione</dd>
</dl>

<strong>Esempi</strong>:

Crea un ID servizio con il nome servizio `sample-test` e la descrizione `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```

Crea un ID servizio bloccato con il nome servizio `sample-test` e la descrizione `hello, world!`

```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```

## ibmcloud iam service-id-update

{: #ibmcloud_iam_service_id_update}
Aggiorna un ID servizio

```
ibmcloud iam service-id-update (NOME|UUID) [-n, --name NUOVO_NOME] [-d, --description DESCRIZIONE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del servizio</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione del servizio</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina l'ID servizio `sample-test` come `sample-test-2` senza conferma

```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```

Aggiorna la descrizione del servizio `sample-test`

```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```

Rinomina l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` con `sample-test-3` con una nuova descrizione

```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Elimina un ID servizio

```
ibmcloud iam service-id-delete (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina l'ID servizio `sample-teset` senza conferma

```
ibmcloud iam service-id-delete sample-teset -f
```

Elimina l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Blocca un ID servizio

```
ibmcloud iam service-id-lock (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca ID servizio `sample-teset` senza conferma

```
ibmcloud iam service-id-lock sample-teset -f
```

Blocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Sblocca un ID servizio

```
ibmcloud iam service-id-unlock (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NOME</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Sblocca ID servizio `sample-teset` senza conferma

```
ibmcloud iam service-id-unlock sample-teset -f
```

Sblocca ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Elenca tutte le chiavi API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-keys
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Crea una nuova chiave API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-create NOME [-d DESCRIZIONE] [--file FILE] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da creare.</dd>
<dt>-d <i>DESCRIZIONE</i> (facoltativo)</dt>
<dd>Descrizione della chiave API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Salva le informazioni della chiave API nel file specificato.</dd>
<dt>--lock</dt>
<dd>Blocca la chiave API quando è in fase di creazione</dd>
</dl>

<strong>Esempi</strong>:

Crea una chiave API e salva in un file

```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```

Crea una chiave API bloccata con il nome "test-key"

```
ibmcloud iam api-key-create test-key --lock
```

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Aggiorna una chiave API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-update (NOME|UUID) [-n name] [-d description]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Il vecchio nome della chiave API da aggiornare, esclusivo con UUID,</dd>
<dt>UUID (obbligatorio)</dt>
<dd>L'UUID della chiave API da aggiornare, esclusivo con NOME</dd>
<dt>-n <i>NOME</i> (facoltativo)</dt>
<dd>Il nuovo nome della chiave API</dd>
<dt>-d <i>DESCRIZIONE</i> (facoltativo)</dt>
<dd>La nuova descrizione della chiave API</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la descrizione di una chiave API:

```
ibmcloud iam api-key-update MyKey -d "la nuova descrizione della mia chiave"
```

## ibmcloud api-key-delete
{: #ibmcloud_iam_api_key_delete}

Elimina una chiave API della piattaforma {{site.data.keyword.Bluemix_notm}}

```
ibmcloud iam api-key-delete (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da eliminare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da eliminare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud api-key-lock
{: #ibmcloud_iam_api_key_lock}

Blocca una chiave API della piattaforma

```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da bloccare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da bloccare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza blocco senza conferma.</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API test-api-key

```
ibmcloud iam api-key-lock test-api-key
```

Blocca la chiave API con l'UUID fornito senza conferma

```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Sblocca una chiave API della piattaforma

```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da sbloccare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>L'UUID della chiave API da sbloccare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza sblocco senza conferma.</dd>
</dl>

<strong>Esempi</strong>:

Sblocca la chiave API test-api-key

```
ibmcloud iam api-key-unlock test-api-key
```

Sblocca la chiave API con l'UUID fornito senza conferma

```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Elenca tutte le chiavi API di un servizio

```
ibmcloud iam service-api-keys (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza le chiavi API del servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutte le chiavi API del servizio `sample-service` :

```
ibmcloud iam service-api-keys sample-service
```

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Elenca i dettagli di una chiave API di servizio

```
ibmcloud iam service-api-key (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [--uuid] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>--uuid</dt>
  <dd>Visualizza l'UUID della chiave API di servizio</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza la chiave API del servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della chiave API `sample-key` del servizio `sample-service` :

```
ibmcloud iam service-api-key sample-key sample-service
```

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Crea una chiave API di servizio

```
ibmcloud iam service-api-key-create NOME (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-d, --description DESCRIZIONE] [--file FILE] [-f, --force] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME (obbligatorio)</dt>
  <dd>Nome dell'ID servizio o chiave API del servizio appena creato</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-d, --description</dt>
  <dd>Descrizione della chiave API</dd>
  <dt>--file</dt>
  <dd>Salva le informazioni della chiave API nel file specificato.</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Crea una chiave API `sample-key` per il servizio `sample-service` senza conferma:

```
ibmcloud iam service-api-key-create sample-key sample-service -f
```

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Aggiorna una chiave API di servizio

```
ibmcloud iam service-api-key-update (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO)  [-n, --name NUOVO_NOME] [-d, --description DESCRIZIONE] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome della chiave API di servizio</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione della chiave API di servizio</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina la chiave API di servizio `sample-key` come `new-sample-key` :

```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Elimina una chiave API di servizio

```
ibmcloud iam service-api-key-delete (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-delete sample-key sample-service
```

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Blocca una chiave API del servizio

```
ibmcloud iam service-api-key-lock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-lock sample-key sample-service
```

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Sblocca una chiave API del servizio

```
ibmcloud iam service-api-key-unlock (NOME_CHIAVE_API|UUID_CHIAVE_API) (NOME_ID_SERVIZIO|UUID_ID_SERVIZIO) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_CHIAVE_API (obbligatorio)</dt>
  <dd>Nome della chiave API, esclusivo con UUID_CHIAVE_API</dd>
  <dt>UUID_CHIAVE_API (obbligatorio)</dt>
  <dd>UUID della chiave API, esclusivo con NOME_CHIAVE_API</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Sblocca la chiave API del servizio `sample-key` dell'ID servizio `sample-service`:

```
ibmcloud iam service-api-key-unlock sample-key sample-service
```

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Elenca le politiche dell'utente `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartengono le politiche</dd>
</dl>

<strong>Esempi</strong>:

Elenca le politiche dell'utente `name@example.com`:

```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Visualizza i dettagli di una politica utente

```
ibmcloud iam user-policy NOME_UTENTE ID_POLITICA
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>ID_POLITICA (obbligatorio)</dt>
<dd>ID della politica</dd>
</dl>

<strong>Esempi</strong>:

Elenca la politica `0bb730daa` dell'utente `name@example.com`:

```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Crea una politica utente

```
ibmcloud iam user-policy-create NOME_UTENTE {--file FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>--file <i>FILE</i> (facoltativo)</dt>
<dd>File JSON della definizione della politica</dd>
<dt>--roles <i>NOME_RUOLO1,NOME_RUOLO2...</i> (facoltativo)</dt>
<dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
<dt>--service-name <i>NOME_SERVIZIO</i> (facoltativo)</dt>
<dd>Nome del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--serivce-instance <i>GUID_ISTANZA_SERVIZIO</i> (facoltativo)</dt>
<dd>GUID dell'istanza del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--region <i>REGIONE</i> (facoltativo)</dt>
<dd>Regione della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-type <i>TIPO_RISORSA</i> (facoltativo)</dt>
<dd>Tipo di risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource <i>RISORSA</i> (facoltativo)</dt>
<dd>Risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-group-name <i>NOME_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>Nome del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-id'.</dd>
<dt>--resource-group-id <i>ID_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>ID del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Crea la politica utente per l'utente `name@example.com` dal file JSON di politiche `policy.json`:

```
ibmcloud iam user-policy-create name@example.com --file @policy.json
```

Assegna a `name@example.com` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`:

```
ibmcloud iam user-policy-create name@example.com --roles Administrator --service-name sample-service
```

Assegna a `name@example.com` il ruolo `Editor` per la risorsa `key123` dell'istanza del servizio di esempio con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`:

```
ibmcloud iam user-policy-create name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Assegna a `name@example.com` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Assegna a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-name sample-resource-group
```

Assegna a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-create name@example.com --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-update
{: #ibmcloud_iam_user_policy_update}

Aggiorna una politica utente

```
ibmcloud iam user-policy-update NOME_UTENTE ID_POLITICA {--file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]}
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>ID_POLITICA (obbligatorio)</dt>
<dd>ID della politica da aggiornare</dd>
<dt>--file <i>FILE</i> (facoltativo)</dt>
<dd>File JSON della definizione della politica</dd>
<dt>--roles <i>NOME_RUOLO1,NOME_RUOLO2...</i> (facoltativo)</dt>
<dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
<dt>--service-name <i>NOME_SERVIZIO</i> (facoltativo)</dt>
<dd>Nome del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--serivce-instance <i>GUID_ISTANZA_SERVIZIO</i> (facoltativo)</dt>
<dd>GUID dell'istanza del servizio della definizione della politica, che è esclusivo con l'indicatore '--file'.</dd>
<dt>--region <i>REGIONE</i> (facoltativo)</dt>
<dd>Regione della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-type <i>TIPO_RISORSA</i> (facoltativo)</dt>
<dd>Tipo di risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource <i>RISORSA</i> (facoltativo)</dt>
<dd>Risorsa della definizione della politica, che è esclusiva con l'indicatore '--file'.</dd>
<dt>--resource-group-name <i>NOME_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>Nome del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-id'.</dd>
<dt>--resource-group-id <i>ID_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>ID del gruppo di risorse, che è esclusivo con gli indicatori '--file', '--resource' e '--resource-group-name'.</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica utente con quella nel file JSON

```
ibmcloud iam user-policy-update name@example.com 0bb730daa --file @policy.json
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di amministratore (`Administrator`) per tutte le risorse `sample-service`：

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Administrator --service-name sample-service
```

 Aggiorna la politica utente per assegnare a `name@example.com` il ruolo `Editor` per la risorsa `key123` dell'istanza del servizio di esempio con GUID `d161aeea-fd02-40f8-a487-df1998bd69a9` nella regione `us-south`:

```
ibmcloud iam user-policy-update name@example.com --roles Editor --service-name sample-service --service-instance d161aeea-fd02-40f8-a487-df1998bd69a9 --region us-south --resource-type key --resource key123
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di operatore (`Operator`) per il gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Operator --resource-type resource-group --resource dda27e49d2a1efca58083a01dfde18f6
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse `sample-resource-group`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-name sample-resource-group
```

Aggiorna la politica utente per assegnare a `name@example.com` il ruolo di visualizzatore (`Viewer`) per i membri del gruppo di risorse con ID `dda27e49d2a1efca58083a01dfde18f6`:

```
ibmcloud iam user-policy-update name@example.com user-policy-id --roles Viewer --resource-group-id dda27e49d2a1efca58083a01dfde18f6
```

## ibmcloud iam user-policy-delete
{: #ibmcloud_iam_user_policy_delete}

Elimina una politica utente

```
ibmcloud iam user-policy-delete ID_UTENTE ID_POLITICA [-f, --force]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Elimina la politica utente senza conferma</dd>
</dl>

<strong>Esempi</strong>:
Elimina le politiche `user-policy-id` dell'utente `name@example.com`:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id
```

Elimina le politiche `user-policy-id` dell'utente `name@example.com` senza conferma:

```
ibmcloud iam user-policy-delete name@example.com user-policy-id -f
```

## ibmcloud iam service-policies
{: #ibmcloud_iam_service_policies}

Elenca tutte le politiche di servizio del servizio specificato

```
ibmcloud iam service-policies ID_SERVIZIO [--output FORMATO] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output delle politiche del servizio, al momento è supportato solo JSON.</dd>
  <dt>-f, --force (facoltativo)</dt>
  <dd>Visualizza le politiche di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elenca le politiche del servizio `test`:

```
ibmcloud iam service-policies test
```
Elenca le politiche del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```

## ibmcloud iam service-policy
{: #ibmcloud_iam_service_policy}

Visualizza i dettagli di una politica di servizio

```
ibmcloud iam service-policy ID_SERVIZIO ID_POLITICA [--output FORMATO] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output della politica del servizio, al momento è supportato solo JSON.</dd>
  <dt>-f, --force (facoltativo)</dt>
  <dd>Visualizza la politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Mostra la politica `140798e2-8ea7db3` del servizio `test`:

```
ibmcloud iam service-policies test 140798e2-8ea7db3
```
Mostra la politica `140798e2-8ea7db3` del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policies ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam service-policy-create
{: #ibmcloud_iam_service_policy_create}

Crea una politica di servizio

```
ibmcloud iam service-policy-create ID_SERVIZIO {--file FILE_JSON | -r, --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]} [-f, --force]",
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica. È esclusivo con gli indicatori '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', '--resource-group-name' e '--resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>--service-name</dt>
  <dd>Nome del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource</dt>
  <dd>Risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Crea politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Crea la politica di servizio dal file JSON per il servizio `test`:

```
ibmcloud iam service-policy-create test --file @policy.json
```
Crea la politica di servizio dal file JSON per il servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-create ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 --file @policy.json
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Aggiorna una politica di servizio

```
ibmcloud iam service-policy-update ID_SERVIZIO ID_POLITICA {--file FILE_JSON | [-r, --roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE]} [-f, --force]",
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica. È esclusivo con gli indicatori '-r, --roles', '--service-name', '--service-instance', '--region', '--resource-type', '--resource', 'resource-group-name' e 'resource-group-id'.</dd>
  <dt>-r, --roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui 'ibmcloud iam roles --service NOME_SERVIZIO'. Questa opzione è esclusiva con '--file'.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. È esclusivo con l'indicatore '--file'.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-id'.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del gruppo di risorse. Questa opzione è esclusiva con '--file' e '--resource-group-name'.</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna la politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica di servizio `140798e2-8ea7db3` dal file JSON per il servizio `test`:

```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```
Aggiorna la politica di servizio `140798e2-8ea7db3` dal file JSON per il servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:

```
ibmcloud iam service-policy-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3 --file @policy.json
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Elimina una politica di servizio

```
ibmcloud iam service-policy-delete ID_SERVIZIO ID_POLITICA [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina la politica `140798e2-8ea7db3` del servizio `test`

```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```
Elimina la politica `140798e2-8ea7db3` del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`

```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Richiama e visualizza i token OAuth per la sessione corrente

```
ibmcloud iam oauth-tokens
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiorna e visualizza i token OAuth

```
ibmcloud iam oauth-tokens
```

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Scollega l'ID IBM pubblico dall'ID non IBM dedicato

```
ibmcloud iam dedicated-id-disconnect [-f, --force]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-f, --force</dt>
  <dd>Forza la disconnessione senza conferma</dd>
</dl>

## ibmcloud iam authorization-policy-create
{: #ibmcloud_iam_authorization_policy_create}

Creare una politica di autorizzazione per consentire a un'istanza del servizio di accedere a un'altra istanza del servizio.

```
ibmcloud iam authorization-policy-create NOME_SERVIZIO_ORIGINE NOME_SERVIZIO_DESTINAZIONE NOME_RUOLO1,NOME_RUOLO2... [—-source-service-instance NOME_ISTANZA_SERVIZIO_ORIGINE] [—-target-service-instance NOME_ISTANZA_SERVIZIO_DESTINAZIONE]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_SERVIZIO_ORIGINE</dt>
  <dd>Servizio di origine che può essere autorizzato ad accedere.</dd>
  <dt>NOME_SERVIZIO_DESTINAZIONE</dt>
  <dd>Servizio di destinazione a cui il servizio di origine può essere autorizzate ad accedere.</dd>
  <dt>NOME_RUOLO1,NOME_RUOLO2...</dt>
  <dd>I ruoli che forniscono l'accesso per il servizio di origine.</dd>  
  <dt>—-source-service-instance NOME_ISTANZA_SERVIZIO_ORIGINE</dt>
  <dd>Nome dell'istanza del servizio di origine, se non specificato, tutte le istanza del servizio di origine saranno autorizzate ad accedere.</dd>
  <dt>—-target-service-instance NOME_ISTANZA_SERVIZIO_DESTINAZIONE</dt>
  <dd>Nome dell'istanza del servizio di destinazione, se non specificato, tutte le istanza del servizio di destinazione saranno autorizzate ad accedere.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Elimina una politica di autorizzazione.

```
ibmcloud iam authorization-policy-delete ID_POLITICA_AUTORIZZAZIONE [-f, --force]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_POLITICA_AUTORIZZAZIONE</dt>
  <dd>ID della politica di autorizzazione da eliminare.</dd>
  <dt>-f, --force</dt>
  <dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud iam authorization-policy
{: #ibmcloud_iam_authorization_policy}

Mostra i dettagli di una politica di autorizzazione.

```
ibmcloud iam authorization-policy ID_POLITICA_AUTORIZZAZIONE
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_POLITICA_AUTORIZZAZIONE</dt>
  <dd>ID della politica di autorizzazione da mostrare.</dd>
</dl>

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Elenca le politiche di autorizzazione nell'account corrente.

```
ibmcloud iam authorization-policies
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

## ibmcloud iam access-groups
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
  <dd>Elenca i gruppi di accesso a cui appartiene l'ID del servizio. Questo indicatore è esclusivo per '-u'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i gruppi di accesso:

```
ibmcloud iam access-groups
```

## ibmcloud iam access-group
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

## ibmcloud iam access-group-create
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

## ibmcloud iam access-group-update
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

## ibmcloud iam access-group-delete
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

## ibmcloud iam access-group-users
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

## ibmcloud iam access-group-user-add
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

## ibmcloud iam access-group-user-remove
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

## ibmcloud iam access-group-user-purge
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

## ibmcloud iam access-group-service-ids
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

## ibmcloud iam access-group-service-id-add
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

## ibmcloud iam access-group-service-id-remove
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

## ibmcloud iam access-group-service-id-purge
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

## ibmcloud iam access-group-policies
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

## ibmcloud iam access-group-policy
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

## ibmcloud iam access-group-policy-create
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

## ibmcloud iam access-group-policy-update
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

## ibmcloud iam access-group-policy-delete
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
