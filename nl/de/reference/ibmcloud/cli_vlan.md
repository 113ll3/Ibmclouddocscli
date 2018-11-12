---

copyright:

  years: 2018


lastupdated: "2018-10-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# VLAN

Virtual Local Area Networks (VLANs) werden von {{site.data.keyword.cloud}} zum Isolieren von Broadcast-Datenverkehr in öffentlichen und privaten Netzen verwendet.

Verwenden Sie die folgenden Befehle, um die VLANs der {{site.data.keyword.Bluemix_notm}}-Infrastruktur zu verwalten.
{: shortdesc}

<table summary="Alphabetisch geordnete VLAN-Befehle der {{site.data.keyword.Bluemix_notm}}-Infrastruktur mit Links zu weiteren Informationen über den Befehl">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_detail)</td>
 <td>[ibmcloud sl vlan edit](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_edit)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

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
Dieser Befehl erstellt ein öffentliches VLAN in Rechenzentrum dal09 mit 16 IP-Adressen und dem Namen myvlan.

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

Abbruch für VLAN.
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
Dieser Befehl bricht das VLAN mit der ID 12345678 ab, ohne zu einer Bestätigung aufzufordern.

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
Dieser Befehl zeigt Details zum VLAN mit der ID 12345678 an, ohne virtuelle Server oder Hardware-Server aufzulisten.

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
Dieser Befehl aktualisiert das VLAN mit der ID 12345678 und benennt es in "myvlan-rename" um.

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
Dieser Befehl listet alle VLANs für das aktuelle Konto, gefiltert nach Rechenzentrum gleich dal09, und sortiert sie nach VLAN-Nummer.

## ibmcloud sl vlan options
{: #sl_vlan_options}

Alle Optionen für die VLAN-Erstellung auflisten.
```
ibmcloud sl vlan options
```


**Beispiele**:
```
ibmcloud sl vlan options
```
Dieser Befehl listet alle Optionen für die VLAN-Erstellung auf, z. B. VLAN-Typ, Rechenzentren, Teilnetzgröße, Router usw.
