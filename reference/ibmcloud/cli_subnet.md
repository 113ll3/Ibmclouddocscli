---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Creating, canceling, and viewing subnets

A subnet is a logical partition of an IP network into multiple, smaller network segments. Use the following commands to manage {{site.data.keyword.Bluemix}} classic infrastructure subnets.
{: shortdesc}

<table summary="Alphabetically ordered  {{site.data.keyword.Bluemix_notm}} classic infrastructure Subnet commands that have links that bring you to more info for the command">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Cancel a subnet.
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl subnet cancel 12345678 -f
```
This command cancels subnet with ID 12345678 without asking for confirmation.

## ibmcloud sl subnet create
{: #sl_subnet_create}

Add a new subnet to your account.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>Order IPv6 Addresses.</dd>
<dt>--test</dt>
<dd>Do not order the subnet; just get a quote.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl subnet create public 16 567
```
This command creates a public subnet with 16 IP v4 addresses and places it on vlan with ID 567.

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

Get details of a subnet.
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
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
ibmcloud sl subnet detail 12345678
```
This command shows detailed information about subnet with ID 12345678, including virtual servers and hardware servers information.

## ibmcloud sl subnet list
{: #sl_subnet_list}

List all subnets on your account.
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--sortby</dt>
<dd>Column to sort by. Options are: id,identifier,type,network_space,datacenter,vlan_id,IPs,hardware,vs.</dd>
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
<dd>Filter by the ID of order that purchased the subnets.</dd>
</dl>

**Examples**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
This command lists IP V4 subnets on current account filtering by datacenter is dal09, subnet type is PRIMARY, and network space is PUBLIC.

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

Find an IP address and display its subnet and device information.
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**Examples**:
```
ibmcloud sl subnet lookup 9.125.235.255
```
This command finds the IP address record with address 9.125.235.255 and display its subnet and device information.
