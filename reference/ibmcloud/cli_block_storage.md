---

copyright:
  years: 2018, 2021
lastupdated: "2021-12-15"

keywords: classic infrastructure, block storage, mpio, ibmcloud sl block, volume-options, snapshot, datacenter, replica, cli, storage type, size

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Working with the {{site.data.keyword.blockstorageshort}} service (ibmcloud sl block)
{: #sl-block-storage}

{{site.data.keyword.cloud}} {{site.data.keyword.blockstorageshort}} is a persistent, high-performance iSCSI storage that is provisioned and managed independently of compute instances. iSCSI-based {{site.data.keyword.blockstorageshort}} LUNs are connected to authorized devices through redundant multi-path I/O (MPIO) connections.
{: shortdesc}

For more information about {{site.data.keyword.blockstorageshort}}, see the [{{site.data.keyword.blockstorageshort}} documentation](/docs/BlockStorage).

Use the following commands from the {{site.data.keyword.cloud_notm}} Command Line Interface to manage a volume for the {{site.data.keyword.cloud_notm}} classic infrastructure {{site.data.keyword.blockstorageshort}} service.

## ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

Authorize hosts to access a volume:

```bash
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-d, --hardware-id
:   The ID of one hardware server to authorize.

-v, --virtual-id
:   The ID of one virtual server to authorize.

-i, --ip-address-id
:   The ID of one IP address to authorize.

-p, --ip-address
:   An IP address to authorize.

**Examples**:
```bash
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
{: codeblock}

This command authorizes virtual server with ID `87654321` to access volume with ID `12345678`.

## ibmcloud sl block access-list
{: #sl_block_access_list}

List hosts that are authorized to access the volume:

```bash
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--sortby
:   Column to sort by. Options are: id,name,type,private_ip_address,source_subnet,host_iqn,username,password,allowed_host_id.

--column
:   Column to display. Options are: id,name,type,private_ip_address,source_subnet,host_iqn,username,password,allowed_host_id. This option can be specified multiple times.

**Examples**:
```bash
ibmcloud sl block access-list 12345678 --sortby id
```
{: codeblock}

This command lists all hosts that are authorized to access volume with ID `12345678` and sorts them by ID.

## ibmcloud sl block access-password
{: #sl_block_access_password}

Changes a password for a volume's access:

```bash
ibmcloud sl block access-password ACCESS_ID PASSWORD
```
{: codeblock}

## ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

Revoke authorization for hosts that are accessing a specific volume:

```bash
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-d, --hardware-id
:   The ID of one hardware server to revoke.

-v, --virtual-id
:   The ID of one virtual server to revoke.

-i, --ip-address-id
:   The ID of one IP address to revoke.

-p, --ip-address
:   An IP address to revoke.

**Examples**:
```bash
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
{: codeblock}

This command revokes access of virtual server with ID `87654321` to volume with ID `12345678`.

## ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

Fail back a block volume from replica:

```bash
ibmcloud sl block replica-failback VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block replica-failback 12345678
```
{: codeblock}

This command performs failback operation for volume with ID `12345678`.

## ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

Fail over a block volume to the specified replica volume:

```bash
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block replica-failover 12345678 87654321
```
{: codeblock}

This command performs failover operation for volume with ID `12345678` to replica volume with ID `87654321`.

## ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

List suitable replication datacenters for the specified volume:

```bash
ibmcloud sl block replica-locations VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block replica-locations 12345678
```
{: codeblock}

This command lists suitable replication data centers for block volume with ID `12345678`.

## ibmcloud sl block replica-order
{: #sl_block_replica_order}

Order a block storage replica volume:

```bash
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --snapshot-schedule
:   Required. Snapshot schedule to use for replication. Options are: HOURLY,DAILY,WEEKLY.

-d, --datacenter
:   Required. Short name of the datacenter for the replica. For example, `dal09`.

-t, --tier
:   Optional. Endurance Storage Tier (IOPS per GB) of the primary volume for which a replica is ordered. Options are: 0.25,2,4,10. If no tier is specified, the tier of the original volume is used.

-i, --iops
:   Performance Storage IOPs. Range [100-6000], and in multiples of 100. If no IOPS is specified, the IOPS of the original volume is used.

-o, --os-type
:   Optional. Operating System type of the primary volume for which a replica is ordered. Options are: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
{: codeblock}

This command orders a replica for volume with ID `12345678`, which performs DAILY replication, is located at `dal09`, tier level is 4, and OS type is Linux.

## ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

List existing replicant volumes for a block volume:

```bash
ibmcloud sl block replica-partners VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block replica-partners 12345678
```
{: codeblock}

This command lists existing replicant volumes for block volume with ID `12345678`.

## ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Cancel existing snapshot space for a specified volume:

```bash
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--reason
:   An optional reason for cancellation.

--immediate
:   Cancel the snapshot space immediately instead of on the billing anniversary.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
{: codeblock}

This command cancels snapshot with ID `12345678` immediately without asking for confirmation.

## ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

Create a snapshot on a specified volume:

```bash
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-n, --note
:   Notes to set on the new snapshot.

**Examples**:
```bash
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
{: codeblock}

This command creates a snapshot for volume with ID `12345678` and with addition note as `snapshotforibmcloud`.

## ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

Disable snapshots on the specified schedule for a specified volume:

```bash
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --schedule-type
:   Required. Snapshot schedule , options are: HOURLY,DAILY,WEEKLY.

**Examples**:
```bash
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
{: codeblock}

This command disables daily snapshot for volume with ID `12345678`.

## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

Enable snapshots for a volume on the specified schedule:

```bash
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --schedule-type
:   Required. Snapshot schedule. Options are: HOURLY,DAILY,WEEKLY.

-c, --retention-count
:   Required. Number of snapshots to retain.

-m, --minute
:   Minute of the hour when snapshots are taken, integer between [0-59].

-r, --hour
:   Hour of the day when snapshots are taken, integer between [0-23].

-d, --day-of-week
:   Day of the week when snapshots are taken, integer between [0-6]. 0 means Sunday,1 means Monday,2 means Tuesday,3 means Wednesday,4 means Thursday,5 means Friday,6 means Saturday.

**Examples**:
```bash
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
{: codeblock}

This command enables snapshot for a volume with ID `12345678`. The snapshot is taken weekly on every Sunday at 2:00, and up to 5 snapshots are retained.

## ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

Delete a snapshot on a specified volume:

```bash
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block snapshot-delete 12345678
```
{: codeblock}

This command deletes snapshot with ID `12345678`.

## ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

List block storage snapshots:

```bash
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--sortby
:   Column to sort by, options are: id,name,created,size_bytes.

**Examples**:
```bash
ibmcloud sl block snapshot-list 12345678 --sortby id
```
{: codeblock}

This command lists all snapshots of volume with ID `12345678` and sorts them by ID.

## ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

Order snapshot space for a block storage volume:

```bash
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --size
:   Required. Size of snapshot space to create in GB.

-t, --tier
:   Optional. Endurance Storage Tier (IOPS per GB) of the block volume for which space is ordered. Options are: 0.25,2,4,10.

-i, --iops
:   Performance Storage IOPs. Range [100 and 6000], and in multiples of 100.

-u, --upgrade
:   Flag to indicate that the order is an upgrade.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
{: codeblock}

This command orders snapshot space for volume with ID `12345678`, the size is 1000 GB, and the tier level is 4 IOPS per GB.

## ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

Restore block volume by using a specified snapshot:

```bash
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block snapshot-restore 12345678 87654321
```
{: codeblock}

This command restores volume with ID `12345678` from snapshot with ID `87654321`.

## ibmcloud sl block snapshot-schedule-list
{: #sl_block_snapshot_schedule_list}

List snapshot schedules for a specified volume:

```bash
ibmcloud sl block snapshot-schedule-list VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block snapshot-schedule-list 12345678
```
{: codeblock}

This command list snapshot schedules for volume with ID `12345678`.

## ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

Cancel an existing block storage volume:

```bash
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--reason
:   An optional reason for cancellation.

--immediate
:   Cancel the block storage volume immediately instead of on the billing anniversary.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
{: codeblock}

This command cancels volume with ID `12345678` immediately and without asking for confirmation.

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

List number of block storage volumes per datacenter:

```bash
ibmcloud sl block volume-count [OPTIONS]
```
{: codeblock}

**Command options**:
-d, --datacenter
:   Filter by datacenter shortname.

## ibmcloud sl block volume-limits
{: #sl_block_volume_limits}

Display the global maximum volume count for the account and the number of {{site.data.keyword.blockstorageshort}} and {{site.data.keyword.filestorage_short}} volumes that are already provisioned.

```bash
ibmcloud sl block volume-limits
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block volume-limits
```
{: codeblock}

This command lists the storage limits for this account.

## ibmcloud sl block volume-list
{: #sl_block_volume_list}

List block storage:

```bash
ibmcloud sl block volume-list [OPTIONS]
```
{: codeblock}

**Command options**:

-u, --username
:   Filter by volume username.

-d, --datacenter
:   Filter by datacenter shortname.

-t, --storage-type
:   Filter by type of storage volume, options are: performance,endurance.

-o, --order
:   Filter by ID of the order that purchased the block storage.

--sortby
:   Column to sort by, default:id, options are: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,lunId,active_transactions,created_by.

--column
:   Column to display. Options are: id,username,datacenter,storage_type,capacity_gb,bytes_used,ip_addr,lunId,created_by,active_transactions,notes. This option can be specified multiple times.

**Examples**:
```bash
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
{: codeblock}

This command lists all endurance volumes on current account that are located at `dal09`, and sorts them by capacity.

## ibmcloud sl block volume-modify
{: #sl_block_volume_modify}

Modify an existing block storage volume:

```bash
ibmcloud sl block volume-modify VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-c, --new-size
:   New Size of block volume in GB. ***If no size is given, the original size of volume is used.*** Potential Sizes: [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000] Minimum: [the original size of the volume]

-i, --new-iops
:   Performance Storage IOPS. Range between [100 and 6000], and in multiples of 100 [only for performance volumes] ***If no IOPS value is specified, the original IOPS value of the volume is used.*** Requirements: [If original IOPS/GB for the volume is less than 0.3, new IOPS/GB must also be less than 0.3. If original IOPS/GB for the volume is greater than or equal to 0.3, new IOPS/GB for the volume must also be greater than or equal to 0.3.]

-t, --new-tier
:   Endurance Storage Tier (IOPS per GB) [only for endurance volumes] ***If no tier is specified, the original tier of the volume is used.***
Requirements: [If original IOPS/GB for the volume is 0.25, new IOPS/GB for the volume must also be 0.25. If original IOPS/GB for the volume is greater than 0.25, new IOPS/GB for the volume must also be greater than 0.25.]

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block volume-modify 12345678 --new-size 1000 --new-iops 4000
```
{: codeblock}

This command modifies volume `12345678` with size of 1000 GB, and IOPS is 4000.

```bash
ibmcloud sl block volume-modify 12345678 --new-size 500 --new-tier 4
```
{: codeblock}

This command modifies volume `12345678` with size 500 GB, and tier level is 4 IOPS per GB.

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

Set the LUN ID on an existing block storage volume:

```bash
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```
{: codeblock}

## ibmcloud sl block volume-convert
{: #sl_block_volume_convert}

Convert a dependent duplicate volume to an independent volume:

```bash
ibmcloud sl block volume-convert VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block volume-convert 12345678
```
{: codeblock}

Convert a dependent duplicate 12345678 to an independent volume.

## ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

Display details for a specified volume:

```bash
ibmcloud sl block volume-detail VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block volume-detail 12345678
```
{: codeblock}

This command shows details of volume with ID `12345678`.

## ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

Order a block volume by duplicating an existing volume:

```bash
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-o, --origin-snapshot-id
:   ID of an origin volume snapshot to use for duplication.

-s, --duplicate-size
:   Size of duplicate block volume in GB. If no size is specified, the size of the original volume is used.

-i, --duplicate-iops
:   Performance Storage IOPS. Range between [100-6000], and in multiples of 100. If no IOPS is specified, the IOPS  of the original volume is used.

-t, --duplicate-tier
:   Endurance Storage Tier. If no tier is specified, the tier of the original volume is used.

-n, --duplicate-snapshot-size
:   The size of snapshot space to order for the duplicate. If no snapshot space size is specified, the snapshot space size of the origin volume is used.

-d, --dependent-duplicate
:   Whether or not this duplicate will be a dependent duplicate of the origin volume.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block volume-duplicate 12345678
```
{: codeblock}

This command shows order a new volume by duplicating the volume with ID `12345678`.

## ibmcloud sl block volume-order
{: #sl_block_volume_order}

Order a block storage volume:

```bash
ibmcloud sl block volume-order [OPTIONS]
```
{: codeblock}

**Command options**:

-t, --storage-type
:   Required. Type of storage volume. Options are: performance,endurance.

-s, --size
:   Required. Size of storage volume in GB.

-i, --iops
:   Performance Storage IOPs. Range between [100-6000], and in multiples of 100 [required for storage-type performance].

-e, --tier
:   Endurance Storage Tier (IOP per GB) [required for storage-type endurance], options are: 0.25,2,4,10.

-o, --os-type
:   Required. Operating System. Options are: HYPER_V,LINUX,VMWARE,WINDOWS_2008,WINDOWS_GPT,WINDOWS,XEN.

-d, --datacenter
:   Required. Datacenter short name.

-n, --snapshot-size
:   Optional parameter for ordering snapshot space along with endurance block storage; specifies the size (in GB) of snapshot space to order.

-b, --billing
:   Optional parameter for Billing rate (default to monthly), options are: hourly, monthly.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
{: codeblock}

This command orders a performance volume with size 1000 GB, IOPS of 4000, OS type is LINUX, and located in datacenter `dal09`.

## ibmcloud sl block volume-options
{: #sl_block_volume_options}

List all options for ordering a block storage:

```bash
ibmcloud sl block volume-options
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block volume-options
```
{: codeblock}

This command lists all options for creating a block storage volume, including storage type, volume size, OS type, IOPS, tier level, datacenter, and snapshot size.

## ibmcloud sl block volume-refresh
{: #sl_block_volume_refresh}

Refresh a dependent duplicate volume with a snapshot from its parent:

```bash
ibmcloud sl block volume-refresh VOLUME_ID SNAPSHOT_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl block volume-refresh 123 456
```
{: codeblock}

Refresh a dependent duplicate 123 with a snapshot from its parent 456.

## ibmcloud sl block snapshot-get-notification-status
{: #sl_block_snapshot_get_notification_status}

This feature will be availble in the January 2022 release of the `ibmcloud` tool. Until then, the following command will perform the same action.


`12345` here is the ID of the block or file volume you want to see the Notification Status for.

```bash
ibmcloud sl call-api SoftLayer_Network_Storage getSnapshotNotificationStatus --init=12345
```
{: codeblock}

Values can be either `0` for disabled, or `1` and ``(null, empty string) for enabled.

## ibmcloud sl block snapshot-set-notification
{: #sl_block_snapshot_set_notification}

This feature will be availble in the January 2022 release of the `ibmcloud` tool. Until then, the following command will perform the same action.

`12345` here is the ID of the block or file volume you want to see the Notification Status for.

Enable snapshot notification:

```bash
ibmcloud sl call-api SoftLayer_Network_Storage setSnapshotNotification --init=12345 --parameters '[1]'
```
{: codeblock}

Disable snapshot notification:

```bash
ibmcloud sl call-api SoftLayer_Network_Storage setSnapshotNotification --init=12345 --parameters '[0]'
```
{: codeblock}
