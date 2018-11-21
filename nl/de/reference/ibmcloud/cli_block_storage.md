---

copyright:

  years: 2018


lastupdated: "2018-11-05"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Block Storage

Bei {{site.data.keyword.Bluemix}}-Blockspeicher handelt es sich um persistenten iSCSI-Speicher mit hoher Leistung, der unabhängig von Recheninstanzen bereitgestellt und verwaltet wird. iSCSI-basierte Blockspeicher-LUNs sind über MPIO-Verbindungen (MPIO - Multipath I/O) mit autorisierten Geräten verbunden. 

Verwenden Sie die folgenden Befehle, um einen angegebenen Datenträger für den Blockspeicherservice der klassischen {{site.data.keyword.Bluemix_notm}}-Infrastruktur zu verwalten.
{: shortdesc}

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Block Storage der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Block Storage der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-password](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_password)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failover)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl block replica-locations](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_locations)</td>
  <td>[ibmcloud sl block replica-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_order)</td>
  <td>[ibmcloud sl block replica-partners](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_partners)</td>
  <td>[ibmcloud sl block snapshot-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_cancel)</td>
  <td>[ibmcloud sl block snapshot-create](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_create)</td>
  <td>[ibmcloud sl block snapshot-disable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_disable)</td>
</tr>
<tr>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_enable)</td>
  <td>[ibmcloud sl block snapshot-delete](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_delete)</td>
  <td>[ibmcloud sl block snapshot-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_list)</td>
  <td>[ibmcloud sl block snapshot-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_order)</td>
  <td>[ibmcloud sl block snapshot-restore](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block snapshot-schedule-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_schedule_list)</td>
</tr>
<tr>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_cancel)</td>
  <td>[ibmcloud sl block volume-count](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_count)</td>
  <td>[ibmcloud sl block volume-detail](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_detail)</td>
  <td>[ibmcloud sl block volume-duplicate](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_duplicate)</td>
  <td>[ibmcloud sl block volume-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_list)</td>
  <td>[ibmcloud sl block volume-modify](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_modify)</td>
</tr>
<tr>
  <td>[ibmcloud sl block volume-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_order)</td>
  <td>[ibmcloud sl block volume-options](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_options)</td>
  <td>[ibmcloud sl block volume-set-lun-id](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_set_lun_id)</td>  
</tr>
</tbody>
</table>
 
## ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Hosts für den Zugriff auf einen bestimmten Datenträger autorisieren.
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>Die ID eines Hardware-Servers, der autorisiert werden soll.</dd>
<dt>-v, --virtual-id</dt>
<dd>Die ID eines virtuellen Servers, der autorisiert werden soll.</dd>
<dt>-i, --ip-address-id</dt>
<dd>Die ID einer IP-Adresse, die autorisiert werden soll.</dd>
<dt>-p, --ip-address</dt>
<dd>Eine IP-Adresse, die autorisiert werden soll.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
Dieser Befehl autorisiert den virtuellen Server mit der ID 87654321 für den Zugriff auf den Datenträger mit der ID 12345678.

