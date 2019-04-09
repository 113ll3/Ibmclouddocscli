---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, block storage, mpio, ibmcloud sl block, volume-options, snapshot, datacenter, replica, cli, storage type, size

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione del servizio {{site.data.keyword.blockstorageshort}}
{: #sl-block-storage}

{{site.data.keyword.cloud}} {{site.data.keyword.blockstorageshort}} è un'archiviazione iSCSI persistente e a elevate prestazioni di cui viene eseguito il provisioning e la gestione indipendentemente dalle istanze di calcolo. Le LUN {{site.data.keyword.blockstorageshort}} basate su iSCSI sono connesse ai dispositivi autorizzati tramite connessioni MPIO (multi-path I/O) ridondanti. 

Utilizza i seguenti comandi per gestire uno specifico volume per il servizio {{site.data.keyword.blockstorageshort}} dell'infrastruttura classica {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Autorizza gli host ad accedere a un determinato volume.
```
ibmcloud sl block access-authorize ID_VOLUME [OPZIONI]
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
</dl>

**Esempi**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```

Questo comando autorizza il server virtuale con ID `87654321` ad accedere al volume con ID `12345678`.

## ibmcloud sl block access-list
{: #sl_block_access_list}

Elenca ACL.
```
ibmcloud sl block access-list ID_VOLUME [OPZIONI]
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
ibmcloud sl block access-list 12345678 --sortby id
```
Questo comando elenca tutti gli host autorizzati ad accedere al volume con ID 12345678 e li ordina in base all'ID.

## ibmcloud sl block access-password
{: #sl_block_access_password}

Modifica una password per l'accesso di un volume.
```
ibmcloud sl block access-password ID_ACCESSO PASSWORD
```

## ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Revoca l'autorizzazione agli host che accedono a un determinato volume.
```
ibmcloud sl block access-revoke ID_VOLUME [OPZIONI]
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
</dl>

**Esempi**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
Questo comando revoca l'accesso del server virtuale con ID 87654321 al volume con ID 12345678.

## ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Failback di un volume di blocchi dalla replica.
```
ibmcloud sl block replica-failback ID_VOLUME
```


**Esempi**:
```
ibmcloud sl block replica-failback 12345678
```

Questo comando esegue l'operazione di failback per il volume con ID `12345678`.

## ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Failover di un volume di blocchi nel volume di replica fornito.
```
ibmcloud sl block replica-failover ID_VOLUME ID_REPLICA
```


**Esempi**:
```
ibmcloud sl block replica-failover 12345678 87654321
```

Questo comando esegue l'operazione di failover per il volume con ID `12345678` nel volume di replica con ID `87654321`.

## ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

Elenca i datacenter di replica appropriati per il volume fornito.
```
ibmcloud sl block replica-locations ID_VOLUME
```


**Esempi**:
```
ibmcloud sl block replica-locations 12345678
```

Questo comando elenca i datacenter di replica appropriati per il volume di blocchi con ID `12345678`.

## ibmcloud sl block replica-order
{: #sl_block_replica_order}

Ordina un volume di replica dell'archiviazione blocchi.
```
ibmcloud sl block replica-order ID_VOLUME [OPZIONI]
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
<dt>-o, --os-type</dt>
<dd>Facoltativo. Tipo di sistema operativo (es. LINUX) del volume primario per cui è ordinata la replica; le opzioni sono: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```

Questo comando ordina una replica per il volume con ID `12345678`, che esegue la replica giornaliera (DAILY); è ubicato in `dal09`, il livello è 4, il tipo di SO è Linux.

## ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

Elenca i volumi di replica esistenti per un volume di blocchi.
```
ibmcloud sl block replica-partners ID_VOLUME [OPZIONI]
```


**Esempi**:
```
ibmcloud sl block replica-partners 12345678
```

Questo comando elenca i volumi di replica esistenti per il volume di blocchi con ID `12345678`.

## ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Annulla lo spazio di istantanea esistente per un determinato volume.
```
ibmcloud sl block snapshot-cancel ID_ISTANTANEA [OPZIONI]
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
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```

Questo comando annulla l'istantanea con ID `12345678` immediatamente senza richiedere la conferma.

## ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Crea un'istantanea in un determinato volume.
```
ibmcloud sl block snapshot-create ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Note da impostare sulla nuova istantanea.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```

Questo comando crea un'istantanea per il volume con ID `12345678` e con la nota aggiunta come `snapshotforibmcloud`.

## ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Disabilita le istantanee nella pianificazione specificata per un determinato volume.
```
ibmcloud sl block snapshot-disable ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Obbligatorio. Pianificazione dell'istantanea; le opzioni sono: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```

Questo comando disabilita l'istantanea giornaliera per il volume con ID `12345678`.

## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Abilita le istantanee per un determinato volume nella pianificazione specificata.
```
ibmcloud sl block snapshot-enable ID_VOLUME [OPZIONI]
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
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
Questo comando abilita l'istantanea per il volume con ID `12345678`, l'istantanea viene acquisita settimanalmente ogni domenica alle 2:00 e vengono conservate fino a 5 istantanee.

## ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Elimina un'istantanea in un determinato volume.
```
ibmcloud sl block snapshot-delete ID_ISTANTANEA
```


**Esempi**:
```
ibmcloud sl block snapshot-delete 12345678
```

Questo comando elimina l'istantanea con ID `12345678`.

## ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

Elenca le istantanee dell'archiviazione blocchi.
```
ibmcloud sl block snapshot-list ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,name,created,size_bytes.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```

Questo comando elenca tutte le istantanee del volume con ID `12345678` e le ordina per ID.

## ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Ordina lo spazio dell'istantanea per un volume dell'archiviazione blocchi.
```
ibmcloud sl block snapshot-order ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Obbligatorio. Dimensione dello spazio dell'istantanea da creare in GB.</dd>
<dt>-t, --tier</dt>
<dd>Facoltativo. Livello archiviazione durata (IOPS per GB) di un volume di blocchi per cui è ordinato lo spazio; le opzioni sono: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Contrassegno per indicare che l'ordine è un aggiornamento.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```

Questo comando ordina lo spazio dell'istantanea per il volume con ID `12345678`, la dimensione è 1000 GB, la classe di livello è 4 IOPS per GB.

## ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Ripristina il volume di blocchi utilizzando un'istantanea fornita.
```
ibmcloud sl block snapshot-restore ID_VOLUME ID_ISTANTANEA
```

**Esempi**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```

Questo comando ripristina il volume con ID `12345678` dall'istantanea con ID `87654321`.

## ibmcloud sl block snapshot-schedule-list
{: #sl_block_snapshot_schedule_list}

Elenca le pianificazioni dell'istantanea per un volume selezionato
```
ibmcloud sl block snapshot-schedule-list VOLUME_ID
```

**Esempi**:
```
ibmcloud sl block snapshot-schedule-list 12345678
```

Questo comando elenca le pianificazioni dell'istantanea dell'elenco comandi per il volume con ID `12345678`

## ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Annulla un volume di archiviazione blocchi esistente.
```
ibmcloud sl block volume-cancel ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--reason</dt>
<dd>Un motivo facoltativo per l'annullamento.</dd>
<dt>--immediate</dt>
<dd>Annulla il volume di archiviazione blocchi immediatamente invece che a una ricorrenza di fatturazione.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```

Questo comando annulla il volume con ID `12345678` immediatamente e senza richiedere conferma.

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

Elenca il numero di volumi di archiviazione blocchi per datacenter.
```
ibmcloud sl block volume-count [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
</dl>

## ibmcloud sl block volume-list
{: #sl_block_volume_list}

Elenca l'archiviazione blocchi.
```
ibmcloud sl block volume-list [OPZIONI]
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
<dd>Filtra in base all'ID dell'ordine che ha acquistato l'archiviazione blocchi.</dd>
<dt>--sortby</dt>
<dd>Colonna da ordinare, le opzioni sono: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
<dt>--columns</dt>
<dd>Colonne da visualizzare; le opzioni sono: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,created_by,notes.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```

Questo comando elenca i volumi di durata sull'account corrente ubicati in `dal09` e li ordina per capacità.

## ibmcloud sl block volume-modify
{: #sl_block_volume_modify}

Modifica un volume di archiviazione blocchi esistente
```
ibmcloud sl block volume-modify VOLUME_ID [OPTIONS]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-c, --new-size</dt>
<dd>Nuova dimensione del volume di blocchi in GB. ***Se non viene fornita alcuna dimensione, viene utilizzata la dimensione originale del volume.*** Dimensioni potenziali: [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000] Minimo: [la dimensione originale del volume]</dd>
<dt>-i, --new-iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100 [solo per i volumi delle prestazioni] ***Se non viene specificato alcun valore IOPS, sarà utilizzato il valore originale del volume.*** Requisiti: [Se l'IOPS/GB originale del volume è inferiore a 0.3, anche il nuovo IOPS/GB deve essere inferiore a 0.3. Se l'IOPS/GB del volume è maggiore di o uguale a 0.3, anche il nuovo IOPS/GB deve essere maggiore di o uguale a 0.3.]</dd>
<dt>-t, --new-tier</dt>
<dd>Livello archiviazione durata (IOPS per GB) [solo per i volumi di durata] ***Se non viene specificato un livello, sarà utilizzato quello originale del volume.***
Requisiti: [Se l'IOPS/GB originale del volume è inferiore a 0.25, anche il nuovo IOPS/GB del volume deve essere 0.25. Se l'IOPS/GB del volume è maggiore di 0.25, anche il nuovo IOPS/GB deve essere maggiore di 0.25.]</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:

```
ibmcloud sl block volume-modify 12345678 --new-size 1000 --new-iops 4000
```

Questo comando modifica un volume `12345678` con dimensione di 1000GB e IOPS 4000.

```
ibmcloud sl block volume-modify 12345678 --new-size 500 --new-tier 4
```

Questo comando modifica un volume `12345678` con dimensione di 500GB, livello 4 IOPS per GB.

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

Imposta l'ID LUN in un volume di archiviazione blocchi esistente.
```
ibmcloud sl block volume-set-lun-id ID_VOLUME ID_LUN
```

## ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Visualizza i dettagli di un volume specificato.
```
ibmcloud sl block volume-detail ID_VOLUME
```

**Esempi**:
```
ibmcloud sl block volume-detail 12345678
```

Questo comando mostra i dettagli del volume con ID `12345678`.

## ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Ordina un volume di blocchi duplicando un volume esistente.
```
ibmcloud sl block volume-duplicate ID_VOLUME [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID di un'istantanea del volume di origine da utilizzare per la duplicazione.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Dimensione del volume di blocchi duplicato in GB; se non si specifica alcuna dimensione, verrà utilizzata la dimensione del volume originale.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>IOPS archiviazione prestazioni, compreso tra 100 e 6000 in multipli di 100; se non viene specificato un IOPS, verrà utilizzato l'IOPS del volume originale.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Livello archiviazione durata, se non si specifica un livello, verrà utilizzato il livello del volume originale.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>La dimensione dello spazio dell'istantanea da ordinare per il duplicato; se non si specifica alcuna dimensione di spazio dell'istantanea, verrà utilizzata la dimensione di spazio istantanea del volume di origine.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block volume-duplicate 12345678
```

Questo comando mostra come ordinare un nuovo volume duplicando il volume con ID `12345678`.

## ibmcloud sl block volume-order
{: #sl_block_volume_order}

Ordina un volume dell'archiviazione blocchi.
```
ibmcloud sl block volume-order [OPZIONI]
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
<dt>-o, --os-type</dt>
<dd>Obbligatorio. Sistema operativo; le opzioni sono: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Obbligatorio. Nome breve del datacenter.</dd>
<dt>-n, --snapshot-size</dt>
<dd>Parametro facoltativo per l'ordinamento dello spazio dell'istantanea insieme all'archiviazione blocchi della durata; specifica la dimensione (in GB) dello spazio dell'istantanea da ordinare.</dd>
<dt>-b, --billing</dt>
<dd>Parametro facoltativo per la frequenza di fatturazione; le opzioni sono: hourly, monthly.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```

Questo comando ordina un volume delle prestazioni con dimensione di 1000 GB, IOPS di 4000, tipo di SO LINUX, ubicato in `dal09`.

## ibmcloud sl block volume-options
{: #sl_block_volume_options}

Elenca tutte le opzioni per l'ordinamento di una archiviazione blocchi.
```
ibmcloud sl block volume-options
```

**Esempi**:
```
ibmcloud sl block volume-options
```

Questo comando elenca tutte le opzioni per la creazione di un volume di archiviazione blocchi, inclusi il tipo di archiviazione, la dimensione del volume, il tipo di SO, l'IOPS, la classe di livello, il datacenter e la dimensione dell'istantanea.
