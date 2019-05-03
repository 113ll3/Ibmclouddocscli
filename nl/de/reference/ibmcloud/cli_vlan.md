---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, vlan, classic vlan, ibmcloud sl vlan, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# VLANs der klassischen Infrastruktur verwalten
{: #manage-classic-vlans}

Virtual Local Area Networks (VLANs) werden von {{site.data.keyword.cloud}} zum Isolieren von Broadcast-Datenverkehr in öffentlichen und privaten Netzen verwendet. VLANs werden so hinzugefügt, wie es für andere Angebote erforderlich ist.

Verwenden Sie die nachfolgend aufgeführten Befehle zum Verwalten von VLANs der klassischen Infrastruktur.
{: shortdesc}

## ibmcloud sl vlan create
{: #sl_vlan_create}

Neues VLAN erstellen.
```
ibmcloud sl vlan create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --vlan-type</dt>
<dd>Der Typ des VLANs, entweder öffentlich oder privat.</dd>
<dt>-r, --router</dt>
<dd>Der Hostname des Routers.</dd>
<dt>-d, --datacenter</dt>
<dd>Der Kurzname des Rechenzentrums.</dd>
<dt>-n, --name</dt>
<dd>Der Name des VLANs.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
{: codeblock}

Dieser Befehl erstellt ein öffentliches VLAN im Rechenzentrum `dal09` mit 16 IP-Adressen und dem Namen `myvlan`.

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

VLAN abbrechen
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan cancel 12345678 -f
```
{: codeblock}

Dieser Befehl bricht das VLAN mit der ID `12345678` ab, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl vlan detail
{: #sl_vlan_detail}

Details zu einem VLAN abrufen.
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONEN]
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
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
{: codeblock}

Dieser Befehl zeigt Details zum VLAN mit der ID `12345678` an, ohne virtuelle Server oder Hardware-Server aufzulisten.

## ibmcloud sl vlan edit
{: #sl_vlan_edit}

Details zu einem VLAN bearbeiten.
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Der Name des VLANs.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
{: codeblock}

Dieser Befehl aktualisiert das VLAN mit der ID `12345678` und benennt es in `myvlan-rename` um.

## ibmcloud sl vlan list
{: #sl_vlan_list}

Alle VLANs für eigenes Konto auflisten.
```
ibmcloud sl vlan list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-n, --number</dt>
<dd>Nach VLAN-Nummer filtern.</dd>
<dt>--name</dt>
<dd>Nach VLAN-Name filtern.</dd>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der das VLAN gekauft wurde.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vlan list -d dal09 --sortby number
```
Dieser Befehl listet alle VLANs für das aktuelle Konto, gefiltert nach 'Rechenzentrum gleich `dal09`' auf und sortiert sie nach VLAN-Nummer.

## ibmcloud sl vlan options
{: #sl_vlan_options}

Alle Optionen für die VLAN-Erstellung auflisten.
```
ibmcloud sl vlan options
```
{: codeblock}

**Beispiele**:
```
ibmcloud sl vlan options
```
{: codeblock}

Dieser Befehl listet alle Optionen für die VLAN-Erstellung auf, z. B. VLAN-Typ, Rechenzentren, Teilnetzgröße, Router usw.
