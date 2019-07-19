---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: manage subnets, classic infrastructure, subnets, ibmcloud sl subnet

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Teilnetze erstellen, löschen und anzeigen
{: #sl-manage-subnets}

Ein Teilnetz ist eine logische Aufteilung eines IP-Netzes, das aus mehreren, kleineren Netzsegmenten besteht. Verwenden Sie die folgenden Befehle, um die Teilnetze der klassischen {{site.data.keyword.cloud}}-Infrastruktur zu verwalten.
{: shortdesc}

## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Abbruch für Teilnetz.
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl subnet cancel 12345678 -f
```
Dieser Befehl bricht das Teilnetz mit der ID `12345678` ab, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl subnet create
{: #sl_subnet_create}

Neues Teilnetz zu eigenem Konto hinzufügen.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>IPv6-Adressen bestellen.</dd>
<dt>--test</dt>
<dd>Teilnetz nicht bestellen, nur ein Angebot anfordern.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl subnet create public 16 567
```
{: codeblock}

Dieser Befehl erstellt ein öffentliches Teilnetz mit 16 IPv4-Adressen und ordnet es im VLAN mit der ID `567` an.

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

Details zu einem Teilnetz abrufen.
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--no-vs</dt>
<dd>Liste des virtuellen Server ausblenden.</dd>
<dt>--no-hardware</dt>
<dd>Hardwareliste ausblenden.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl subnet detail 12345678
```
{: codeblock}

Dieser Befehl zeigt detaillierte Informationen zum Teilnetz mit der ID `12345678` an, einschließlich Informationen zu virtuellen Servern und Hardware-Servern.

## ibmcloud sl subnet list
{: #sl_subnet_list}

Alle Teilnetze für eigenes Konto auflisten.
```
ibmcloud sl subnet list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>--identifier</dt>
<dd>Nach Netz-ID filtern.</dd>
<dt>-t, --subnet-type</dt>
<dd>Nach Teilnetztyp filtern.</dd>
<dt>--network-space</dt>
<dd>Nach Netzbereich filtern.</dd>
<dt>--v4, --ipv4</dt>
<dd>Nur IPv4-Teilnetze anzeigen.</dd>
<dt>--v6, --ipv6</dt>
<dd>Nur IPv6-Teilnetze anzeigen.</dd>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der die Teilnetze gekauft wurden.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
{: codeblock}

Dieser Befehl listet IPv4-Teilnetze für das aktuelle Konto auf, gefiltert nach Rechenzentrum, Ort `dal09`, Teilnetztyp `PRIMARY` und Netzbereich `PUBLIC`.

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

IP-Adresse suchen und ihr Teilnetz sowie Gerätedaten anzeigen.
```
ibmcloud sl subnet lookup IP_ADDRESS
```

**Beispiele**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
{: codeblock}

Dieser Befehl sucht nach dem IP-Adressdatensatz mit der Adresse `9.125.235.255` und zeigt sein Teilnetz und die Gerätedaten an.
