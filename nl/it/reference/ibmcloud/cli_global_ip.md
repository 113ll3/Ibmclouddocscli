---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione dell'IP globale dell'infrastruttura {{site.data.keyword.Bluemix_notm}}

<table summary="Comandi generali dell'infrastruttura {{site.data.keyword.Bluemix_notm}} riportati in ordine alfabetico  con dei link a ulteriori informazioni sul comando">
<caption>Tabella 1. Comandi IP globali dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Comandi IP globali dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl globalip assign
{: #sl_globalip_assign}

Assegna un IP globale a un dispositivo o a un router di destinazione.
```
ibmcloud sl globalip assign IDENTIFICATIVO DESTINAZIONE
```


**Esempi**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
Questo comando assegna l'indirizzo IP con ID 12345678 a un dispositivo di destinazione il cui indirizzo IP è 9.111.123.456.

## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Annulla un IP globale.
```
ibmcloud sl globalip cancel IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl globalip cancel 12345678
```
Questo comando annulla l'indirizzo IP con ID 12345678.

 ## ibmcloud sl globalip create
{: #sl_globalip_create}

Crea un IP globale.
```
ibmcloud sl globalip create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--v6</dt>
<dd>Ordina un indirizzo IP IPv6.</dd>
<dt>--test</dt>
<dd>Verifica l'ordine.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl globalip create --v6
```
Questo comando crea un indirizzo IP V6.

## ibmcloud sl globalip list
{: #sl_globalip_list}

Elenca tutti gli IP globali per il tuo account.
```
ibmcloud sl globalip list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--v4</dt>
<dd>Visualizza solo IPv4.</dd>
<dt>--v6</dt>
<dd>Visualizza solo IPv6.</dd>
<dt>--order</dt>
<dd>Filtra in base all'ID dell'ordine che ha acquistato questo indirizzo IP.</dd>
</dl>

**Esempi**:
```
ibmcloud sl globalip list --v4
```
Questo comando elenca tutti gli indirizzi IP V4 sull'account corrente.

## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Annulla l'assegnazione di un IP globale da un router o un dispositivo di destinazione.
```
ibmcloud sl globalip unassign IDENTIFICATIVO
```


**Esempi**:
```
ibmcloud sl globalip unassign 12345678
```
Questo comando annulla l'assegnazione dell'indirizzo IP con ID 12345678 dal dispositivo di destinazione.
