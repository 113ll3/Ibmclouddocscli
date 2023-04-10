---

copyright:
  years: 2018, 2023
lastupdated: "2023-04-10"

keywords: cli, classic infrastructure, file storage service, ibmcloud sl file, snapshot, file storage, storage, nfs, nas, iops, volume, datacenter, file storage cli

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Working with the {{site.data.keyword.filestorage_short}} service (ibmcloud sl file)
{: #sl-file-storage-service}

{{site.data.keyword.filestorage_full}} is a persistent, fast, and flexible network-attached, NFS-based {{site.data.keyword.filestorage_short}}. In this network-attached storage (NAS) environment, you have total control over your file shares function and performance.

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage a volume in the {{site.data.keyword.cloud_notm}} classic infrastructure {{site.data.keyword.filestorage_short}} service.
{: shortdesc}
 
## ibmcloud sl file access-authorize
{: #sl_file_access_authorize}

Authorize hosts to access a volume:

```bash
ibmcloud sl file access-authorize VOLUME_ID [OPTIONS]
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

-s, --subnet-id
:   An ID of one subnet to authorize.

**Examples**:
```bash
ibmcloud sl file access-authorize 12345678 --virtual-id 87654321
```
{: codeblock}

This command authorizes virtual server with ID `87654321` to access volume with ID `12345678`.

## ibmcloud sl file access-list
{: #sl_file_access_list}

List hosts that are authorized to access the volume:

```bash
ibmcloud sl file access-list VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--sortby
:   Column to sort by. Options are: id, name, type, private_ip_address, source_subnet, host_iqn, username, password, allowed_host_id.

--column
:   Column to display. Options are: id,name,type,private_ip_address,source_subnet,host_iqn,username,password,allowed_host_id. This option can be specified multiple times.

**Examples**:
```bash
ibmcloud sl file access-list 12345678 --sortby id
```
{: codeblock}

This command lists all hosts that are authorized to access volume with ID `12345678` and sorts them by ID.

## ibmcloud sl file access-revoke
{: #sl_file_access_revoke}

Revoke authorization for hosts that access a specific volume:

```bash
ibmcloud sl file access-revoke VOLUME_ID [OPTIONS]
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

-s, --subnet-id
:   An ID of one subnet to revoke.

**Examples**:
```bash
ibmcloud sl file access-revoke 12345678 --virtual-id 87654321
```
{: codeblock}

This command revokes access of virtual server with ID `87654321` to volume with ID `12345678`.

## ibmcloud sl file replica-failback
{: #sl_file_replica_failback}

Fail back a file volume from replica:

```bash
ibmcloud sl file replica-failback VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file replica-failback 12345678
```
{: codeblock}

This command performs failback operation for volume with ID `12345678`.

## ibmcloud sl file replica-failover
{: #sl_file_replica_failover}

Fail over a file volume to the specified replica volume:

```bash
ibmcloud sl file replica-failover VOLUME_ID REPLICA_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file replica-failover 12345678 87654321
```
{: codeblock}

This command performs a failover operation for a volume with ID `12345678` to replica volume with ID `87654321`.

## ibmcloud sl file replica-locations
{: #sl_file_replica_locations}

List suitable replication data centers for the specified volume:
```bash
ibmcloud sl file replica-locations VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file replica-locations 12345678
```
{: codeblock}

This command lists suitable replication data centers for a file volume with ID `12345678`.

## ibmcloud sl file replica-order
{: #sl_file_replica_order}

Order a file storage replica volume:
```bash
ibmcloud sl file replica-order VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --snapshot-schedule
:   Required. Snapshot schedule to use for replication. Options are: HOURLY,DAILY,WEEKLY.

-d, --datacenter
:   Required. Short name of the datacenter for the replica. For example, `dal09`.

-t, --tier
:   Optional. Endurance Storage Tier (IOPS per GB) of the primary volume for which a replica is ordered. Options are: [0.25,2,4,10]. If no tier is specified, the tier of the original volume is used.

-i, --iops
:   Performance Storage IOPs. Range `100-6000`, and in multiples of 100. If no IOPS are specified, the IOPS value of the original volume is used.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl file replica-order 12345678 -s DAILY -d dal09 --tier 4
```
{: codeblock}

This command orders a replica for volume with ID `12345678`, which performs DAILY replication, is located at `dal09`, tier level is 4.

## ibmcloud sl file replica-partners
{: #sl_file_replica_partners}

List existing replicant volumes for a file volume:
```bash
ibmcloud sl file replica-partners VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file replica-partners 12345678
```
{: codeblock}

This command lists existing replicant volumes for file volume with ID `12345678`.

## ibmcloud sl file snapshot-cancel
{: #sl_file_snapshot_cancel}

Cancel existing snapshot space for a volume:
```bash
ibmcloud sl file snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
ibmcloud sl file snapshot-cancel 12345678 --immediate -f
```
{: codeblock}

This command cancels snapshot with ID `12345678` immediately without asking for confirmation.

## ibmcloud sl file snapshot-create
{: #sl_file_snapshot_create}

Create a snapshot on a given volume:
```bash
ibmcloud sl file snapshot-create VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-n, --note
:   Notes to set on the new snapshot.

**Examples**:
```bash
ibmcloud sl file snapshot-create 12345678 --note snapshotforibmcloud
```
{: codeblock}

This command creates a snapshot for volume with ID `12345678` and with addition note as `snapshotforibmcloud`.

## ibmcloud sl file snapshot-disable
{: #sl_file_snapshot_disable}

Disable snapshots on the specified schedule for a given volume:
```bash
ibmcloud sl file snapshot-disable VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --schedule-type
:   Required. Snapshot schedule, options are: HOURLY, DAILY, WEEKLY.

**Examples**:
```bash
ibmcloud sl file snapshot-disable 12345678 -s DAILY
```
{: codeblock}

This command disables daily snapshot for volume with ID `12345678`.

## ibmcloud sl file snapshot-enable
{: #sl_file_snapshot_enable}

Enable snapshots for a volume on the specified schedule:
```bash
ibmcloud sl file snapshot-enable VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --schedule-type
:   Required. Snapshot schedule, options are: HOURLY,DAILY,WEEKLY.

-c, --retention-count
:   Required. Number of snapshots to retain.

-m, --minute
:   Minute of the hour when snapshots should be taken, integer 0 - 59.

-r, --hour
:   Hour of the day when snapshots should be taken, integer 0 - 23.

-d, --day-of-week
:   Day of the week when snapshots should be taken, integer 0 - 6. 0 means Sunday, 1 means Monday, 2 means Tuesday, 3 means Wednesday, 4 means Thursday, 5 means Friday, 6 means Saturday.

**Examples**:
```bash
ibmcloud sl file snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
{: codeblock}

This command enables snapshot for volume with ID `12345678`. The snapshot is taken weekly on every Sunday at 2:00, and up to 5 snapshots are retained.

## ibmcloud sl file snapshot-delete
{: #sl_file_snapshot_delete}

Delete a snapshot on a volume:
```bash
ibmcloud sl file snapshot-delete SNAPSHOT_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file snapshot-delete 12345678
```
{: codeblock}

This command deletes snapshot with ID `12345678`.

## ibmcloud sl file snapshot-list
{: #sl_file_snapshot_list}

List file storage snapshots:
```bash
ibmcloud sl file snapshot-list VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--sortby
:   Column to sort by. Options are: id, name, created, size_bytes.

**Examples**:
```bash
ibmcloud sl file snapshot-list 12345678 --sortby id
```
{: codeblock}

This command lists all snapshots of volume with ID `12345678` and sorts them by ID.

## ibmcloud sl file snapshot-order
{: #sl_file_snapshot_order}

Order snapshot space for a file storage volume:
```bash
ibmcloud sl file snapshot-order VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-s, --size
:   Required. Size of snapshot space to create in GB.

-t, --tier
:   Optional. Endurance Storage Tier (IOPS per GB) of the file volume for which space is ordered. Options are: 0.25, 2, 4, 10.

-i, --iops
:   Performance Storage IOPs. Range `100-6000`, and in multiples of 100.

-u, --upgrade
:   Flag to indicate that the order is an upgrade.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl file snapshot-order 12345678 -s 1000 -t 4
```
{: codeblock}

This commands orders a snapshot space for the volume with ID `12345678`. The size is 1000 GB, and the tier level is 4 IOPS per GB.

## ibmcloud sl file snapshot-restore
{: #sl_file_snapshot_restore}

Restore a file volume by using a specified snapshot:
```bash
ibmcloud sl file snapshot-restore VOLUME_ID SNAPSHOT_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file snapshot-restore 12345678 87654321
```
{: codeblock}

This command restores volume with ID `12345678` from snapshot with ID `87654321`.

## ibmcloud sl file snapshot-schedule-list
{: #sl_file_snapshot_schedule_list}

List snapshot schedules for a volume:
```bash
ibmcloud sl file snapshot-schedule-list VOLUME_ID 
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file snapshot-schedule-list 12345678
```
{: codeblock}

This command list snapshot schedules for volume with ID `12345678`.

## ibmcloud sl file volume-cancel
{: #sl_file_volume_cancel}

Cancel an existing file storage volume:
```bash
ibmcloud sl file volume-cancel VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

--reason
:   An optional reason for cancellation.

--immediate
:   Cancel the file storage volume immediately instead of on the billing anniversary.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl file volume-cancel 12345678 --immediate -f
```
{: codeblock}

This command cancels volume with ID `12345678` immediately and without asking for confirmation.

## ibmcloud sl file volume-count
{: #sl_file_volume_count}

List number of file storage volumes per data center:
```bash
ibmcloud sl file volume-count [OPTIONS]
```
{: codeblock}

**Command options**:

-d, --datacenter
:   Filter by datacenter shortname.

## ibmcloud sl file volume-limits
{: #sl_file_volume_limits}

Display the global maximum volume count for the account and the number of {{site.data.keyword.blockstorageshort}} and {{site.data.keyword.filestorage_short}} volumes that are already provisioned.
```bash
ibmcloud sl file volume-limits
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file volume-limits
```
{: codeblock}

This command lists the storage limits for this account.

## ibmcloud sl file volume-list
{: #sl_file_volume_list}

List file storage:
```bash
ibmcloud sl file volume-list [OPTIONS]
```
{: codeblock}

**Command options**:

-u, --username
:   Filter by volume username.

-d, --datacenter
:   Filter by data center shortname.

-t, --storage-type
:   Filter by type of storage volume, options are: performance, endurance.

-o, --order
:   Filter by ID of the order that purchased the file storage.

--sortby
:   Column to sort by. Default: id. Options are: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr,active_transactions, created_by, mount_addr.

--column
:   Column to display. Options are: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions,mount_addr, created_by, notes. This option can be specified multiple times.

**Examples**:
```bash
ibmcloud sl file volume-list -d dal09 -t endurance --sortby capacity_gb
```
{: codeblock}

This command lists all endurance volumes on the current account that are located in data center `dal09`, and sorts them by capacity.

## ibmcloud sl file volume-convert
{: #sl_file_volume_convert}

Convert a dependent duplicate volume to an independent volume:
```bash
ibmcloud sl file volume-convert VOLUME_ID
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file volume-convert 12345678
```
{: codeblock}

Convert a dependent duplicate 12345678 to an independent volume.

## ibmcloud sl file volume-detail
{: #sl_file_volume_detail}

Display details for a specified volume:
```bash
ibmcloud sl file volume-detail VOLUME_ID 
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file volume-detail 12345678
```
{: codeblock}

This command shows details of volume with ID `12345678`.

## ibmcloud sl file volume-duplicate
{: #sl_file_volume_duplicate}

Order a file volume by duplicating an existing volume:
```bash
ibmcloud sl file volume-duplicate VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-o, --origin-snapshot-id
:   ID of an original volume snapshot to use for duplication.

-s, --duplicate-size
:   Size of duplicate file volume in GB. If no size is specified, the size of the original volume is used.

-i, --duplicate-iops
:   Performance Storage IOPS. Range `100-6000`, and in multiples of 100. If no IOPS is specified, the IOPS of the original volume is used.

-t, --duplicate-tier
:   Endurance Storage Tier. If no tier is specified, the tier of the original volume is used.

-n, --duplicate-snapshot-size
:   The size of snapshot space to order for the duplicate. If no snapshot space size is specified, the snapshot space size of the original volume is used.

-d, --dependent-duplicate
:   Whether this duplicate is a dependent duplicate of the origin volume.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl file volume-duplicate 12345678
```
{: codeblock}

This command shows order a new volume by duplicating the volume with ID `12345678`.

## ibmcloud sl file volume-order
{: #sl_file_volume_order}

Order a file storage volume:
```bash
ibmcloud sl file volume-order [OPTIONS]
```
{: codeblock}

**Command options**:

-t, --storage-type
:   Required. Type of storage volume, options are: performance, endurance.

-s, --size
:   Required. Size of storage volume in GB.

-i, --iops
:   Performance Storage IOPs. Range `100-6000`, and in multiples of 100 [required for storage-type performance].

-e, --tier
:   Endurance Storage Tier (IOP per GB) [required for storage-type endurance]. Options are: 0.25,2,4,10.

-d, --datacenter
:   Required. Data center short name.

-n, --snapshot-size
:   Optional parameter for ordering snapshot space along with the volume.

-b, --billing
:   Optional parameter for Billing rate (default to monthly), options are: hourly, monthly.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl file volume-order --storage-type performance --size 1000 --iops 4000  -d dal09
```
{: codeblock}

This command orders a performance volume with size is 1000 GB, IOPS is 4000, and in data center `dal09`.

## ibmcloud sl file volume-modify
{: #sl_file_volume_modify}

Modify an existing file storage volume:
```bash
ibmcloud sl file volume-modify VOLUME_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-c, --new-size
:   New Size of file volume in GB. If no size is given, the original size of volume is used. Potential Sizes: [20, 40, 80, 100, 250, 500, 1000, 2000, 4000, 8000, 12000] Minimum: [the original size of the volume]

-i, --new-iops
:   Performance Storage IOPS. Range [100-6000], and in multiples of 100 [only for performance volumes]. If no IOPS value is specified, the original IOPS value of the volume is used. Requirements: [If original IOPS/GB for the volume is less than 0.3, new IOPS/GB must also be less than 0.3. If original IOPS/GB for the volume is greater than or equal to 0.3, new IOPS/GB for the volume must also be greater than or equal to 0.3.]

-t, --new-tier
:   Endurance Storage Tier (IOPS per GB) [only for endurance volumes]. If no tier is specified, the original tier of the volume is used.
Requirements: [If original IOPS/GB for the volume is 0.25, new IOPS/GB for the volume must also be 0.25. If original IOPS/GB for the volume is greater than 0.25, new IOPS/GB for the volume must also be greater than 0.25.]

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl file volume-modify 12345678 --new-size 1000 --new-iops 4000
```
{: codeblock}

This command modifies volume `12345678` with size of 1000 GB, and IOPS of 4000.
```bash
ibmcloud sl file volume-modify 12345678 --new-size 500 --new-tier 4
```
{: codeblock}

This command modifies volume `12345678` with size 500 GB, and tier level 4 IOPS per GB.

## ibmcloud sl file volume-options
{: #sl_file_volume_options}

List all options for ordering a file storage:
```bash
ibmcloud sl file volume-options
```
{: codeblock}

**Examples**:
```bash
ibmcloud sl file volume-options
```
{: codeblock}

This command lists all options for creating a file storage volume, including storage type, volume size, IOPS, tier level, data center, and snapshot size.

## ibmcloud sl file volume-refresh
{: #sl_file_volume_refresh}

Refresh a dependent duplicate volume with a snapshot from its parent:
```bash
ibmcloud sl file volume-refresh VOLUME_ID SNAPSHOT_ID [OPTIONS]
```
{: codeblock}

**Command options**:

-f, --force-refresh
:   Force the volume refresh. Ongoing transactions are canceled.
--output
:   Specify output format. Only JSON is supported now.

**Examples**:
```bash
ibmcloud sl file volume-refresh 123 456
```
{: codeblock}

Refresh a dependent duplicate 123 with a snapshot from its parent 456.

## ibmcloud sl file volume-set-note
{: #sl_file_volume_setnote}

Set a note for an existing file storage volume:

```bash
ibmcloud sl file volume-set-note [OPTIONS] VOLUME_ID
```
{: codeblock}

**Command options**:

-n value, --note value
:   Public notes related to a storage volume [required]

--output value,
:   Specify output format. Only JSON is supported now.

**Examples**:

```bash
ibmcloud sl file volume-set-note 12345678 --note 'this is my note'
```
{: codeblock}

## ibmcloud sl file snapshot-get-notification-status
{: #sl_file_snapshot_get_notification_status}

Get snapshots space usage threshold warning flag setting for a given volume.

```bash
sl file snapshot-get-notification-status IDENTIFIER [flags]
```
{: codeblock}

**Command options**:

--output string
:  Specify output format. Only JSON is supported now.

**Example**:

`12345` here is the ID of the block or file volume that you want to see the notification Status for.

```bash
sl file snapshot-get-notification-status 12345
```
{: codeblock}

Values can be either `0` for disabled, or `1` and ``(null, empty string) for enabled.

## ibmcloud sl file snapshot-set-notification
{: #sl_file_snapshot_set_notification}

Enables or disables snapshot space usage threshold warning for a given volume.

```bash
sl file snapshot-set-notification IDENTIFIER [flags]
```
{: codeblock}

**Command options**:

--disable
:   Disable snapshot notification.

--enable
:   Enable snapshot notification.

--output string
:   Specify output format. Only JSON is supported now.

**Examples**:

`12345` here is the ID of the block or file volume that you want to see the Notification Status for.

Enable snapshot notification:

```bash
ibmcloud sl file snapshot-set-notification 12345 -enable'
```
{: codeblock}

Disable snapshot notification:

```bash
ibmcloud sl file snapshot-set-notification 12345 --disable
```
{: codeblock}
