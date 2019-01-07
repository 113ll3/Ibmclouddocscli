---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Creazione, annullamento e visualizzazione di sottoreti

Una sottorete è una partizione logica di una rete IP in più segmenti di rete più piccoli. Utilizza i seguente comandi per gestire le sottoreti dell'infrastruttura classica {{site.data.keyword.Bluemix}}.
{: shortdesc}

<table summary="Comandi delle sottoreti dell'infrastruttura classica {{site.data.keyword.Bluemix_notm}} ordinati alfabeticamente che presentano dei link che ti portano a ulteriori informazioni per il comando">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Annulla una sottorete.
```
ibmcloud sl subnet cancel IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl subnet cancel 12345678 -f
```
Questo comando annulla la sottorete con ID 12345678 senza richiedere conferma.

## ibmcloud sl subnet create
{: #sl_subnet_create}

Aggiungi una nuova sottorete al tuo account.
```
ibmcloud sl subnet create QUANTITÀ RETE ID_VLAN [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>Ordina indirizzi IPv6.</dd>
<dt>--test</dt>
<dd>Non ordinare la sottorete; ottieni solo un preventivo.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl subnet create public 16 567
```
Questo comando crea una sottorete pubblica con 16 indirizzi IP v4 e la posiziona nella vlan con ID 567.

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

Ottieni i dettagli di una sottorete.
```
ibmcloud sl subnet detail IDENTIFICATIVO [OPZIONI]
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
ibmcloud sl subnet detail 12345678
```
Questo comando mostra informazioni dettagliate sulla sottorete con ID 12345678, incluse le informazioni sui server virtuali e i server hardware.

## ibmcloud sl subnet list
{: #sl_subnet_list}

Elenca tutte le sottoreti per il tuo account.
```
ibmcloud sl subnet list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna da ordinare. Le opzioni sono: id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
<dt>--identifier</dt>
<dd>Filtra per identificativo di rete.</dd>
<dt>-t, --subnet-type</dt>
<dd>Filtra per tipo di sottorete.</dd>
<dt>--network-space</dt>
<dd>Filtra per spazio di rete.</dd>
<dt>--v4, --ipv4</dt>
<dd>Visualizza solo le sottoreti IPv4.</dd>
<dt>--v6, --ipv6</dt>
<dd>Visualizza solo le sottoreti IPv6.</dd>
<dt>--order</dt>
<dd>Filtra in base all'ID dell'ordine che ha acquistato le sottoreti.</dd>
</dl>

**Esempi**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
Questo comando elenca le sottoreti IP V4 sull'account corrente eseguendo il filtro per il datacenter dal09, il tipo di sottorete è PRIMARY e lo spazio di rete è PUBLIC.

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

Trova un indirizzo IP e visualizzane le informazioni su sottorete e dispositivo.
```
ibmcloud sl subnet lookup INDIRIZZO_IP
```


**Esempi**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
Questo comando trova il record dell'indirizzo IP con indirizzo 9.125.235.255 e ne visualizza le informazioni su sottorete e dispositivo.
