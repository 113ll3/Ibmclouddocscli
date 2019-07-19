---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: domain management, dns service, ibmcloud sl dns, classic infrastructure, management interface, dns, dns cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Domänen mit dem DNS-Service verwalten
{: #sl-manage-domains}

Der DNS-Service von {{site.data.keyword.cloud}} (DNS = Domain Name Service) bietet Kunden einen zentralen Ausgangspunkt zur Anzeige und Verwaltung ihrer Domänen über die DNS-Basismanagementschnittstelle sowie die Option, Reverse DNS und Secondary DNS über denselben Ausgangspunkt kostenfrei zu verwalten.

Verwenden Sie die folgenden Befehle, um den DNS-Service der klassischen {{site.data.keyword.cloud_notm}}-Infrastruktur zu verwalten.
{: shortdesc}

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
Dieser Befehl gibt die Zone mit dem Namen 'ibm.com' im BIND-Format aus.
