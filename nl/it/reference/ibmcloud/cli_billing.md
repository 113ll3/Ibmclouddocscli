---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Fatturazione 
{: #ibmcloud_billing}

Utilizza i seguenti comandi per richiamare le informazioni sull'utilizzo delle risorse e sulla fatturazione.
{: shortdesc}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire l'utilizzo e la fatturazione {{site.data.keyword.Bluemix_notm}}.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud billing account-usage](cli_billing.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](cli_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 
 ## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostra l'utilizzo mensile dell'account corrente (solo amministratore dell'account)

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

Mostra l'utilizzo mensile di un'organizzazione (solo il gestore della fatturazione dell'organizzazione o l'amministratore dell'account)

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

Mostra l'utilizzo mensile di un gruppo di risorse (solo l'amministratore del gruppo di risorse o l'amministratore dell'account)

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

Mostra l'utilizzo mensile delle istanze della risorsa nell'account corrente.

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
  <dd>Visualizza i dati per il mese e la data specificata tramite l'utilizzo nel formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--output FORMATO (facoltativo)</dt>
  <dd>Specifica il formato di output, al momento è supportato solo JSON.</dd>
</dl>
