---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-17"

keywords: cli, classic infrastructure, bare metal, ibmcloud sl hardware, hardware, power-cycle, firmware

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}

# Creating and working with bare metal servers (ibmcloud sl hardware)
{: #sl-manage-bare-metal}

{{site.data.keyword.baremetal_long}} are single-tenant physical servers that provide you performance and control with low-level access to the hardware resources. Bare metal servers provide the raw horsepower you demand for your processor-intensive and disk I/O-intensive workloads. These servers come with the most complete package of standard features and services.

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classic infrastructure Bare-metal hardware servers.
{: shortdesc}

## ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Cancel a hardware server:
```bash
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

**Command options**:

-i, --immediate
:   Cancels the server immediately (instead of on the billing anniversary).

-r, --reason
:   An optional cancellation reason. See `ibmcloud sl hardware cancel-reasons` for a list of available options.

-c, --comment
:   An optional comment to add to the cancellation ticket.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Display a list of cancellation reasons:
```bash
ibmcloud sl hardware cancel-reasons
```

## ibmcloud sl hardware create
{: #sl_hardware_create}

Order/create a hardware server:
```bash
ibmcloud sl hardware create [OPTIONS]
```

**Command options**:

-H, --hostname
:   Required. Host portion of the FQDN.

-D, --domain
:   Required. Domain portion of the FQDN.

-s, --size
:   Required. Hardware size.

-o, --os
:   Required. OS installation code.

-d, --datacenter
:   Required. Datacenter shortname.

-p, --port-speed
:   Required. Port speed.

-b, --billing
:   Billing rate, either hourly or monthly, default is hourly if not specified.

-i, --post-install
:   Post-install script to download.

-k, --key
:   SSH keys to add to the root user, multiple occurrence allowed.

-n, --no-public
:   Private network only.

-e, --extra
:   Extra options, multiple occurrence allowed.

-t, --test
:   Do not actually create the virtual server.

-m, --template
:   A template file that defaults the command line options.

-x, --export
:   Exports options to a template file.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

View the server order options for a chassis:
```bash
ibmcloud sl hardware create-options
```

## ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

List hardware server credentials:
```bash
ibmcloud sl hardware credentials IDENTIFIER
```

## ibmcloud sl hardware detail
{: #sl_hardware_detail}

Get details for a hardware server:
```bash
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

**Command options**:

-p, --passwords
:   Show passwords (check over your shoulder!).

-c, --price
:   Show associated prices.

## ibmcloud sl hardware edit
{: #sl_hardware_edit}

Edit hardware server details:
```bash
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

**Command options**:

-H, --hostname
:   Host portion of the FQDN.

-D, --domain
:   Domain portion of the FQDN.

-g, --tag
:   Tags to set or empty string to remove all.

-F, --userfile
:   Read user data from a file.

-u, --userdata
:   User defined metadata string.

-p, --public-speed
:   Public port speed, options are: 0,10,100,1000,10000.

-v, --private-speed
:   Private port speed, options are: 0,10,100,1000,10000.

## ibmcloud sl hardware list
{: #sl_hardware_list}

List hardware servers:
```bash
ibmcloud sl hardware list [OPTIONS]
```

**Command options**:

-c, --cpu
:   Filter by number of CPU cores.

-D, --domain
:   Filter by domain.

-H, --hostname
:   Filter by host name.

-d, --datacenter
:   Filter by datacenter.

-m, --memory
:   Filter by memory in GB.

-n, --network
:   Filter by network port speed in Mbps.

-g, --tag
:   Filter by tags. You can specify more than one.

-p, --public-ip
:   Filter by public IP address.

-v, --private-ip
:   Filter by private IP address.

-o, --order
:   Filter by the ID of the order that purchased the hardware server.

--owner
:   Filter by ID of the owner.

--sortby
:   Column to sort by, default:hostname, option:id,guid,hostname,domain,public_ip,private_ip,cpu,memory,os,datacenter,status,ipmi_ip,created,created_by.

--column
:   Column to display,  options are: id,hostname,domain,public_ip,private_ip,datacenter,status,guid,cpu,memory,os,ipmi_ip,created,created_by,tags. This option can be specified multiple times.

## ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Power cycle a server:
```bash
ibmcloud sl hardware power-cycle IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Power off an active server:
```bash
ibmcloud sl hardware power-off IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Power on a server:
```bash
ibmcloud sl hardware power-on IDENTIFIER
```

## ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Reboot an active server:
```bash
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
```

**Command options**:

--hard
:   Perform a hard reboot.

--soft
:   Perform a soft reboot.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware reload
{: #sl_hardware_reload}

Reload operating system on a server:
```bash
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

**Command options**:

-i, --postinstall
:   Post-install script to download, only HTTPS executes, HTTP leaves file in /root.

-k, --key
:   IDs of SSH key to add to the root user. You can specify more than one.

-b, --upgrade-bios
:   Upgrade BIOS.

-w, --upgrade-firmware
:   Upgrade all hard disk drive firmware.

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Reboot server into a rescue image:
```bash
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

## ibmcloud sl hardware toggle-ipmi
{: #sl_hardware_toggle-ipmi}

Toggle the IPMI interface on and off. This command is asynchronous.
```bash
ibmcloud sl hardware toggle-ipmi IDENTIFIER [OPTIONS]
```

**Command options**:

--enable
:   Enable the IPMI interface.

--disable
:   Disable the IPMI interface.

-q, --quiet
:   Suppress verbose output.

## ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Update server firmware:
```bash
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.


