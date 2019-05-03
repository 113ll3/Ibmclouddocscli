---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl globalip, globalip, global ip addresses, assign global ip

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione degli IP globali
{: #sl-manage-global-ip}

Un indirizzo IP globale è una sottorete secondaria statica specializzata. Ti viene fornito come una sottorete /32 (in altre parole, un singolo indirizzo IP) che può essere instradato a qualsiasi altro indirizzo IP sul tuo account.

Utilizza i seguenti comandi per gestire un IP globale nel servizio IP globale dell'infrastruttura classica {{site.data.keyword.Bluemix}}.
{: shortdesc}

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

Questo comando assegna l'indirizzo IP con ID `12345678` su un dispositivo di destinazione il cui indirizzo IP è `9.111.123.456`.

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

Questo comando annulla l'indirizzo IP con ID `12345678`.

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

Questo comando annulla l'assegnazione dell'indirizzo IP con ID `12345678` dal dispositivo di destinazione.
