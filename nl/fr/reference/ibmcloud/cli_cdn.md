---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: content delivery network, cdn service, cdn, classic infrastructure, ibmcloud sl cdn

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Utilisation du service CDN
{: #sl-cdn-service}

Le service CDN (Content Delivery Network) distribue du contenu là où cela est nécessaire. La première fois qu'un contenu est demandé, il est extrait du serveur hôte sur le réseau, où il reste pour que d'autres utilisateurs puissent y accéder.

Utilisez les commandes suivantes pour gérer le service CDN de l'infrastructure classique {{site.data.keyword.cloud_notm}}.
{: shortdesc}

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
