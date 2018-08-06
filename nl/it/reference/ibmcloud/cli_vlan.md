---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi per gestire la VLAN dell'infrastruttura {{site.data.keyword.Bluemix_notm}} 

<table summary="Comandi generali dell'infrastruttura {{site.data.keyword.Bluemix_notm}} riportati in ordine alfabetico  con dei link a ulteriori informazioni sul comando">

<caption>Tabella 1. Comandi VLAN dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</caption>

 <thead>
 <th colspan="6">Comandi VLAN dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_detail)</td>
 <td>[ibmcloud sl vlan edit](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_edit)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options
](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

 ### ibmcloud sl vlan create
{: #sl_vlan_create}

Crea una nuova VLAN.
```
ibmcloud sl vlan create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>Il tipo della VLAN, pubblica o privata.</dd>
<dt>-r, --router</dt>
<dd>Il nome host del router.</dd>
<dt>-d, --datacenter</dt>
<dd>Il nome breve del datacenter.</dd>
<dt>-s, --size</dt>
<dd>La dimensione delle sottoreti, le opzioni sono: 8 (5 IP utilizzabili), 16 (13 IP utilizzabili) o 32 (29 IP utilizzabili).</dd>
<dt>-n, --name</dt>
<dd>Il nome della VLAN.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
Questo comando crea una vlan pubblica ubicata nel datacenter dal09 con 16 indirizzi IP e con il nome myvlan.

### ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Annulla una VLAN.
```
ibmcloud sl vlan cancel IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vlan cancel 12345678 -f
```
Questo comando annulla la vlan con ID 12345678 senza richiedere conferma.

### ibmcloud sl vlan detail
{: #sl_vlan_detail}

Ottieni i dettagli di una VLAN.
```
ibmcloud sl vlan detail IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--no-vs</dt>
<dd>Nascondi elenco server virtuali.</dd>
<dt>--no-hardware</dt>
<dd>Nascondi elenco hardware.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
Questo comando mostra i dettagli della vlan con ID 12345678 e non elenca il server virtuale o il server hardware.

### ibmcloud sl vlan edit
{: #sl_vlan_edit}

Modifica i dettagli di una VLAN.
```
ibmcloud sl vlan edit IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Il nome della VLAN.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
Questo comando aggiorna la vlan con ID 12345678 e le fornisce un nuovo nome "myvlan-rename".

### ibmcloud sl vlan list
{: #sl_vlan_list}

Elenca tutte le VLAN per il tuo account.
```
ibmcloud sl vlan list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna da ordinare, le opzioni sono: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
<dt>-n, --number</dt>
<dd>Filtra in base al numero della VLAN.</dd>
<dt>--name</dt>
<dd>Filtra in base al nome della VLAN.</dd>
<dt>--order</dt>
<dd>Filtra in base all'ID dell'ordine che ha acquistato la VLAN.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
Questo comando elenca tutte le vlan sull'account corrente eseguendo il filtro per un datacenter uguale a dal09 e le ordina per numero di vlan.

### ibmcloud sl vlan options
{: #sl_vlan_options}

Elenca tutte le opzioni per la creazione della VLAN.
```
ibmcloud sl vlan options
```


**Esempi**:
```
ibmcloud sl vlan options
```
Questo comando elenca tutte le opzioni per la creazione di una vlan, ad es. il tipo di vlan, i datacenter, la dimensione della sottorete, i router, ecc
