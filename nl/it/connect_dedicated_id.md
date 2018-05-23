---



copyright:

  years: 2015，2018

lastupdated: "2018-04-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Connessione di un ID dedicato al tuo ID IBM pubblico
{: #connect_dedicated_id}

Per accedere a un cloud dedicato in cui è disponibile il servizio IAM pubblico, la CLI {{site.data.keyword.Bluemix_notm}} richiede che accedi con il tuo ID IBM pubblico invece del tuo ID dedicato.


```
  $ bluemix login -a https://api.{dedicated_env}.bluemix.net
  Endpoint API: https://api.{dedicated_env}.bluemix.net

  Il servizio del token IAM pubblico è disponibile nell'ambiente dedicato.
  Accedi con il tuo ID IBM pubblico o utilizza '--no-iam' per accedere soltanto come un utente dedicato.

  Email>
```

Se il tuo ID dedicato è già stato connesso all'ID IBM pubblico, esegue l'autenticazione e l'accesso:

```
  Autenticazione in corso...
  OK

  Connesso all'utente dedicato my_dedicated_id
```

Tuttavia, se il tuo ID dedicato non è stato connesso all'ID IBM pubblico, ti viene richiesto di connetterti manualmente all'ID IBM pubblico:

```
  Stai eseguendo l'accesso con un ID IBM non associato ad alcun utente dedicato.
  Per configurare la connessione, immetti le credenziali dell'utente dedicato.

  Scegli un tipo di credenziale:
  1. Nome utente e password
  2. Codice monouso (Ottienine uno in https://login.{dedicated_env}.bluemix.net.com/passcode)
  Immetti un numero>
```

Seleziona un'opzione per immettere le credenziali per l'ID dedicato. Dopo aver eseguito correttamente l'autenticazione, il tuo ID dedicato verrà connesso al tuo ID IBM pubblico.

## Forza l'accesso al server UAA locale

Per forzare l'accesso al server UAA con un ID dedicato, specifica l'opzione `--no-iam` nel comando `bluemix login`:

```
  $ bluemix login --no-iam
```

## Disconnetti il tuo ID dedicato dall'ID IBM pubblico 

Puoi utilizzare `bluemix iam dedicated-id-disconnect` per disconnettere l'ID IBM pubblico dall'ID dedicato.

```
  $ bluemix iam dedicated-id-disconnect
  Desideri veramente disconnettere my_dedicated_id dall'ID IBM pubblico? (S/N)> s
  Disconnessione utente dedicato my_dedicated_id dall'ID IBM pubblico...
  OK

  Disconnessione in corso...
  OK
```

