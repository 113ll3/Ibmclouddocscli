---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Hardware CLI commands

<table summary="Alphabetically ordered general {{site.data.keyword.BluSoftlayer_notm}} infrastructure commands that have links that bring you to more info for the command">
<caption>Table 1. {{site.data.keyword.BluSoftlayer_notm}} infrastructure hardware commands</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} infrastructure hardware commands</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl hardware cancel](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel)</td>
 <td>[ibmcloud sl hardware cancel-reasons](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_cancel_reasons)</td>
 <td>[ibmcloud sl hardware create](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create)</td>
 <td>[ibmcloud sl hardware create-options](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_create_options)</td>
 <td>[ibmcloud sl hardware credentials](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_credentials)</td>
 <td>[ibmcloud sl hardware detail](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_detail)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware edit](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_edit)</td>
 <td>[ibmcloud sl hardware list](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_list)</td>
 <td>[ibmcloud sl hardware power-cycle](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_cycle)</td>
 <td>[ibmcloud sl hardware power-off](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_off)</td>
 <td>[ibmcloud sl hardware power-on](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_power_on)</td>
 <td>[ibmcloud sl hardware reboot](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reboot)</td>
 </tr>
<tr>
 <td>[ibmcloud sl hardware reload](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_reload)</td>
 <td>[ibmcloud sl hardware rescue](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_rescue)</td>
 <td>[ibmcloud sl hardware update-firmware](/docs/cli/reference/softlayer/sl_cli_hardware.html#sl_hardware_update_firmware)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Cancel a hardware server.
```
ibmcloud sl hardware cancel IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-i, --immediate</dt>
<dd>Cancels the server immediately (instead of on the billing anniversary).</dd>
<dt>-r, --reason</dt>
<dd>An optional cancellation reason. See 'ibmcloud sl hardware cancel-reasons' for a list of available options.</dd>
<dt>-c, --comment</dt>
<dd>An optional comment to add to the cancellation ticket.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

### ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Display a list of cancellation reasons.
```
ibmcloud sl hardware cancel-reasons
```

### ibmcloud sl hardware create
{: #sl_hardware_create}

Order/create a hardware server.
```
ibmcloud sl hardware create [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Host portion of the FQDN, required.</dd>
<dt>-D, --domain</dt>
<dd>Domain portion of the FQDN, required.</dd>
<dt>-s, --size</dt>
<dd>Hardware size, required.</dd>
<dt>-o, --os</dt>
<dd>OS install code, required.</dd>
<dt>-d, --datacenter</dt>
<dd>Datacenter shortname, required.</dd>
<dt>-p, --port-speed</dt>
<dd>Port speed, required.</dd>
<dt>-b, --billing</dt>
<dd>Billing rate, either hourly or monthly, default is hourly if not specified.</dd>
<dt>-i, --post-install</dt>
<dd>Post-install script to download.</dd>
<dt>-k, --key</dt>
<dd>SSH keys to add to the root user, multiple occurrence allowed.</dd>
<dt>-n, --no-public</dt>
<dd>Private network only.</dd>
<dt>-e, --extra</dt>
<dd>Extra options, multiple occurrence allowed.</dd>
<dt>-t, --test</dt>
<dd>Do not actually create the virtual server.</dd>
<dt>-m, --template</dt>
<dd>A template file that defaults the command-line options.</dd>
<dt>-x, --export</dt>
<dd>Exports options to a template file.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

### ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

Server order options for a given chassis.
```
ibmcloud sl hardware create-options
```

### ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

List hardware server credentials.
```
ibmcloud sl hardware credentials IDENTIFIER
```

### ibmcloud sl hardware detail
{: #sl_hardware_detail}

Get details for a hardware server.
```
ibmcloud sl hardware detail IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-p, --passwords</dt>
<dd>Show passwords (check over your shoulder!).</dd>
<dt>-c, --price</dt>
<dd>Show associated prices.</dd>
</dl>

### ibmcloud sl hardware edit
{: #sl_hardware_edit}

Edit hardware server details.
```
ibmcloud sl hardware edit IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Host portion of the FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Domain portion of the FQDN.</dd>
<dt>-g, --tag</dt>
<dd>Tags to set or empty string to remove all.</dd>
<dt>-F, --userfile</dt>
<dd>Read userdata from file.</dd>
<dt>-u, --userdata</dt>
<dd>User defined metadata string.</dd>
<dt>-p, --public-speed</dt>
<dd>Public port speed, options are: 0,10,100,1000,10000.</dd>
<dt>-v, --private-speed</dt>
<dd>Private port speed, options are: 0,10,100,1000,10000.</dd>
</dl>

### ibmcloud sl hardware list
{: #sl_hardware_list}

List hardware servers.
```
ibmcloud sl hardware list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filter by number of CPU cores.</dd>
<dt>-D, --domain</dt>
<dd>Filter by domain.</dd>
<dt>-H, --hostname</dt>
<dd>Filter by hostname.</dd>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter.</dd>
<dt>-m, --memory</dt>
<dd>Filter by memory in gigabytes.</dd>
<dt>-n, --network</dt>
<dd>Filter by network port speed in Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Filter by tags, multiple occurrence allowed.</dd>
<dt>-p, --public-ip</dt>
<dd>Filter by public IP address.</dd>
<dt>-v, --private-ip</dt>
<dd>Filter by private IP address.</dd>
<dt>-o, --order</dt>
<dd>Filter by ID of the order which purchased hardware server.</dd>
<dt>--owner</dt>
<dd>Filter by ID of the owner.</dd>
<dt>--sortby</dt>
<dd>Column to sort by, default:hostname, option:id,guid,hostname,domain,public_ip,private_ip,datacenter,status,ipmi_ip,created,created_by.</dd>
<dt>--columns</dt>
<dd>Columns to display, default:id,hostname,domain,public_ip,private_ip,datacenter,status, options:guid,cpu,memory,os,ipmi_ip,created,created_by,tags.</dd>
</dl>

### ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Power cycle a server.
```
ibmcloud sl hardware power-cycle IDENTIFIER
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

### ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Power off an active server.
```
ibmcloud sl hardware power-off IDENTIFIER
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

### ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Power on a server.
```
ibmcloud sl hardware power-on IDENTIFIER
```

### ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Reboot an active server.
```
ibmcloud sl hardware reboot IDENTIFIER [OPTIONS]
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

### ibmcloud sl hardware reload
{: #sl_hardware_reload}

Reload operating system on a server.
```
ibmcloud sl hardware reload IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Post-install script to download, only HTTPS executes, HTTP leaves file in /root.</dd>
<dt>-k, --key</dt>
<dd>IDs of SSH key to add to the root user, multiple occurrence allowed.</dd>
<dt>-b, --upgrade-bios</dt>
<dd>Upgrade BIOS.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>Upgrade all hard drives' firmware.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

### ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Reboot server into a rescue image.
```
ibmcloud sl hardware rescue IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

### ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Update server firmware.
```
ibmcloud sl hardware update-firmware IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>
