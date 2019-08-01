---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Visualizzazione dell'utilizzo per gli account, le organizzazioni, i gruppi di risorse e le risorse 
{: #ibmcloud_billing}

Utilizza i seguenti comandi per richiamare le informazioni sull'utilizzo delle risorse e sulla fatturazione.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostra l'utilizzo mensile dell'account corrente (solo amministratore dell'account):
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

<strong>Esempi</strong>:

Mostra il report su costo e utilizzo dell'account corrente per 2016-06:
```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Mostra l'utilizzo mensile di un'organizzazione (solo il gestore della fatturazione dell'organizzazione o l'amministratore dell'account):
```
ibmcloud billing org-usage NOME_ORGANIZZAZIONE [-d YYYY-MM] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
  <dd>Nome dell'organizzazione.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostra l'utilizzo mensile di un gruppo di risorse (solo l'amministratore del gruppo di risorse o l'amministratore dell'account):
```
ibmcloud billing resource-group-usage NOME_GRUPPO [-d YYYY-MM] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>NOME_GRUPPO (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostra l'utilizzo mensile delle istanze della risorsa nell'account corrente:
```
ibmcloud billing resource-instances-usage [-o ORGANIZZAZIONE] [-g GRUPPO_RISORSE] [-d YYYY-MM] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-o NOME_ORGANIZZAZIONE (facoltativo)</dt>
  <dd>Filtra istanze per organizzazione.</dd>
  <dt>-g NOME_GRUPPO</dt>
  <dd>Filtra istanza per gruppo di risorse.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

Mostra i report sull'utilizzo aziendale:
```
ibmcloud billing enterprise-usage [--account-group NOME_GRUPPO_ACCOUNT | --account-group-id ID_GRUPPO_ACCOUNT | --account NOME_ACCOUNT | --account-id ID_ACCOUNT] [--month MESE] [--children] [--output FORMATO]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>--account NOME_ACCOUNT (facoltativo)</dt>
  <dd>Nome dell'account di destinazione.</dd>
  <dt>--account-id ID_ACCOUNT (facoltativo)</dt>
  <dd>ID dell'account di destinazione.</dd>
  <dt>--account-group NOME_GRUPPO_ACCOUNT (facoltativo)</dt>
  <dd>Nome del gruppo di account di destinazione.</dd>
  <dt>--account-group-id ID_GRUPPO_ACCOUNT (facoltativo)</dt>
  <dd>ID del gruppo di account di destinazione.</dd>
  <dt>--children (facoltativo)</dt>
  <dd>Mostra i report sull'utilizzo di elementi child.</dd>
  <dt>--month MESE (facoltativo)</dt>
  <dd>Mese di destinazione. Il valore predefinito è il mese corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>
