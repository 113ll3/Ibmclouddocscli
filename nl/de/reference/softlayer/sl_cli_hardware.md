---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Hardware-CLI-Befehle

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Hardwarebefehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} - Hardwarebefehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Einen Server abbrechen.
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-i, --immediate</dt>
<dd>Bricht den Server sofort ab (anstatt am Rechnungsstichtag).</dd>
<dt>-r, --reason</dt>
<dd>Ein optionaler Grund für den Abbruch. Eine Liste mit verfügbaren Optionen finden Sie unter 'ibmcloud sl hardware cancel-reasons'. </dd>
<dt>-c, --comment</dt>
<dd>Ein optionaler Kommentar, der dem Abbruchticket hinzugefügt werden soll. </dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Zeigt eine Liste mit Gründen für den Abbruch an. 
```
ibmcloud sl hardware cancel-reasons
```

### ibmcloud sl hardware create
{: #sl_hardware_create}

Einen Server bestellen/erstellen
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-H, --hostname</dt>
<dd>Host-Teil des FQDN, erforderlich</dd>
<dt>-D, --domain</dt>
<dd>Domänenteil des FQDN, erforderlich</dd>
<dt>-s, --size</dt>
<dd>Hardwaregröße, erforderlich</dd>
<dt>-o, --os</dt>
<dd>Betriebssystem-Installationscode, erforderlich</dd>
<dt>-d, --datacenter</dt>
<dd>Rechenzentrum-Kurzname, erforderlich</dd>
<dt>-p, --port-speed</dt>
<dd>Portgeschwindigkeit, erforderlich</dd>
<dt>-b, --billing</dt>
<dd>Verrechnungssatz, entweder 'hourly' oder 'monthly', Standardwert: 'hourly' (falls keine andere Angabe erfolgt)</dd>
<dt>-i, --post-install</dt>
<dd>Nachinstallationsscript herunterladen.</dd>
<dt>-k, --key</dt>
<dd>SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen, Mehrfachvorkommen zulässig</dd>
<dt>-n, --no-public</dt>
<dd>Nur privates Netz</dd>
<dt>-e, --extra</dt>
<dd>Zusätzliche Optionen, Mehrfachvorkommen zulässig</dd>
<dt>-t, --test</dt>
<dd>Virtuellen Server nicht tatsächlich erstellen.</dd>
<dt>-m, --template</dt>
<dd>Eine Vorlagendatei, mit der die Befehlszeilenoptionen auf Standardwerte zurückgesetzt werden.</dd>
<dt>-x, --export</dt>
<dd>Optionen in eine Vorlagendatei exportieren.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

Serverbestelloptionen für ein bestimmtes Chassis
```
ibmcloud sl hardware create-options
```

### ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

Berechtigungsnachweise für Hardware-Server auflisten
```
ibmcloud sl hardware credentials IDENTIFIER
```

### ibmcloud sl hardware detail
{: #sl_hardware_detail}

Details zu einem Hardware-Server abrufen
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-p, --passwords</dt>
<dd>Kennwörter anzeigen (achten Sie darauf, dass niemand dabei zusehen kann!).</dd>
<dt>-c, --price</dt>
<dd>Zugeordnete Preise anzeigen.</dd>
</dl>

### ibmcloud sl hardware edit
{: #sl_hardware_edit}

Hardware-Server-Details bearbeiten
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-H, --hostname</dt>
<dd>Hostteil des FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Domänenteil des FQDN.</dd>
<dt>-g, --tag</dt>
<dd>Tags zum Festlegen oder leere Zeichenfolge, um alle zu entfernen.</dd>
<dt>-F, --userfile</dt>
<dd>Benutzerdaten aus Datei lesen.</dd>
<dt>-u, --userdata</dt>
<dd>Benutzerdefinierte Metadaten-Zeichenfolge.</dd>
<dt>-p, --public-speed</dt>
<dd>Übertragungsgeschwindigkeit des öffentlichen Ports; Optionen: 0,10,100,1000,10000.</dd>
<dt>-v, --private-speed</dt>
<dd>Übertragungsgeschwindigkeit des privaten Ports; Optionen: 0,10,100,1000,10000.</dd>
</dl>

### ibmcloud sl hardware list
{: #sl_hardware_list}

Server auflisten
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-c, --cpu</dt>
<dd>Nach Anzahl der CPU-Cores filtern.</dd>
<dt>-D, --domain</dt>
<dd>Nach Domäne filtern. </dd>
<dt>-H, --hostname</dt>
<dd>Nach Hostname filtern. </dd>
<dt>-d, --datacenter</dt>
<dd>Nach Rechenzentrum filtern. </dd>
<dt>-m, --memory</dt>
<dd>Nach Speicher in Gigabyte filtern. </dd>
<dt>-n, --network</dt>
<dd>Nach Übertragungsgeschwindigkeit des Netzports in MB/s filtern.</dd>
<dt>-g, --tag</dt>
<dd>Nach Tags filtern, Mehrfachvorkommen zulässig. </dd>
<dt>-p, --public-ip</dt>
<dd>Nach IP-Adresse filtern. </dd>
<dt>-v, --private-ip</dt>
<dd>Nach privater IP-Adresse filtern. </dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der der Server gekauft wurde. </dd>
<dt>--owner</dt>
<dd>Nach ID des Eigners filtern. </dd>
<dt>--sortby</dt>
<dd>Spalte, nach der standardmäßig sortiert werden soll: hostname, Optionen: id,guid,hostname,domain,public_ip,private_ip,datacenter,status,ipmi_ip,created,created_by.</dd>
<dt>--columns</dt>
<dd>Spalten, die standardmäßig angezeigt werden sollen: id,hostname,domain,public_ip,private_ip,datacenter,status, Optionen: guid,cpu,memory,os,ipmi_ip,created,created_by,tags.</dd>
</dl>

### ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Server aus- und wieder einschalten.
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Aktiven Server ausschalten. 
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Server einschalten.
```
ibmcloud sl hardware power-on IDENTIFIER
```

### ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Warmstart für aktiven Server durchführen.
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--hard</dt>
<dd>Kaltstart durchführen.</dd>
<dt>--soft</dt>
<dd>Warmstart durchführen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware reload
{: #sl_hardware_reload}

Betriebssystem auf einen Server neu laden.
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-i, --postinstall</dt>
<dd>Nachinstallationsscript zum Herunterladen, nur HTTPS wird ausgeführt, HTTP lässt Datei in /root.</dd>
<dt>-k, --key</dt>
<dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen, Mehrfachvorkommen zulässig.</dd>
<dt>-b, --upgrade-bios</dt>
<dd>BIOS aktualisieren.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>Gesamte Firmware der Festplatte aktualisieren. </dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Warmstart für Server in ein Wiederherstellungsimage durchführen
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Server-Firmware aktualisieren.
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>
