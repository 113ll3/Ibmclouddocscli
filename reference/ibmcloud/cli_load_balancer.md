---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-14"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Working with the Load Balancer service
{: #sl-load-balancer-service}

The {{site.data.keyword.cloud}} Load Balancer service helps improve availability of your business-critical applications by distributing traffic among multiple application server instances, and by forwarding traffic to healthy instances only.

Use the following commands to manage load balancers in the {{site.data.keyword.cloud_notm}} classic infrastructure Load Balancer service.
{: shortdesc}

## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

Cancel an existing load balancer.
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

Adds a load balancer given the id returned from create-options.
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

Get price options to create a load balancer with.
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

Get Load balancer details.
```
ibmcloud sl loadbal detail LOADBAL_ID
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

Adds a new load_balancer service.
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Required. The allocated percent of connections .</dd>
<dt>-p, --port</dt>
<dd>Required. The port number .</dd>
<dt>-t, --routing-type</dt>
<dd>Required. The ID of routing type . Run 'ibmcloud sl loadbal routing-types' to find an ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Required. The ID of routing method . Run 'ibmcloud sl loadbal routing-methods' to find an ID.</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

Deletes an existing load balancer service group.
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

Edit an existing load balancer service group.
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>Change the allocated percent of connections.</dd>
<dt>-p, --port</dt>
<dd>Change the port number.</dd>
<dt>-t, --routing-type</dt>
<dd>Change the ID of routing type. Run 'ibmcloud sl loadbal routing-types' to find an ID.</dd>
<dt>-m, --routing-method</dt>
<dd>Change the ID of routing method. Run 'ibmcloud sl loadbal routing-methods' to find an ID.</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

Reset connections on a certain service group.
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

List health check types.
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

List active load balancers.
```
ibmcloud sl loadbal list
```

<strong>Command options</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Filter by datacenter shortname.</dd>
<dt>-o, --order</dt>
<dd>Filter by ID of the order that purchased the load balancer.</dd>
<dt>-p, --ip-address</dt>
<dd>Filter by IP address.</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

List routing methods.
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

List routing types.
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

Adds a new load balancer service.
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--disabled</dt>
<dd>Optional. Create the service as disabled,default is enabled if not specified .</dd>
<dt>-p, --port</dt>
<dd>Required. The port number for the service .</dd>
<dt>-w, --weight</dt>
<dd>Required. The weight of the service .</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Required. The health check type .</dd>
<dt>-i, --ip-address</dt>
<dd>Required. The IP address of the service .</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

Deletes an existing load balancer service.
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

Edit the properties of a service group.
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--disabled</dt>
<dd>Disable the service.</dd>
<dt>--enabled</dt>
<dd>Enable the service.</dd>
<dt>-p, --port</dt>
<dd>Change the port number for the service.</dd>
<dt>-w, --weight</dt>
<dd>Change the weight of the service.</dd>
<dt>-t, --healthcheck-type</dt>
<dd>Change the health check type.</dd>
<dt>-i, --ip-address</dt>
<dd>Change the IP address of the service.</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

Toggle the status of an existing load balancer service.
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>Command options</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Force operation without confirmation.</dd>
</dl>
