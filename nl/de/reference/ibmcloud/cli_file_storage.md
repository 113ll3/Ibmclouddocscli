---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}}-Infrastruktur - File Storage

Verwenden Sie die folgenden Befehle, um einen angegebenen Datenträger für den File Storage-Service der {{site.data.keyword.Bluemix_notm}}-Infrastruktur zu verwalten.
{: shortdesc}

<table summary="Alphabetisch geordnete File Storage-Befehle der {{site.data.keyword.Bluemix_notm}}-Infrastruktur mit Links zu weiteren Informationen über den Befehl">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl file access-authorize](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_access_authorize)</td>
  <td>[ibmcloud sl file access-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_access_list)</td>
  <td>[ibmcloud sl file access-revoke](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_access_revoke)</td>
  <td>[ibmcloud sl file replica-failback](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_failback)</td>
  <td>[ibmcloud sl file replica-failover](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_failover)</td>
  <td>[ibmcloud sl file replica-locations](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_locations)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl file replica-order](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_order)</td>
  <td>[ibmcloud sl file replica-partners](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_replica_partners)</td>
  <td>[ibmcloud sl file snapshot-cancel](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_cancel)</td>
  <td>[ibmcloud sl file snapshot-create](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_create)</td>
  <td>[ibmcloud sl file snapshot-disable](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_disable)</td>
  <td>[ibmcloud sl file snapshot-enable](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_enable)</td>
  </tr>
 <tr>
  <td>[ibmcloud sl file snapshot-delete](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_delete)</td>
  <td>[ibmcloud sl file snapshot-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_list)</td>
  <td>[ibmcloud sl file snapshot-order](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_order)</td>
  <td>[ibmcloud sl file snapshot-restore](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_snapshot_restore)</td>
  <td>[ibmcloud sl file volume-cancel](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_cancel)</td>  
  <td>[ibmcloud sl file volume-count](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_count)</td>
   </tr>
 <tr>
   <td>[ibmcloud sl file volume-detail](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_detail)</td>
   <td>[ibmcloud sl file volume-duplicate](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_duplicate)</td>
   <td>[ibmcloud sl file volume-list](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_list)</td>
   <td>[ibmcloud sl file volume-order](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_order)</td>
   <td>[ibmcloud sl file volume-options](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_options)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Hosts für den Zugriff auf einen bestimmten Datenträger autorisieren.
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONEN]
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
<dt>-s, --subnet-id</dt>
<dd>Eine ID für ein zu autorisierendes Teilnetz.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
Dieser Befehl autorisiert den virtuellen Server mit der ID 87654321 für den Zugriff auf den Datenträger mit der ID 12345678.

## ibmcloud sl file access-list
{: #sl_file_access_list}

Listet ACLs auf.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONEN]
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
ibmcloud sl file access-list 12345678 --sortby id
```
Dieser Befehl listet alle Hosts auf, die für den Zugriff auf den Datenträger mit der ID 12345678 autorisiert sind, und sortiert diese nach ID.

## ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Autorisierung für Hosts widerrufen, die auf einen bestimmten Datenträger zugreifen.
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONEN]
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
<dt>-s, --subnet-id</dt>
<dd>Eine ID für ein zu widerrufendes Teilnetz.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
Dieser Befehl widerruft den Zugriff des virtuellen Servers mit der ID 87654321 auf den Datenträger mit der ID 12345678.

## ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Failback eines Dateidatenträgers von einem Replikat.
```
ibmcloud sl file replica-failback VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl file replica-failback 12345678
```
Dieser Befehl führt eine Failback-Operation für den Datenträger mit der ID 12345678 aus.

## ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Failover eines Dateidatenträgers auf den angegebenen Replikatdatenträger.
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Beispiele**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
Dieser Befehl führt eine Failover-Operation für den Datenträger mit der ID 12345678 auf den Replikatdatenträger mit der ID 87654321 aus.

## ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Geeignete Replikationsrechenzentren für den angegebenen Datenträger auflisten.
```
ibmcloud sl file replica-locations VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl file replica-locations 12345678
```
Dieser Befehl listet passende Replikationsrechenzentren für den Dateidatenträger mit der ID 12345678 auf.

## ibmcloud sl file replica-order
{: #sl_file_replica_order}

Datenspeicher-Replikatdatenträger bestellen.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONEN]
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
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
Dieser Befehl bestellt ein Replikat für den Datenträger mit der ID 12345678, der eine DAILY-Replikation durchführt, mit dem Ort 'dal09' und der Tierebene 4.

## ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Vorhandene Replicant-Datenträger für einen Dateidatenträger auflisten.
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONEN]
```


**Beispiele**:
```
ibmcloud sl file replica-partners 12345678
```
Dieser Befehl listet vorhandene Replicant-Datenträger für den Dateidatenträger mit der ID 12345678 auf.

## ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Vorhandenen Snapshotbereich für einen bestimmten Datenträger abbrechen.
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONEN]
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
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Snapshot mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Snapshot für einen bestimmten Datenträger erstellen.
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Anmerkungen zum neuen Snapshot.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
Dieser Befehl erstellt einen Snapshot für den Datenträger mit der ID 12345678 und mit Zusatzanmerkung snapshotforibmcloud.

## ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Snapshots für den angegebenen Zeitplan für einen bestimmten Datenträger inaktivieren.
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Erforderlich. Snapshotplan. Optionen: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
Dieser Befehl inaktiviert den täglichen Snapshot für den Datenträger mit der ID 12345678.

## ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Snapshots für einen bestimmten Datenträger gemäß angegebenem Zeitplan aktivieren.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONEN]
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
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Dieser Befehl aktiviert den Snapshot für den Datenträger mit der ID 12345678; der Snapshot wird wöchentlich jeden Sonntag um 2:00 ausgeführt und bis zu 5 Snapshots werden beibehalten.

## ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Snapshot für einen bestimmten Datenträger löschen.
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl file snapshot-delete 12345678
```
Dieser Befehl löscht den Snapshot mit der ID 12345678.

## ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Dateidatenträgersnapshots auflisten.
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,name,created,size_bytes.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
Dieser Befehl listet alle Snapshots des Datenträgers mit der ID 12345678 auf und sortiert diese nach ID.

## ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Snapshotbereich für einen Dateispeicherdatenträger bestellen.
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Erforderlich. Die Größe des zu erstellenden Snapshotbereichs in GB.</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance-Speichertier (E/A-Operationen pro Sekunde pro GB) des Dateidatenträgers, für den ein Bereich bestellt wurde. Optionen: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Flag zum Anzeigen, dass die Bestellung ein Upgrade ist.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Diese Befehle bestellen Snapshotbereich für den Datenträger mit der ID 12345678, Größe 1000 GB, Tierebene 4 E/A-Operationen pro Sekunde pro GB.

## ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Dateidatenträger mithilfe eines bestimmten Snapshots wiederherstellen.
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Beispiele**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```
Dieser Befehl stellt den Datenträger mit der ID 12345678 aus dem Snapshot mit der ID 87654321 wieder her.

## ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Abbruch für vorhandenen Dateispeicherdatenträger.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>--immediate</dt>
<dd>Dateispeicherdatenträger sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
Dieser Befehl bricht den Datenträger mit der ID 12345678 sofort ab, ohne zu einer Bestätigung aufzufordern.

## ibmcloud sl file volume-count
{: #sl_file_volume_count}

Anzahl der Dateispeicherdatenträger pro Rechenzentrum auflisten.
```
ibmcloud sl file volume-count [OPTIONS]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Nach Kurzname des Rechenzentrums filtern.</dd>
</dl>

## ibmcloud sl file volume-list
{: #sl_file_volume_list}

Dateispeicher auflisten.
```
ibmcloud sl file volume-list [OPTIONEN]
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
<dd>Nach ID der Bestellung filtern, mit der der Dateispeicher gekauft wurde.</dd>
<dt>--sortby</dt>
<dd>Spalte, nach der sortiert werden soll. Optionen: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,mount_addr.</dd>
<dt>--columns</dt>
<dd>Spalten für die Anzeige, Optionen: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
Dieser Befehl listet alle Endurance-Datenträger für das aktuelle Konto mit dem Ort 'dal09' auf und sortiert sie nach Kapazität.

## ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Details zu einem angegebenen Datenträger anzeigen.
```
ibmcloud sl file volume-detail VOLUME_ID
```


**Beispiele**:
```
ibmcloud sl file volume-detail 12345678
```
Dieser Befehl führt Details zu dem Datenträger mit der ID 12345678 auf.

## ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Dateidatenträger durch Duplizieren eines vorhandenen Datenträgers bestellen.
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID eines Originaldatenträgersnapshots zur Verwendung für die Duplizierung.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Größe des duplizierten Dateidatenträgers in GB; falls keine Größe angegeben wird, verwendet das System die Größe des Originaldatenträgers.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>E/A-Operationen pro Sekunde für Leistungsspeicher, zwischen 100 und 6000 als Vielfaches von 100. Wenn keine E/A-Operationen pro Sekunde angegeben sind, werden die E/A-Operationen pro Sekunde des Originaldatenträgers verwendet.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance-Speichertier; falls kein Tier angegeben ist, wird das Tier des Originaldatenträgers verwendet.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>Die Größe des Snapshotbereichs, der für das Duplikat bestellt werden muss; falls keine Größe für den Snapshotbereich angegeben wird, verwendet das System die Snapshotbereichsgröße des Originaldatenträgers.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-duplicate 12345678
```
Dieser Befehl zeigt die Bestellung eines neuen Datenträgers durch Duplizierung des Datenträgers mit der ID 12345678 an.

## ibmcloud sl file volume-order
{: #sl_file_volume_order}

Dateispeicherdatenträger bestellen.
```
ibmcloud sl file volume-order [OPTIONEN]
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
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Rechenzentrum-Kurzname.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Optionaler Parameter für die Bestellung eines Snapshotbereichs zusammen mit dem Datenträger.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
Dieser Befehl bestellt einen Leistungsdatenträger mit einer Größe von 1000 GB. Der Wert für die E/A-Operationen pro Sekunde beträgt 4000, der Ort ist 'dal09'.

## ibmcloud sl file volume-options
{: #sl_file_volume_options}

Alle Optionen für die Anforderung eines Dateispeichers auflisten.
```
ibmcloud sl file volume-options
```


**Beispiele**:
```
ibmcloud sl file volume-options
```
Dieser Befehl listet alle Optionen für die Erstellung eines Dateispeicherdatenträgers auf, einschließlich Speichertyp, Datenträgergröße, E/A-Operationen pro Sekunde, Tierebene, Rechenzentrum und Snapshotgröße.
