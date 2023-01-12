---

copyright:
  years: 2018, 2020
lastupdated: "2021-12-15"

keywords: cli, manage security groups, ingress, egress, traffic, virtual server cli, classic infrastructure cli, securitygroup, ibmcloud sl securitygroup, security group cli

subcollection: cli

---

{{site.data.keyword.attribute-definition-list}}

# Managing security groups for virtual server traffic (ibmcloud sl securitygroup)
{: #sl-manage-securitygroups}

A security group is a set of IP filter rules that define how to handle incoming (ingress) and outgoing (egress) traffic from the public and private interfaces of a virtual server instance. The rules that you add to a security group are known as security group rules.
{: shortdesc}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage a security group by using the {{site.data.keyword.cloud_notm}} classic infrastructure Security Group service.

## ibmcloud sl securitygroup create
{: #sl_securitygroup_create}

Create a security group:
```bash
ibmcloud sl securitygroup create [OPTIONS]
```

**Command options**:

-n, --name
:   The name of the security group.

-d, --description
:   The description of the security group.

## ibmcloud sl securitygroup delete
{: #sl_securitygroup_delete}

Delete the security group:
```bash
ibmcloud sl securitygroup delete SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.

## ibmcloud sl securitygroup detail
{: #sl_securitygroup_detail}

Get details about a security group:
```bash
ibmcloud sl securitygroup detail SECURITYGROUP_ID [OPTIONS]
```

## ibmcloud sl securitygroup edit
{: #sl_securitygroup_edit}

Edit details of a security group:
```bash
ibmcloud sl securitygroup edit SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

-n, --name
:   The name of the security group.

-d, --description
:   The description of the security group.

## ibmcloud sl securitygroup interface-add
{: #sl_securitygroup_interface_add}

Attach an interface to a security group:
```bash
ibmcloud sl securitygroup interface-add SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

-n, --network-component
:   The network component ID to associate with the security group.

-s, --server
:   The server ID to associate with the security group.

-i, --interface
:   The interface of the server to associate (public or private).

## ibmcloud sl securitygroup interface-list
{: #sl_securitygroup_interface_list}

List interfaces associated with security group:
```bash
ibmcloud sl securitygroup interface-list SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

--sortby
:   Column to sort by. Options are: id,virtualServerId,hostname.

## ibmcloud sl securitygroup interface-remove
{: #sl_securitygroup_interface_remove}

Detach an interface from a security group:
```bash
ibmcloud sl securitygroup interface-remove SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

-n, --network-component
:   The network component to remove from the security group.

-s, --server
:   The server ID to remove from the security group.

-i, --interface
:   The interface of the server to remove (public or private).

## ibmcloud sl securitygroup list
{: #sl_securitygroup_list}

List security groups:
```bash
ibmcloud sl securitygroup list [OPTIONS]
```

**Command options**:

--sortby
:   Column to sort by. Options are: id,name,description,created.

## ibmcloud sl securitygroup rule-add
{: #sl_securitygroup_rule_add}

Add a security group rule to a security group:
```bash
ibmcloud sl securitygroup rule-add SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

-r, --remote-ip
:   The remote IP/CIDR to enforce.

-s, --remote-group
:   The ID of the remote security group to enforce.

-d, --direction
:   The direction of traffic to enforce (ingress or egress), required.

-e, --ether-type
:   The ethertype (IPv4 or IPv6) to enforce, default is IPv4 if not specified.

-M, --port-max
:   The upper port bound to enforce.

-m, --port-min
:   The lower port bound to enforce.

-p, --protocol
:   The protocol (icmp, tcp, udp) to enforce.

## ibmcloud sl securitygroup rule-edit
{: #sl_securitygroup_rule_edit}

Edit a security group rule in a security group:
```bash
ibmcloud sl securitygroup rule-edit SECURITYGROUP_ID RULE_ID [OPTIONS]
```

**Command options**:

-r, --remote-ip
:   The remote IP/CIDR to enforce.

-s, --remote-group
:   The ID of the remote security group to enforce.

-d, --direction
:   The direction of traffic to enforce (ingress or egress), required.

-e, --ether-type
:   The ethertype (IPv4 or IPv6) to enforce, default is IPv4 if not specified.

-M, --port-max
:   The upper port bound to enforce.

-m, --port-min
:   The lower port bound to enforce.

-p, --protocol
:   The protocol (icmp, tcp, or udp) to enforce.

## ibmcloud sl securitygroup rule-list
{: #sl_securitygroup_rule_list}

List security group rules:
```bash
ibmcloud sl securitygroup rule-list SECURITYGROUP_ID [OPTIONS]
```

**Command options**:

--sortby
:   Column to sort by. Options are: id,remoteIp,remoteGroupId,direction,ethertype,portRangeMin,portRangeMax,protocol.

## ibmcloud sl securitygroup rule-remove
{: #sl_securitygroup_rule_remove}

Remove a rule from a security group:
```bash
ibmcloud sl securitygroup rule-remove SECURITYGROUP_ID RULE_ID [OPTIONS]
```

**Command options**:

-f, --force
:   Force operation without confirmation.
