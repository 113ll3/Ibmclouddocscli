---

copyright:

  years: 2018


lastupdated: "2018-08-20"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing {{site.data.keyword.Bluemix_notm}} infrastructure File storage

<table summary="Alphabetically ordered general {{site.data.keyword.Bluemix_notm}} infrastructure commands that have links that bring you to more info for the command">
<caption>Table 1. {{site.data.keyword.Bluemix_notm}} infrastructure File storage</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} infrastructure File storage</th>
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

 ### ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Authorize hosts to access a given volume.
```
ibmcloud sl file access-authorize VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>The ID of one hardware server to authorize.</dd>
<dt>-v, --virtual-id</dt>
<dd>The ID of one virtual server to authorize.</dd>
<dt>-i, --ip-address-id</dt>
<dd>The ID of one IP address to authorize.</dd>
<dt>-p, --ip-address</dt>
<dd>An IP address to authorize.</dd>
<dt>-s, --subnet-id</dt>
<dd>An ID of one subnet to authorize.</dd>
</dl>

**Examples**:
```
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
This command authorizes virtual server with ID 87654321 to access volume with ID 12345678.

### ibmcloud sl file access-list
{: #sl_file_access_list}

List ACLs.
```
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,name,type,private_ip_address,host_iqn,username,password.</dd>
<dt>--columns</dt>
<dd>Columns to display, options are: id,name,type,private_ip_address,host_iqn,username,password.</dd>
</dl>

**Examples**:
```
ibmcloud sl file access-list 12345678 --sortby id
```
This command lists all hosts that are authorized to access volume with ID 12345678 and sorts them by ID.

### ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Revoke authorization for hosts accessing a given volume.
```
ibmcloud sl file access-revoke VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>The ID of one hardware server to revoke.</dd>
<dt>-v, --virtual-id</dt>
<dd>The ID of one virtual server to revoke.</dd>
<dt>-i, --ip-address-id</dt>
<dd>The ID of one IP address to revoke.</dd>
<dt>-p, --ip-address</dt>
<dd>An IP address to revoke.</dd>
<dt>-s, --subnet-id</dt>
<dd>An ID of one subnet to revoke.</dd>
</dl>

**Examples**:
```
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
This command revokes access of virtual server with ID 87654321 to volume with ID 12345678.

### ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Failback a file volume from replica.
```
ibmcloud sl file replica-failback VOLUME_ID
```


**Examples**:
```
ibmcloud sl file replica-failback 12345678
```
This command performs failback operation for volume with ID 12345678.

### ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Failover a file volume to the given replica volume.
```
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```


**Examples**:
```
ibmcloud sl file replica-failover 12345678 87654321
```
This command performs failover operation for volume with ID 12345678 to replica volume with ID 87654321.

### ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

List suitable replication datacenters for the given volume.
```
ibmcloud sl file replica-locations VOLUME_ID
```


**Examples**:
```
ibmcloud sl file replica-locations 12345678
```
This command lists suitable replication data centers for file volume with ID 12345678.

### ibmcloud sl file replica-order
{: #sl_file_replica_order}

Order a file storage replica volume.
```
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Required. Snapshot schedule to use for replication, , options are: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Required. Short name of the datacenter for the replica, eg. dal09 .</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance Storage Tier (IOPS per GB) of the primary volume for which a replica is ordered , options are: 0.25,2,4,10,if no tier is specified, the tier of the original volume will be used.</dd>
<dt>-i, --iops</dt>
<dd>Performance Storage IOPs, between 100 and 6000 in multiples of 100,if no IOPS  is specified, the IOPS  of the original volume will be used.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
This command orders a replica for volume with ID 12345678, which performs DAILY replication, is located at dal09, tier level is 4.

### ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

List existing replicant volumes for a file volume.
```
ibmcloud sl file replica-partners VOLUME_ID [OPTIONS]
```


**Examples**:
```
ibmcloud sl file replica-partners 12345678
```
This command lists existing replicant volumes for file volume with ID 12345678.

### ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Cancel existing snapshot space for a given volume.
```
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--reason</dt>
<dd>An optional reason for cancellation.</dd>
<dt>--immediate</dt>
<dd>Cancel the snapshot space immediately instead of on the billing anniversary.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
This command cancels snapshot with ID 12345678 immediately without asking for confirmation.

### ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Create a snapshot on a given volume.
```
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notes to set on the new snapshot.</dd>
</dl>

**Examples**:
```
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
This command creates a snapshot for volume with ID 12345678 and with addition note as snapshotforibmcloud.

### ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Disable snapshots on the specified schedule for a given volume.
```
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Required. Snapshot schedule , options are: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Examples**:
```
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
This command disables daily snapshot for volume with ID 12345678.

### ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Enable snapshots for a given volume on the specified schedule.
```
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Required. Snapshot schedule , options are: HOURLY,DAILY,WEEKLY.</dd>
<dt>-c, --retention-count</dt>
<dd>Required. Number of snapshots to retain .</dd>
<dt>-m, --minute</dt>
<dd>Minute of the hour when snapshots should be taken, integer between 0 to 59.</dd>
<dt>-r, --hour</dt>
<dd>Hour of the day when snapshots should be taken, integer between 0 to 23.</dd>
<dt>-d, --day-of-week</dt>
<dd>Day of the week when snapshots should be taken, integer between 0 to 6. 0 means Sunday,1 means Monday,2 means Tuesday,3 means Wendesday,4 means Thursday,5 means Friday,6 means Saturday.</dd>
</dl>

**Examples**:
```
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
This command enables snapshot for volume with ID 12345678, snapshot is taken weekly on every Sunday at 2:00, and up to 5 snapshots are retained.

### ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Delete a snapshot on a given volume.
```
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```


**Examples**:
```
ibmcloud sl file snapshot-delete 12345678
```
This command deletes snapshot with ID 12345678.

### ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

List file storage snapshots.
```
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,name,created,size_bytes.</dd>
</dl>

**Examples**:
```
ibmcloud sl file snapshot-list 12345678 --sortby id
```
This command lists all snapshots of volume with ID 12345678 and sorts them by ID.

### ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Order snapshot space for a file storage volume.
```
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Required. Size of snapshot space to create in GB  .</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance Storage Tier (IOPS per GB) of the file volume for which space is ordered , options are: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>Performance Storage IOPs, between 100 and 6000 in multiples of 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Flag to indicate that the order is an upgrade.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
This commands order snapshot space for volume with ID 12345678, the size is 1000GB, the tier level is 4 IOPS per GB.

### ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Restore file volume using a given snapshot.
```
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Examples**:
```
ibmcloud sl file snapshot-restore 12345678 87654321
```
This command restores volume with ID 12345678 from snapshot with ID 87654321.

### ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Cancel an existing file storage volume.
```
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--reason</dt>
<dd>An optional reason for cancellation.</dd>
<dt>--immediate</dt>
<dd>Cancel the file storage volume immediately instead of on the billing anniversary.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
This command cancels volume with ID 12345678 immediately and without asking for confirmation.

### ibmcloud sl file volume-count
{: #sl_file_volume_count}

List number of file storage volumes per datacenter.
```
ibmcloud sl file volume-count [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter shortname.</dd>
</dl>

### ibmcloud sl file volume-list
{: #sl_file_volume_list}

List file storage.
```
ibmcloud sl file volume-list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-u, --username</dt>
<dd>Filter by volume username.</dd>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter shortname.</dd>
<dt>-t, --storage-type</dt>
<dd>Filter by type of storage volume, options are: performance,endurance.</dd>
<dt>-o, --order</dt>
<dd>Filter by ID of the order that purchased the file storage.</dd>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,mount_addr.</dd>
<dt>--columns</dt>
<dd>Columns to display, options are: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,mount_addr.</dd>
</dl>

**Examples**:
```
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
This command lists all endurance volumes on current account that are located at dal09, and sorts them by capacity.

### ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Display details for a specified volume.
```
ibmcloud sl file volume-detail VOLUME_ID
```


**Examples**:
```
ibmcloud sl file volume-detail 12345678
```
This command shows details of volume with ID 12345678.

### ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Order a file volume by duplicating an existing volume.
```
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID of an original volume snapshot to use for duplication.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Size of duplicate file volume in GB, if no size is specified, the size of the original volume will be used.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>Performance Storage IOPS, between 100 and 6000 in multiples of 100, if no IOPS  is specified, the IOPS  of the original volume will be used.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance Storage Tier, if no tier is specified, the tier of the original volume will be used.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>The size of snapshot space to order for the duplicate, if no snapshot space size is specified, the snapshot space size of the original volume will be used.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl file volume-duplicate 12345678
```
This command shows order a new volume by duplicating the volume with ID 12345678.

### ibmcloud sl file volume-order
{: #sl_file_volume_order}

Order a file storage volume.
```
ibmcloud sl file volume-order [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>Required. Type of storage volume , options are: performance,endurance.</dd>
<dt>-s, --size</dt>
<dd>Required. Size of storage volume in GB .</dd>
<dt>-i, --iops</dt>
<dd>Performance Storage IOPs, between 100 and 6000 in multiples of 100 [required for storage-type performance].</dd>
<dt>-e, --tier</dt>
<dd>Endurance Storage Tier (IOP per GB) [required for storage-type endurance], options are: 0.25,2,4,10.</dd>
<dt>-d, --datacenter</dt>
<dd>Required. Datacenter short name .</dd>
<dt>-n, --snapshot-size</dt>
<dd>Optional parameter for ordering snapshot space along with the volume.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
This command orders a performance volume with size is 1000GB, IOPS is 4000, located at dal09.

### ibmcloud sl file volume-options
{: #sl_file_volume_options}

List all options for ordering a file storage.
```
ibmcloud sl file volume-options
```


**Examples**:
```
ibmcloud sl file volume-options
```
This command lists all options for creating a file storage volume, including storage type, volume size, IOPS, tier level, datacenter, and snapshot size.
