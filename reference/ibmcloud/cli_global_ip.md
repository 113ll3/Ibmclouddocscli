---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing Global IPs

A Global IP address is a specialized static secondary subnet. It is delivered to you as a /32 subnet (in other words, a single IP address) that can be routed to any other IP address on your account.

Use the following commands to manage a global IP in the {{site.data.keyword.Bluemix}} classic infrastructure Global IP service.
{: shortdesc}

<table summary="Alphabetically ordered  {{site.data.keyword.Bluemix_notm}} classic infrastructure Global IP commands that have links that bring you to more info for the command">
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl globalip assign
{: #sl_globalip_assign}

Assign a global IP to a target router or device.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Examples**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
This command assigns IP address with ID 12345678 to a target device whose IP address is 9.111.123.456.

## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Cancel a global IP.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl globalip cancel 12345678
```
This command cancels IP address with ID 12345678.

 ## ibmcloud sl globalip create
{: #sl_globalip_create}

Create a global IP.
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--v6</dt>
<dd>Order a IPv6 IP address.</dd>
<dt>--test</dt>
<dd>Test order.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl globalip create --v6
```
This command creates an IP V6 address.

## ibmcloud sl globalip list
{: #sl_globalip_list}

List all global IPs on your account.
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--v4</dt>
<dd>Display only IPv4.</dd>
<dt>--v6</dt>
<dd>Display only IPv6.</dd>
<dt>--order</dt>
<dd>Filter by the ID of order that purchased this IP address.</dd>
</dl>

**Examples**:
```
ibmcloud sl globalip list --v4
```
This command lists all IP V4 addresses on current account.

## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Unassign a global IP from a target router or device.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**Examples**:
```
ibmcloud sl globalip unassign 12345678
```
This command unassigns IP address with ID 12345678 from target device.
