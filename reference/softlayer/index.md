---

copyright:

  years: 2016,2017

lastupdated: "2017-05-24"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl) commands
{: #softlayer_cli}

The {{site.data.keyword.BluSoftlayer:}} plugin has been merged into the {{site.data.keyword.Bluemix_notm:}} CLI. You no longer need to install the plug-in.

Use {{site.data.keyword.BluSoftlayer_notm}} commands in the {{site.data.keyword.Bluemix_notm:}} command line interface (CLI) to configure and manage SoftLayer services.


To get started, install the IBM {{site.data.keyword.Bluemix_notm:}} CLI. See
[Bluemix CLI ![External link icon](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window} for details.

For a complete list of {{site.data.keyword.Bluemix_notm:}} commands, see: [{{site.data.keyword.Bluemix_notm:}} (bx) commands](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli)


## List of {{site.data.keyword.BluSoftlayer_notm}} commands
The following commands are supported. Use the `bluemix sl` command to see the list of available commands:

<table summary="Alphabetically ordered general commands that have links that bring you to more info for the command">
<caption>Table 1. General Softlayer commands</caption>
 <thead>
 <th colspan="6">General Softlayer commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl config](/docs/cli/reference/softlayer/index.html#sl_config)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>

 <table summary="Alphabetically ordered general Softlayer commands that have links that bring you to more info for the command">
<caption>Table 2. Softlayer Block storage</caption>
 <thead>
 <th colspan="6">Softlayer Block storage</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl block access-authorize](/docs/cli/reference/softlayer/index.html#sl_block_access_authorize)</td>
  <td>[bluemix sl block access-list](/docs/cli/reference/softlayer/index.html#sl_block_access_list)</td>
  <td>[bluemix sl block access-revoke](/docs/cli/reference/softlayer/index.html#sl_block_access_revoke)</td>
  <td>[bluemix sl block replica-failback](/docs/cli/reference/softlayer/index.html#sl_block_replica_failback)</td>
  <td>[bluemix sl block replica-failover](/docs/cli/reference/softlayer/index.html#sl_block_replica_failover)</td>
  <td>[bluemix sl block replica-order](/docs/cli/reference/softlayer/index.html#sl_block_replica_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_cancel)</td>
 <td>[bluemix sl block snapshot-create](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_create)</td>
 <td>[bluemix sl block snapshot-disable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_disable)</td>
 <td>[bluemix sl block snapshot-enable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_enable)</td>
 <td>[bluemix sl block snapshot-delete](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_delete)</td>
 <td>[bluemix sl block snapshot-list](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_list)</td>
  </tr>
 <tr>
 <td>[bluemix sl block snapshot-order](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_order)</td>
  <td>[bluemix sl block snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_restore)</td>
  <td>[bluemix sl block volume-cancel](/docs/cli/reference/softlayer/index.html#sl_block_volume_cancel)</td>  
  <td>[bluemix sl block volume-detail](/docs/cli/reference/softlayer/index.html#sl_block_volume_detail)</td>
  <td>[bluemix sl block volume-list](/docs/cli/reference/softlayer/index.html#sl_block_volume_list)</td>
  <td>[bluemix sl block volume-order](/docs/cli/reference/softlayer/index.html#sl_block_volume_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block volume-options](/docs/cli/reference/softlayer/index.html#sl_block_volume_options)</td>
 </tr>
   </tbody>
 </table>

<table summary="Alphabetically ordered general Softlayer commands that have links that bring you to more info for the command">
<caption>Table 3. Softlayer dns commands</caption>
 <thead>
 <th colspan="6">Softlayer dns commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl dns import](/docs/cli/reference/softlayer/index.html#sl_dns_import)</td>
 <td>[bluemix sl dns record-add](/docs/cli/reference/softlayer/index.html#sl_dns_record_add)</td>
 <td>[bluemix sl dns record-edit](/docs/cli/reference/softlayer/index.html#sl_dns_record_edit)</td>
 <td>[bluemix sl dns record-list](/docs/cli/reference/softlayer/index.html#sl_dns_record_list)</td>
 <td>[bluemix sl dns record-remove](/docs/cli/reference/softlayer/index.html#sl_dns_record_remove)</td>
  <td>[bluemix sl dns zone-create](/docs/cli/reference/softlayer/index.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[bluemix sl dns zone-delete](/docs/cli/reference/softlayer/index.html#sl_dns_zone_delete)</td>
   <td>[bluemix sl dns zone-list](/docs/cli/reference/softlayer/index.html#sl_dns_zone_list)</td>
   <td>[bluemix sl dns zone-print](/docs/cli/reference/softlayer/index.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

<table summary="Alphabetically ordered general Softlayer commands that have links that bring you to more info for the command">
<caption>Table 4. Softlayer Global IP addresses</caption>
 <thead>
 <th colspan="6">Softlayer Global IP addresses</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl globalip assign](/docs/cli/reference/softlayer/index.html#sl_globalip_assign)</td>
  <td>[bluemix sl globalip cancel](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
  <td>[bluemix sl globalip create](/docs/cli/reference/softlayer/index.html#sl_globalip_create)</td>
 <td>[bluemix sl globalip list](/docs/cli/reference/softlayer/index.html#sl_globalip_list)</td>
 <td>[bluemix sl globalip unassign](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
 </tr>
   </tbody>
 </table>



 <table summary="Alphabetically ordered general Openwhisk commands that have links that bring you to more info for the command">
<caption>Table 5. Softlayer image commands</caption>
 <thead>
 <th colspan="6">Softlayer image commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl image delete](/docs/cli/reference/softlayer/index.html#sl_image_delete)</td>
 <td>[bluemix sl image detail](/docs/cli/reference/softlayer/index.html#sl_image_detail)</td>
 <td>[bluemix sl image edit](/docs/cli/reference/softlayer/index.html#sl_image_edit)</td>
 <td>[bluemix sl image export](/docs/cli/reference/softlayer/index.html#sl_image_export)</td>
<td>[bluemix sl image import](/docs/cli/reference/softlayer/index.html#sl_image_import)</td>
 <td>[bluemix sl image list](/docs/cli/reference/softlayer/index.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>

  <table summary="Alphabetically ordered general Openwhisk commands that have links that bring you to more info for the command">
<caption>Table 6. Softlayer Legacy ISCSI strorage commands</caption>
 <thead>
 <th colspan="6">Softlayer Legacy ISCSI strorage commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl iscsi cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_cancel)</td>
 <td>[bluemix sl iscsi create](/docs/cli/reference/softlayer/index.html#sl_iscsi_create)</td>
 <td>[bluemix sl iscsi detail](/docs/cli/reference/softlayer/index.html#sl_iscsi_detail)</td>
 <td>[bluemix sl iscsi list](/docs/cli/reference/softlayer/index.html#sl_iscsi_list)</td>
 <td>[bluemix sl iscsi snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_cancel)</td>
 <td>[bluemix sl iscsi snapshot-create](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create)</td>
 </tr>
 <tr>
 <td>[bluemix sl iscsi snapshot-create-space](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create-space)</td>
 <td>[bluemix sl iscsi snapshot-list](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_list)</td>
 <td>[bluemix sl iscsi snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_restore)</td>
 </tr>
   </tbody>
 </table>


 <table summary="Alphabetically ordered general Softlayer commands that have links that bring you to more info for the command">
<caption>Table 7. Softlayer security commands</caption>
 <thead>
 <th colspan="5">Softlayer security commands</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl security sshkey-add](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_add)</td>
  <td>[bluemix sl security sshkey-edit](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_edit)</td>
  <td>[bluemix sl security sshkey-list](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_list)</td>
  <td>[bluemix sl security sshkey-print](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_print)</td>   <td>[bluemix sl security sshkey-remove](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[bluemix sl security cert-add](/docs/cli/reference/softlayer/index.html#sl_security_cert_add)</td>
  <td>[bluemix sl security cert-edit](/docs/cli/reference/softlayer/index.html#sl_security_cert_edit)</td>
  <td>[bluemix sl security cert-download](/docs/cli/reference/softlayer/index.html#sl_security_cert_download)</td>
  <td>[bluemix sl security cert-list](/docs/cli/reference/softlayer/index.html#sl_security_cert_list)</td>
  <td>[bluemix sl security cert-remove](/docs/cli/reference/softlayer/index.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>


 <table summary="Alphabetically ordered general Openwhisk commands that have links that bring you to more info for the command">
<caption>Table 8. Softlayer subnet commands</caption>
 <thead>
 <th colspan="5">Softlayer subnet commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl subnet cancel](/docs/cli/reference/softlayer/index.html#sl_subnet_cancel)</td>
 <td>[bluemix sl subnet create](/docs/cli/reference/softlayer/index.html#sl_subnet_create)</td>
 <td>[bluemix sl subnet detail](/docs/cli/reference/softlayer/index.html#sl_subnet_detail)</td>
 <td>[bluemix sl subnet list](/docs/cli/reference/softlayer/index.html#sl_subnet_list)</td>
 <td>[bluemix sl subnet lookup](/docs/cli/reference/softlayer/index.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 <table summary="Alphabetically ordered general Openwhisk commands that have links that bring you to more info for the command">
<caption>Table 9. Softlayer virtual server commands</caption>
 <thead>
 <th colspan="6">Softlayer virtual server commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vs cancel](/docs/cli/reference/softlayer/index.html#sl_vs_cancel)</td>
 <td>[bluemix sl vs capture](/docs/cli/reference/softlayer/index.html#sl_vs_capture)</td>
 <td>[bluemix sl vs create](/docs/cli/reference/softlayer/index.html#sl_vs_create)</td>
 <td>[bluemix sl vs options](/docs/cli/reference/softlayer/index.html#sl_vs_options)</td>
 <td>[bluemix sl vs-credentials](/docs/cli/reference/softlayer/index.html#sl_vs_credentials)</td>
 <td>[bluemix sl vs detail](/docs/cli/reference/softlayer/index.html#sl_vs_detail)</td>
 </tr><tr>
 <td>[bluemix sl vs dns-sync](/docs/cli/reference/softlayer/index.html#sl_vs_dns_sync)</td>
 <td>[bluemix sl vs edit](/docs/cli/reference/softlayer/index.html#sl_vs_edit)</td>
 <td>[bluemix sl vs list](/docs/cli/reference/softlayer/index.html#sl_vs_list)</td>
 <td>[bluemix sl vs pause](/docs/cli/reference/softlayer/index.html#sl_vs_pause)</td>
 <td>[bluemix sl vs power-off](/docs/cli/reference/softlayer/index.html#sl_vs_power_off)</td>
 <td>[bluemix sl vs power-on](/docs/cli/reference/softlayer/index.html#sl_vs_power_on)
 </tr><tr>
 <td>[bluemix sl vs ready](/docs/cli/reference/softlayer/index.html#sl_vs_ready)</td>
 <td>[bluemix sl vs reboot](/docs/cli/reference/softlayer/index.html#sl_vs_reboot)</td>
 <td>[bluemix sl vs reload](/docs/cli/reference/softlayer/index.html#sl_vs_reload)</td>
 <td>[bluemix sl vs rescure](/docs/cli/reference/softlayer/index.html#sl_vs_rescure)</td>
 <td>[bluemix sl vs resume](/docs/cli/reference/softlayer/index.html#sl_vs_resume)</td>
 <td>[bluemix sl vs upgrade](/docs/cli/reference/softlayer/index.html#sl_vs_upgrade)</td>
 </tr>
   </tbody>
 </table>

  <table summary="Alphabetically ordered general Openwhisk commands that have links that bring you to more info for the command">
<caption>Table 10. Softlayer VLAN commands</caption>
 <thead>
 <th colspan="6">Softlayer VLAN commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vlan create](/docs/cli/reference/softlayer/index.html#sl_vlan_create)</td>
 <td>[bluemix sl vlan cancel](/docs/cli/reference/softlayer/index.html#sl_vlan_cancel)</td>
 <td>[bluemix sl vlan detail](/docs/cli/reference/softlayer/index.html#sl_vlan_detail)</td>
 <td>[bluemix sl vlan edit](/docs/cli/reference/softlayer/index.html#sl_vlan_edite)</td>
 <td>[bluemix sl vlan list](/docs/cli/reference/softlayer/index.html#sl_vlan_list)</td>
 <td>[bluemix sl vlan options](/docs/cli/reference/softlayer/index.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

### Command usage
To view help information for the commands, run: `bluemix sl [command] -h`.

### bluemix sl config
{: #sl_config}

Edit or show the configuration that is used to connect to the SoftLayer environment. The configuration includes user name, API key or password, and endpoint.
```
bluemix sl config [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--list</dt>
   <dd>Show the configuration.</dd>
    </dl>

For example,
```
 runhc$ bluemix sl config

Username []> johndoe@us.ibm.com

API Key or password []> myPwd4sl   

Endpoint (public|private|custom) [public]> public
```

### bluemix sl help
{: #sl_help}

View help information for all commands to operate Softlayer environment.
```
bluemix wsk help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

Authorize hosts to access a given volume.
```
bluemix sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>The ID of one hardware server to authorize.</dd>
   <dt>--virtual-id</dt>
   <dd>The ID of one virtual server to authorize.</dd>
   <dt>--ip-address-id</dt>
   <dd>The ID of one IP address to authorize.</dd>
   <dt>--ip-address</dt>
   <dd>An IP address to authorize.</dd>
    </dl>

**Examples**:
Authorize virtual server with ID `87654321` to access volume with ID `12345678`.
```
   bluemix sl block access-authorize 12345678 --virtual-id 87654321

```


### bluemix sl block access-list
{: #sl_block_access_list}

List ACLs.
```
bluemix sl block access-list VOLUME_ID [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Column to sort by, options are: `id`, `name`,  `type`, `private_ip_address`, `host_iqn,username`, or `password`.</dd>
   <dt>--columns</dt>
   <dd>  Columns to display, options are:  `id`, `name`, `type`, `private_ip_address`, `host_iqn,username`, or `password`.</dd>
</dl>

**Examples**:

List all hosts that are authorized to access volume with ID `12345678` and sorts them by ID.
```
bluemix sl block access-list 12345678 --sortby id
```

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

Revoke authorization for hosts accessing a given volume.
```
 bluemix sl block access-revoke VOLUME_ID [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>The ID of one hardware server to authorize.</dd>
   <dt>--virtual-id</dt>
   <dd>The ID of one virtual server to authorize.</dd>
   <dt>--ip-address-id</dt>
   <dd>The ID of one IP address to authorize.</dd>
   <dt>--ip-address</dt>
   <dd>An IP address to authorize.</dd>
    </dl>

**Examples**:
Revoke access of virtual server with ID `87654321` to volume with ID `12345678`.
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```


### bluemix sl block replica-failback
{: #sl_block_replica_failback}

Failback a block volume from replica.
```
 bluemix sl block replica-failback VOLUME_ID
```
**Examples**:
Perform failback operation for volume with ID `12345678`.
```
 bluemix sl block replica-failback 12345678
```


### bluemix sl block replica-failover
{: #sl_block_replica_failover}

Failover a block volume to the given replica volume.
```
bluemix sl block replica-failover VOLUME_ID REPLICA_ID
```
**Examples**:
Perform failover operation for volume with ID `12345678` to replica volume with ID `87654321`.
```
 bluemix sl block replica-failover 12345678 87654321
```

### bluemix sl block replica-order
{: #sl_block_replica_order}

Order a block storage replica volume.
```
 bluemix sl block replica-order VOLUME_ID [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>Required. Snapshot schedule to use for replication. The options are: `HOURLY`,`DAILY`, or `WEEKLY`.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Required. Short name of the datacenter for the replica. For example, `dal09`.</dd>
   <dt>--tier</dt>
   <dd>Optional. Endurance Storage Tier (IOPS per GB) of the primary volume for which a replica is ordered. The options are: `0.25`, `2`, `4`, or `10`.</dd>
   <dt>--os-type</dt>
   <dd>Optional. Operating System Type of the primary volume for which a replica is ordered. The options are: `HYPER_V`, `LINUX`, `VMWARE`, `WINDOWS_2008`, `WINDOWS_GPT`, `WINDOWS`, or `XEN`.</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
    </dl>

**Examples**:
Order a replica for volume with ID `12345678`, which performs DAILY replication, is located at dal09 with tier level `4` and OS type `Linux`.
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

Cancel existing snapshot space for a given volume.
```
 bluemix sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
Cancel the snapshot with ID 12345678 immediately without asking for confirmation.
```
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```


### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

Create a snapshot on a given volume.
```
 bluemix sl block snapshot-create VOLUME_ID [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt> -n, --note</dt>
   <dd>Notes to set on the new snapshot</dd>
	</dl>

**Examples**:
Create a snapshot for volume with ID `12345678` and with addition note as `snapshotforbluemix`.
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

Disable snapshots on the specified schedule for a given volume.
```
 bluemix sl block snapshot-disable VOLUME_ID [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Required. The snapshot schedule: `HOURLY`, `DAILY`, or `WEEKLY`.</dd>
	</dl>

**Examples**:
Disable daily snapshot for volume with ID `12345678`.
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

Enable snapshots for a given volume on the specified schedule.
```
 bluemix sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>Required. The snapshot schedule: `HOURLY`, `DAILY`, or `WEEKLY`.</dd>
   <dt>-c, --retention-count</dt>
   <dd>Required. Number of snapshots to retain.</dd>
   <dt>-m, --minute</dt>
   <dd>Minute of the hour when snapshots should be taken, integer between 0 to 59.</dd>
   <dt>--hour</dt>
   <dd>Hour of the day when snapshots should be taken, integer between 0 to 23.</dd>
   <dt>-d, --day-of-week</dt>
   <dd>Day of the week when snapshots should be taken, integer between 0 to 6.
0 means Sunday,1 means Monday,2 means Tuesday,3 means Wendesday,4 means Thursday,5 means Friday,6 means Saturday.</dd>
	</dl>

**Examples**:
Enable snapshot for volume with ID `12345678`. The snapshot is taken at 2:00 every Sunday, and up to 5 snapshots are retained.
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

Delete a snapshot on a given volume.
```
  bluemix sl block snapshot-delete SNAPSHOT_ID
```

**Examples**:
Delete snapshots with ID `12345678`.
```
 bluemix sl block snapshot-delete 12345678
```


### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

List block storage snapshots
```
 bluemix sl block snapshot-list VOLUME_ID [OPTIONS]

```

<strong>Command options</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Column to sort by. The options are: `id`, `name`, `created`, and `size_bytes`.</dd>
	</dl>

**Examples**:
list all snapshots of volume with ID `12345678` and sorts them by ID.
```
 bluemix sl block snapshot-list 12345678 --sortby id
```

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

Order snapshot space for a block storage volume.
```
 bluemix sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-s, --size</dt>
   <dd>Required. The size of snapshot space to create in GB.</dd>
   <dt>-t, --tier</dt>
   <dd>Optional. Endurance Storage Tier (IOPS per GB) of the block volume for which space is ordered. The options are: 0.25,2,4,10</dd>
   <dt>-u, --upgrade</dt>
   <dd>Flag to indicate that the order is an upgrade.</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
	</dl>

**Examples**:
Order snapshot space for volume with ID `12345678`, the size is 1000GB, the tier level is 4 IOPS per GB.
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```


### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

Restore block volume using a given snapshot
```
 bluemix sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**Examples**:
Restore volume with ID `12345678` from snapshot with ID `87654321`.

```
 bluemix sl block snapshot-restore 12345678 87654321
```

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

Cancel an existing block storage volume
```
 bluemix sl block volume-cancel VOLUME_ID [OPTIONS]
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
Cancel volume with ID `12345678` immediately and without asking for confirmation.
```
 bluemix sl block volume-cancel 12345678 --immediate -f
```


### bluemix sl block volume-detail
{: #sl_block_volume_detail}

Display details for a specified volume
```
 bluemix sl block volume-detail VOLUME_ID
```

**Examples**:
Show details of volume with ID `12345678`.
```
 bluemix sl block volume-detail 12345678
```

### bluemix sl block volume-list
{: #sl_block_volume_list}

List block storage.
```
 bluemix sl block volume-list [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-u, --username</dt>
   <dd>Filter by volume username.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filter by datacenter shortname.</dd>
   <dt>-t, --storage-type</dt>
   <dd>Filter by type of storage volume. The options are: `performance`, and `endurance`.</dd>
   <dt>--order</dt>
   <dd>Filter by ID of the order that purchased the block storage.</dd>
   <dt>--sortby</dt>
   <dd>Column to sort by, options are: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, active_transactions, created_by.</dd>
   <dt>--columns</dt>
   <dd>Columns to display, options are: id, username, datacenter, storage_type, capacity_gb, bytes_used, ip_addr, created_by.</dd>
   </dl>

**Examples**:
List all endurance volumes on current account that are located at dal09, and sorts them by capacity.
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```


### bluemix sl block volume-order
{: #sl_block_volume_order}

Order a block storage volume
```
   bluemix sl block volume-order [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--storage-type</dt>
   <dd>Type of storage volume [required], options are: performance,endurance.</dd>
   <dt>--size</dt>
   <dd>Size of storage volume in GB [required]</dd>
   <dt>--iops</dt>
   <dd>Performance Storage IOPs, between 100 and 6000 in multiples of 100 [required for storage-type performance]</dd>
   <dt>--tier</dt>
   <dd>Endurance Storage Tier (IOP per GB) [required for storage-type endurance], options are: 0.25,2,4,10</dd>
   <dt>--os-type</dt>
   <dd>Operating System [required], options are: HYPER_V, LINUX, VMWARE, WINDOWS_2008, WINDOWS_GPT, WINDOWS, XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Datacenter short name [required]</dd>
   <dt>--snapshot-size</dt>
   <dd>Optional parameter for ordering snapshot space along with endurance block storage; specifies the size (in GB) of snapshot space to order</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
   </dl>


**Examples**:
Order a performance volume with size is 1000GB, IOPS is 4000, OS type is LINUX, located at dal09.
```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
Order a endurance volume with size is 500GB, tier level is 4 IOPS per GB, OS type is XEN, located at dal09, and additional snapshot space size is 500GB.
```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```

### bluemix sl block volume-options
{: #sl_block_volume_options}

List all options for ordering a block storage
```
 bluemix sl block volume-options
```

**Examples**:
List all options for creating a block storage volume, including storage type, volume size, OS type, IOPS, tier level, datacenter, and snapshot size.
```
 bluemix sl block volume-options
```

### bluemix sl dns import
{: #sl_dns_import}

Imports zone based off a BIND zone file.
```
bluemix sl dns-import [OPTIONS] ZONEFILE
```
<strong>Command options</strong>:
   <dl>
   <dt>--dry-run</dt>
   <dd>Do not actually create records.</dd>
    </dl>

**Examples**:
Import zone and its resource records from file: `~/blumix.net.txt`.
```
 bluemix sl dns import ~/blumix.net.txt
```

### bluemix sl dns record-add
{: #sl_dns_record_add}
Add resource record.

```
bluemix sl dns-record-add [OPTIONS] ZONE RECORD TYPE DATA
```
<strong>Command options</strong>:
   <dl>
   <dt>--ttl</dt>
   <dd>TTL value in seconds, such as 86400  [default: 7200].</dd>
    </dl>

**Examples**:
Add an A record to zone: bluemix.net, its host is `ftp`, data is `127.0.0.1` and ttl is 86400 seconds.
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

Update resource records in a zone
```
   bluemix sl dns record-edit ZONE [OPTIONS]
```


<strong>Command options</strong>:
   <dl>
   <dt>--by-record</dt>
   <dd>Edit by host record, such as www.</dd>
   <dt>--by-id</dt>
   <dd>Edit a single record by its ID.</dd>
   <dt>--data</dt>
   <dd>Record data, such as an IP address.</dd>
   <dt>--ttl</dt>
   <dd>TTL value in seconds, such as: 86400.</dd>
   </dl>

**Examples**:
Edit records under the zone `bluemix.net` with `12345678`, and set its data to `127.0.0.2` and ttl to 3600.

```
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
Edit records under the zone `bluemix.net` with host name `kibana`, and set their ttl all to 3600.
```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```


### bluemix sl dns record-list
{: #sl_dns_record_list}

List all the resource records in a zone

```
   bluemix sl dns record-list ZONE [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--data</dt>
   <dd>Filter by record data, such as an IP address.</dd>
   <dt>--record</dt>
   <dd>Filter by host record, such as www.</dd>
   <dt>--ttl</dt>
   <dd>Filter by TTL value in seconds, such as 86400.</dd>
   <dt>--type</dt>
   <dd>Filter by record type, such as A or CNAME</dd>
   </dl>

**Examples**:
list all A records under the zone `bluemix.net`,filtered by host is `elasticsearch` and ttl is 900 seconds.
```
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```




### bluemix sl dns record-remove
{: #sl_dns_record_remove}

Remove resource record from a zone
```
 bluemix sl dns record-remove RECORD_ID
```

**Examples**:
```   
 bluemix sl dns record-remove 12345678
```
This command removes resource record with ID `12345678`.

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

Create a zone.
```
 bluemix sl dns zone-create ZONE
```
**Examples**:
```
 bluemix sl dns zone-create bluemix.net
```
This command creates a zone named `bluemix.net`.

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

Delete a zone.
```
 bluemix sl dns zone-delete ZONE
```
**Examples**:
```
 bluemix sl dns zone-delete bluemix.net
```
This command deletes a zone named `bluemix.net`.

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

List all zones on your account
```
   bluemix sl dns zone-list
```
**Examples**:
```
   bluemix sl dns zone-list
```
This command lists all zones under current account.

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

Print zone and resource records in BIND format
```
 bluemix sl dns zone-print ZONE
```

**Examples**:
```
 bluemix sl dns zone-print bluemix.net
```
This command prints zone named bluemix.net in BIND format.


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

Assign a global IP to a target router or device.
```
 bluemix sl globalip assign [OPTIONS] IDENTIFIER TARGET
```
**Examples**:
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
This command assigns IP address with ID 12345678 to a target device whose IP address is 9.111.123.456.


### bluemix sl globalip-create
{: #sl_globalip_create}

Creates a global IP.
```
bluemix sl globalip-create [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--v6</dt>
   <dd>Order a IPv6 IP.</dd>
   <dt>--test</dt>
   <dd>Test order.</dd>
    <dt>-f, --force</dt>
   <dd>Create a global IP without confirmation.</dd>
    </dl>

**Examples**:
```
     bluemix sl globalip create --v6
```
 This command creates an IP V6 address.

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

Cancels a global IP.
```
bluemix sl globalip-cancel [OPTIONS] IDENTIFIER
```
<strong>Command options</strong>:
   <dl>
    <dt>-f, --force</dt>
   <dd>Create a global IP without confirmation.</dd>
    </dl>

**Examples**:
```
 bluemix sl globalip cancel 12345678
```
This command cancels IP address with ID `12345678`.

### bluemix sl globalip-list
{: #sl_globalip_list}

Lists all global IPs.
```
bluemix sl globalip-list [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--v4</dt>
   <dd>Display IPv4 IPs only.</dd>
   <dt>--v6</dt>
   <dd>Display IPv6 IPs only.</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

Unassign a global IP from a target router or device
```
 bluemix sl globalip unassign IDENTIFIER
```
**Examples**:
```
 bluemix sl globalip unassign 12345678
```
This command unassigns IP address with ID `12345678` from target device.


### bluemix sl image delete
{: #sl_dns_image_delete}

Delete an image.
```
   bluemix sl image delete IDENTIFIER
```
**Examples**:
```
   bluemix sl image delete 12345678
```
This command deletes image with ID `12345678`.


### bluemix sl image detail
{: #sl_dns_image_detail}

Get details for an image.
```
 bluemix sl image detail IDENTIFIER
```
**Examples**:
```
 bluemix sl image detail 12345678
```
This command gets details for image with ID 12345678.

### bluemix sl image edit
{: #sl_dns_image_edit}

Edit details of an image
```
   bluemix sl image edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Name of the image.</dd>
   <dt>--note</dt>
   <dd>Additional note for the image.</dd>
   <dt>--tag</dt>
   <dd>Tags for the image</dd>
   </dl>


**Examples**:
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
   This command edits image with ID `12345678` and set its name to `ubuntu16`, note to `testing`, and tag to `staging`.


### bluemix sl image export
{: #sl_dns_image_export}

Export an image to an object storage
```
   bluemix sl image export [OPTIONS] IDENTIFIER URI
```

The URI for an object storage object (.vhd/.iso file) in the format:
`swift://<objectStorageAccount>@<cluster>/<container>/<objectPath>`.


### bluemix sl image import
{: #sl_dns_image_import}

Import an image from an object storage
```
   bluemix sl image import [OPTIONS] NAME URI  
```

The URI for an object storage object (.vhd/.iso file) in the format:
`swift://<objectStorageAccount>@<cluster>/<container>/<objectPath>`.

<strong>Command options</strong>:
   <dl>
   <dt> --note</dt>
   <dd>The note to be applied to the imported template.</dd>
   <dt>--os-code</dt>
   <dd>The referenceCode of the operating system software description for the imported VHD.</dd>
    </dl>



### bluemix sl image edit
{: #sl_dns_image_edit}

Edit details of an image
```
   bluemix sl image edit [OPTIONS] IDENTIFIER
```

<strong>Command options</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Name of the image.</dd>
   <dt>--note</dt>
   <dd>Additional note for the image.</dd>
   <dt>--tag</dt>
   <dd>Tags for the image</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

List all images on your account
```
   bluemix sl image list [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--name</dt>
   <dd>Filter on image name.</dt>
   <dd>--public</dt>
   <dd>Display only public images.</dd>
   <dt>--private</dt>
   <dd>Display only private images.</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

Cancel an existing iSCSI volume
```
   bluemix sl iscsi cancel IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>An optional reason for cancellation.</dd>
   <dt>--immediate</dt>
   <dd>Cancels the iSCSI immediately instead of on the billing anniversary.</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

Create an iSCSI volume
```
   bluemix sl iscsi create [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--size</dt>
   <dd>Size of the iSCSI volume to create (in gibibytes) [required]</dd>
   <dt>--datacenter</dt>
   <dd>Datacenter shortname [required]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

Get details for an iSCSI volume
```
   bluemix sl iscsi detail IDENTIFIER [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--password</dt>
   <dd>Show credentials to access the iSCSI target.</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

List iSCSI volumes
```
 bluemix sl iscsi list [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--order</dt>
   <dd>The ID of the order that bought this iscsi storage</dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

Cancel/Delete iSCSI snapshot
```
 bluemix sl iscsi snapshot-cancel IDENTIFIER [OPTIONS]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

Create a snapshot of an iSCSI volume
```
   bluemix sl iscsi snapshot-create IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--notes</dt>
   <dd>An optional note for the snapshot.</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

Order snapshot space for given iSCSI volume
```
 bluemix sl iscsi snapshot-create-space IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--capacity</dt>
   <dd>Size of snapshot space to create.</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

List snapshots of an iSCSI volume
```
 bluemix sl iscsi snapshot-list IDENTIFIER [OPTIONS]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

Add a new SSH key
```
 bluemix sl security sshkey-add LABEL [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-f value, --in-file value</dt>
   <dd>The id_rsa.pub file to import for this key</dd>
   <dt>-k value, --key value</dt>
   <dd>The actual SSH key</dd>
   <dt>--note value</dt>
   <dd>Extra note that will be associated with key</dd>
   </dl>


**Examples**:
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
This command adds a SSH key from file: ~/.ssh/id_rsa.pub with a note "mykey".


### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

Add a new SSH key
```
 bluemix sl security sshkey-add LABEL [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-f value, --in-file value</dt>
   <dd>The id_rsa.pub file to import for this key</dd>
   <dt>-k value, --key value</dt>
   <dd>The actual SSH key</dd>
   <dt>--note value</dt>
   <dd>Extra note that will be associated with key</dd>
   </dl>


**Examples**:
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
This command adds a SSH key from file: ~/.ssh/id_rsa.pub with a note "mykey".


### bluemix sl subnet cancel
{: #sl_subnet_cancel}

Cancel a subnet.
```
 bluemix sl subnet cancel [OPTIONS] IDENTIFIER
```

<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
    </dl>


**Examples**:
```
 bluemix sl subnet cancel 12345678 -f
```
This command cancels subnet with ID 12345678 without asking for confirmation.

### bluemix sl subnet create
{: #sl_subnet_create}

Add a new subnet to your account.
```
   bluemix sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

Valid quantities vary by type.

 * Type    - Valid Quantities (IPv4)
    ** public  - 4, 8, 16, 32
    ** private - 4, 8, 16, 32, 64
 * Type    - Valid Quantities (IPv6)
    ** public  - 64

<strong>Command options</strong>:
   <dl>
   <dt>--v6, --ipv6</dt>
   <dd>Order IPv6 Addresses.</dd>
   <dt>--test</dt>
   <dd>Do not order the subnet; just get a quote.</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
   </dl>

**Examples**:
```
 bluemix sl subnet create public 16 567
```
This command creates a public subnet with 16 IP v4 addresses and places it on vlan with ID 567.



### bluemix sl subnet detail
{: #sl_subnet_detail}

Get details of a subnet.
```
   bluemix sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>Hide virtual server listing.</dd>
   <dt>--no-hardware</dt>
   <dd>Hide hardware listing.</dd>
   </dl>


**Examples**:
```
 bluemix sl subnet detail 12345678
```
This command shows detailed information about subnet with ID 12345678, including virtual servers and hardware servers information.


### bluemix sl subnet-list
{: #sl_subnet_list}

List all subnets on your account
```
   bluemix sl subnet list [OPTIONS]
```


<strong>Command options</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Column to sort by. Options are: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware, vs.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filter by datacenter shortname.</dd>
   <dt>--identifier</dt>
   <dd>Filter by network identifier.</dd>
   <dt>-t, --subnet-type</dt>
   <dd>Filter by subnet type.</dd>
   <dt>--network-space</dt>
   <dd>Filter by network space.</dd>
   <dt>--v4, --ipv4</dt>
   <dd>Display only IPv4 subnets.</dd>
   <dt>--v6, --ipv6</dt>
   <dd>Display only IPv6 subnets.</dd>
   <dt>--order</dt>
   <dd>Filter by the ID of order that purchased the subnets</dd>
   </dl>

**Examples**:
```
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
This command lists IP V4 subnets on current account filtering by datacenter is dal09, subnet type is PRIMARY, and network space is PUBLIC.



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

Find an IP address and display its subnet and device information
```
   bluemix sl subnet lookup IP_ADDRESS
```

**Examples**:
```
 bluemix sl subnet lookup 9.125.235.255
```
This command finds the IP address record with address 9.125.235.255 and display its subnet and device information.


### bluemix sl vs cancel
{: #sl_vs_cancel}

Cancel virtual server instance
```
   bluemix sl vs cancel IDENTIFIER [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
   </dl>

**Examples**:
```
 bluemix sl vs cancel 12345678
```
This command cancels virtual server instance with ID of 12345678.


### bluemix sl vs capture
{: #sl_vs_capture}

Capture virtual server instance into an image
```
 bluemix sl vs capture IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-n, --name</dt>
   <dd>Name of the image [required].</dd>
   <dt>--all</dt>
   <dd>Capture all disks belonging to the VS.</dd>
   <dt>--note</dt>
   <dd>Add a note to be associated with the image.</dd>
   </dl>

**Examples**:
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
This command captures virtual server instance with ID of 12345678 with all disks into an image named "mybluemix" with note "testing".



### bluemix sl vs create
{: #sl_vs_create}

Create virtual server instance
```
   bluemix sl vs create [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-H, --hostname</dt>
   <dd>Host portion of the FQDN [required]</dd>
   <dt>-D, --domain</dt>
   <dd>Domain portion of the FQDN [required]</dd>
   <dt>-c, --cpu</dt>
   <dd>Number of CPU cores [required]</dd>
   <dt>-m, --memory</dt>
   <dd>Memory in megabytes [required]</dd>
   <dt>-d, --datacenter</dt>
   <dd>Datacenter shortname [required]</dd>
   <dt>-o, --os</dt>
   <dd>OS install code. Tip: you can specify <OS>_LATEST</dd>
   <dt>--image</dt>
   <dd>Image ID. See: [bluemix sl image list](#bluemix_sl_image_list) for reference</dd>
   <dt>--billing</dt>
   <dd>Billing rate. Default is: hourly. Options are: hourly, monthly</dd>
   <dt>--dedicated</dt>
   <dd>Create a dedicated Virtual Server (Private Node)</dd>
   <dt>--san</dt>
   <dd>Use SAN storage instead of local disk</dd>
   <dt>--test</dt>
   <dd>Do not actually create the virtual server</dd>
   <dt>--export</dt>
   <dd>Exports options to a template file</dd>
   <dt>-i, --postinstall</dt>
   <dd>Post-install script to download</dd>
   <dt>-k, --key</dt>
   <dd>The IDs of the SSH keys to add to the root user (multiple occurrence permitted)</dd>
   <dt>--disk</dt>
   <dd>Disk sizes (multiple occurrence permitted)</dd>
   <dt>--private</dt>
   <dd>Forces the virtual server to only have access the private network</dd>
   <dt>--like</dt>
   <dd>Use the configuration from an existing virtual server</dd>
   <dt>-n, --network</dt>
   <dd>Network port speed in Mbps</dd>
   <dt>--tag</dt>
   <dd>Tags to add to the instance (multiple occurrence permitted)</dd>
   <dt>-t, --template</dt>
   <dd>A template file that defaults the command-line options</dd>
   <dt>-u, --userdata</dt>
   <dd>User defined metadata string</dd>
   <dt>-F, --userfile</dt>
   <dd>Read userdata from file</dd>
   <dt>--vlan-public</dt>
   <dd>The ID of the public VLAN on which you want the virtual server placed</dd>
   <dt>--vlan-private</dt>
   <dd>The ID of the private VLAN on which you want the virtual server placed</dd>
   <dt>--wait</dt>
   <dd>Wait until the virtual server is finished provisioning for up to X seconds before returning</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
	</dl>

**Examples**:
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
This command orders a virtual server instance with hostname is myvsi, domain is bluemix.net, 4 cpu cores, 4096M memory, located at datacenter: dal10,
  operation system is UBUNTU 16 64 bits, 2 disks, one is 100G, the other is 1000G, and placed at public vlan with ID 413.
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
This command tests whether the order is valid with above options before the order is actually placed.
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

This command exports above options to a file: myvsi.txt under user home directory for later use.


### bluemix sl vs options
{: #sl_vs_options}

List options for creating virtual server instance
```
   bluemix sl vs options [OPTIONS]
```

**Examples**:
```
 bluemix sl vs options
```
This command lists all the options for creating a virtual server instance, eg.datacenters, cpu, memory, os, disk, network speed, etc.



### bluemix sl vs credentials
{: #sl_vs_credentials}

List virtual server instance credentials
```
   bluemix sl vs credentials IDENTIFIER [OPTIONS]
```
**Examples**:
```
 bluemix sl vs credentials 12345678
```
This command lists all username and password pairs of virtual server instance with ID 12345678.

### bluemix sl vs detail
{: #sl_vs_detail}

Get details for a virtual server instance
```
   bluemix sl vs detail IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--passwords</dt>
   <dd>Show passwords.</dd>
   <dt>--price</dt>
   <dd>Show associated prices.</dd>
   </dl>


**Examples**:
```
   bluemix sl vs details 12345678
```
This command lists detailed information about virtual server instance with ID 12345678.


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

Synchronize DNS records for a virtual server instance
```
   bluemix sl vs dns-sync IDENTIFIER [OPTIONS]
```
Note: If you don't specify any arguments, it will attempt to update both the A
   and PTR records. If you don't want to update both records, you may use the
   -a or --ptr arguments to limit the records updated.

<strong>Command options</strong>:
   <dl>
   <dt>-a, --a-record</dt>
   <dd>Sync the A record for the host</dd>
   <dt>--aaaa-record</dt>
   <dd>Sync the AAAA record for the host</dd>
   <dt>--ptr</dt>
   <dd>Sync the PTR record for the host</dd>
   <dt>--ttl</dt>
   <dd>Sets the TTL for the A and/or PTR records, default is: 7200</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
   </dl>


**Examples**:
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
This command synchronizes A record(IP V4 address) of virtual server instance with ID 12345678 to DNS server and sets ttl of this A record to 3600.
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
This command synchronizes both AAAA record(IP V6 address) and PTR record of virtual server instance with ID 12345678 to DNS server.


### bluemix sl vs edit
{: #sl_vs_edit}

Edit a virtual server instance's details
```
   bluemix sl vs edit IDENTIFIER [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>-D, --domain</dt>
   <dd>Domain portion of the FQDN</dd>
   <dt>-H, --hostname</dt>
   <dd>Host portion of the FQDN. example: server</dd>
   <dt>--tag</dt>
   <dd>Tags to set or empty string to remove all</dd>
   <dt>-u, --userdata</dt>
   <dd>User defined metadata string</dd>
   <dt>-F, --userfile</dt>
   <dd>Read userdata from file</dd>
   <dt>--public-speed</dt>
   <dd>Public port speed, options are: 0, 10, 100, 1000, 10000</dd>
   <dt>--private-speed</dt>
   <dd>Private port speed, options are: 0, 10, 100, 1000, 10000</dd>
   </dl>

**Examples**:
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
This command updates virtual server instance with ID `12345678` and set its domain to be `bluemix.net`, hostname to `myapp`, tag to `testcli`, and public network port speed to 1000 Mbps.



### bluemix sl vs list
{: #sl_vs_list}
List virtual server instances on your account
```
   bluemix sl vs list [OPTIONS]
```


<strong>Command options</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Number of CPU cores</dd>
   <dt>-D, --domain</dt>
   <dd>Domain portion of the FQDN</dd>
   <dt>-d, --datacenter</dt>
   <dd>Datacenter shortname</dd>
   <dt>-H, --hostname</dt>
   <dd>Host portion of the FQDN</dd>
   <dt>-m, --memory</dt>
   <dd>Memory in megabytes</dd>
   <dt>-n, --network</dt>
   <dd>Network port speed in Mbps</dd>
   <dt>--hourly</dt>
   <dd>Show only hourly instances</dd>
   <dt>--monthly</dt>
   <dd>Show only monthly instances</dd>
   <dt>--tag</dt>
   <dd>Filter by tags (multiple occurrence permitted)</dd>
   <dt>--sortby</dt>
   <dd>Column to sort by, options are: id, hostname, domain, datacenter, cpu, memory, primary_ip, backend_ip. Default is: hostname</dd>
   <dt>--columns</dt>
   <dd>Columns to display, options are: guid, primary_ip, backend_ip, datacenter, action, power_state, created_by, tags. Default is: id, hostname, primary_ip, backend_ip, datacenter, action</dd>
    </dl>

**Examples**:
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
This command lists all hourly-billing virtual server instances on current account filtering domain equals to "bluemix.net" and sort them by memory.



### bluemix sl vs-pause
{: #sl_vs_pause}

Pause an active virtual server instance
```
   bluemix sl vs pause IDENTIFIER [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
    </dl>

**Examples**:
```
 bluemix sl vs pause 12345678 -f
```
   This command pauses virtual server instance with ID 12345678 without asking for confirmation.



### bluemix sl vs power-off
{: #sl_vs_power_off}

Power off an active virtual server instance
```
   bluemix sl vs power-off IDENTIFIER [OPTIONS]
```

**Examples**:
```
   bluemix sl vs power-off 12345678 --soft
```
This command performs a soft power off for virtual server instance with ID 12345678.

<strong>Command options</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>Perform a hard shutdown</dd>
   <dt>--soft</dt>
   <dd>Perform a soft shutdown</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

Power on a virtual server instance
```
 bluemix sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>

**Examples**:
```
 bluemix sl vs power-on 12345678
```
This command performs a power on for virtual server instance with ID 12345678.


### bluemix sl vs ready
{: #sl_vs_ready}

Check if a virtual server instance is ready for use
```
 bluemix sl vs ready IDENTIFIER [OPTIONS]
```

**Examples**:
```
 bluemix sl vs ready 12345678 --wait 30
```
This command checks virtual server instance with ID 12345678 status to see if it is ready for use continuously and waits up to 30 seconds.

<strong>Command options</strong>:
   <dl>
   <dt>--wait</dt>
   <dd>Wait until the virtual server is finished provisioning for up to X seconds before returning</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

Reboot an active virtual server instance
```
 bluemix sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>Perform a hard reboot</dd>
   <dt>--soft</dt>
   <dd>Perform a hard reboot</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
    </dl>

**Examples**:
```
 bluemix sl vs reboot 12345678 --hard
```
This command performs a hard reboot for virtual server instance with ID 12345678.



### bluemix sl vs reload
{: #sl_vs_reload}

Reload operating system on a virtual server instance
```
 bluemix sl vs reload IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>Post-install script to download</dd>
   <dt>--image</dt>
   <dd>Image ID. The default is to use the current operating system.
See: 'bluemix sl image list' for reference</dd>
   <dt>-k, --key</dt>
   <dd>The IDs of the SSH keys to add to the root user (multiple occurrence permitted)</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>

**Examples**:
```
   bluemix sl vs reload 12345678
```
This command reloads current operating system for virtual server instance with ID 12345678.
```
 bluemix sl vs reload 12345678 --image 1234
```
This command reloads operating system from image with ID 1234 for virtual server instance with ID 12345678.



### bluemix sl vs rescure
{: #sl_vs_rescure}

Reboot a virtual server instance into a rescue image
```
 bluemix sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>
**Examples**:
```
 bluemix sl vs rescue 12345678
```
This command reboots virtual server instance with ID 12345678 into a rescue image.



### bluemix sl vs resume
{: #sl_vs_resume}

Resume a paused virtual server instance
```
   bluemix sl vs resume IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>

**Examples**:
```
 bluemix sl vs resume 12345678
```
This command resumes virtual server instance with ID 12345678.


### bluemix sl vs upgrade
{: #sl_vs_upgrade}

Upgrade a virtual server instance
```
   bluemix sl vs upgrade IDENTIFIER [OPTIONS]
```
Note: SoftLayer automatically reboots the instance once upgrade request is placed. The instance is halted until the upgrade transaction is completed. However for Network, no reboot is required.

<strong>Command options</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>Number of CPU cores</dd>
   <dt>--private</dt>
   <dd>CPU core will be on a dedicated host server.</dd>
   <dt>-m, --memory</dt>
   <dd>Memory in megabytes.</dd>
   <dt>--network</dt>
   <dd>Network port speed in Mbps.</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation.</dd>
    </dl>

**Examples**:
```
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
This commands upgrades virtual server instance with ID 12345678 and set number of CPU cores to 8, memory to 8192M, network port speed to 1000 Mbps.



### bluemix sl vlan create
{: #sl_vlan_create}

Create a new VLAN
```
   bluemix sl vlan create [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>The type of the VLAN, either public or private</dd>
   <dt>-r, --router</dt>
   <dd>The hostname of the router</dd>
   <dt>-d, --datacenter</dt>
   <dd>The short name of the datacenter</dd>
   <dt>-s, --size</dt>
   <dd>The size of the subnets, options are: 8 (5 usable IPs) or 16 (13 usable IPs) or 32 (29 usable IPs)</dd>
   <dt>-n, --name</dt>
   <dd>The name of the VLAN</dd>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>

**Examples**:
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
This command creates a public vlan located at datacenter dal09 with 16 IP addresses and name is myvlan.
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
This command creates a vlan placed on router bcr01a.dal09 with 16 IP addresses and name is myvlan.



### bluemix sl vlan cancel
{: #sl_vlan_cancel}

Cancel a VLAN
```
   bluemix sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>Force operation without confirmation</dd>
    </dl>

**Examples**:
```
   bluemix sl vlan cancel 12345678 -f
```
This command cancels vlan with ID 12345678 without asking for confirmation.



### bluemix sl vlan detail
{: #sl_vlan_detail}

Get details about a VLAN.
```
 bluemix sl vlan detail IDENTIFIER [OPTIONS]
```			

<strong>Command options</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>Hide virtual server listing.</dd>
   <dt>--no-hardware</dt>
   <dd>Hide hardware listing</dd>
   </dl>

**Examples**:
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
   This command shows details of vlan with ID 12345678, and not list virtual server or hardware server.



### bluemix sl vlan edit
{: #sl_vlan_edite}

Edit the details about a VLAN
```
   bluemix sl vlan edit IDENTIFIER [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--n, --name</dt>
   <dd>The name of the VLAN</dd>
    </dl>

**Examples**:
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
This command updates vlan with ID 12345678 and gives it a new name "myvlan-rename".



### bluemix sl vlan list
{: #sl_vlan_list}

List all the VLANs on your account
```
 bluemix sl vlan list [OPTIONS]
```
<strong>Command options</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>Column to sort by, options are: id, number, name, firewall, datacenter, hardware, virtual_servers, public_ips.</dd>
   <dt>-d, --datacenter</dt>
   <dd>Filter by datacenter shortname</dd>
   <dt>-n, --number</dt>
   <dd>Filter by VLAN number</dd>
   <dt>--name</dt>
   <dd>Filter by VLAN name</dd>
   <dt>--order</dt>
   <dd>Filter by ID of the order that purchased the VLAN</dd>
   </dl >

**Examples**:
```
 bluemix sl vlan list -d dal09 --sortby number
```
This commands lists all vlans on current account filtering by datacenter equals to dal09, and sort them by vlan number.




### bluemix sl vlan options
{: #sl_vlan_options}

List all the options for creating VLAN
```
   bluemix sl vlan options
```
**Examples**:
```
 bluemix sl vlan options
```
This command lists all options for creating a vlan, eg. vlan type, datacenters, subnet size, routers, etc.
