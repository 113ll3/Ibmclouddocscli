---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, classic infrastructure, load balancer service, ibmcloud sl loadbal, sl loadbal, load balancer cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 使用 Load Balancer 服务
{: #sl-load-balancer-service}

{{site.data.keyword.cloud}} Load Balancer 服务通过在多个应用程序服务器实例之间分配流量，以及仅将流量转发到运行正常的实例，从而帮助提高业务关键型应用程序的可用性。

使用以下命令可在 {{site.data.keyword.cloud_notm}} 经典基础架构 Load Balancer 服务中管理负载均衡器。
{: shortdesc}

## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

取消现有负载均衡器。
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

根据从 create-options 返回的标识添加负载均衡器。
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

获取用于创建负载均衡器的价格选项。
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

获取负载均衡器详细信息。
```
ibmcloud sl loadbal detail LOADBAL_ID
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

添加新的负载均衡器服务。
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-a, --allocation</dt>
<dd>必需。已分配的连接百分比。</dd>
<dt>-p, --port</dt>
<dd>必需。端口号。</dd>
<dt>-t, --routing-type</dt>
<dd>必需。路由类型的标识。运行 `ibmcloud sl loadbal routing-types` 可查找标识。</dd>
<dt>-m, --routing-method</dt>
<dd>必需。路由方法的标识。运行 `ibmcloud sl loadbal routing-methods` 可查找标识。</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

删除现有的负载均衡器服务组。
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

编辑现有的负载均衡器服务组。
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-a, --allocation</dt>
<dd>更改已分配的连接百分比。</dd>
<dt>-p, --port</dt>
<dd>更改端口号。</dd>
<dt>-t, --routing-type</dt>
<dd>更改路由类型的标识。运行 `ibmcloud sl loadbal routing-types` 可查找标识。</dd>
<dt>-m, --routing-method</dt>
<dd>更改路由方法的标识。运行 `ibmcloud sl loadbal routing-methods` 可查找标识。</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

重置特定服务组上的连接。
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

列出运行状况检查类型。
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

列出活动的负载均衡器。
```
ibmcloud sl loadbal list
```

<strong>命令选项</strong>：
<dl>
<dt>-d, --datacenter</dt>
<dd>按数据中心短名称过滤。</dd>
<dt>-o, --order</dt>
<dd>按购买了负载均衡器的订单的标识过滤。</dd>
<dt>-p, --ip-address</dt>
<dd>按 IP 地址过滤。</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

列出路由方法。
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

列出路由类型。
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

添加新的负载均衡器服务。
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--disabled</dt>
<dd>可选。创建服务但禁用此服务，如果未指定，缺省值为已启用。</dd>
<dt>-p, --port</dt>
<dd>必需。服务的端口号。</dd>
<dt>-w, --weight</dt>
<dd>必需。服务的权重。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>必需。运行状况检查类型。</dd>
<dt>-i, --ip-address</dt>
<dd>必需。服务的 IP 地址。</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

删除现有的负载均衡器服务。
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

编辑服务组的属性。
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--disabled</dt>
<dd>禁用服务。</dd>
<dt>--enabled</dt>
<dd>启用服务。</dd>
<dt>-p, --port</dt>
<dd>更改服务的端口号。</dd>
<dt>-w, --weight</dt>
<dd>更改服务的权重。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>更改运行状况检查类型。</dd>
<dt>-i, --ip-address</dt>
<dd>更改服务的 IP 地址。</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

切换现有负载均衡器服务的状态。
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>
