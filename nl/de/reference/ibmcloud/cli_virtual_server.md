---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl, virtual server, virtual server commands

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Virtuelle Server erstellen und verwenden
{: #cli-virtual-servers}

{{site.data.keyword.BluVirtServers}} sind skalierbare virtuelle Server, die mit dedizierten Cores und Hauptspeicherzuordnungen gekauft werden. Sie sind eine hervorragende Möglichkeit, wenn Sie Rechenressourcen benötigen, die in wenigen Minuten mit Funktionen wie Imagevorlagen hinzugefügt werden können. 

Verwenden Sie die folgenden Befehle, um virtuelle Server der klassischen Infrastruktur zu verwalten.
{: shortdesc}

## ibmcloud sl vs cancel
{: #sl_vs_cancel}

Abbruch für virtuelle Serverinstanz.
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs cancel 12345678
```
{: codeblock}

Dieser Befehl bricht die virtuelle Serverinstanz mit der ID `12345678` ab.

## ibmcloud sl vs capture
{: #sl_vs_capture}

Virtuelle Serverinstanz in einem Image erfassen.
```
ibmcloud sl vs capture IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Erforderlich. Name des Images.</dd>
<dt>--all</dt>
<dd>Alle zum virtuellen Server gehörigen Platten erfassen.</dd>
<dt>--note</dt>
<dd>Anmerkung hinzufügen, die dem Image zugeordnet werden soll.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
{: codeblock}

Dieser Befehl erfasst die virtuelle Serverinstanz mit der ID  `12345678` mit allen Platten in einem Image mit dem Namen `mycloud` und der Anmerkung `testing`.

## ibmcloud sl vs create
{: #sl_vs_create}

Virtuelle Serverinstanz erstellen.
```
ibmcloud sl vs create [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Erforderlich. Hostteil des FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Erforderlich. Domänenteil des FQDN.</dd>
<dt>-c, --cpu</dt>
<dd>Erforderlich. Anzahl der CPU-Cores.</dd>
<dt>-m, --memory</dt>
<dd>Erforderlich. Speicher in Megabyte.</dd>
<dt>--flavor</dt>
<dd>Name des Schlüssels für Version des öffentlichen virtuellen Servers</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname des Rechenzentrums.</dd>
<dt>-o, --os</dt>
<dd>Betriebssystem-Installationscode. Tipp: Sie können <OS>_LATEST angeben.</dd>
<dt>--image</dt>
<dd>Image-ID. Siehe 'ibmcloud sl image list'.</dd>
<dt>--billing</dt>
<dd>Verrechnungssatz. Standardwert: hourly. Optionen: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Dedizierten virtuellen Server erstellen (privater Knoten).</dd>
<dt>--host-id</dt>
<dd>Host-ID, unter der ein dedizierter virtueller Server bereitgestellt wird.</dd>
<dt>--san</dt>
<dd>SAN-Speicher anstelle der lokalen Festplatte verwenden.</dd>
<dt>--test</dt>
<dd>Virtuellen Server nicht tatsächlich erstellen.</dd>
<dt>--export</dt>
<dd>Optionen in eine Vorlagendatei exportieren.</dd>
<dt>-i, --postinstall</dt>
<dd>Nachinstallationsscript herunterladen.</dd>
<dt>-k, --key</dt>
<dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen (Mehrfachvorkommen zulässig).</dd>
<dt>--disk</dt>
<dd>Plattengrößen (Mehrfachvorkommen zulässig).</dd>
<dt>--private</dt>
<dd>Erzwingt, dass der virtuelle Server nur auf das private Netz zugreifen kann.</dd>
<dt>--like</dt>
<dd>Konfiguration von einem vorhandenen virtuellen Server verwenden.</dd>
<dt>-n, --network</dt>
<dd>Übertragungsgeschwindigkeit des Netzports in MB/s.</dd>
<dt>-g, --tag</dt>
<dd>Zur Instanz hinzuzufügende Tags (Mehrfachvorkommen zulässig).</dd>
<dt>-t, --template</dt>
<dd>Eine Vorlagendatei, mit der die Befehlszeilenoptionen auf Standardwerte zurückgesetzt werden.</dd>
<dt>-u, --userdata</dt>
<dd>Benutzerdefinierte Metadaten-Zeichenfolge.</dd>
<dt>-F, --userfile</dt>
<dd>Benutzerdaten aus Datei lesen.</dd>
<dt>--vlan-public</dt>
<dd>Die ID des öffentlichen VLANs, in dem der virtuelle Server angeordnet werden soll.</dd>
<dt>--vlan-private</dt>
<dd>Die ID des privaten VLANs, in dem der virtuelle Server angeordnet werden soll.</dd>
<dt>-S, --public-security-group</dt>
<dd>Der öffentlichen Schnittstelle zuzuordnende Sicherheitsgruppen-ID (mehrere Vorkommen zulässig)</dd>
<dt>-s, --private-security-group</dt>
<dd>Der privaten Schnittstelle zuzuordnende Sicherheitsgruppen-ID (mehrere Vorkommen zulässig)</dd>
<dt>--wait</dt>
<dd>Warten Sie bis zu X Sekunden, bis der virtuelle Server die Bereitstellung fertiggestellt hat, bevor Sie zurückkehren.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
{: codeblock}

Dieser Befehl bestellt eine virtuelle Serverinstanz mit dem Hostnamen myvsi, der Domäne ibm.com, 4 CPU-Cores, 4096 M Speicher und Position im Rechenzentrum `dal10`.

## ibmcloud sl vs options
{: #sl_vs_options}

Optionen für Erstellung einer virtuellen Serverinstanz auflisten.
```
ibmcloud sl vs options [OPTIONEN]
```

**Beispiele**:
```
ibmcloud sl vs options
```
{: codeblock}

Dieser Befehl listet alle Optionen für die Erstellung einer virtuellen Serverinstanz auf, z. B. Rechenzentren, CPU, Speicher, Betriebssystem, Platte, Netzgeschwindigkeit usw.

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

Berechtigungsnachweise für virtuelle Serverinstanz auflisten.
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONEN]
```

**Beispiele**:
```
ibmcloud sl vs credentials 12345678
```
{: codeblock}

Dieser Befehl listet alle Benutzername/Kennwort-Paare der virtuellen Serverinstanz mit der ID `12345678` auf.

## ibmcloud sl vs detail
{: #sl_vs_detail}

Details zu einer virtuellen Serverinstanz abrufen.
```
ibmcloud sl vs detail IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--passwords</dt>
<dd>Kennwörter anzeigen (achten Sie darauf, dass niemand dabei zusehen kann!).</dd>
<dt>--price</dt>
<dd>Zugeordnete Preise anzeigen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs details 12345678
```
{: codeblock}

Dieser Befehl listet detaillierte Informationen zur virtuellen Serverinstanz mit der ID `12345678` auf.

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

DNS-Datensätze für eine virtuelle Serverinstanz synchronisieren.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>A-Datensatz für Host synchronisieren.</dd>
<dt>--aaaa-record</dt>
<dd>AAAA-Datensatz für Host synchronisieren.</dd>
<dt>--ptr</dt>
<dd>PTR-Datensatz für Host synchronisieren.</dd>
<dt>--ttl</dt>
<dd>Legt TTL für die A- und/oder PTR-Datensätze fest; Standardwert: 7200.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
{: codeblock}

Dieser Befehl synchronisiert den A-Datensatz (IPv4-Adresse) der virtuellen Serverinstanz mit der ID `12345678` mit dem DNS-Server und legt das TTL dieses A-Datensatzes auf 3600 fest.

## ibmcloud sl vs edit
{: #sl_vs_edit}

Details zu einer virtuellen Serverinstanz bearbeiten.
```
ibmcloud sl vs edit IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Domänenteil des FQDN.</dd>
<dt>-H, --hostname</dt>
<dd>Hostteil des FQDN. Beispiel: Server.</dd>
<dt>-g, --tag</dt>
<dd>Tags zum Festlegen oder leere Zeichenfolge, um alle zu entfernen.</dd>
<dt>-u, --userdata</dt>
<dd>Benutzerdefinierte Metadaten-Zeichenfolge.</dd>
<dt>-F, --userfile</dt>
<dd>Benutzerdaten aus Datei lesen.</dd>
<dt>--public-speed</dt>
<dd>Übertragungsgeschwindigkeit des öffentlichen Ports; Optionen: 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>Übertragungsgeschwindigkeit des privaten Ports; Optionen: 0,10,100,1000,10000.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
Dieser Befehl aktualisiert die virtuelle Serverinstanz mit der ID `12345678` und legt als zugehörige Domäne "ibm.com", als Hostnamen "myapp" und als Tag "testcli" fest.

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

Erstellt einen Host für dedizierte virtuelle Server.
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Erforderlich. Hostteil des FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Erforderlich. Domänenteil des FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname des Rechenzentrums.</dd>
<dt>-s, --size</dt>
<dd>Größe des dedizierten Hosts. Zurzeit einzige verfügbare Größe: 56_CORES_X_242_RAM_X_1_4_TB</dd>
<dt>-b, --billing</dt>
<dd>Verrechnungssatz. Standardwert: hourly. Optionen: hourly, monthly.</dd>
<dt>-v, --vlan-private</dt>
<dd>Die ID des privaten VLANs, in dem der dedizierte Host angeordnet werden soll. Siehe: 'ibmcloud sl vlan list' als Referenz.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

Listet dedizierte Hosts in Ihrem Konto auf.
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Nach Name des dedizierten Hosts filtern.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Rechenzentrum des dedizierten Hosts filtern.</dd>
<dt>--owner</dt>
<dd>Nach Eigner des dedizierten Hosts filtern.</dd>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der der dedizierte Host gekauft wurde.</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

Virtuelle Serverinstanzen für eigenes Konto auflisten.
```
ibmcloud sl vs list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Nach Anzahl der CPU-Cores filtern.</dd>
<dt>-D, --domain</dt>
<dd>Nach Domänenteil des FQDN filtern.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-H, --hostname</dt>
<dd>Nach Hostteil des FQDN filtern.</dd>
<dt>-m, --memory</dt>
<dd>Nach Speicher in Megabyte filtern.</dd>
<dt>-n, --network</dt>
<dd>Nach Übertragungsgeschwindigkeit des Netzports in MB/s filtern.</dd>
<dt>-P, --public-ip</dt>
<dd>Nach öffentlicher IP-Adresse filtern.</dd>
<dt>-p, --private-ip</dt>
<dd>Nach privater IP-Adresse filtern.</dd>
<dt>--hourly</dt>
<dd>Nur stündliche Instanzen anzeigen.</dd>
<dt>--monthly</dt>
<dd>Nur monatliche Instanzen anzeigen.</dd>
<dt>-g, --tag</dt>
<dd>Nach Tags filtern (Mehrfachvorkommen zulässig).</dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der diese Instanz gekauft wurde.</dd>
<dt>--owner</dt>
<dd>Gefiltert nach ID des Benutzers, zu dem die Instanzen gehören.</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Standardwert: hostname. Optionen sind: id,hostname,domain,datacenter,cpu,memory,public_ip,private_ip.</dd>
<dt>--columns</dt>
<dd>Anzuzeigende Spalten. Standardwert: id,hostname,public_ip,private_ip,datacenter,action. Optionen sind: guid,power_state,created_by,tags.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
Dieser Befehl listet alle virtuellen Serverinstanzen mit stündlicher Abrechnung für das aktuelle Konto auf, gefiltert nach Domäne gleich "ibm.com", und sortiert sie nach Speicher.

## ibmcloud sl vs pause
{: #sl_vs_pause}

Aktive virtuelle Serverinstanz anhalten.
```
ibmcloud sl vs pause IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs pause 12345678 -f
```
Dieser Befehl hält die virtuelle Serverinstanz mit der ID `12345678` an, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

Aktive virtuelle Serverinstanz ausschalten.
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--hard</dt>
<dd>Erzwungenen Systemabschluss durchführen.</dd>
<dt>--soft</dt>
<dd>Normalen Systemabschluss durchführen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs power-off 12345678 --soft
```
Dieser Befehl führt eine normale Abschaltung der virtuellen Serverinstanz mit der ID `12345678` durch.

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

Virtuelle Serverinstanz einschalten.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs power-on 12345678
```
{: codeblock}

Dieser Befehl schaltet die virtuelle Serverinstanz mit der ID `12345678` ein.

## ibmcloud sl vs ready
{: #sl_vs_ready}

Prüfen, ob eine virtuelle Serverinstanz betriebsbereit ist.
```
ibmcloud sl vs ready IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--wait</dt>
<dd>Warten Sie bis zu X Sekunden, bis der virtuelle Server die Bereitstellung fertiggestellt hat, bevor Sie zurückkehren.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
Dieser Befehl prüft den Status der virtuellen Serverinstanz mit der ID `12345678`  darauf hin, ob sie durchgehend betriebsbereit ist, und wartet bis zu 30 Sekunden.

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

Aktive virtuelle Serverinstanz neu starten.
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--hard</dt>
<dd>Kaltstart durchführen.</dd>
<dt>--soft</dt>
<dd>Warmstart durchführen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs reboot 12345678 --hard
```
{: codeblock}

Dieser Befehl führt einen Kaltstart für die virtuelle Serverinstanz mit der ID `12345678` durch.

## ibmcloud sl vs reload
{: #sl_vs_reload}

Betriebssystem auf virtueller Serverinstanz erneut laden.
```
ibmcloud sl vs reload IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Nachinstallationsscript herunterladen.</dd>
<dt>--image</dt>
<dd>Image-ID. Standardeinstellung ist die Verwendung des aktuellen Betriebssystems.</dd>
<dt>Siehe:</dt>
<dd>'ibmcloud sl image list' als Referenz.</dd>
<dt>-k, --key</dt>
<dd>Die IDs der SSH-Schlüssel, die dem Rootbenutzer hinzugefügt werden sollen (Mehrfachvorkommen zulässig).</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs reload 12345678
```
Dieser Befehl lädt das aktuelle Betriebssystem für die virtuelle Serverinstanz mit der ID `12345678` neu.

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

Warmstart für virtuelle Serverinstanz in ein Wiederherstellungsimage durchführen.
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONEN
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs rescue 12345678
```
Dieser Befehl startet die virtuelle Serverinstanz mit der ID `12345678` neu in ein Wiederherstellungsimage.

## ibmcloud sl vs resume
{: #sl_vs_resume}

Angehaltene virtuelle Serverinstanz wieder aufnehmen.
```
ibmcloud sl vs resume IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs resume 12345678
```
Dieser Befehl nimmt die virtuelle Serverinstanz mit der ID `12345678` wieder auf.

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Upgrade für eine virtuelle Serverinstanz durchführen.
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Anzahl der CPU-Cores.</dd>
<dt>--private</dt>
<dd>CPU-Core soll sich auf einem dedizierten Host-Server befinden.</dd>
<dt>-m, --memory</dt>
<dd>Speicher in Megabyte.</dd>
<dt>--network</dt>
<dd>Übertragungsgeschwindigkeit des Netzports in MB/s.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
{: codeblock}

Dieser Befehl führt ein Upgrade für die virtuelle Serverinstanz mit der ID `12345678` durch und legt die Anzahl der CPU-Cores auf 8, den Speicher auf 8192 M und die Übertragungsgeschwindigkeit des Netzports auf 1000 MT/s fest.
