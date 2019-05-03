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

# Gestione del servizio CDN
{: #sl-cdn-service}

Il servizio CDN (Content Delivery Network) distribuisce il contenuto dove è necessario. La prima volta che viene richiesto il contenuto, viene trasmesso dal server host alla rete e rimane lì in modo che altri utenti possano accedervi.

Utilizza i seguenti comandi per gestire il servizio CDN dell'infrastruttura classica {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

Annulla un account CDN.
```
ibmcloud sl cdn cancel ID_ACCOUNT [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

Fornisci dettagli di un account CDN.
```
ibmcloud sl cdn detail ID_ACCOUNT
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

Elenca tutti gli account CDN.
```
ibmcloud sl cdn list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id, name, type, created.</dd>
<dt>--order</dt>
<dd>Filtra in base all'ID ordine.</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

Memorizza nella cache uno o più file su tutti i nodi edge.
```
ibmcloud sl cdn load ID_ACCOUNT URL_CONTENUTO [URL_CONTENUTO...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

Ordina un account CDN.
```
ibmcloud sl cdn order [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>Larghezza di banda CDN, verrà utilizzato il prezzo 'Pagamento a consumo', se non specificato.</dd>
<dt>-s, --storage</dt>
<dd>Archiviazione CDN, verrà utilizzato il prezzo 'Pagamento a consumo', se non specificato.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

Opzioni di larghezza di banda e archiviazione per ordinare l'account CDN.
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Crea un'associazione del pull di origine.
```
ibmcloud sl cdn origin-add ID_ACCOUNT URL_CONTENUTO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-t, --type</dt>
<dd>Il tipo di elemento multimediale per questa associazione (http, flash, wm, ...); il valore predefinito è: http.</dd>
<dt>-c, --cname</dt>
<dd>Un CNAME facoltativo da collegare all'associazione.</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Elenca le associazioni del pull di origine.
```
ibmcloud sl cdn origin-list ID_ACCOUNT
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Rimuove un'associazione del pull di origine.
```
ibmcloud sl cdn origin-remove ID_ACCOUNT ID_ORIGINE [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

Elimina i file memorizzati nella cache da tutti i nodi edge.
```
ibmcloud sl cdn purge ID_ACCOUNT URL_CONTENUTO [URL_CONTENUTO...] [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>