## ibmcloud sl block access-list
{: #sl_block_access_list}

Listet ACLs auf.
```
ibmcloud sl block access-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Anzuzeigende Spalten. Optionen: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
Dieser Befehl listet alle Hosts auf, die für den Zugriff auf den Datenträger mit der ID 12345678 autorisiert sind, und sortiert diese nach ID.

## ibmcloud sl block access-password
{: #sl_block_access_password}

Ändert ein Kennwort für den Datenträgerzugriff.
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

## ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Autorisierung für Hosts widerrufen, die auf einen bestimmten Datenträger zugreifen.
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>Die ID eines der zu widerrufenden Hardware-Server.</dd>
<dt>-v, --virtual-id</dt>
<dd>Die ID eines der zu widerrufenden virtuellen Server.</dd>
<dt>-i, --ip-address-id</dt>
<dd>Die ID einer der zu widerrufenden IP-Adressen.</dd>
<dt>-p, --ip-address</dt>
<dd>Eine zu widerrufende IP-Adresse.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
Dieser Befehl widerruft den Zugriff des virtuellen Servers mit der ID 87654321 auf den Datenträger mit der ID 12345678.

## ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Failback eines Blockdatenträgers von einem Replikat.
```
ibmcloud sl block replica-failback VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl block replica-failback 12345678
```
Dieser Befehl führt eine Failback-Operation für den Datenträger mit der ID 12345678 aus.

## ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Failover eines Blockdatenträgers auf den angegebenen Replikatdatenträger.
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**Beispiele**:
```
ibmcloud sl block replica-failover 12345678 87654321
```
Dieser Befehl führt eine Failover-Operation für den Datenträger mit der ID 12345678 auf den Replikatdatenträger mit der ID 87654321 aus.

## ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

Geeignete Replikationsrechenzentren für den angegebenen Datenträger auflisten.
```
ibmcloud sl block replica-locations VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl block replica-locations 12345678
```
Dieser Befehl listet passende Replikationsrechenzentren für den Blockdatenträger mit der ID 12345678 auf.

## ibmcloud sl block replica-order
{: #sl_block_replica_order}

Blockspeicher-Replikatdatenträger bestellen.
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Erforderlich. Für die Replikation zu verwendender Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname für Rechenzentrum des Replikats, z. B. dal09.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: 0.25,2,4,10. Wenn kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-o, --os-type</dt>
<dd>Optional. Betriebssystemtyp (z. B. Linux) des Primärdatenträgers, für den ein Replikat bestellt wurde. Optionen: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
Dieser Befehl bestellt ein Replikat für den Datenträger mit der ID 12345678, der eine DAILY-Replikation durchführt, mit dem Ort 'dal09', der Tierebene 4 und dem Betriebssystemtyp Linux.

## ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

Vorhandene Replicant-Datenträger für Blockdatenträger auflisten.
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONEN]
```


**Beispiele**:
```
ibmcloud sl block replica-partners 12345678
```
Dieser Befehl listet vorhandene Replicant-Datenträger für den Blockdatenträger mit der ID 12345678 auf.

## ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Vorhandenen Snapshotbereich für einen bestimmten Datenträger abbrechen.
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>--immediate</dt>
<dd>Snapshotbereich sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Snapshot mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Snapshot für einen bestimmten Datenträger erstellen.
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Anmerkungen zum neuen Snapshot.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
Dieser Befehl erstellt einen Snapshot für den Datenträger mit der ID 12345678 und mit Zusatzanmerkung snapshotforibmcloud.

## ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Snapshots für den angegebenen Zeitplan für einen bestimmten Datenträger inaktivieren.
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
Dieser Befehl inaktiviert den täglichen Snapshot für den Datenträger mit der ID 12345678.

## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Snapshots für einen bestimmten Datenträger gemäß angegebenem Zeitplan aktivieren.
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Erforderlich. Anzahl der beizubehaltenden Snapshots.</dd>
<dt>-m, --minute</dt>
<dd>Minute der Stunde, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 59.</dd>
<dt>-r, --hour</dt>
<dd>Stunde des Tages, zu der Snapshots erfasst werden sollen; Ganzzahl zwischen 0 und 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Wochentag, an dem Snapshot erfasst werden sollen; Ganzzahl zwischen 0 und 6. 0 steht für Sonntag, 1 für Montag, 2 für Dienstag, 3 für Mittwoch, 4 für Donnerstag, 5 für Freitag, 6 für Samstag.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Dieser Befehl aktiviert den Snapshot für den Datenträger mit der ID 12345678; der Snapshot wird wöchentlich jeden Sonntag um 2:00 ausgeführt und bis zu 5 Snapshots werden beibehalten.

## ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Snapshot für einen bestimmten Datenträger löschen.
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl block snapshot-delete 12345678
```
Dieser Befehl löscht den Snapshot mit der ID 12345678.

## ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

Blockspeichersnapshots auflisten.
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,created,size_bytes.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
Dieser Befehl listet alle Snapshots des Datenträgers mit der ID 12345678 auf und sortiert diese nach ID.

## ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Snapshotbereich für einen Blockspeicherdatenträger bestellen.
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Erforderlich. Die Größe des zu erstellenden Snapshotbereichs in GB.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Blockdatenträgers, für den ein Bereich bestellt wurde. Optionen: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Flag zum Anzeigen, dass die Bestellung ein Upgrade ist.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
Dieser Befehl bestellt Snapshotbereich für den Datenträger mit der ID 12345678, Größe 1000 GB, Tierebene 4 E/A-Operationen pro Sekunde pro GB.

## ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Blockdatenträger mithilfe eines bestimmten Snapshots wiederherstellen.
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
Dieser Befehl stellt den Datenträger mit der ID 12345678 aus dem Snapshot mit der ID 87654321 wieder her.

## ibmcloud sl block snapshot-schedule-list
{: #sl_block_snapshot_schedule_list}

Snapshotzeitpläne für einen angegebenen Datenträger auflisten
```
ibmcloud sl block snapshot-schedule-list VOLUME_ID
```

**Beispiele**:
```
ibmcloud sl block snapshot-schedule-list 12345678
```
Mit diesem Befehl wird eine Liste der Snapshotzeitpläne für den Datenträger mit der ID 12345678 aufgelistet.

## ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Abbruch für vorhandenen Blockspeicherdatenträger.
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>--immediate</dt>
<dd>Blockspeicherdatenträger sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Datenträger mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

Anzahl der Blockspeicherdatenträger pro Rechenzentrum auflisten.
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
</dl>

## ibmcloud sl block volume-list
{: #sl_block_volume_list}

Blockspeicher auflisten.
```
ibmcloud sl block volume-list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Nach Datenträger-Benutzernamen filtern.</dd>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
<dt>-t, --storage-type</dt>
<dd>Nach Typ des Speicherdatenträgers filtern, Optionen: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Nach ID der Bestellung filtern, mit der der Blockspeicher gekauft wurde.</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>Spalten für die Anzeige, Optionen: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
Dieser Befehl listet alle Endurance-Datenträger für das aktuelle Konto mit dem Ort 'dal09' auf und sortiert sie nach Kapazität.

## ibmcloud sl block volume-modify
{: #sl_block_volume_modify}

Vorhandenen Blockspeicherdatenträger ändern
```
ibmcloud sl block volume-modify VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-c, --new-size</dt>
<dd>Neue Größe von Blockdatenträger in GB. ***Ist keine Größe angegeben, wird die ursprüngliche Größe des Datenträgers verwendet.*** Mögliche Größen: [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000]. Minimum: [ursprüngliche Größe des Datenträgers]</dd>
<dt>-i, --new-iops</dt>
<dd>E/A-Operationen pro Sekunde (IOPS) für Performance-Speicher, zwischen 100 und 6000 als Vielfaches von 100 [nur für Performance-Datenträger] ***Ist kein IOPS-Wert angegeben, wird der ursprüngliche IOPS-Wert des Datenträgers verwendet.*** Anforderungen: [Liegt der ursprüngliche Wert für IOPS/GB für den Datenträger unter 0,3, muss der neue Wert für IOPS/GB ebenfalls unter 0,3 liegen. Ist der ursprüngliche Wert für IOPS/GB für den Datenträger größer-gleich 0,3, muss der neue Wert für IOPS/GB ebenfalls größer-gleich 0,3 sein.]</dd>
<dt>-t, --new-tier</dt>
<dd>Endurance-Speichertier (E/A-Operationen pro Sekunde/GB) [nur für Endurance-Datenträger] ***Ist kein Tier angegeben, wird das ursprüngliche Tier des Datenträgers verwendet.***
Anforderungen: [Beträgt der ursprüngliche IOPS/GB-Wert für den Datenträger 0,25, muss der neue IOPS/GB-Wert für den Datenträger ebenfalls 0,25 betragen. Liegt der ursprüngliche IOPS/GB-Wert für den Datenträger über 0,25, muss der neue IOPS/GB-Wert für den Datenträger ebenfalls über 0,25 liegen.]</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:

```
ibmcloud sl block volume-modify 12345678 --new-size 1000 --new-iops 4000
```
Mit diesem Befehl wird der Datenträger 12345678 geändert. Neue Größe: 1000 GB. Neuer Wert für IOPS: 4000.

```
ibmcloud sl block volume-modify 12345678 --new-size 500 --new-tier 4
```
Mit diesem Befehl wird der Datenträger 12345678 geändert. Neue Größe: 500 GB. Neue Tierebene: 4 IOPS pro GB.

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

LUN-ID für einen vorhandenen Blockspeicherdatenträger festlegen.
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

## ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Details zu einem angegebenen Datenträger anzeigen.
```
ibmcloud sl block volume-detail VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl block volume-detail 12345678
```
Dieser Befehl führt Details zu dem Datenträger mit der ID 12345678 auf.

## ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Blockdatenträger durch Duplizieren eines vorhandenen Datenträgers bestellen.
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID eines Ursprungsdatenträgersnapshots zur Verwendung für die Duplizierung.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Größe des duplizierten Blockdatenträgers in GB; falls keine Größe angegeben wird, verwendet das System die Größe des Originaldatenträgers.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance-Speichertier; falls kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>Die Größe des Snapshotbereichs, der für das Duplikat bestellt werden muss; falls keine Größe für den Snapshotbereich angegeben wird, verwendet das System die Snapshotbereichsgröße des Ursprungsdatenträgers.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-duplicate 12345678
```
Dieser Befehl zeigt die Bestellung eines neuen Datenträgers durch Duplizierung des Datenträgers mit der ID 12345678 an.

## ibmcloud sl block volume-order
{: #sl_block_volume_order}

Blockspeicherdatenträger bestellen.
```
ibmcloud sl block volume-order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Erforderlich. Typ des Speicherdatenträgers; Optionen: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Erforderlich. Größe des Speicherdatenträgers in GB.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfache von 100 [erforderlich für Speichertyp 'Performance'].</dd>
<dt>-e, --tier</dt>
<dd>Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) [erforderlich für Endurance-Speichertyp], Optionen: 0.25,2,4,10.</dd>
<dt>-o, --os-type</dt>
<dd>Erforderlich. Betriebssystem; Optionen: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Rechenzentrum-Kurzname.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Optionaler Parameter für die Bestellung eines Snapshotbereichs zusammen mit Endurance-Blockspeicher; gibt die Größe des zu bestellenden Snapshotbereichs in GB an.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Dieser Befehl bestellt einen Leistungsdatenträger mit Größe 1000 GB, 4000 E/A-Operationen pro Sekunde, Betriebssystem LINUX, Ort 'dal09'.

## ibmcloud sl block volume-options
{: #sl_block_volume_options}

Alle Optionen für die Anforderung eines Blockspeichers auflisten.
```
ibmcloud sl block volume-options
```


**Beispiele**:
```
ibmcloud sl block volume-options
```
Dieser Befehl listet alle Optionen für die Erstellung eines Blockspeicherdatenträgers auf, einschließlich Speichertyp, Datenträgergröße, Betriebssystemtyp, E/A-Operationen pro Sekunde, Tierebene, Rechenzentrum und Snapshotgröße.
