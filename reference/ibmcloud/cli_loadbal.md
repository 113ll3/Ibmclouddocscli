---

copyright:
  years: 2020
lastupdated: "2020-08-20"

keywords: cli, classic infrastructure, load balancer, loadbal

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}
{:codeblock: .codeblock}
{:external: target="_blank" .external}

# Managing load balancers (ibmcloud sl loadbal)
{: #sl-manage-loadbal}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage {{site.data.keyword.cloud_notm}} classical infrastructure load balancers.
{: shortdesc}

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

List active load balancers:
```
ibmcloud sl loadbal list
```

**Examples**:
```
ibmcloud sl loadbal list
```
{: codeblock}

## ibmcloud sl loadbal order
{: #sl_loadbal_order}

Order a load balancer:
```
ibmcloud sl loadbal order (-n, --name NAME) (-d, --datacenter DATACENTER) (-t, --type PublicToPrivate | PrivateToPrivate | PublicToPublic ) [-l, --label LABEL] [ -s, --subnet SUBNET_ID] [--frontend-protocol PROTOCOL] [--frontend-port PORT] [--backend-protocol PROTOCOL] [--backend-port PORT] [-m, --method METHOD] [-c, --connections CONNECTIONS] [--sticky cookie | source-ip] [--use-public-subnet] [--verify]
```

<strong>Command options</strong>:
<dl>
    <dt>-n,  --name NAME (required)</dt>
    <dd>Name for this load balancer.</dd>
    <dt>-d, --datacenter NAME (required)</dt>
    <dd>Data center name. It can be found from the keyName in the command `ibmcloud sl order package-locations LBAAS` output.</dd>
    <dt>-t, --type TYPE (required)</dt>
    <dd>Load balancer type. Accepted values are PublicToPrivate, PrivateToPrivate, PublicToPublic.</dd>
    <dt>-s, --subnet ID</dt>
    <dd>Private subnet ID to order the load balancer. See `ibmcloud sl loadbal order-options`. Only PublicToPrivate and PrivateToPrivate load balancer types are accepted.</dd>
    <dt>-l, --label LABEL</dt>
    <dd>A descriptive label for this load balancer.</dd>
    <dt>--frontend-protocol PROTOCOL</dt>
    <dd>Frontend protocol. Default: HTTP</dd>
    <dt>--frontend-port PORT</dt>
    <dd>Frontend port. Default: 80</dd>
    <dt>-m, --method METHOD</dt>
    <dd>Balancing method. Accepted values are ROUNDROBIN | LEASTCONNECTION | WEIGHTED_RR. Default: ROUNDROBIN</dd>
    <dt>-c, --connections COUNT</dt>
    <dd>Maximum number of connections.</dd>
    <dt>--sticky METHOD</dt>
    <dd>Sticky session method: cookie or source-ip.</dd>
    <dt>--use-public-subnet</dt>
    <dd>If this option is specified, the public IP is allocated from a public subnet in this account. Otherwise, it is allocated from the IBM system pool. Only available in PublicToPrivate load balancer type.</dd>
    <dt>--verify</dt>
    <dd>Verify an order, but do not create it.</dd>
    <dt>-f, --force</dt>
    <dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal order -n my-lb -d DALLAS10 -t PublicToPrivate -s 1234567 --frontend-protocol TCP --frontend-port 123 --backend-protocol TCP --backend-port 123 -m LEASTCONNECTION -c 100 --sticky cookie
```
{: codeblock}

## ibmcloud sl loadbal order-options
{: #sl_loadbal_order-options}

List options for order a load balancer:
```
ibmcloud sl loadbal order-options [-d, --datacenter DATACENTER]
```

<strong>Command options</strong>:
<dl>
  <dt>-d, --datacenter NAME</dt>
  <dd>Show only the selected data center. Use shortname (dal13) format.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal order-options
```
{: codeblock}

## ibmcloud sl loadbal protocol-add
{: #sl_loadbal_protocol-add}

Add a load balancer protocol:
```
ibmcloud sl loadbal protocol-add (--id LOADBAL_ID) [--front-protocol PROTOCOL] [back-protocol PROTOCOL] [--front-port PORT] [--back-port PORT] [-m, --method METHOD] [-c, --connections CONNECTIONS] [--sticky cookie | source-ip]
```

<strong>Command options</strong>:
<dl>
  <dt>--id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
  <dt>--front-protocol TYPE</dt>
  <dd>Protocol type to use for incoming connections: [HTTP|HTTPS|TCP]. Default: HTTP</dd>
  <dt>--back-protocol TYPE</dt>
  <dd>Protocol type to use when connecting to backend servers: [HTTP|HTTPS|TCP]. Defaults to whatever --front-protocol is.</dd>
  <dt>--front-port PORT</dt>
  <dd>Internet side port. Default: 80</dd>
  <dt>--back-port PORT</dt>
  <dd>Private side port. Default: 80</dd>
  <dt>-m, --method METHOD</dt>
  <dd>Balancing method: [ROUNDROBIN|LEASTCONNECTION|WEIGHTED_RR]. Default: ROUNDROBIN</dd>
  <dt>-c, --connections COUNT</dt>
  <dd>Maximum number of connections to allow.</dd>
  <dt>--sticky METHOD</dt>
  <dd>Use `cookie` or `source-ip` to stick.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal protocol-add --id 123456 -m ROUNDROBIN --sticky cookie
```
{: codeblock}

## ibmcloud sl loadbal protocol-delete
{: #sl_loadbal_protocol-delete}

Delete a protocol:
```
ibmcloud sl loadbal protocol-delete (--lb-id LOADBAL_ID) (--protocol-uuid PROTOCOL_UUID)
```

<strong>Command options</strong>:
<dl>
  <dt>--lb-id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
  <dt>--protocol-uuid UUID (required)</dt>
  <dd>UUID of the protocol.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal protocol-delete --lb-id 123 --protocol-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd
```
{: codeblock}

## ibmcloud sl loadbal member-add
{: #sl_loadbal_member-add}

Add a load balancer member:
```
ibmcloud sl loadbal member-add (--id LOADBAL_ID) (--ip PRIVATE_IP)
```

<strong>Command options</strong>:
<dl>
  <dt>--id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
  <dt>--ip (required)</dt>
  <dd>Private IP of the new member.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal member-add --id 939818 --ip 10.0.0.1
```
{: codeblock}

## ibmcloud sl loadbal member-delete
{: #sl_loadbal_member-delete}

Remove a load balancer member:
```
ibmcloud sl loadbal member-delete (--lb-id LOADBAL_ID) (-m, --member-uuid MEMBER_UUID)
```

<strong>Command options</strong>:
<dl>
  <dt>--lb-id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
  <dt>-m MEMBER_UUID, --member-uuid MEMBER_UUID (required)</dt>
  <dd>Member UUID.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal member-delete --lb-id 123456 --member-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd

```
{: codeblock}

## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Cancel an existing load balancer:
```
ibmcloud sl loadbal cancel (--id LOADBAL_ID) [-f, --force]
```

<strong>Command options</strong>:
<dl>
  <dt>--id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
  <dt>-f, --force</dt>
  <dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal cancel --id 123456 -f
```
{: codeblock}

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Get load balancer details:
```
ibmcloud sl loadbal detail (--id LOADBAL_ID)
```

<strong>Command options</strong>:
<dl>
  <dt>--id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal detail --id 123456
```
{: codeblock}

## ibmcloud sl loadbal health-edit
{: #sl_loadbal_health-edit}

Edit load balancer health check:
```
ibmcloud sl loadbal health-edit (--lb-id LOADBAL_ID)  (--health-uuid HEALTH_CHECK_UUID) [-i, --interval INTERVAL] [-r, --retry RETRY] [-t, --timeout TIMEOUT] [-u, --url URL]
```

<strong>Command options</strong>:
<dl>
  <dt>--lb-id ID (required)</dt>
  <dd>ID of the load balancer.</dd>
  <dt>--health-uuid UUID (required)</dt>
  <dd>Health check UUID.</dd>
  <dt>-i, --interval INTERVAL</dt>
  <dd>Seconds between checks [2-60].</dd>
  <dt>-r,--retry COUNT</dt>
  <dd>Number of times before marking as DOWN [1-10].</dd>
  <dt>-t, --timeout TIMEOUT</dt>
  <dd>Seconds to wait for a connection [1-59].</dd>
  <dt>-u, --url URL</dt>
  <dd>URL path for HTTP/HTTPS checks.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal health-edit --lb-id 123456  --health-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd -i 2
```
{: codeblock}

## ibmcloud sl loadbal l7member-add
{: #sl_loadbal_l7member-add}

Add a L7 pool member:
```
ibmcloud sl loadbal l7member-add (--pool-uuid L7POOL_UUID) (--address IP_ADDRESS) (--port PORT)
```

<strong>Command options</strong>:
<dl>
  <dt>--port-uuid UUID (required)</dt>
  <dd>UUID for the load balancer pool.</dd>
  <dt>--address IP_ADDRESS (required)</dt>
  <dd>Backend servers IP address.</dd>
  <dt>--port PORT (required)</dt>
  <dd>Backend servers port.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7member-add --pool-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd --address 10.0.0.1 --port 80
```
{: codeblock}

## ibmcloud sl loadbal l7member-delete
{: #sl_loadbal_l7member-delete}

Remove a load balancer member:
```
ibmcloud sl loadbal l7member-delete (--pool-uuid L7POOL_UUID) (--member-uuid L7MEMBER_UUID)
```

<strong>Command options</strong>:
<dl>
  <dt>--pool-uuid UUID (required)</dt>
  <dd>UUID for the load balancer pool.</dd>
  <dt>--member-uuid UUID (required)</dt>
  <dd>UUID for the load balancer member.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7member-delete --pool-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd --member-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd
```
{: codeblock}

## ibmcloud sl loadbal l7policies
{: #sl_loadbal_l7polocies}

List L7 policies:
```
ibmcloud sl loadbal l7policies (--protocol-id PROTOCOL_ID)
```

<strong>Command options</strong>:
<dl>
  <dt>--protocol-id ID (required)</dt>
  <dd>ID for the load balancer protocol.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7policies --protocol-id 123456
```
{: codeblock}

## ibmcloud sl loadbal l7policy-add
{: #sl_loadbal_l7policy-add}

Add a L7 policy:
```
ibmcloud sl loadbal l7policy-add (--protocol-uuid PROTOCOL_UUID) (-n, --name NAME) (-a,--action REJECT | REDIRECT_POOL | REDIRECT_URL) [-r,--redirect REDIRECT] [-p,--priority PRIORITY]
```

<strong>Command options</strong>:
<dl>
  <dt>--protocol-uuid UUID (required)</dt>
  <dd>UUID for the load balancer protocol.</dd>
  <dt>-n, --name NAME</dt>
  <dd>Policy name.</dd>
  <dt>-a, --action TYPE</dt>
  <dd>Policy action: REJECT | REDIRECT_POOL | REDIRECT_URL.</dd>
  <dt>-r, --redirect INPUT</dt>
  <dd>URL or POOL_UUID. It's only available in REDIRECT_POOL | REDIRECT_URL action.</dd>
  <dt>-p --priority PRIORITY</dt>
  <dd>Policy priority.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7policy-add --protocol-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd -n my-policy -a REJECT
```
{: codeblock}

## ibmcloud sl loadbal l7policy-delete
{: #sl_loadbal_l7policy-delete}

Delete a L7 pool:
```
ibmcloud sl loadbal l7policy-delete (--policy-id POLICY_ID) [-f, --force]
```

<strong>Command options</strong>:
<dl>
  <dt>--policy-id ID (required)</dt>
  <dd>ID for the load balancer policy.</dd>
  <dt>-f, --force</dt>
  <dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7policy-delete --policy-id 27204f2c-1853-4fd2-9c97-1654cd536edd -f
```
{: codeblock}

## ibmcloud sl loadbal l7pool-add
{: #sl_loadbal_l7pool-add}

Add a L7 pool:
```
ibmcloud sl loadbal l7pool-add (--id LOADBAL_ID) (-n, --name NAME) [-m, --method METHOD] [-s, --server BACKEND_IP:PORT] [-p, --protocol PROTOCOL] [--health-path PATH] [--health-interval INTERVAL] [--health-retry RETRY] [--health-timeout TIMEOUT] [--sticky cookie | source-ip]
```

<strong>Command options</strong>:
<dl>
  <dt>--id ID (required)</dt>
  <dd>ID for the load balancer.</dd>
  <dt>-n, --name NAME (required)</dt>
  <dd>Name for this L7 pool.</dd>
  <dt>-m, --method</dt>
  <dd>Balancing method: [ROUNDROBIN|LEASTCONNECTION|WEIGHTED_RR]. [default: ROUNDROBIN]</dd>
  <dt>-p, --protocol PROTOCOL</dt>
  <dd>Protocol type to use for incoming connections. [default: HTTP]</dd>
  <dt>-s, --server SERVER</dt>
  <dd>Backend servers that are part of this pool. Format: BACKEND_IP:PORT. For example, 10.0.0.1:80 (multiple occurrences permitted).</dd>
  <dt>--health-path PATH</dt>
  <dd>Health check path. [default: /]</dd>
  <dt>--health-internal INTERVAL</dt>
  <dd>Health check interval between checks. [default: 5]</dd>
  <dt>--health-retry COUNT</dt>
  <dd>Health check number of times before marking as DOWN. [default: 2]</dd>
  <dt>--health-time TIMEOUT</dt>
  <dd>Health check timeout. [default: 2]</dd>
  <dt>--sticky METHOD</dt>
  <dd>Use `cookie` or `source-ip` to stick.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7pool-add --id 123 -n my-pool -m ROUNDROBIN
```
{: codeblock}

## ibmcloud sl loadbal l7pool-delete
{: #sl_loadbal_l7pool-delete}

Delete a L7 pool:
```
ibmcloud sl loadbal l7pool-delete (--pool-id L7POOL_ID)
```

<strong>Command options</strong>:
<dl>
  <dt>--pool-id ID (required)</dt>
  <dd>ID for the load balancer pool.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7pool-delete --pool-id 123456
```
{: codeblock}

## ibmcloud sl loadbal l7pool-detail
{: #sl_loadbal_l7pool-detail}

Show L7 pool details:
```
ibmcloud sl loadbal l7pool-detail (--pool-id L7POOL_ID)
```

<strong>Command options</strong>:
<dl>
  <dt>--pool-id ID (required)</dt>
  <dd>ID for the load balancer pool.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7pool-detail --pool-id 123456
```
{: codeblock}

## ibmcloud sl loadbal l7pool-edit
{: #sl_loadbal_l7pool-edit}

Edit a L7 pool:
```
ibmcloud sl loadbal l7pool-edit (--pool-uuid L7POOL_UUID) [-m, --method METHOD] [-s, --server BACKEND_IP:PORT] [-p, --protocol PROTOCOL] [--health-path PATH] [--health-interval INTERVAL] [--health-retry RETRY] [--health-timeout TIMEOUT] [--sticky cookie | source-ip]
```

<strong>Command options</strong>:
<dl>
  <dt>--pool-uuid UUID</dt>
  <dd>UUID for the load balancer pool.</dd>
  <dt>-m, --method</dt>
  <dd>Balancing method: [ROUNDROBIN|LEASTCONNECTION|WEIGHTED_RR]. [default: ROUNDROBIN]</dd>
  <dt>-p, --protocol PROTOCOL</dt>
  <dd>Protocol type to use for incoming connections. [default: HTTP]</dd>
  <dt>-s, --server SERVER</dt>
  <dd>Backend servers that are part of this pool. Format: BACKEND_IP:PORT. For example, 10.0.0.1:80 (multiple occurrences permitted).</dd>
  <dt>--health-path PATH</dt>
  <dd>Health check path. [default: /]</dd>
  <dt>--health-internal INTERVAL</dt>
  <dd>Health check interval between checks. [default: 5]</dd>
  <dt>--health-retry COUNT</dt>
  <dd>Health check number of times before marking as DOWN. [default: 2]</dd>
  <dt>--health-time TIMEOUT</dt>
  <dd>Health check timeout. [default: 2]</dd>
  <dt>--sticky METHOD</dt>
  <dd>Use `cookie` or `source-ip` to stick.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7pool-edit --pool-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd -m ROUNDROBIN
```
{: codeblock}

## ibmcloud sl loadbal l7rule-add
{: #sl_loadbal_l7rule-add}

Add a L7 rule:
```
ibmcloud sl loadbal l7rule-add (--policy-uuid L7POLICY_UUID) (-t, --type HOST_NAME | FILE_TYPE | HEADER | COOKIE | PATH ) (-c, --compare-type EQUAL_TO | ENDS_WITH | STARTS_WITH | REGEX | CONTAINS) (-v,--value VALUE) [-k,--key KEY] [--invert 0 | 1]
```

<strong>Command options</strong>:
<dl>
  <dt>--policy-uuid UUID (required)</dt>
  <dd>UUID for the load balancer policy.</dd>
  <dt>-t, --type TYPE (required)</dt>
  <dd>Rule type: HOST_NAME | FILE_TYPE | HEADER | COOKIE | PATH</dd>
  <dt>-c, --compare-type COMPARE_TYPE (required)</dt>
  <dd>Compare type: EQUAL_TO | ENDS_WITH | STARTS_WITH | REGEX | CONTAINS</dd>
  <dt>-v, --value COMPARE_VALUE (required)</dt>
  <dd>Compared value.</dd>
  <dt>-k, --key KEY</dt>
  <dd>Key name. Available only in HEADER or COOKIE type.</dd>
  <dt>--invert VALUE</dt>
  <dd>Invert rule: 0 | 1</dd>
</dl>

## ibmcloud sl loadbal l7rule-delete
{: #sl_loadbal_l7rule-delete}

Delete a L7 rule:
```
ibmcloud sl loadbal l7rule-delete (--policy-uuid L7POLICY_UUID) (--rule-uuid L7RULE_UUID) [-f, --force]
```

<strong>Command options</strong>:
<dl>
  <dt>--policy-uuid UUID (required)</dt>
  <dd>UUID for the load balancer policy.</dd>
  <dt>--rule-uuid UUID (required)</dt>
  <dd>UUID for the load balancer rule.</dd>
  <dt>-f, --force</dt>
  <dd>Force operation without confirmation.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7rule-delete --policy-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd --rule-uuid 27204f2c-1853-4fd2-9c97-1654cd536edd -f

```
{: codeblock}

## ibmcloud sl loadbal l7rules
{: #sl_loadbal_l7rules}

List L7 rules:
```
ibmcloud sl loadbal l7rules (--policy-id Policy_ID)
```

<strong>Command options</strong>:
<dl>
  <dt>--policy-id ID (required)</dt>
  <dd>ID for the load balancer policy.</dd>
</dl>

**Examples**:
```
ibmcloud sl loadbal l7rules --policy-id 27204f2c-1853-4fd2-9c97-1654cd536edd
```
{: codeblock}
