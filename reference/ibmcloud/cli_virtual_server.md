---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-14"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Creating and working with virtual servers
{: #cli-virtual-servers}

{{site.data.keyword.BluVirtServers}} are scalable virtual servers that are purchased with dedicated cores and memory allocations. They are a great option if you are looking for compute resources, that can be added in minutes, with access to features like image templates. 

Use the following commands to manage classic infrastructure virtual servers.
{: shortdesc}

## ibmcloud sl vs cancel
{: #sl_vs_cancel}

Cancel virtual server instance.
```
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs cancel 12345678
```
{: codeblock}

This command cancels virtual server instance with ID of `12345678`.

## ibmcloud sl vs capture
{: #sl_vs_capture}

Capture virtual server instance into an image.
```
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Required. Name of the image .</dd>
<dt>--all</dt>
<dd>Capture all disks belonging to the VS.</dd>
<dt>--note</dt>
<dd>Add a note to be associated with the image.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
{: codeblock}

This command captures virtual server instance with ID of `12345678` with all disks into an image that is named `mycloud` with note `testing`.

## ibmcloud sl vs create
{: #sl_vs_create}

Create virtual server instance.
```
ibmcloud sl vs create [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Required. Host portion of the FQDN .</dd>
<dt>-D, --domain</dt>
<dd>Required. Domain portion of the FQDN .</dd>
<dt>-c, --cpu</dt>
<dd>Required. Number of CPU cores .</dd>
<dt>-m, --memory</dt>
<dd>Required. Memory in megabytes .</dd>
<dt>--flavor</dt>
<dd>Public Virtual Server flavor key name.</dd>
<dt>-d, --datacenter</dt>
<dd>Required. Datacenter shortname .</dd>
<dt>-o, --os</dt>
<dd>OS install code. Tip: you can specify <OS>_LATEST.</dd>
<dt>--image</dt>
<dd>Image ID. See: 'ibmcloud sl image list' for reference.</dd>
<dt>--billing</dt>
<dd>Billing rate. Default is: hourly. Options are: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Create a dedicated Virtual Server (Private Node).</dd>
<dt>--host-id</dt>
<dd>Host Id to provision a Dedicated Virtual Server onto.</dd>
<dt>--san</dt>
<dd>Use SAN storage instead of local disk.</dd>
<dt>--test</dt>
<dd>Do not actually create the virtual server.</dd>
<dt>--export</dt>
<dd>Exports options to a template file.</dd>
<dt>-i, --postinstall</dt>
<dd>Post-install script to download.</dd>
<dt>-k, --key</dt>
<dd>The IDs of the SSH keys to add to the root user (multiple occurrence permitted).</dd>
<dt>--disk</dt>
<dd>Disk sizes (multiple occurrence permitted).</dd>
<dt>--private</dt>
<dd>Forces the virtual server to only have access the private network.</dd>
<dt>--like</dt>
<dd>Use the configuration from an existing virtual server.</dd>
<dt>-n, --network</dt>
<dd>Network port speed in Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Tags to add to the instance (multiple occurrence permitted).</dd>
<dt>-t, --template</dt>
<dd>A template file that defaults the command-line options.</dd>
<dt>-u, --userdata</dt>
<dd>User defined metadata string.</dd>
<dt>-F, --userfile</dt>
<dd>Read userdata from file.</dd>
<dt>--vlan-public</dt>
<dd>The ID of the public VLAN on which you want the virtual server placed.</dd>
<dt>--vlan-private</dt>
<dd>The ID of the private VLAN on which you want the virtual server placed.</dd>
<dt>-S, --public-security-group</dt>
<dd>Security group ID to associate with the public interface (multiple occurrence permitted).</dd>
<dt>-s, --private-security-group</dt>
<dd>Security group ID to associate with the private interface (multiple occurrence permitted).</dd>
<dt>--wait</dt>
<dd>Wait until the virtual server is finished provisioning for up to X seconds before returning.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
{: codeblock}

This command orders a virtual server instance with hostname is myvsi, domain is ibm.com, 4 cpu cores, 4096M memory, located at datacenter: dal10,

## ibmcloud sl vs options
{: #sl_vs_options}

List options for creating virtual server instance.
```
ibmcloud sl vs options [OPTIONS]
```

**Examples**:
```
ibmcloud sl vs options
```
{: codeblock}

This command lists all the options for creating a virtual server instance, eg.datacenters, cpu, memory, os, disk, network speed, etc.

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

List virtual server instance credentials.
```
ibmcloud sl vs credentials IDENTIFIER [OPTIONS]
```

**Examples**:
```
ibmcloud sl vs credentials 12345678
```
{: codeblock}

This command lists all username and password pairs of virtual server instance with ID `12345678`.

## ibmcloud sl vs detail
{: #sl_vs_detail}

Get details for a virtual server instance.
```
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--passwords</dt>
<dd>Show passwords (check over your shoulder!).</dd>
<dt>--price</dt>
<dd>Show associated prices.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs details 12345678
```
{: codeblock}

This command lists detailed information about virtual server instance with ID `12345678`.

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Synchronize DNS records for a virtual server instance.
```
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>Sync the A record for the host.</dd>
<dt>--aaaa-record</dt>
<dd>Sync the AAAA record for the host.</dd>
<dt>--ptr</dt>
<dd>Sync the PTR record for the host.</dd>
<dt>--ttl</dt>
<dd>Sets the TTL for the A and/or PTR records, default is: 7200.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
{: codeblock}

This command synchronizes A record(IP V4 address) of virtual server instance with ID `12345678` to DNS server and sets TTL of this A record to 3600.

## ibmcloud sl vs edit
{: #sl_vs_edit}

Edit a virtual server instance's details.
```
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Domain portion of the FQDN.</dd>
<dt>-H, --hostname</dt>
<dd>Host portion of the FQDN. example: server.</dd>
<dt>-g, --tag</dt>
<dd>Tags to set or empty string to remove all.</dd>
<dt>-u, --userdata</dt>
<dd>User defined metadata string.</dd>
<dt>-F, --userfile</dt>
<dd>Read userdata from file.</dd>
<dt>--public-speed</dt>
<dd>Public port speed, options are: 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>Private port speed, options are: 0,10,100,1000,10000.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
This command updates virtual server instance with ID 12345678 and set its domain to be "ibm.com", hostname to "myapp", tag to "testcli",

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

Create a host for dedicated virtual servers.
```
ibmcloud sl vs host-create [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Required. Host portion of the FQDN .</dd>
<dt>-D, --domain</dt>
<dd>Required. Domain portion of the FQDN .</dd>
<dt>-d, --datacenter</dt>
<dd>Required. Datacenter shortname .</dd>
<dt>-s, --size</dt>
<dd>Size of the dedicated host, currently only one size is avaiable: 56_CORES_X_242_RAM_X_1_4_TB.</dd>
<dt>-b, --billing</dt>
<dd>Billing rate. Default is: hourly. Options are: hourly, monthly.</dd>
<dt>-v, --vlan-private</dt>
<dd>The ID of the private VLAN on which you want the dedicated host placed. See: 'ibmcloud sl vlan list' for reference.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

List dedicated hosts on your account.
```
ibmcloud sl vs host-list [OPTIONS]
```


<strong>Command options</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Filter by name of the dedicated host.</dd>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter of the dedicated host.</dd>
<dt>--owner</dt>
<dd>Filter by owner of the dedicated host.</dd>
<dt>--order</dt>
<dd>Filter by ID of the order which purchased this dedicated host.</dd>
</dl>

## ibmcloud sl vs list
{: #sl_vs_list}

List virtual server instances on your account.
```
ibmcloud sl vs list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filter by number of CPU cores.</dd>
<dt>-D, --domain</dt>
<dd>Filter by domain portion of the FQDN.</dd>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter shortname.</dd>
<dt>-H, --hostname</dt>
<dd>Filter by host portion of the FQDN.</dd>
<dt>-m, --memory</dt>
<dd>Filter by memory in megabytes.</dd>
<dt>-n, --network</dt>
<dd>Filter by network port speed in Mbps.</dd>
<dt>-P, --public-ip</dt>
<dd>Filter by public IP address.</dd>
<dt>-p, --private-ip</dt>
<dd>Filter by private IP address.</dd>
<dt>--hourly</dt>
<dd>Show only hourly instances.</dd>
<dt>--monthly</dt>
<dd>Show only monthly instances.</dd>
<dt>-g, --tag</dt>
<dd>Filter by tags (multiple occurrence permitted).</dd>
<dt>-o, --order</dt>
<dd>Filter by ID of the order which purchased this instance.</dd>
<dt>--owner</dt>
<dd>Filtered by Id of user who owns the instances.</dd>
<dt>--sortby</dt>
<dd>Column to sort by, default is:hostname, options are:id,hostname,domain,datacenter,cpu,memory,public_ip,private_ip.</dd>
<dt>--columns</dt>
<dd>Columns to display, default is:id,hostname,public_ip,private_ip,datacenter,action, options are: guid,power_state,created_by,tags.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
This command lists all hourly-billing virtual server instances on current account filtering domain equals to "ibm.com" and sort them by memory.

## ibmcloud sl vs pause
{: #sl_vs_pause}

Pause an active virtual server instance.
```
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs pause 12345678 -f
```
This command pauses virtual server instance with ID 12345678 without asking for confirmation.

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

Power off an active virtual server instance.
```
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--hard</dt>
<dd>Perform a hard shutdown.</dd>
<dt>--soft</dt>
<dd>Perform a soft shutdown.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs power-off 12345678 --soft
```
This command performs a soft power off for virtual server instance with ID 12345678.

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

Power on a virtual server instance.
```
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs power-on 12345678
```
{: codeblock}

This command performs a power on for virtual server instance with ID `12345678`.

## ibmcloud sl vs ready
{: #sl_vs_ready}

Check if a virtual server instance is ready for use.
```
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--wait</dt>
<dd>Wait until the virtual server is finished provisioning for up to X seconds before returning.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
This command checks virtual server instance with ID `12345678` status to see if it is ready for use continuously and waits up to 30 seconds.

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

Reboot an active virtual server instance.
```
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--hard</dt>
<dd>Perform a hard reboot.</dd>
<dt>--soft</dt>
<dd>Perform a soft reboot.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs reboot 12345678 --hard
```
{: codeblock}

This command performs a hard reboot for virtual server instance with ID `12345678`.

## ibmcloud sl vs reload
{: #sl_vs_reload}

Reload operating system on a virtual server instance.
```
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Post-install script to download.</dd>
<dt>--image</dt>
<dd>Image ID. The default is to use the current operating system.</dd>
<dt>See:</dt>
<dd>'ibmcloud sl image list' for reference.</dd>
<dt>-k, --key</dt>
<dd>The IDs of the SSH keys to add to the root user (multiple occurrence permitted).</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs reload 12345678
```
This command reloads current operating system for virtual server instance with ID 12345678.

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

Reboot a virtual server instance into a rescue image.
```
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs rescue 12345678
```
This command reboots virtual server instance with ID 12345678 into a rescue image.

## ibmcloud sl vs resume
{: #sl_vs_resume}

Resume a paused virtual server instance.
```
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl vs resume 12345678
```
This command resumes virtual server instance with ID 12345678.

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Upgrade a virtual server instance.
```
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Number of CPU cores.</dd>
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
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
{: codeblock}

This commands upgrades virtual server instance with ID `12345678` and set number of CPU cores to 8, memory to 8192M, network port speed to 1000 Mbps.
