---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Block storage CLI commands

 <table summary="Alphabetically ordered general {{site.data.keyword.BluSoftlayer_notm}} infrastructure commands that have links that bring you to more info for the command">
<caption>Table 1. {{site.data.keyword.BluSoftlayer_notm}} infrastructure Block storage</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} infrastructure Block storage</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-password](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_access_password)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_replica_failover)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl block replica-locations](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_replica_locations)</td>
  <td>[ibmcloud sl block replica-order](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_replica_order)</td>
  <td>[ibmcloud sl block replica-partners](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_replica_partners)</td>
  <td>[ibmcloud sl block snapshot-cancel](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_cancel)</td>
  <td>[ibmcloud sl block snapshot-create](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_create)</td>
  <td>[ibmcloud sl block snapshot-disable](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_disable)</td>
</tr>
<tr>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_enable)</td>
  <td>[ibmcloud sl block snapshot-delete](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_delete)</td>
  <td>[ibmcloud sl block snapshot-list](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_list)</td>
  <td>[ibmcloud sl block snapshot-order](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_order)</td>
  <td>[ibmcloud sl block snapshot-restore](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_cancel)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-count](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_count)</td>    <td>[ibmcloud sl block volume-detail](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_detail)</td>
   <td>[ibmcloud sl block volume-duplicate](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_duplicate)</td>
   <td>[ibmcloud sl block volume-list](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_list)</td>
   <td>[ibmcloud sl block volume-order](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_options)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-set-lun-id](/docs/cli/reference/softlayer/sl_cli_block_storage.html#sl_block_volume_set_lun_id)</td>  
</tr>
</tbody>
</table>
 
### ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Authorize hosts to access a given volume.
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
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
</dl>

**Examples**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
This command authorizes virtual server with ID 87654321 to access volume with ID 12345678.

### ibmcloud sl block access-list
{: #sl_block_access_list}

List ACLs.
```
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
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
ibmcloud sl block access-list 12345678 --sortby id
```
This command lists all hosts that are authorized to access volume with ID 12345678 and sorts them by ID.

### ibmcloud sl block access-password
{: #sl_block_access_password}

Changes a password for a volume's access.
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

### ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Revoke authorization for hosts accessing a given volume.
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
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
</dl>

**Examples**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
This command revokes access of virtual server with ID 87654321 to volume with ID 12345678.

### ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Failback a block volume from replica.
```
ibmcloud sl block replica-failback VOLUME_ID
```


**Examples**:
```
ibmcloud sl block replica-failback 12345678
```
This command performs failback operation for volume with ID 12345678.

### ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Failover a block volume to the given replica volume.
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**Examples**:
```
ibmcloud sl block replica-failover 12345678 87654321
```
This command performs failover operation for volume with ID 12345678 to replica volume with ID 87654321.

### ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

List suitable replication datacenters for the given volume.
```
ibmcloud sl block replica-locations VOLUME_ID
```


**Examples**:
```
ibmcloud sl block replica-locations 12345678
```
This command lists suitable replication data centers for block volume with ID 12345678.

### ibmcloud sl block replica-order
{: #sl_block_replica_order}

Order a block storage replica volume.
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>Required. Snapshot schedule to use for replication, options are: HOURLY,DAILY,WEEKLY.</dd>
<dt>-d, --datacenter</dt>
<dd>Required. Short name of the datacenter for the replica, eg. dal09 .</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance Storage Tier (IOPS per GB) of the primary volume for which a replica is ordered , options are: 0.25,2,4,10,if no tier is specified, the tier of the original volume will be used.</dd>
<dt>-i, --iops</dt>
<dd>Performance Storage IOPs, between 100 and 6000 in multiples of 100,if no IOPS  is specified, the IOPS  of the original volume will be used.</dd>
<dt>-o, --os-type</dt>
<dd>Optional. Operating System Type (eg. LINUX) of the primary volume for which a replica is ordered , options are: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
This command orders a replica for volume with ID 12345678, which performs DAILY replication, is located at dal09, tier level is 4, OS type is Linux.

### ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

List existing replicant volumes for a block volume.
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONS]
```


**Examples**:
```
ibmcloud sl block replica-partners 12345678
```
This command lists existing replicant volumes for block volume with ID 12345678.

### ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Cancel existing snapshot space for a given volume.
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
This command cancels snapshot with ID 12345678 immediately without asking for confirmation.

### ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Create a snapshot on a given volume.
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-n, --note</dt>
<dd>Notes to set on the new snapshot.</dd>
</dl>

**Examples**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
This command creates a snapshot for volume with ID 12345678 and with addition note as snapshotforibmcloud.

### ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Disable snapshots on the specified schedule for a given volume.
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>Required. Snapshot schedule , options are: HOURLY,DAILY,WEEKLY.</dd>
</dl>

**Examples**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
This command disables daily snapshot for volume with ID 12345678.

### ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Enable snapshots for a given volume on the specified schedule.
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
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
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
This command enables snapshot for volume with ID 12345678, snapshot is taken weekly on every Sunday at 2:00, and up to 5 snapshots are retained.

### ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Delete a snapshot on a given volume.
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**Examples**:
```
ibmcloud sl block snapshot-delete 12345678
```
This command deletes snapshot with ID 12345678.

### ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

List block storage snapshots.
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,name,created,size_bytes.</dd>
</dl>

**Examples**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
This command lists all snapshots of volume with ID 12345678 and sorts them by ID.

### ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Order snapshot space for a block storage volume.
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-s, --size</dt>
<dd>Required. Size of snapshot space to create in GB  .</dd>
<dt>-t, --tier</dt>
<dd>Optional. Endurance Storage Tier (IOPS per GB) of the block volume for which space is ordered , options are: 0.25,2,4,10.</dd>
<dt>-i, --iops</dt>
<dd>Performance Storage IOPs, between 100 and 6000 in multiples of 100.</dd>
<dt>-u, --upgrade</dt>
<dd>Flag to indicate that the order is an upgrade.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
This command orders snapshot space for volume with ID 12345678, the size is 1000GB, the tier level is 4 IOPS per GB.

### ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Restore block volume using a given snapshot.
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**Examples**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
This command restores volume with ID 12345678 from snapshot with ID 87654321.

### ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Cancel an existing block storage volume.
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--reason</dt>
<dd>An optional reason for cancellation.</dd>
<dt>--immediate</dt>
<dd>Cancel the block storage volume immediately instead of on the billing anniversary.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
This command cancels volume with ID 12345678 immediately and without asking for confirmation.

### ibmcloud sl block volume-count
{: #sl_block_volume_count}

List number of block storage volumes per datacenter.
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter shortname.</dd>
</dl>

### ibmcloud sl block volume-list
{: #sl_block_volume_list}

List block storage.
```
ibmcloud sl block volume-list [OPTIONS]
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
<dd>Filter by ID of the order that purchased the block storage.</dd>
<dt>--sortby</dt>
<dd>Column to sort by, options are: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,active_transactions,created_by.</dd>
<dt>--columns</dt>
<dd>Columns to display, options are: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,created_by.</dd>
</dl>

**Examples**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
This command lists all endurance volumes on current account that are located at dal09, and sorts them by capacity.

### ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

Set the LUN ID on an existing block storage volume.
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

### ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Display details for a specified volume.
```
ibmcloud sl block volume-detail VOLUME_ID
```


**Examples**:
```
ibmcloud sl block volume-detail 12345678
```
This command shows details of volume with ID 12345678.

### ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Order a block volume by duplicating an existing volume.
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>ID of an origin volume snapshot to use for duplication.</dd>
<dt>-s, --duplicate-size</dt>
<dd>Size of duplicate block volume in GB, if no size is specified, the size of the original volume will be used.</dd>
<dt>-i, --duplicate-iops</dt>
<dd>Performance Storage IOPS, between 100 and 6000 in multiples of 100, if no IOPS  is specified, the IOPS  of the original volume will be used.</dd>
<dt>-t, --duplicate-tier</dt>
<dd>Endurance Storage Tier, if no tier is specified, the tier of the original volume will be used.</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>The size of snapshot space to order for the duplicate, if no snapshot space size is specified, the snapshot space size of the origin volume will be used.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl block volume-duplicate 12345678
```
This command shows order a new volume by duplicating the volume with ID 12345678.

### ibmcloud sl block volume-order
{: #sl_block_volume_order}

Order a block storage volume.
```
ibmcloud sl block volume-order [OPTIONS]
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
<dt>-o, --os-type</dt>
<dd>Required. Operating System , options are: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.</dd>
<dt>-d, --datacenter</dt>
<dd>Required. Datacenter short name .</dd>
<dt>-n, --snapshot-size</dt>
<dd>Optional parameter for ordering snapshot space along with endurance block storage; specifies the size (in GB) of snapshot space to order.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
This command orders a performance volume with size is 1000GB, IOPS is 4000, OS type is LINUX, located at dal09.

### ibmcloud sl block volume-options
{: #sl_block_volume_options}

List all options for ordering a block storage.
```
ibmcloud sl block volume-options
```


**Examples**:
```
ibmcloud sl block volume-options
```
This command lists all options for creating a block storage volume, including storage type, volume size, OS type, IOPS, tier level, datacenter, and snapshot size.
