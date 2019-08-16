---

copyright:
  years: 2018, 2019
lastupdated: "2019-08-15"

keywords: cli, manage subnet cli, classic infrastructure cli, subnet cli, ibmcloud sl subnet, subnet cli, newtork cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Creating, canceling, and viewing subnets
{: #sl-manage-subnets}

A subnet is a logical partition of an IP network into multiple, smaller network segments. Use the following commands to manage {{site.data.keyword.cloud}} classic infrastructure subnets.
{: shortdesc}

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
This command cancels subnet with ID `12345678` without asking for confirmation.

## ibmcloud sl subnet create
{: #sl_subnet_create}

Add a subnet to your account.
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--v6, --ipv6</dt>
<dd>Order IPV6 Addresses.</dd>
<dt>--test</dt>
<dd>Do not order the subnet; just get a quote.</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl subnet create public 16 567
```
{: codeblock}

This command creates a public subnet with 16 IPV4 addresses and places it on VLAN with ID `567`.

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
{: codeblock}

This command shows detailed information about subnet with ID `12345678`, including virtual servers and hardware servers information.

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
<dd>Display only IPV6 subnets.</dd>
<dt>--order</dt>
<dd>Filter by the ID of order that purchased the subnets.</dd>
</dl>

**Examples**:
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
{: codeblock}

This command lists IPV4 subnets on the current account, and filters by datacenter `dal09`, subnet type `PRIMARY`, and network space `PUBLIC`.

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
{: codeblock}

This command finds the IP address record with IP address `9.125.235.255` and displays its subnet and device information.
