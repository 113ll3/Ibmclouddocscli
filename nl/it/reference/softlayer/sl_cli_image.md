---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi CLI per l'immagine

<table summary="Comandi generali dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}} riportati in ordine alfabetico  con dei link a ulteriori informazioni sul comando">
<caption>Tabella 1. Comandi di immagine dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Comandi di immagine dell'infrastruttura {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl image delete
{: #sl_image_delete}

Elimina un'immagine.
```
ibmcloud sl image delete IDENTIFICATIVO
```
**Esempi**:
```
   ibmcloud sl image delete 12345678
```
Questo comando elimina l'immagine con ID `12345678`.

### ibmcloud sl image detail
{: #sl_image_detail}

Ottieni i dettagli per un'immagine.
```
ibmcloud sl image detail IDENTIFICATIVO
```
**Esempi**:
```
 ibmcloud sl image detail 12345678
```
Questo comando ottiene i dettagli per l'immagine con ID 12345678.

### ibmcloud sl image edit
{: #sl_image_edit}

Modifica i dettagli di un'immagine.
```
ibmcloud sl image edit IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--name</dt>
<dd>Nome dell'immagine.</dd>
<dt>--note</dt>
<dd>Nota supplementare per l'immagine.</dd>
<dt>--tag</dt>
<dd>Le tag per l'immagine.</dd>
</dl>

*Esempi**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Questo comando modifica l'immagine con ID `12345678` e imposta il suo nome su `ubuntu16`, la nota su `testing` e la tag su `staging`.

### ibmcloud sl image list
{: #sl_image_list}

Elenca tutte le immagini per il tuo account.
```
ibmcloud sl image list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--name</dt>
<dd>Filtra il nome dell'immagine.</dd>
<dt>--public</dt>
<dd>Visualizza solo le immagini pubbliche.</dd>
<dt>--private</dt>
<dd>Visualizza solo le immagini private.</dd>
</dl>
