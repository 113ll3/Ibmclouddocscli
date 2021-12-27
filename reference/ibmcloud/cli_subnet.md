---

copyright:
  years: 2018, 2020
lastupdated: "2020-12-15"

keywords: cli, manage subnet cli, classic infrastructure cli, subnet cli, ibmcloud sl subnet, subnet cli, network cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Creating, canceling, and viewing subnets (ibmcloud sl subnet)
{: #sl-manage-subnets}

A subnet is a logical partition of an IP network into multiple, smaller network segments. Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classic infrastructure subnets.
{: shortdesc}

## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

Cancel a subnet:
```bash
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl subnet cancel 12345678 -f
```
{: codeblock}

This command cancels subnet with ID `12345678` without asking for confirmation.

## ibmcloud sl subnet create
{: #sl_subnet_create}

Add a new subnet to your account:
```bash
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

**Command options**:


--v6, --ipv6
:   Order IPv6 Addresses.

--test
:   Do not order the subnet; just get a quote.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl subnet create public 16 567
```
{: codeblock}

This command creates a public subnet with 16 IPv4 addresses and places it on VLAN with ID `567`.

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

Get details of a subnet:
```bash
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
```

**Command options**:

--no-vs
:   Hide virtual server listing.

--no-hardware
:   Hide hardware listing.

**Examples**:
```bash
ibmcloud sl subnet detail 12345678
```
{: codeblock}

This command shows detailed information about subnet with ID `12345678`, including virtual servers and hardware servers information.

## ibmcloud sl subnet list
{: #sl_subnet_list}

List all subnets on your account:
```bash
ibmcloud sl subnet list [OPTIONS]
```

**Command options**:

--sortby
:   Column to sort by. Options are: id, identifier, type, network_space, datacenter, vlan_id, IPs, hardware ,vs.

-d, --datacenter
:   Filter by datacenter shortname.

--identifier
:   Filter by network identifier.

-t, --subnet-type
:   Filter by subnet type.

--network-space
:   Filter by network space.

--v4, --ipv4
:   Display only IPv4 subnets.

--v6, --ipv6
:   Display only IPv6 subnets.

--order
:   Filter by the ID of order that purchased the subnets.

**Examples**:
```bash
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
{: codeblock}

This command lists IPv4 subnets on the current account, and filters by datacenter `dal09`, subnet type `PRIMARY`, and network space `PUBLIC`.

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

Find an IP address and display its subnet and device information:
```bash
ibmcloud sl subnet lookup IP_ADDRESS [OPTIONS]
```

**Examples**:
```bash
ibmcloud sl subnet lookup 9.125.235.255
```
{: codeblock}

This command finds the IP address record with IP address `9.125.235.255` and displays its subnet and device information.

