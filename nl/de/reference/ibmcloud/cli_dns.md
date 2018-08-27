---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}}-Infrastruktur - DNS verwalten

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.Bluemix_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. DNS-Befehle der Infrastruktur für {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.Bluemix_notm}} - DNS-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

## ibmcloud sl dns import
{: #sl_dns_import}

Zone auf Basis einer BIND-Zonendatei importieren.
```
ibmcloud sl dns import ZONEFILE [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--dry-run</dt>
<dd>Datensätze nicht tatsächlich erstellen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns import ~/ibm.com.txt
```
Dieser Befehl importiert die Zone und ihre Ressourcendatensätze aus der Datei: ~/ibm.com.txt.

## ibmcloud sl dns record-add
{: #sl_dns_record_add}

Ressourcendatensatz in einer Zone hinzufügen.
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL-Wert (Time-To-Live) in Sekunden, z. B. 86400; Standardwert ist: 7200.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
Dieser Befehl fügt einen A-Datensatz zur Zone ibm.com hinzu, deren Host "ftp" und deren Daten "127.0.0.1" und deren ttl 86400 Sekunden sind.

## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

Ressourcendatensätze in einer Zone aktualisieren.
```
ibmcloud sl dns record-edit ZONE [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--by-record</dt>
<dd>Nach Hostdatensatz bearbeiten, z. B. www.</dd>
<dt>--by-id</dt>
<dd>Einzelnen Datensatz nach ID bearbeiten.</dd>
<dt>--data</dt>
<dd>Daten aufzeichnen, wie z. B. eine IP-Adresse.</dd>
<dt>--ttl</dt>
<dd>Nach TTL-Wert in Sekunden filtern, z. B. 86400.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Dieser Befehl bearbeitet Datensätze unter der Zone ibm.com, deren ID 12345678 ist, und legt ihre Daten auf "127.0.0.2" und ttl auf 3600 fest.

## ibmcloud sl dns record-list
{: #sl_dns_record_list}

Alle Ressourcendatensätze in einer Zone auflisten.
```
ibmcloud sl dns record-list ZONE [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--data</dt>
<dd>Nach Datensatzdaten filtern, z. B. IP-Adresse.</dd>
<dt>--record</dt>
<dd>Nach Hostdatensatz filtern, z. B. www.</dd>
<dt>--ttl</dt>
<dd>Nach TTL-Wert in Sekunden filtern, z. B. 86400.</dd>
<dt>--type</dt>
<dd>Nach Datensatztyp filtern, z. B. A oder CNAME.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
Dieser Befehl listet alle A-Datensätze unter der Zone ibm.com auf; der Host, nach dem gefiltert wird, ist elasticsearch und TTL ist 900 Sekunden.

## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

Ressourcendatensätze aus einer Zone entfernen.
```
ibmcloud sl dns record-remove RECORD_ID
```


**Beispiele**:
```
ibmcloud sl dns record-remove 12345678
```
Dieser Befehl entfernt den Ressourcendatensatz mit der ID 12345678.

## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

Zone erstellen.
```
ibmcloud sl dns zone-create ZONE
```


**Beispiele**:
```
ibmcloud sl dns zone-create ibm.com
```
Dieser Befehl erstellt eine Zone mit dem Namen ibm.com.

## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

Zone löschen.
```
ibmcloud sl dns zone-delete ZONE
```


**Beispiele**:
```
ibmcloud sl dns zone-delete ibm.com
```
Dieser Befehl löscht die Zone mit dem Namen ibm.com.

## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

Alle Zonen für eigenes Konto auflisten.
```
ibmcloud sl dns zone-list
```


**Beispiele**:
```
ibmcloud sl dns zone-list
```
Dieser Befehl listet alle Zonen unter einem aktuellen Konto auf.

## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

Zone und Ressourcendatensätze in BIND-Format ausgeben.
```
ibmcloud sl dns zone-print ZONE
```


**Beispiele**:
```
ibmcloud sl dns zone-print ibm.com
```
Dieser Befehl druckt die Zone mit dem Namen ibm.com im Format BIND.
