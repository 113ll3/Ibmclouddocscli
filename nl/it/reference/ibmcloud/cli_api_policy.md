---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-18"

keywords: iam, iam access, api keys, service ids, access groups, authorization policy, ibmcloud iam, cli, manage keys, manage service ids, manage iam users cli, iam cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:note: .note}

# Gestione dell'accesso IAM, delle chiavi API, degli ID servizio e dei gruppi di accesso
{: #ibmcloud_commands_iam}

Utilizza i seguenti comandi per gestire le chiavi API, gli ID servizio, i gruppi di accesso e le politiche di autorizzazione per utenti, servizi e gruppi di accesso.
{: shortdesc}

## ibmcloud iam service-ids
{: #ibmcloud_iam_service_ids}

Elenca tutti gli ID servizio:
```
ibmcloud iam service-ids [--uuid] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--uuid</dt>
  <dd>Mostra l'UUID solo degli ID servizio</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca l'UUID di tutti gli ID servizio nell'account corrente:
```
ibmcloud iam service-ids --uuid
```
{: codeblock}

## ibmcloud iam service-id
{: #ibmcloud_iam_service_id}

Visualizza i dettagli di un ID servizio:
```
ibmcloud iam service-id (NAME|UUID) [--uuid] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NAME</dd>
  <dt>--uuid</dt>
  <dd>Visualizza l'UUID dell'ID servizio</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli dell'ID servizio `sample-test`:
```
ibmcloud iam service-id sample-test
```
{: codeblock}

Mostra i dettagli dell'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-create
{: #ibmcloud_iam_service_id_create}

Crea un ID servizio:
```
ibmcloud iam service-id-create NAME [-d, --description DESCRIPTION] [--lock] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome del servizio</dd>
  <dt>-d, --description</dt>
  <dd>Descrizione dell'ID servizio</dd>
  <dt>--lock</dt>
  <dd>Blocca l'ID servizio quando è in fase di creazione</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Crea un ID servizio con il nome servizio `sample-test` e la descrizione `hello, world!`:
```
ibmcloud iam service-id-create sample-test -d 'hello, world!'
```
{: codeblock}

Crea un ID servizio bloccato con il nome servizio `sample-test` e la descrizione `hello, world!`:
```
ibmcloud iam service-id-create sample-test -d 'hello, world!' --lock
```
{: codeblock}

## ibmcloud iam service-id-update
{: #ibmcloud_iam_service_id_update}

Aggiorna un ID servizio:
```
ibmcloud iam service-id-update (NAME|UUID) [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NAME</dd>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del servizio</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione del servizio</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina l'ID servizio `sample-test` in `sample-test-2` senza conferma:
```
ibmcloud iam service-id-update sample-test -n sample-test-2 -f
```
{: codeblock}

Aggiorna la descrizione del servizio `sample-test`:
```
ibmcloud iam service-id-update sample-test -d 'hello, friend!'
```
{: codeblock}

Rinomina l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976` in `sample-test-3` con la nuova descrizione:
```
ibmcloud iam service-id-update ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 -n sample-test-3 -d 'hello, my friends!'
```
{: codeblock}

## ibmcloud iam service-id-delete
{: #ibmcloud_iam_service_id_delete}

Elimina un ID servizio:
```
ibmcloud iam service-id-delete (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Elimina senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elimina l'ID servizio `sample-teset` senza conferma:
```
ibmcloud iam service-id-delete sample-teset -f
```
{: codeblock}

Elimina l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-lock
{: #ibmcloud_iam_service_id_lock}

Blocca un ID servizio:
```
ibmcloud iam service-id-lock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Blocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Blocca l'ID servizio `sample-teset` senza conferma:
```
ibmcloud iam service-id-lock sample-teset -f
```
{: codeblock}

Blocca l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id-lock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam service-id-unlock
{: #ibmcloud_iam_service_id_unlock}

Sblocca un ID servizio:
```
ibmcloud iam service-id-unlock (NAME|UUID) [-f, --force]
```
{: codeblock}

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome del servizio, esclusivo con UUID</dd>
  <dt>UUID (obbligatorio)</dt>
  <dd>UUID del servizio, esclusivo con NAME</dd>
  <dt>-f, --force</dt>
  <dd>Sblocca senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Sblocca l'ID servizio `sample-teset` senza conferma:
```
ibmcloud iam service-id-unlock sample-teset -f
```
{: codeblock}

Sblocca l'ID servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-id-unlock ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976
```
{: codeblock}

## ibmcloud iam api-keys
{: #ibmcloud_iam_api_keys}

Elenca tutte le chiavi API della piattaforma {{site.data.keyword.cloud_notm}}:
```
ibmcloud iam api-keys [--output FORMAT]
```
{: codeblock}

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud iam api-key-create
{: #ibmcloud_iam_api_key_create}

Crea una chiave API della piattaforma {{site.data.keyword.cloud_notm}}:
```
ibmcloud iam api-key-create NAME [-d DESCRIPTION] [--file FILE] [--lock] [--output FORMAT]
```

L'utilizzo dell'accesso alla CLI {{site.data.keyword.cloud_notm}} con una chiave API non funziona con la chiave API SL legacy disponibile in `control.softlayer.com`. Per l'accesso alla CLI {{site.data.keyword.cloud_notm}} con una chiave API è richiesto un account {{site.data.keyword.cloud_notm}} aggiornato in cui l'infrastruttura è gestita tramite [cloud.ibm.com](https://cloud.ibm.com/registration){: new_window} ![Icona link esterno](../../../icons/launch-glyph.svg "Icona link esterno").
{: note}

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome della chiave API da creare.</dd>
<dt>-d <i>DESCRIPTION</i> (facoltativo)</dt>
<dd>Descrizione della chiave API</dd>
<dt>--file <i>FILE</i></dt>
<dd>Salva le informazioni della chiave API nel file specificato.</dd>
<dt>--lock</dt>
<dd>Blocca la chiave API quando viene creata.</dd>
<dt>--output FORMAT</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Crea una chiave API e salva in un file:
```
ibmcloud iam api-key-create MyKey -d "this is my API key" --file key_file
```
{: codeblock}

Crea una chiave API bloccata con il nome "test-key":
```
ibmcloud iam api-key-create test-key --lock
```
{: codeblock}

## ibmcloud iam api-key-update
{: #ibmcloud_iam_api_key_update}

Aggiorna una chiave API della piattaforma {{site.data.keyword.cloud_notm}}:
```
ibmcloud iam api-key-update (NAME|UUID) [-n name] [-d description] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NAME (obbligatorio)</dt>
<dd>Il vecchio nome della chiave API da aggiornare, esclusivo con UUID,</dd>
<dt>UUID (obbligatorio)</dt>
<dd>L'UUID della chiave API da aggiornare, esclusivo con NAME</dd>
<dt>-n <i>NAME</i> (facoltativo)</dt>
<dd>Il nuovo nome della chiave API</dd>
<dt>-d <i>DESCRIPTION</i> (facoltativo)</dt>
<dd>La nuova descrizione della chiave API</dd>
<dt>--output FORMAT</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la descrizione di una chiave API:
```
ibmcloud iam api-key-update MyKey -d "la nuova descrizione della mia chiave"
```
{: codeblock}

## ibmcloud iam api-key-delete
{: #ibmcloud_iam_api_key_delete}

Elimina una chiave API della piattaforma {{site.data.keyword.cloud_notm}}:
```
ibmcloud iam api-key-delete (NOME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NAME (obbligatorio)</dt>
<dd>Nome della chiave API da eliminare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da eliminare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza l'eliminazione senza conferma.</dd>
</dl>

## ibmcloud iam api-key-lock
{: #ibmcloud_iam_api_key_lock}

Blocca una chiave API della piattaforma:
```
ibmcloud iam api-key-lock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NAME (obbligatorio)</dt>
<dd>Nome della chiave API da bloccare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>UUID della chiave API da bloccare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza blocco senza conferma.</dd>
</dl>

<strong>Esempi</strong>:

Blocca la chiave API test-api-key:
```
ibmcloud iam api-key-lock test-api-key
```
{: codeblock}

Blocca la chiave API con l'UUID fornito senza conferma:
```
ibmcloud iam api-key-lock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}s

## ibmcloud iam api-key-unlock
{: #ibmcloud_iam_api_key_unlock}

Sblocca una chiave API della piattaforma:
```
ibmcloud iam api-key-unlock (NAME|UUID) [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>NAME (obbligatorio)</dt>
<dd>Nome della chiave API da sbloccare, esclusivo con UUID</dd>
<dt>UUID (obbligatorio)</dt>
<dd>L'UUID della chiave API da sbloccare, esclusivo con NOME</dd>
<dt>-f, --force</dt>
<dd>Forza sblocco senza conferma.</dd>
</dl>

<strong>Esempi</strong>:

Sblocca la chiave API test-api-key:
```
ibmcloud iam api-key-unlock test-api-key
```
{: codeblock}

Sblocca la chiave API con l'UUID fornito senza conferma:
```
ibmcloud iam api-key-unlock ApiKey-18f773b0-db53-43f1-ad68-92c667c218fe --force
```
{: codeblock}

## ibmcloud iam service-api-keys
{: #ibmcloud_iam_service_api_keys}

Elenca tutte le chiavi API di un servizio:
```
ibmcloud iam service-api-keys (SERVICE_ID_NAME|SERVICE_ID_UUID) [--output FORMAT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza le chiavi API del servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutte le chiavi API del servizio `sample-service` :
```
ibmcloud iam service-api-keys sample-service
```
{: codeblock}

## ibmcloud iam service-api-key
{: #ibmcloud_iam_service_api_key}

Elenca i dettagli di una chiave API di servizio:
```
ibmcloud iam service-api-key (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID) [--uuid] [--output FORMAT] [-f, --force]
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
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
  <dt>-f, --force</dt>
  <dd>Visualizza la chiave API del servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della chiave API `sample-key` del servizio `sample-service` :
```
ibmcloud iam service-api-key sample-key sample-service
```
{: codeblock}

## ibmcloud iam service-api-key-create
{: #ibmcloud_iam_service_api_key_create}

Crea una chiave API di servizio:
```
ibmcloud iam service-api-key-create NAME (SERVICE_ID_NAME|SERVICE_ID_UUID) [-d, --description DESCRIPTION] [--file FILE] [--output FORMAT] [-f, --force] [--lock]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>NAME (obbligatorio)</dt>
  <dd>Nome dell'ID servizio o chiave API del servizio appena creato</dd>
  <dt>NOME_ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome dell'ID servizio, esclusivo con UUID_ID_SERVIZIO</dd>
  <dt>UUID_ID_SERVIZIO (obbligatorio)</dt>
  <dd>UUID dell'ID servizio, esclusivo con NOME_ID_SERVIZIO</dd>
  <dt>-d, --description</dt>
  <dd>Descrizione della chiave API</dd>
  <dt>--file</dt>
  <dd>Salva le informazioni della chiave API nel file specificato.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
  <dt>-f, --force</dt>
  <dd>Forza la creazione senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Crea una chiave API `sample-key` per il servizio `sample-service` senza conferma:
```
ibmcloud iam service-api-key-create sample-key sample-service -f
```
{: codeblock}

## ibmcloud iam service-api-key-update
{: #ibmcloud_iam_service_api_key_update}

Aggiorna una chiave API di servizio:
```
ibmcloud iam service-api-key-update (APIKEY_NAME|APIKEY_UUID) (SERVICE_ID_NAME|SERVICE_ID_UUID)  [-n, --name NEW_NAME] [-d, --description DESCRIPTION] [--output FORMAT] [-f, --force]
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
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Rinomina la chiave API di servizio `sample-key` come `new-sample-key` :
```
ibmcloud iam service-api-key-update sample-key sample-service -n new-sample-key
```
{: codeblock}

## ibmcloud iam service-api-key-delete
{: #ibmcloud_iam_service_api_key_delete}

Elimina una chiave API di servizio:
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
{: codeblock}

## ibmcloud iam service-api-key-lock
{: #ibmcloud_iam_service_api_key_lock}

Blocca una chiave API di servizio:
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
{: codeblock}

## ibmcloud iam service-api-key-unlock
{: #ibmcloud_iam_service_api_key_unlock}

Sblocca una chiave API di servizio:
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
{: codeblock}

## ibmcloud iam user-policies
{: #ibmcloud_iam_user_policies}

Elenca le politiche di un utente
```
ibmcloud iam user-policies USER_NAME [--output FORMAT]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartengono le politiche</dd>
<dt>--output FORMAT</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:
 
Elenca le politiche dell'utente `name@example.com`:
```
ibmcloud iam user-policies name@example.com
```

## ibmcloud iam user-policy
{: #ibmcloud_iam_user_policy}

Visualizza i dettagli di una politica utente:
```
ibmcloud iam user-policy USER_NAME POLICY_ID [--output FORMAT]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>ID_POLITICA (obbligatorio)</dt>
<dd>ID della politica</dd>
<dt>--output FORMAT</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca la politica `0bb730daa` dell'utente `name@example.com`:
```
ibmcloud iam user-policy name@example.com 0bb730daa
```

## ibmcloud iam user-policy-create
{: #ibmcloud_iam_user_policy_create}

Crea una politica utente:
```
ibmcloud iam user-policy-create USER_NAME {--file JSON_FILE | --roles ROLE_NAME1,ROLE_NAME2... [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE] [--account-management]} [--output FORMATO]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni del comando</strong>:
<dl>
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>--file <i>FILE</i> (facoltativo)</dt>
<dd>File JSON della definizione della politica</dd>
<dt>--roles <i>NOME_RUOLO1,NOME_RUOLO2...</i> (facoltativo)</dt>
<dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui `ibmcloud iam roles --service SERVICE_NAME`. Questa opzione è esclusiva con `--file`.</dd>
<dt>--service-name <i>NOME_SERVIZIO</i> (facoltativo)</dt>
<dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--serivce-instance <i>GUID_ISTANZA_SERVIZIO</i> (facoltativo)</dt>
<dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--region <i>REGIONE</i> (facoltativo)</dt>
<dd>Regione della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--resource-type <i>TIPO_RISORSA</i> (facoltativo)</dt>
<dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--resource <i>RISORSA</i> (facoltativo)</dt>
<dd>Risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--resource-group-name <i>NOME_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>Nome del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con gli indicatori `--file`, `--resource` e `--resource-group-id`.</dd>
<dt>--resource-group-id <i>ID_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>ID del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con gli indicatori `--file`, `--resource` e `--resource-group-name`.</dd>
<dt>--account-management (facoltativo)</dt>
<dd>Concede l'accesso a tutti i servizi di gestione dell'account.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
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

Aggiorna una politica utente:
```
ibmcloud iam user-policy-update USER_NAME POLICY_ID {--file JSON_FILE | [--roles ROLE_NAME1,ROLE_NAME2...] [--service-name NOME_SERVIZIO] [--service-instance GUID_ISTANZA_SERVIZIO] [--region REGIONE] [--resource-type TIPO_RISORSA] [--resource RISORSA] [--resource-group-name NOME_GRUPPO_RISORSE] [--resource-group-id ID_GRUPPO_RISORSE] [--account-management]} [--output FORMATO]
```

<strong>Prerequisiti</strong>: Endpoint, Accesso, Account di destinazione

<strong>Opzioni comando</strong>:
<dt>NOME_UTENTE (obbligatorio)</dt>
<dd>Nome utente a cui appartiene la politica</dd>
<dt>ID_POLITICA (obbligatorio)</dt>
<dd>ID della politica da aggiornare</dd>
<dt>--file <i>FILE</i> (facoltativo)</dt>
<dd>File JSON della definizione della politica</dd>
<dt>--roles <i>NOME_RUOLO1,NOME_RUOLO2...</i> (facoltativo)</dt>
<dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui `ibmcloud iam roles --service SERVICE_NAME`. Questa opzione è esclusiva con `--file`.</dd>
<dt>--service-name <i>NOME_SERVIZIO</i> (facoltativo)</dt>
<dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--serivce-instance <i>GUID_ISTANZA_SERVIZIO</i> (facoltativo)</dt>
<dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--region <i>REGIONE</i> (facoltativo)</dt>
<dd>Regione della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--resource-type <i>TIPO_RISORSA</i> (facoltativo)</dt>
<dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--resource <i>RISORSA</i> (facoltativo)</dt>
<dd>Risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
<dt>--resource-group-name <i>NOME_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>Nome del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con gli indicatori `--file`, `--resource` e `--resource-group-id`.</dd>
<dt>--resource-group-id <i>ID_GRUPPO_RISORSE</i> (facoltativo)</dt>
<dd>ID del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con gli indicatori `--file`, `--resource` e `--resource-group-name`.</dd>
<dt>--account-management (facoltativo)</dt>
<dd>Concede l'accesso a tutti i servizi di gestione dell'account.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
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

Elenca tutte le politiche di servizio del servizio specificato:
```
ibmcloud iam service-policies ID_SERVIZIO [--output FORMATO] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>--output FORMAT</dt>
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

Visualizza i dettagli di una politica di servizio:
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
  <dt>--output FORMAT</dt>
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

Crea una politica di servizio:
```
ibmcloud iam service-policy-create ID_SERVIZIO {--file FILE_JSON | -r, --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica. Questa opzione è esclusiva con gli indicatori `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `--resource-group-name` e `--resource-group-id`.</dd>
  <dt>-r, --roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui `ibmcloud iam roles --service SERVICE_NAME`. Questa opzione è esclusiva con `--file`.</dd>
  <dt>--service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>--service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>--resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>--resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-id`.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-name`.</dd>
  <dt>--account-management (facoltativo)</dt>
  <dd>Concede l'accesso a tutti i servizi di gestione dell'account</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
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

Concede al servizio `test` il ruolo `Administrator` per tutti i servizi di gestione dell'account.
```
ibmcloud iam service-policy-create test --roles Administrator --account-management
```

Concede al servizio `test` il ruolo `Viewer` per tutte le risorse nell'account:
```
ibmcloud iam service-policy-create test --roles Viewer
```

## ibmcloud iam service-policy-update
{: #ibmcloud_iam_service_policy_update}

Aggiorna una politica di servizio:
```
ibmcloud iam service-policy-update SERVICE_ID POLICY_ID {--file JSON_FILE | [-r, --roles ROLE_NAME1,ROLE_NAME2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID] [--account-management]} [--output FORMAT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_SERVIZIO (obbligatorio)</dt>
  <dd>Nome o UUID dell'ID del servizio</dd>
  <dt>ID_POLITICA (obbligatorio)</dt>
  <dd>ID della politica di servizio<dd>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica. Questa opzione è esclusiva con gli indicatori `-r, --roles`, `--service-name`, `--service-instance`, `--region`, `--resource-type`, `--resource`, `resource-group-name` e `resource-group-id`.</dd>
  <dt>-r, --roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui `ibmcloud iam roles --service SERVICE_NAME`. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con l'indicatore `--file`.</dd>
  <dt>--resource-group-name</dt>
  <dd>Nome del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-id`.</dd>
  <dt>--resource-group-id </dt>
  <dd>ID del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-name`.</dd>
  <dt>--account-management (facoltativo)</dt>
  <dd>Concede l'accesso a tutti i servizi di gestione dell'account</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
  <dt>-f, --force</dt>
  <dd>Aggiorna la politica di servizio senza conferma</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la politica di servizio `140798e2-8ea7db3` dal file JSON per il servizio `test`:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

Aggiorna la politica di servizio `140798e2-8ea7db3` dal file JSON per il servizio `test`:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --file @policy.json
```

Aggiorna la politica del servizio `140798e2-8ea7db3` per concedere al servizio `test` il ruolo `Administrator` per tutti i servizi di gestione dell'account.
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Administrator --account-management
```

Aggiorna la politica del servizio `140798e2-8ea7db3` per concedere al servizio `test` il ruolo `Viewer` per tutte le risorse nell'account:
```
ibmcloud iam service-policy-update test 140798e2-8ea7db3 --roles Viewer
```

## ibmcloud iam service-policy-delete
{: #ibmcloud_iam_service_policy_delete}

Elimina una politica di servizio:
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

Elimina la politica `140798e2-8ea7db3` del servizio `test`:
```
ibmcloud iam service-policy-delete test 140798e2-8ea7db3
```

Elimina la politica `140798e2-8ea7db3` del servizio `ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976`:
```
ibmcloud iam service-policy-delete ServiceId-cb258cb9-8de3-4ac0-9aec-b2b2d27ac976 140798e2-8ea7db3
```

## ibmcloud iam oauth-tokens
{: #ibmcloud_iam_oauth_tokens}

Richiama e visualizza i token OAuth per la sessione corrente:
```
ibmcloud iam oauth-tokens [--output FORMAT]
```
{: codeblock}

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna e visualizza i token OAuth:
```
ibmcloud iam oauth-tokens
```
{: codeblock}

## ibmcloud iam roles
{: #ibmcloud_iam_roles}

Elenca i ruoli definiti della piattaforma e del servizio:
```
ibmcloud iam roles [--service SERVICE_NAME] [--output FORMAT]
```
{: codeblock}

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--service SERVICE_NAME</dt>
  <dd>Nome del servizio, se non specificato elenca solo i ruoli definiti dalla piattaforma.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca i ruoli della piattaforma
```
ibmcloud iam roles
```

Elenca i ruoli per il servizio `cloudantnosql` in JSON:
```
ibmcloud iam roles --service cloudantnosql --output JSON
```
{: codeblock}

## ibmcloud iam dedicated-id-disconnect
{: #ibmcloud_iam_dedicated_id_disconnect}

Disconnetti l'ID IBM pubblico dall'ID non IBM dedicato:
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

Crea una politica di autorizzazione per consentire a un'istanza del servizio di accedere a un'altra istanza del servizio:

```
ibmcloud iam authorization-policy-create NOME_SERVIZIO_ORIGINE NOME_SERVIZIO_DESTINAZIONE NOME_RUOLO1,NOME_RUOLO2... [—-source-service-instance-name NOME_ISTANZA_SERVIZIO_DI_ORIGINE | --source-service-instance-id ID_ISTANZA_SERVIZIO_DI_ORIGINE] [--source-resource-type TIPO_DI_RISORSA] [—-target-service-instance-name NOME_ISTANZA_SERVIZIO_DI_DESTINAZIONE] [--target-resource-type TIPO_DI_RISORSA | --target-service-instance-id ID_ISTANZA_SERVIZIO_DI_DESTINAZIONE] [--output FORMATO]
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
  <dt>--source-service-instance-name NOME_ISTANZA_SERVIZIO_DI_ORIGINE</dt>
  <dd>Nome dell'istanza del servizio di origine, si esclude a vicenda con `--source-service-instance-id`. Se non specificato, tutte le istanze del servizio di origine sono autorizzate ad accedere.</dd>
  <dt>--source-service-instance-id ID_ISTANZA_SERVIZIO_DI_ORIGINE</dt>
  <dd>ID dell'istanza del servizio di origine, si esclude a vicenda con `--source-service-instance-name`. Se non specificato, tutte le istanze del servizio di origine sono autorizzate ad accedere.</dd>
  <dt>--source-resource-type</dt>
  <dd>Il tipo di risorsa del servizio di origine</dd>
  <dt>--target-service-instance-name NOME_ISTANZA_SERVIZIO_DI_DESTINAZIONE</dt>
  <dd>Il nome dell'istanza del servizio di destinazione, si esclude a vicenda con `--target-service-instance-id`. Se non specificato, tutte le istanze del servizio di destinazione sono autorizzate ad accedere.</dd>
  <dt>--target-service-instance-id ID_ISTANZA_SERVIZIO_DI_DESTINAZIONE</dt>
  <dd>L'ID dell'istanza del servizio di destinazione, si esclude a vicenda con `--target-service-instance-name`. Se non specificato, tutte le istanze del servizio di destinazione sono autorizzate ad accedere.</dd>
  <dt>--target-resource-type</dt>
  <dd>Il tipo di risorsa del servizio di destinazione</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud iam authorization-policy-delete
{: #ibmcloud_iam_authorization_policy_delete}

Elimina una politica di autorizzazione:
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

Mostra i dettagli di una politica di autorizzazione:
```
ibmcloud iam authorization-policy AUTHORIZATION_POLICY_ID [--output FORMAT]
```

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>ID_POLITICA_AUTORIZZAZIONE</dt>
  <dd>ID della politica di autorizzazione da mostrare.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl> 

## ibmcloud iam authorization-policies
{: #ibmcloud_iam_authorization_policies}

Elenca le politiche di autorizzazione nell'account corrente:
```
ibmcloud iam authorization-policies [--output FORMAT]
```
{: codeblock}

<strong>Prerequisiti</strong>: Accesso, Destinazione

<strong>Opzioni comando</strong>:
   <dl>
   <dt>--output FORMATO (facoltativo)</dt>
   <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
   </dl>

## ibmcloud iam access-groups
{: #ibmcloud_iam_access_groups}

Elenca i gruppi di accesso nell'account corrente:
```
ibmcloud iam access-groups [-u USER_NAME | -s SERVICE_ID_NAME] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-u</dt>
  <dd>Elenca i gruppi di accesso a cui appartiene l'utente. Questo indicatore è esclusivo per '-s'.</dd>
  <dt>-s</dt>
  <dd>Elenca i gruppi di accesso a cui appartiene l'ID del servizio. Questo indicatore è esclusivo per '-u'.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i gruppi di accesso:
```
ibmcloud iam access-groups
```
{: codeblock}

## ibmcloud iam access-group
{: #ibmcloud_iam_access_group}

Mostra i dettagli di un gruppo di accesso:
```
ibmcloud iam access-group GROUP_NAME [--id] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-id</dt>
  <dd>Mostra solo l'ID</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli del gruppo di accesso `example_group`:
```
ibmcloud iam access-group example_group
```

## ibmcloud iam access-group-create
{: #ibmcloud_iam_access_group_create}

Crea un gruppo di accesso:
```
ibmcloud iam access-group-create GROUP_NAME [-d, --description DESCRIPTION] [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-d, --description</dt>
  <dd>Descrizione del gruppo di accesso</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Crea un gruppo di accesso `example_group`:
```
ibmcloud iam access-group-create example_group -d "example access group"
```

## ibmcloud iam access-group-update
{: #ibmcloud_iam_access_group_update}

Aggiorna un gruppo di accesso:
```
ibmcloud iam access-group-update GROUP_NAME [-n, --name NEW_NAME] [-d, --description NEW_DESCRIPTION] [--output FORMAT] [-f, --force]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-n, --name</dt>
  <dd>Nuovo nome del gruppo di accesso</dd>
  <dt>-d, --description</dt>
  <dd>Nuova descrizione</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
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

Elenca gli utenti in un gruppo di accesso:
```
ibmcloud iam access-group-users GROUP_NAME [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>--output FORMAT</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti gli utenti nel gruppo di accesso `example_group`:
```
ibmcloud iam access-group-users example_group
```

## ibmcloud iam access-group-user-add
{: #ibmcloud_iam_access_group_user_add}

Aggiungi utenti a un gruppo di accesso:
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

Rimuovi un utente da un gruppo di accesso:
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

Rimuovi l'utente da tutti i gruppi di accesso:
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

Elenca gli ID del servizio in un gruppo di accesso:
```
ibmcloud iam access-group-service-ids GROUP_NAME [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
<dt>--output FORMAT</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti gli ID del servizio nel gruppo di accesso `example_group`:
```
ibmcloud iam access-group-service-ids example_group
```

## ibmcloud iam access-group-service-id-add
{: #ibmcloud_iam_access_group_service_id_add}

Aggiungi l'ID del servizio a un gruppo di accesso:
```
ibmcloud iam access-group-service-id-add NOME_GRUPPO NOME_ID_SERVIZIO [NOME_ID_SERVIZIO2...]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Aggiungi l'ID del servizio `example-service` al gruppo di accesso `example_group`:
```
ibmcloud iam access-group-service-id-add example_group example-service
```

## ibmcloud iam access-group-service-id-remove
{: #ibmcloud_iam_access_group_service_id_remove}

Rimuovi un ID del servizio da un gruppo di accesso:
```
ibmcloud iam access-group-service-id-remove NOME_GRUPPO NOME_ID_SERVIZIO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
</dl>

<strong>Esempi</strong>:

Rimuovi l'ID del servizio `example-service` dal gruppo di accesso `example_group`:
```
ibmcloud iam access-group-service-id-remove example_group example-service
```

## ibmcloud iam access-group-service-id-purge
{: #ibmcloud_iam_access_group_service_id_purge}

Rimuovi l'ID del servizio da tutti i gruppi di accesso:
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

Rimuovi l'ID del servizio `example-service` da tutti i gruppi di accesso:

```
ibmcloud iam access-group-service-id-purge example --force
```

## ibmcloud iam access-group-policies
{: #ibmcloud_iam_access_group_policies}

Elenca le politiche di un gruppo di accesso:
```
ibmcloud iam access-group-policies GROUP_NAME [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutte le politiche del gruppo di accesso `example_group`:
```
ibmcloud iam access-group-policies example_group
```

## ibmcloud iam access-group-policy
{: #ibmcloud_iam_access_group_policy}

Mostra i dettagli di una politica del gruppo di accesso:
```
ibmcloud iam access-group-policy GROUP_NAME POLICY_ID [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

<strong>Esempi</strong>:

Mostra i dettagli della politica `51b9717e-76b0-4f6a-bda7-b8132431f926` del gruppo di accesso `example_group`:
```
ibmcloud iam access-group-policy example_group 51b9717e-76b0-4f6a-bda7-b8132431f926
```

## ibmcloud iam access-group-policy-create
{: #ibmcloud_iam_access_group_policy_create}

Crea una politica del gruppo di accesso:
```
ibmcloud iam access-group-policy-create NOME_GRUPPO {--file @FILE_JSON | --roles NOME_RUOLO1,NOME_RUOLO2... [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica</dd>
  <dt>-roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui `ibmcloud iam roles --service SERVICE_NAME`. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-id`.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-name`.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
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

Aggiorna una politica del gruppo di accesso:
```
ibmcloud iam access-group-policy-update ID_POLITICA_NOME_GRUPPO {--file FILE_JSON | [--roles NOME_RUOLO1,NOME_RUOLO2...] [--service-name SERVICE_NAME] [--service-instance SERVICE_INSTANCE_GUID] [--region REGION] [--resource-type RESOURCE_TYPE] [--resource RESOURCE] [--resource-group-name RESOURCE_GROUP_NAME] [--resource-group-id RESOURCE_GROUP_ID]} [--output FORMAT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--file</dt>
  <dd>File JSON della definizione della politica</dd>
  <dt>--roles</dt>
  <dd>Nomi dei ruoli della definizione della politica. Per i ruoli supportati di uno specifico servizio, esegui `ibmcloud iam roles --service SERVICE_NAME`. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-service-name</dt>
  <dd>Nome del servizio della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-service-instance <i>GUID_ISTANZA_SERVIZIO</i></dt>
  <dd>GUID dell'istanza del servizio della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-region</dt>
  <dd>Regione della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-resource-type</dt>
  <dd>Tipo di risorsa della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-resource</dt>
  <dd>Risorsa della definizione della politica. Questa opzione è esclusiva con `--file`.</dd>
  <dt>-resource-group-name</dt>
  <dd>Nome del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-id`.</dd>
  <dt>-resource-group-id</dt>
  <dd>ID del gruppo di risorse. `*` indica tutti i gruppi di risorse. Questa opzione è esclusiva con `--file` e `--resource-group-name`.</dd>
  <dt>--output FORMAT</dt>
  <dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
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

Elimina a una politica del gruppo di accesso:
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
