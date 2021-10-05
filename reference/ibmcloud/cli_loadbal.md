---

copyright:
  years: 2020, 2021
lastupdated: "2021-10-05"

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
 
### Examples
{: #examples-}
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

### Command options 
{: #options-sl_loadbal_order}

-n,  --name NAME (required)
:   Name for this load balancer.

-d, --datacenter NAME (required)
:   Data center name. It can be found from the keyName in the command `ibmcloud sl order package-locations LBAAS` output.

-t, --type TYPE (required)
:   Load balancer type. Accepted values are PublicToPrivate, PrivateToPrivate, PublicToPublic.

-s, --subnet ID
:   Private subnet ID to order the load balancer. See `ibmcloud sl loadbal order-options`. Only PublicToPrivate and PrivateToPrivate load balancer types are accepted.

-l, --label LABEL
:   A descriptive label for this load balancer.

--frontend-protocol PROTOCOL
:   Frontend protocol. Default: HTTP

--frontend-port PORT
:   Frontend port. Default: 80

-m, --method METHOD
:   Balancing method. Accepted values are ROUNDROBIN | LEASTCONNECTION | WEIGHTED_RR. Default: ROUNDROBIN

-c, --connections COUNT
:   Maximum number of connections.

--sticky METHOD<
:   Sticky session method: cookie or source-ip.

--use-public-subnet
:   If this option is specified, the public IP is allocated from a public subnet in this account. Otherwise, it is allocated from the IBM system pool. Only available in PublicToPrivate load balancer type.

--verify
:   Verify an order, but do not create it.

-f, --force
:   Force operation without confirmation.
 
### Examples
{: #examples-sl_loadbal_order}
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

### Command options 
{: #options-sl_loadbal_order-options}

-d, --datacenter NAME
:   Show only the selected data center. Use shortname (dal13) format.
 
### Examples
{: #examples-sl_loadbal_order-options}
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

### Command options 
{: #options-sl_loadbal_protocol-add}

--id ID (required)
:   ID for the load balancer.

--front-protocol TYPE
:   Protocol type to use for incoming connections: [HTTP|HTTPS|TCP]. Default: HTTP

--back-protocol TYPE
:   Protocol type to use when connecting to backend servers: [HTTP|HTTPS|TCP]. Defaults to whatever --front-protocol is.

--front-port PORT
:   Internet side port. Default: 80

--back-port PORT
:   Private side port. Default: 80

-m, --method METHOD
:   Balancing method: [ROUNDROBIN|LEASTCONNECTION|WEIGHTED_RR]. Default: ROUNDROBIN

-c, --connections COUNT
:   Maximum number of connections to allow.

--sticky METHOD
:   Use `cookie` or `source-ip` to stick.
 
### Examples
{: #examples-sl_loadbal_protocol-add}
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

### Command options 
{: #options-sl_loadbal_protocol-delete}

--lb-id ID (required)
:   ID for the load balancer.

--protocol-uuid UUID (required)
:   UUID of the protocol.
 
### Examples
{: #examples-sl_loadbal_protocol-delete}
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

### Command options 
{: #options-sl_loadbal_member-add}

--id ID (required)
:   ID for the load balancer.

--ip (required)
:   Private IP of the new member.
 
### Examples
{: #examples-sl_loadbal_member-add}
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

### Command options 
{: #options-sl_loadbal_member-delete}

--lb-id ID (required)<
:   ID for the load balancer.

-m MEMBER_UUID, --member-uuid MEMBER_UUID (required)
:   Member UUID.
 
### Examples
{: #examples-sl_loadbal_member-delete}
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

### Command options 
{: #options-sl_loadbal_cancel}

--id ID (required)
:   ID for the load balancer.

-f, --force<
:   Force operation without confirmation.
 
### Examples
{: #examples-sl_loadbal_cancel}
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

### Command options 
{: #options-sl_loadbal_detail}

--id ID (required)
:   ID for the load balancer.
 
### Examples
{: #examples-sl_loadbal_detail}
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

### Command options 
{: #options-sl_loadbal_health-edit}

--lb-id ID (required)
:   ID of the load balancer.

--health-uuid UUID (required)
:   Health check UUID.

-i, --interval INTERVAL
:   Seconds between checks [2-60].

-r,--retry COUNT
:   Number of times before marking as DOWN [1-10].

-t, --timeout TIMEOUT
:   Seconds to wait for a connection [1-59].

-u, --url URL
:   URL path for HTTP/HTTPS checks.
 
### Examples
{: #examples-sl_loadbal_health-edit}
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

### Command options 
{: #options-sl_loadbal_l7member-add}

--port-uuid UUID (required)
:   UUID for the load balancer pool.

--address IP_ADDRESS (required)
:   Backend servers IP address.

--port PORT (required)
:   Backend servers port.
 
### Examples
{: #examples-sl_loadbal_l7member-add}
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

### Command options 
{: #options-sl_loadbal_l7member-delete}

--pool-uuid UUID (required)
:   UUID for the load balancer pool.

--member-uuid UUID (required)
:   UUID for the load balancer member.
 
### Examples
{: #examples-sl_loadbal_l7member-delete}
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

### Command options 
{: #options-sl_loadbal_l7polocies}

--protocol-id ID (required)
:   ID for the load balancer protocol.
 
### Examples
{: #examples-sl_loadbal_l7polocies}
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

### Command options 
{: #options-sl_loadbal_l7policy-add}

--protocol-uuid UUID (required)
:   UUID for the load balancer protocol.

-n, --name NAME
:   Policy name.

-a, --action TYPE
:   Policy action: REJECT | REDIRECT_POOL | REDIRECT_URL.

-r, --redirect INPUT
:   URL or POOL_UUID. It's only available in REDIRECT_POOL | REDIRECT_URL action.

-p --priority PRIORITY
:   Policy priority.
 
### Examples
{: #examples-sl_loadbal_l7policy-add}
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

### Command options 
{: #options-sl_loadbal_l7policy-delete}

--policy-id ID (required)
:   ID for the load balancer policy.

-f, --force
:   Force operation without confirmation.
 
### Examples
{: #examples-sl_loadbal_l7policy-delete}
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

### Command options 
{: #options-sl_loadbal_l7pool-add}

--id ID (required)
:   ID for the load balancer.

-n, --name NAME (required)
:   Name for this L7 pool.

-m, --method
:   Balancing method: [ROUNDROBIN|LEASTCONNECTION|WEIGHTED_RR]. [default: ROUNDROBIN]

-p, --protocol PROTOCOL
:   Protocol type to use for incoming connections. [default: HTTP]

-s, --server SERVER
:   Backend servers that are part of this pool. Format: BACKEND_IP:PORT. For example, 10.0.0.1:80 (multiple occurrences permitted).

--health-path PATH
:   Health check path. [default: /]

--health-internal INTERVAL
:   Health check interval between checks. [default: 5]

--health-retry COUNT
:   Health check number of times before marking as DOWN. [default: 2]

--health-time TIMEOUT
:   Health check timeout. [default: 2]

--sticky METHOD
:   Use `cookie` or `source-ip` to stick.
 
### Examples
{: #examples-sl_loadbal_l7pool-add}
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

### Command options 
{: #options-sl_loadbal_l7pool-delete}

--pool-id ID (required)
:   ID for the load balancer pool.
 
### Examples
{: #examples-sl_loadbal_l7pool-delete}
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

### Command options 
{: #options-sl_loadbal_l7pool-detail}

--pool-id ID (required)
:   ID for the load balancer pool.
 
### Examples
{: #examples-sl_loadbal_l7pool-detail}
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

### Command options 
{: #options-sl_loadbal_l7pool-edit}

--pool-uuid UUID
:   UUID for the load balancer pool.

-m, --method
:   Balancing method: [ROUNDROBIN|LEASTCONNECTION|WEIGHTED_RR]. [default: ROUNDROBIN]

-p, --protocol PROTOCOL
:   Protocol type to use for incoming connections. [default: HTTP]

-s, --server SERVER
:   Backend servers that are part of this pool. Format: BACKEND_IP:PORT. For example, 10.0.0.1:80 (multiple occurrences permitted).

--health-path PATH
:   Health check path. [default: /]

--health-internal INTERVAL
:   Health check interval between checks. [default: 5]

--health-retry COUNT
:   Health check number of times before marking as DOWN. [default: 2]

--health-time TIMEOUT
:   Health check timeout. [default: 2]

--sticky METHOD
:   Use `cookie` or `source-ip` to stick.
 
### Examples
{: #examples-sl_loadbal_l7pool-edit}
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

### Command options 
{: #options-sl_loadbal_l7rule-add}

--policy-uuid UUID (required)
:   UUID for the load balancer policy.

-t, --type TYPE (required)
:   Rule type: HOST_NAME | FILE_TYPE | HEADER | COOKIE | PATH

-c, --compare-type COMPARE_TYPE (required)
:   Compare type: EQUAL_TO | ENDS_WITH | STARTS_WITH | REGEX | CONTAINS

-v, --value COMPARE_VALUE (required)
:   Compared value.

-k, --key KEY
:   Key name. Available only in HEADER or COOKIE type.

--invert VALUE
:   Invert rule: 0 | 1

## ibmcloud sl loadbal l7rule-delete
{: #sl_loadbal_l7rule-delete}

Delete a L7 rule:
```
ibmcloud sl loadbal l7rule-delete (--policy-uuid L7POLICY_UUID) (--rule-uuid L7RULE_UUID) [-f, --force]
```

### Command options 
{: #options-sl_loadbal_l7rule-delete}

--policy-uuid UUID (required)
:   UUID for the load balancer policy.

--rule-uuid UUID (required)
:   UUID for the load balancer rule.

-f, --force
:   Force operation without confirmation.
 
### Examples
{: #examples-sl_loadbal_l7rule-delete}
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

### Command options 
{: #options-sl_loadbal_l7rules}

--policy-id ID (required)
:   ID for the load balancer policy.
 
### Examples
{: #examples-sl_loadbal_l7rules}
```
ibmcloud sl loadbal l7rules --policy-id 27204f2c-1853-4fd2-9c97-1654cd536edd
```
{: codeblock}
