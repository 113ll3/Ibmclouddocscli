---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, classic infrastructure, ibmcloud sl globalip, globalip, global ip addresses, assign global ip

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing global IPs (ibmcloud sl globalip)
{: #sl-manage-global-ip}

A global IP address is a specialized static secondary subnet. It is delivered to you as a `/32` subnet (in other words, a single IP address) that can be routed to any other IP address on your account.

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage a global IP in the {{site.data.keyword.cloud_notm}} classic infrastructure Global IP service.
{: shortdesc}

## ibmcloud sl globalip assign
{: #sl_globalip_assign}

Assign a global IP to a target router or device:
```bash
ibmcloud sl globalip assign IDENTIFIER TARGET [OPTIONS]
```

**Examples**:
```bash
ibmcloud sl globalip assign 12345678 9.111.123.456
```
{: codeblock}

This command assigns IP address with ID `12345678` to a target device whose IP address is `9.111.123.456`.

## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Cancel a global IP:
```bash
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl globalip cancel 12345678
```
{: codeblock}

This command cancels IP address with ID `12345678`.

## ibmcloud sl globalip create
{: #sl_globalip_create}

Create a global IP:
```bash
ibmcloud sl globalip create [OPTIONS]
```

**Command options**:

--v6
:   Order an IPv6 IP address.

--test
:   Test order.

-f, --force
:   Force operation without confirmation.

**Examples**:
```bash
ibmcloud sl globalip create --v6
```
{: codeblock}

This command creates an IPv6 address.

## ibmcloud sl globalip list
{: #sl_globalip_list}

List all global IPs on your account:
```bash
ibmcloud sl globalip list [OPTIONS]
```

**Command options**:

--v4
:   Display IPv4 IPs only.

--v6
:   Display IPv6 IPs only.

--order
:   Filter by the ID of order that purchased this IP address.

**Examples**:
```bash
ibmcloud sl globalip list --v4
```
{: codeblock}

This command lists all IPv4 addresses on the current account.

## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Unassign a global IP from a target router or device:
```bash
ibmcloud sl globalip unassign IDENTIFIER [OPTIONS]
```

**Examples**:
```bash
ibmcloud sl globalip unassign 12345678
```
{: codeblock}

This command unassigns IP address with ID `12345678` from the target device.

