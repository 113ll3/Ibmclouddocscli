---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-07"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestione degli utenti dell'infrastruttura classica 
{: #manage-sl-users}

Utilizza i seguenti comandi per gestire gli utenti dell'infrastruttura classica {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

Per creare un utente: 
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--email</dt>
<dd>Indirizzo email per questo utente. Obbligatorio per la creazione. </dd>
<dt>--password</dt>
<dd>Password da impostare per questo utente. Se non viene fornita alcuna password, all'utente viene inviata un'email per generarne una, che scade in 24 ore. Specifica l'opzione '-p generate' per generare una password. Le password devono avere 8+ caratteri, caratteri maiuscoli e minuscoli, un numero e un simbolo. </dd>
<dt>--from-user</dt>
<dd>L'utente di base da utilizzare come modello per la creazione di questo utente. L'impostazione predefinita è utilizzare l'utente che sta eseguendo questo comando. Le informazioni fornite in --template sostituiscono questo template. </dd>
<dt>--template</dt>
<dd>Una stringa JSON che descrive https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/. </dd>
<dt>--api-key</dt>
<dd>Crea una chiave API per questo utente. </dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

Imposta lo stato di un utente su `CANCEL_PENDING`, che disabilita immediatamente l'account e viene infine rimosso dall'account mediante un processo interno automatizzato. 
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

Per visualizzare i dettagli di un utente: 
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--keys</dt>
<dd>Mostra la chiave API dell'utente. </dd>
<dt>--permissions</dt>
<dd>Visualizza le autorizzazioni assegnate a questo utente. Gli utenti master non visualizzeranno alcuna autorizzazione. </dd>
<dt>--hardware</dt>
<dd>Visualizza l'hardware a cui ha accesso questo utente. </dd>
<dt>--virtual</dt>
<dd>Visualizza i guest virtuali a cui ha accesso questo utente. </dd>
<dt>--logins</dt>
<dd>Mostra la cronologia di accesso di questo utente per gli ultimi 30 giorni. </dd>
<dt>--events</dt>
<dd>Mostra il log di controllo per questo utente. </dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

Per modificare i dettagli di un utente: 
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--template</dt>
<dd>Una stringa JSON che descrive https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/. </dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

Per abilitare o disabilitare specifiche autorizzazioni utente: 
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--enable</dt>
<dd>Abilita o disabilita le autorizzazioni selezionate. Gli input accettati sono 'true' e 'false'. L'impostazione predefinita è 'true'. </dd>
<dt>--permission</dt>
<dd>Il `keyName` dell'autorizzazione da impostare, sono consentite più istanze. Utilizza la parola chiave ALL per selezionare TUTTE le autorizzazioni. </dd>
<dt>--from-user</dt>
<dd>Imposta le autorizzazioni in modo che corrispondano alle autorizzazioni di questo utente. Aggiunge e rimuove le autorizzazioni appropriate. </dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

Per elencare gli utenti: 
```
ibmcloud sl user list [OPTIONS]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--column</dt>
<dd>La colonna da visualizzare. [opzioni: id,username,email,displayName,status,hardwareCount,virtualGuestCount][default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

Per visualizzare le autorizzazioni utente: 
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

