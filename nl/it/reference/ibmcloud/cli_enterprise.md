---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud enterprise, view enterprise, view enterprise account, view enterprise account group., enterprise, account-group, account-group-create, account-group-update, 

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione di azienda, gruppi di account ed account
{: #ibmcloud_enterprise}

Utilizza i seguenti comandi per gestire l'azienda, i gruppi di account e gli account.
{: shortdesc}

## ibmcloud enterprise create
{: #ibmcloud_enterprise_create} 

Crea un'azienda.
```
ibmcloud enterprise create NOME [-d, --domain NOME_DOMINIO] [--primary-contact-id ID_UTENTE_CONTATTO_PRIMARIO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome dell'azienda.</dd>
<dt>-d, --domain NOME_DOMINIO (facoltativo)</dt>
<dd>Nome dominio.</dd>
<dt>--primary-contact-id ID_UTENTE_CONTATTO_PRIMARIO (facoltativo)</dt>
<dd>L'ID utente di contatto primario dell'azienda.</dd>
</dl>

## ibmcloud enterprise update
{: #ibmcloud_enterprise_update} 

Aggiorna le informazioni sull'azienda.
```
ibmcloud enterprise update (-n, --name NUOVO_NOME) [-f, --force] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>-f, --force (facoltativo)</dt>
<dd>Aggiorna senza conferma.</dd>
<dt>-n, --name NUOVO_NOME (obbligatorio)</dt>
<dd>Nuovo nome dell'azienda.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise show
{: #ibmcloud_enterprise_show} 

Visualizza i dettagli dell'azienda.
```
ibmcloud enterprise show [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-group-create
{: #ibmcloud_enterprise_account_group_create} 

Crea un gruppo di account.
```
ibmcloud enterprise account-group-create NOME [--parent-account-group NOME_GRUPPO_ACCOUNT] [--primary-contact-id ID_UTENTE_CONTATTO_PRIMARIO] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>NOME (obbligatorio)</dt>
<dd>Nome gruppo di account.</dd>
<dt>--parent-account-group NOME_GRUPPO_ACCOUNT (facoltativo)</dt>
<dd>Nome del gruppo di account parent. Se omesso, il parent sarà l'azienda attuale.</dd>
<dt>--primary-contact-id ID_UTENTE_CONTATTO_PRIMARIO (facoltativo)</dt>
<dd>L'ID utente di contatto primario del gruppo di account.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-group-update
{: #ibmcloud_enterprise_account_group_update} 

Aggiorna un gruppo di account.
```
ibmcloud enterprise account-group-update (-n, --name NOME | --id ID) (--new-name NUOVO_NOME) [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--id ID (obbligatorio)</dt>
<dd>ID del gruppo di account di destinazione.Questa opzione è esclusiva con `-n, --name`.</dd>
<dt>-n, --name NOME (obbligatorio)</dt>
<dd>Nome del gruppo di account di destinazione.Questa opzione è esclusiva con `--id`.</dd>
<dt>--new-name NUOVO_NOME (obbligatorio)</dt>
<dd>Nuovo nome del gruppo di account di destinazione.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-group
{: #ibmcloud_enterprise_account_group} 

Visualizza i dettagli del gruppo di account.
```
ibmcloud enterprise account-group (-n, --name NOME | --id ID) [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--id ID (obbligatorio)</dt>
<dd>ID del gruppo di account. Questa opzione è esclusiva con `-n, --name`.</dd>
<dt>-n, --name NOME (obbligatorio)</dt>
<dd>Nome del gruppo di account. Questa opzione è esclusiva con `--id`.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-groups
{: #ibmcloud_enterprise_account_groups} 

Elenca i gruppi di account.
```
ibmcloud enterprise account-groups [--parent-account-group NOME_GRUPPO_ACCOUNT | --parent-account-group-id ID_GRUPPO_ACCOUNT [--recursive] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--parent-account-group NOME_GRUPPO_ACCOUNT (facoltativo)</dt>
<dd>Nome del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ID_GRUPPO_ACCOUNT (facoltativo)</dt>
<dd>ID del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group`.</dd>
<dt>--recursive (facoltativo)</dt>
<dd>Mostra i gruppi di account discendenti.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-create
{: #ibmcloud_enterprise_account_create} 

Crea un account.
```
ibmcloud enterprise account-create NOME [--parent-account-group NOME_GRUPPO_ACCOUNT] [--owner ID_UTENTE] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>NAME (obbligatorio)</dt>
<dd>Nome gruppo di account.</dd>
<dt>--owner ID_UTENTE (facoltativo)</dt>
<dd>ID utente del gruppo di account.</dd>
<dt>--parent-account-group NOME_GRUPPO_ACCOUNT (facoltativo).</dt>
<dd>Nome del gruppo di account parent. Se omesso, il parent sarà l'azienda attuale.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-move
{: #ibmcloud_enterprise_account_move} 

Sposta un account sotto un parent differente.
```
ibmcloud enterprise account-move (-n, --name NOME | --id ID) (--parent-account-group NOME_GRUPPO_ACCOUNT | --parent-account-group-id ID_GRUPPO_ACCOUNT | --parent-enterprise)
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--id ID (obbligatorio)</dt>
<dd>ID dell'account di destinazione.Questa opzione è esclusiva con `-n, --name`.</dd>
<dt>-n, --name NOME (obbligatorio)</dt>
<dd>Nome dell'account di destinazione.Questa opzione è esclusiva con `--id`.</dd>
<dt>--parent-account-group NOME_GRUPPO_ACCOUNT (obbligatorio)</dt>
<dd>Nome del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group-id` e `--parent-enterprise`.</dd>
<dt>--parent-account-group-id ID_GRUPPO_ACCOUNT (obbligatorio)</dt>
<dd>ID del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group` e `--parent-enterprise`.</dd>
<dt>--parent-enterprise (obbligatorio)</dt>
<dd>Imposta l'azienda come parent. Questa opzione è esclusiva con `--parent-account-group` e `--parent-account-group-id`.</dd>
</dl>

## ibmcloud enterprise account-show
{: #ibmcloud_enterprise_account_show} 

Visualizza i dettagli di un account.
```
ibmcloud enterprise account-show (-n, --name NOME | --id ID) [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--id ID (obbligatorio)</dt>
<dd>ID dell'account. Questa opzione è esclusiva con `-n, --name`.</dd>
<dt>-n, --name NOME (obbligatorio)</dt>
<dd>Nome dell'account. Questa opzione è esclusiva con `--id`.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise accounts
{: #ibmcloud_enterprise_accounts} 

Elenca gli account.
```
ibmcloud enterprise accounts [--parent-account-group NOME_GRUPPO_ACCOUNT | --parent-account-group-id ID_GRUPPO_ACCOUNT [--recursive] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--parent-account-group NOME_GRUPPO_ACCOUNT (facoltativo)</dt>
<dd>Nome del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ID_GRUPPO_ACCOUNT (facoltativo)</dt>
<dd>ID del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group`.</dd>
<dt>--recursive (facoltativo)</dt>
<dd>Mostra gli account discendenti.</dd>
<dt>--output FORMATO (facoltativo)</dt>
<dd>Specifica il formato di output, è supportato solo 'JSON'.</dd>
</dl>

## ibmcloud enterprise account-import
{: #ibmcloud_enterprise_account_import} 

Importa un account autonomo.
```
ibmcloud enterprise account-import (--account-id ID) [--parent-account-group NOME_GRUPPO_ACCOUNT | --parent-account-group-id ID_GRUPPO_ACCOUNT]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
<dt>--account-id</dt>
<dd>ID dell'account di origine.</dd>
<dt>--parent-account-group GRUPPO_ACCOUNT_PARENT (facoltativo)</dt>
<dd>Nome del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group-id`.</dd>
<dt>--parent-account-group-id ID_GRUPPO_ACCOUNT_PARENT (facoltativo)</dt>
<dd>ID del gruppo di account parent. Questa opzione è esclusiva con `--parent-account-group`.</dd>
</dl>
