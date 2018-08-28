---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione dell'archiviazione file dell'infrastruttura {{site.data.keyword.Bluemix_notm}}

<table summary="Comandi generali dell'infrastruttura {{site.data.keyword.Bluemix_notm}} riportati in ordine alfabetico  con dei link a ulteriori informazioni sul comando">
<caption>Tabella 1. Archiviazione file dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Archiviazione file dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</th>
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
   <td>[ibmcloud sl file volume-options
](/docs/cli/reference/ibmcloud/cli_file_storage.html#sl_file_volume_options)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Autorizza gli host ad accedere a un determinato volume.
```
ibmcloud sl file access-authorize ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>L'ID di un server hardware da autorizzare.</dd>
<dt>-v, --virtual-id</dt>
<dd>L'ID di un server virtuale da autorizzare.</dd>
<dt>-i, --ip-address-id</dt>
<dd>L'ID di un indirizzo IP da autorizzare.</dd>
<dt>-p, --ip-address</dt>
<dd>Un indirizzo IP da autorizzare.</dd>
<dt>-s, --subnet-id</dt>
<dd>Un ID di una sottorete da autorizzare.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
Questo comando autorizza il server virtuale con ID 87654321 ad accedere al volume con ID 12345678.

## ibmcloud sl file access-list
{: #sl_file_access_list}

Elenca ACL.
```
ibmcloud sl file access-list ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Colonne da visualizzare; le opzioni sono: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file access-list 12345678 --sortby id
```
Questo comando elenca tutti gli host autorizzati ad accedere al volume con ID 12345678 e li ordina in base all'ID.

## ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Revoca l'autorizzazione agli host che accedono a un determinato volume.
```
ibmcloud sl file access-revoke ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>L'ID di un server hardware da revocare.</dd>
<dt>-v, --virtual-id</dt>
<dd>L'ID di un server virtuale da revocare.</dd>
<dt>-i, --ip-address-id</dt>
<dd>L'ID di un indirizzo IP da revocare.</dd>
<dt>-p, --ip-address</dt>
<dd>Un indirizzo IP da revocare.</dd>
<dt>-s, --subnet-id</dt>
<dd>Un ID di una sottorete da revocare.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
Questo comando revoca l'accesso del server virtuale con ID 87654321 al volume con ID 12345678.

## ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Failback di un volume di file dalla replica.
```
ibmcloud sl file replica-failback ID_VOLUME
```


**Esempi**:
```
ibmcloud sl file replica-failback 12345678
```
Questo comando esegue l'operazione di failback per il volume con ID 12345678.

## ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Failover di un volume di file per un volume di replica fornito.
```
ibmcloud sl file replica-failover ID_VOLUME ID_REPLICA
```


**Esempi**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
Questo comando esegue l'operazione di failover per il volume con ID 12345678 nel volume di replica con ID 87654321.

## ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

Elenca i datacenter di replica appropriati per il volume fornito.
```
ibmcloud sl file replica-locations ID_VOLUME
```


**Esempi**:
```
ibmcloud sl file replica-locations 12345678
```
Questo comando elenca i datacenter di replica appropriati per il volume di file con ID 12345678.

## ibmcloud sl file replica-order
{: #sl_file_replica_order}

Ordina un volume di replica dell'archiviazione file.
```
ibmcloud sl file replica-order ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Obbligatorio. Pianificazione dell'istantanea da utilizzare per la replica; le opzioni sono: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Obbligatorio. Nome breve del datacenter per la replica, ad es. dal09.</dd>
<dt>-t, --tier</dt>
<dd>Facoltativo. Livello archiviazione durata (IOPS per GB) del volume primario per cui è ordinata la replica; le opzioni sono: 0.25,2,4,10; se non si specifica un livello, verrà utilizzato il livello del volume originale.</dd>
<dt>-i, --iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100; se non si specifica l'IOPS, verrà utilizzato il volume originale.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
Questo comando ordina una replica per il volume con ID 12345678, che esegue la replica giornaliera (DAILY); è ubicato in dal09, il livello è 4.

## ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

Elenca i volumi di replica esistenti per un volume di file.
```
ibmcloud sl file replica-partners ID_VOLUME [OPZIONI]
```


**Esempi**:
```
ibmcloud sl file replica-partners 12345678
```
Questo comando elenca i volumi di replica esistenti per il volume di file con ID 12345678.

## ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Annulla lo spazio di istantanea esistente per un determinato volume.
```
ibmcloud sl file snapshot-cancel ID_ISTANTANEA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Un motivo facoltativo per l'annullamento.</dd>
<dt>--immediate</dt>
<dd>Annulla lo spazio dell'istantanea immediatamente invece che a una ricorrenza di fatturazione.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
Questo comando annulla l'istantanea con ID 12345678 immediatamente senza richiedere la conferma.

## ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Crea un'istantanea in un determinato volume.
```
ibmcloud sl file snapshot-create ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Note da impostare sulla nuova istantanea.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
Questo comando crea un'istantanea per il volume con ID 12345678 e con una nota aggiunta come snapshotforibmcloud.

## ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Disabilita le istantanee nella pianificazione specificata per un determinato volume.
```
ibmcloud sl file snapshot-disable ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obbligatorio. Pianificazione dell'istantanea; le opzioni sono: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
Questo comando disabilita l'istantanea giornaliera per il volume con ID 12345678.

## ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Abilita le istantanee per un determinato volume nella pianificazione specificata.
```
ibmcloud sl file snapshot-enable ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obbligatorio. Pianificazione dell'istantanea; le opzioni sono: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Obbligatorio. Numero di istantanee da conservare.</dd>
<dt>-m, --minute</dt>
<dd>Minuto dell'ora in cui dovrebbero essere acquisite le istantanee, numero intero compreso tra 0 e 59.</dd>
<dt>-r, --hour</dt>
<dd>Ora del giorno in cui dovrebbero essere acquisite le istantanee, numero intero compreso tra 0 e 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Giorno della settimana in cui dovrebbero essere acquisite le istantanee, numero intero compreso tra 0 e 6. 0 indica domenica, 1 indica lunedì, 2 indica martedì, 3 indica mercoledì, 4 indica giovedì, 5 indica venerdì, 6 indica sabato.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Questo comando abilita l'istantanea per il volume con ID 12345678, l'istantanea viene acquisita settimanalmente ogni domenica alle 2:00 e vengono conservate fino a 5 istantanee.

## ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Elimina un'istantanea in un determinato volume.
```
ibmcloud sl file snapshot-delete ID_ISTANTANEA
```


**Esempi**:
```
ibmcloud sl file snapshot-delete 12345678
```
Questo comando elimina l'istantanea con ID 12345678.

## ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

Elenca le istantanee dell'archiviazione file.
```
ibmcloud sl file snapshot-list ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,name,created,size_bytes.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
Questo comando elenca tutte le istantanee del volume con ID 12345678 e le ordina in base all'ID.

## ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Ordina lo spazio dell'istantanea per un volume dell'archiviazione file.
```
ibmcloud sl file snapshot-order ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Obbligatorio. Dimensione dello spazio dell'istantanea da creare in GB.</dd>
<dt>-t, --tier</dt>
<dd>Facoltativo. Livello archiviazione durata (IOPS per GB) del volume di file per cui è ordinato lo spazio; le opzioni sono: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Contrassegno per indicare che l'ordine è un aggiornamento.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
Questo comando ordina lo spazio dell'istantanea per il volume con ID 12345678, la dimensione è 1000GB, la classe di livello è 4 IOPS per GB.

## ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Ripristina il volume di file utilizzando un'istantanea fornita.
```
ibmcloud sl file snapshot-restore ID_VOLUME ID_ISTANTANEA
```


**Esempi**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```
Questo comando ripristina il volume con ID 12345678 dall'istantanea con ID 87654321.

## ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Annulla un volume di archiviazione file esistente.
```
ibmcloud sl file volume-cancel ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Un motivo facoltativo per l'annullamento.</dd>
<dt>--immediate</dt>
<dd>Annulla il volume di archiviazione file immediatamente invece che a una ricorrenza di fatturazione.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
Questo comando annulla il volume con ID 12345678 immediatamente e senza richiedere conferma.

## ibmcloud sl file volume-count
{: #sl_file_volume_count}

Elenca il numero di volumi di archiviazione file per datacenter.
```
ibmcloud sl file volume-count [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
</dl>

## ibmcloud sl file volume-list
{: #sl_file_volume_list}

Elenca l'archiviazione file.
```
ibmcloud sl file volume-list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Filtra per nome utente del volume.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
<dt>-t, --storage-type</dt>
<dd>Filtra in base al tipo di volume di archiviazione; le opzioni sono: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Filtra in base all'ID dell'ordine che ha acquistato l'archiviazione file.</dd>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,mount_addr.</dd>
<dt>--columns</dt>
<dd>Colonne da visualizzare; le opzioni sono: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
Questo comando elenca i volumi di durata sull'account corrente ubicati in dal09 e li ordina per capacità.

## ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Visualizza i dettagli di un volume specificato.
```
ibmcloud sl file volume-detail ID_VOLUME
```


**Esempi**:
```
ibmcloud sl file volume-detail 12345678
```
Questo comando mostra i dettagli del volume con ID 12345678.

## ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Ordina un volume di file duplicando un volume esistente.
```
ibmcloud sl file volume-duplicate ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID di un'istantanea del volume originale da utilizzare per la duplicazione.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Dimensione del volume di file duplicato in GB; se non si specifica alcuna dimensione, verrà utilizzata la dimensione del volume originale.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100; se non viene specificato un IOPS, verrà utilizzato l'IOPS del volume originale.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Livello archiviazione durata, se non si specifica un livello, verrà utilizzato il livello del volume originale.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>La dimensione dello spazio dell'istantanea da ordinare per il duplicato; se non si specifica alcuna dimensione di spazio dell'istantanea, verrà utilizzata la dimensione di spazio istantanea del volume originale.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file volume-duplicate 12345678
```
Questo comando mostra come ordinare un nuovo volume duplicando il volume con ID 12345678.

## ibmcloud sl file volume-order
{: #sl_file_volume_order}

Ordina un volume dell'archiviazione file.
```
ibmcloud sl file volume-order [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Obbligatorio. Tipo del volume di archiviazione; le opzioni sono: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Obbligatorio. Dimensione del volume di archiviazione in GB.</dd>
<dt>-i, --iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100 [obbligatorio per storage-type performance].</dd>
<dt>-e, --tier</dt>
<dd>Livello archiviazione durata (IOPS per GB) [obbligatorio per storage-type endurance]; le opzioni sono: 0.25,2,4,10.</dd>
<dt>-d, --datacenter</dt>
<dd>Obbligatorio. Nome breve del datacenter.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parametro facoltativo per l'ordinamento dello spazio dell'istantanea con il volume.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
Questo comando ordina un volume delle prestazioni con dimensione di 1000GB, IOPS di 4000, ubicato in dal09.

## ibmcloud sl file volume-options
{: #sl_file_volume_options}

Elenca tutte le opzioni per l'ordinamento di un'archiviazione file.
```
ibmcloud sl file volume-options
```


**Esempi**:
```
ibmcloud sl file volume-options
```
Questo comando elenca tutte le opzioni per la creazione di un volume di archiviazione file, inclusi il tipo di archiviazione, la dimensione del volume, gli IOPS, la classe di livello, il datacenter e la dimensione dell'istantanea.
