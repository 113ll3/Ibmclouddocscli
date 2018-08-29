---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestion du réseau de diffusion de contenu (CDN) de l'infrastructure {{site.data.keyword.Bluemix_notm}}

 <table summary="Commandes générales de l'infrastructure {{site.data.keyword.Bluemix_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Commandes CDN de l'infrastructure {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">CDN de l'infrastructure {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options
](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/ibmcloud/cli_cdn.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>

 ## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Permet d'annuler un compte CDN.
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

Permet d'afficher les détails d'un compte CDN.
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

Permet de répertorier tous les comptes CDN.
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filtrer par ID de commande.</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

Permet de mettre en cache un ou plusieurs fichiers sur tous les noeuds périphériques.
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

Permet de commander un compte CDN.
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-b, --bandwidth</dt>
<dd>Bande passante CDN. Le prix 'Paiement à la carte' sera utilisé si cette option n'est pas spécifiée.</dd>
<dt>-s, --storage</dt>
<dd>Stockage CDN. Le prix 'Paiement à la carte' sera utilisé si cette option n'est pas spécifiée.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

Options de bande passante et de stockage pour la commande d'un compte CDN.
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Permet de créer un mappage d'extraction d'origine.
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-t, --type</dt>
<dd>Type de support pour ce mappage (http, flash, wm, ...). La valeur par défaut est : http.</dd>
<dt>-c, --cname</dt>
<dd>Type d'enregistrement CNAME facultatif à joindre au mappage.</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Permet de répertorier les mappages d'extraction d'origine.
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Permet de retirer un mappage d'extraction d'origine.
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

Permet de purger les fichiers mis en cache depuis tous les noeuds périphériques.
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>
