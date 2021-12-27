---

copyright:
  years: 2018, 2021
lastupdated: "2021-12-15"

keywords: cli, classic infrastructure cli, ibmcloud sl vs, virtual server cli, virtual server commands

subcollection: cli

---


{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Creating and working with virtual servers (ibmcloud sl vs)
{: #cli-virtual-servers}

{{site.data.keyword.BluVirtServers}} are scalable virtual servers that are purchased with dedicated cores and memory allocations. They are a great option if you are looking for compute resources, that can be added in minutes, with access to features like image templates. 

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage classic infrastructure virtual servers.
{: shortdesc}

## ibmcloud sl vs cancel
{: #sl_vs_cancel}

Cancel virtual server instance:
```bash
ibmcloud sl vs cancel IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs cancel 12345678
```
{: codeblock}

This command cancels virtual server instance with ID of `12345678`.

## ibmcloud sl vs capture
{: #sl_vs_capture}

Capture virtual server instance into an image:
```bash
ibmcloud sl vs capture IDENTIFIER [OPTIONS]
```

**Command options**:

-n, --name
:   Required. Name of the image.

--all
:   Capture all disks that belong to the virtual server.

--note
:   Add a note to be associated with the image.

**Examples**:
```bash
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
{: codeblock}

This command captures virtual server instance with ID of `12345678` with all disks into an image that is named `mycloud` with note `testing`.

## ibmcloud sl vs create
{: #sl_vs_create}

Create virtual server instance:
```bash
ibmcloud sl vs create [OPTIONS]
```

**Command options**:

-H, --hostname
:   Required. Host portion of the FQDN.

-D, --domain
:   Required. Domain portion of the FQDN.

-c, --cpu
:   Required. Number of CPU cores.

-m, --memory
:   Required. Memory in MB.

--flavor
:   Public Virtual Server flavor key name. Required if the "suspend billing" capabilities are needed.

-d, --datacenter
:   Required. Datacenter shortname.

-o, --os
:   OS installation code. Tip: you can specify "OS"_LATEST.

--image
:   Image ID. See: `ibmcloud sl image list` for reference.

--billing
:   Billing rate. Default is: hourly. Options are: hourly, monthly.

--dedicated
:   Create a dedicated Virtual Server (Private Node).

--host-id
:   Host ID to provision a Dedicated Virtual Server onto.

--san
:   Use SAN storage instead of local disk.

--test
:   Run this command as a test and do not actually create the virtual server.

--export
:   Exports options to a template file.

-i, --postinstall
:   Post-install script to download.

-k, --key
:   The IDs of the SSH keys to add to the root user. You can specify this option multiple times. 

--disk
:   Disk sizes. You can specify more than one.

--private
:   Forces the virtual server to only have access to the private network.

--like
:   Use the configuration from an existing virtual server.

-n, --network
:   Network port speed in Mbps.

-g, --tag
:   Tags to add to the instance. You can specify this option multiple times.

-t, --template
:   A template file that defaults the command line options.

-u, --userdata
:   User-defined metadata string.

-F, --userfile
:   Read user data from file.

--vlan-public
:   The ID of the public VLAN on which you want the virtual server placed.

--vlan-private
:   The ID of the private VLAN on which you want the virtual server placed.

-S, --public-security-group
:   Security group ID to associate with the public interface. You can specify this option multiple times.

-s, --private-security-group
:   Security group ID to associate with the private interface. You can specify this option multiple times.

--wait
:   Wait until the virtual server is finished provisioning for up to X seconds.

--placement-group-id
:   Placement Group Id to order this guest on.

--boot-mode
:   Specify the mode to boot the OS in. Supported modes are HVM and PV.

--subnet-public
:   The ID of the public SUBNET on which you want the virtual server placed.

--subnet-private
:   The ID of the private SUBNET on which you want the virtual server placed.

--transient
:   Create a transient virtual server.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
{: codeblock}

This command orders a virtual server instance with host name `myvsi`, domain `ibm.com`, 4 cpu cores, 4096 M memory, and at datacenter `dal10`,

## ibmcloud sl vs credentials
{: #sl_vs_credentials}

List virtual server instance credentials:
```bash
ibmcloud sl vs credentials IDENTIFIER 
```

**Examples**:
```bash
ibmcloud sl vs credentials 12345678
```
{: codeblock}

This command lists all username and password pairs of virtual server instance with ID `12345678`.

## ibmcloud sl vs detail
{: #sl_vs_detail}

Get details for a virtual server instance:
```bash
ibmcloud sl vs detail IDENTIFIER [OPTIONS]
```

**Command options**:

--passwords
:   Show passwords (check over your shoulder!).

--price
:   Show associated prices.

**Examples**:
```bash
ibmcloud sl vs detail 12345678
```
{: codeblock}

This command lists detailed information about virtual server instance with ID `12345678`.

## ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Synchronize DNS records for a virtual server instance:
```bash
ibmcloud sl vs dns-sync IDENTIFIER [OPTIONS]
```

**Command options**:

-a, --a-record
:   Sync the A record for the host.

--aaaa-record
:   Sync the AAAA record for the host.

--ptr
:   Sync the PTR record for the host.

--ttl
:   Sets the TTL for the A and PTR records. The default value is 7200.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
{: codeblock}

This command synchronizes an A record (IPv4 address) of virtual server instance with ID `12345678` to DNS server and sets the `TTL` of this A record to 3600.

## ibmcloud sl vs edit
{: #sl_vs_edit}

Edit a virtual server instance's details:
```bash
ibmcloud sl vs edit IDENTIFIER [OPTIONS]
```

**Command options**:

-D, --domain
:   Domain portion of the FQDN.

-H, --hostname
:   Host portion of the FQDN. example: server.

-g, --tag
:   Tags to set or empty string to remove all.

-u, --userdata
:   User defined metadata string.

-F, --userfile
:   Read user data from file.

--public-speed
:   Public port speed, options are: 0,10,100,1000,10000.

--private-speed
:   Private port speed, options are: 0,10,100,1000,10000.

**Examples**:
```bash
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
{: codeblock}

This command updates the virtual server instance with ID `12345678`, and sets its domain to "ibm.com", host name to "myapp", and tag to "testcli".

## ibmcloud sl vs host-create
{: #sl_vs_host_create}

Create a host for dedicated virtual servers:
```bash
ibmcloud sl vs host-create [OPTIONS]
```

**Command options**:

-H, --hostname
:   Required. Host portion of the FQDN.

-D, --domain
:   Required. Domain portion of the FQDN.

-d, --datacenter
:   Required. Datacenter shortname.

-s, --size
:   Size of the dedicated host, currently only one size is available: 56_CORES_X_242_RAM_X_1_4_TB.

-b, --billing
:   Billing rate. Default is: hourly. Options are: hourly, monthly.

-v, --vlan-private
:   The ID of the private VLAN on which you want the dedicated host placed. See: `ibmcloud sl vlan list` for reference.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl vs host-list
{: #sl_vs_host_list}

List dedicated hosts on your account:
```bash
ibmcloud sl vs host-list [OPTIONS]
```

**Command options**:

-n, --name
:   Filter by name of the dedicated host.

-d, --datacenter
:   Filter by datacenter of the dedicated host.

--owner
:   Filter by owner of the dedicated host.

--order
:   Filter by ID of the order that purchased this dedicated host.

## ibmcloud sl vs list
{: #sl_vs_list}

List virtual server instances on your account:
```bash
ibmcloud sl vs list [OPTIONS]
```

**Command options**:

-c, --cpu
:   Filter by number of CPU cores.

-D, --domain
:   Filter by domain portion of the FQDN.

-d, --datacenter
:   Filter by datacenter shortname.

-H, --hostname
:   Filter by host portion of the FQDN.

-m, --memory
:   Filter by memory in megabytes.

-n, --network
:   Filter by network port speed in Mbps.

-P, --public-ip
:   Filter by public IP address.

-p, --private-ip
:   Filter by private IP address.

--hourly
:   Show only hourly instances.

--monthly
:   Show only monthly instances.

-g, --tag
:   Filter by tags. This option can be specified multiple times.

-o, --order
:   Filter by ID of the order that purchased this instance.

--owner
:   Filtered by ID of user who owns the instances.

--sortby
:   Column to sort by, default is: hostname, options are: id, hostname, domain, datacenter, cpu, memory, public_ip, private_ip.

--column
:   Column to display. Options are: id, hostname, domain, cpu, memory, public_ip, private_ip, datacenter, action, guid, power_state, created_by,tags. This option can be specified multiple times.

**Examples**:
```bash
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
{: codeblock}

This command lists all hourly-billing virtual server instances on current account filtering domain equals to "ibm.com" and sort them by memory.

## ibmcloud sl vs options
{: #sl_vs_options}

List options for creating virtual server instance:
```bash
ibmcloud sl vs options [OPTIONS]
```

**Examples**:
```bash
ibmcloud sl vs options
```
{: codeblock}

This command lists all the options for creating a virtual server instance, eg.datacenters, cpu, memory, os, disk, network speed, etc.

## ibmcloud sl vs pause
{: #sl_vs_pause}

Pause an active virtual server instance:
```bash
ibmcloud sl vs pause IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs pause 12345678 -f
```
{: codeblock}

This command pauses virtual server instance with ID `12345678` without asking for confirmation.

## ibmcloud sl vs power-off
{: #sl_vs_power_off}

Power off an active virtual server instance:
```bash
ibmcloud sl vs power-off IDENTIFIER [OPTIONS]
```

**Command options**:

--hard
:   Perform a hard shutdown.

--soft
:   Perform a soft shutdown.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs power-off 12345678 --soft
```
{: codeblock}

This command gracefully powers off a virtual server instance with ID `12345678`.

## ibmcloud sl vs power-on
{: #sl_vs_power_on}

Power on a virtual server instance:
```bash
ibmcloud sl vs power-on IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs power-on 12345678
```
{: codeblock}

This command powers on a virtual server instance with ID `12345678`.

## ibmcloud sl vs ready
{: #sl_vs_ready}

Check whether a virtual server instance is ready for use:
```bash
ibmcloud sl vs ready IDENTIFIER [OPTIONS]
```

**Command options**:

--wait
:   Wait until the virtual server is finished provisioning for up to X seconds.

**Examples**:
```bash
ibmcloud sl vs ready 12345678 --wait 30
```
{: codeblock}

This command checks virtual server instance with ID `12345678` status to see whether it is ready for use continuously and waits up to 30 seconds.

## ibmcloud sl vs reboot
{: #sl_vs_reboot}

Reboot an active virtual server instance:
```bash
ibmcloud sl vs reboot IDENTIFIER [OPTIONS]
```

**Command options**:

--hard
:   Perform a hard reboot.

--soft
:   Perform a soft reboot.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs reboot 12345678 --hard
```
{: codeblock}

This command hard reboots a virtual server instance with ID `12345678`.

## ibmcloud sl vs reload
{: #sl_vs_reload}

Reload operating system on a virtual server instance:
```bash
ibmcloud sl vs reload IDENTIFIER [OPTIONS]
```

**Command options**:

-i, --postinstall
:   Post-install script to download.

--image
:   Image ID. The default is to use the current operating system.

See:
:   `ibmcloud sl image list` for reference.

-k, --key
:   The IDs of the SSH keys to add to the root user. This option can be specified multiple times.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs reload 12345678
```
{: codeblock}

This command reloads current operating system for virtual server instance with ID `12345678`.

## ibmcloud sl vs rescue
{: #sl_vs_rescue}

Reboot a virtual server instance into a rescue image:
```bash
ibmcloud sl vs rescue IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs rescue 12345678
```
{: codeblock}

This command reboots virtual server instance with ID `12345678` into a rescue image.

## ibmcloud sl vs resume
{: #sl_vs_resume}

Resume a paused virtual server instance:
```bash
ibmcloud sl vs resume IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs resume 12345678
```
{: codeblock}

This command resumes virtual server instance with ID `12345678`.

## ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Upgrade a virtual server instance:
```bash
ibmcloud sl vs upgrade IDENTIFIER [OPTIONS]
```

**Command options**:

-c, --cpu
:   Number of CPU cores.

--private
:   CPU core is on a dedicated host server.

-m, --memory
:   Memory in MB.

--network
:   Network port speed in Mbps.

--flavor
:   Flavor key name.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
{: codeblock}

This command upgrades the virtual server instance with ID `12345678` and sets the number of CPU cores to 8, memory to 8192 MB, network port speed to 1000 Mbps.

