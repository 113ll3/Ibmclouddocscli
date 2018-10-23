---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 負載平衡器

{{site.data.keyword.Bluemix}} Load Balancer 服務有助於改善企業關鍵應用程式的可用性，因為它會將資料流量分散在多個應用程式伺服器實例，以及只將資料流量轉遞到性能健全的實例。

請使用下列指令在 {{site.data.keyword.Bluemix_notm}} 基礎架構 Load Balancer 服務中管理負載平衡器。
{: shortdesc}

<table summary="按字母順序排序的 {{site.data.keyword.Bluemix_notm}} 負載平衡器指令，其鏈結提供指令的相關資訊">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types
](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

 ## ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

取消現有負載平衡器。
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl loadbal create
{: #sl_loadbal_create}

提供從 create-options 傳回的 ID，以新增負載平衡器。
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

取得用來建立負載平衡器的價格選項。
```
ibmcloud sl loadbal create-options
```

## ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

取得負載平衡器詳細資料。
```
ibmcloud sl loadbal detail LOADBAL_ID
```

## ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

新增 load_balancer 服務。
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-a, --allocation</dt>
<dd>必要。已配置的連線百分比。</dd>
<dt>-p, --port</dt>
<dd>必要。埠號。</dd>
<dt>-t, --routing-type</dt>
<dd>必要。遞送類型的 ID。請執行 'ibmcloud sl loadbal routing-types' 以尋找 ID。</dd>
<dt>-m, --routing-method</dt>
<dd>必要。遞送方法的 ID。請執行 'ibmcloud sl loadbal routing-methods' 以尋找 ID。</dd>
</dl>

## ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

刪除現有負載平衡器服務群組。
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

編輯現有負載平衡器服務群組。
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-a, --allocation</dt>
<dd>變更已配置的連線百分比。</dd>
<dt>-p, --port</dt>
<dd>變更埠號。</dd>
<dt>-t, --routing-type</dt>
<dd>變更遞送類型的 ID。請執行 'ibmcloud sl loadbal routing-types' 以尋找 ID。</dd>
<dt>-m, --routing-method</dt>
<dd>變更遞送方法的 ID。請執行 'ibmcloud sl loadbal routing-methods' 以尋找 ID。</dd>
</dl>

## ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

重設特定服務群組上的連線。
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

## ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

列出性能檢查類型。
```
ibmcloud sl loadbal health-checks
```

## ibmcloud sl loadbal list
{: #sl_loadbal_list}

列出作用中的負載平衡器。
```
ibmcloud sl loadbal list
```

<strong>指令選項</strong>：
<dl>
<dt>-d, --datacenter</dt>
<dd>依資料中心簡稱過濾。</dd>
<dt>-o, --order</dt>
<dd>依購買負載平衡器的訂單 ID 過濾。</dd>
<dt>-p, --ip-address</dt>
<dd>依 IP 位址過濾。</dd>
</dl>

## ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

列出遞送方法。
```
ibmcloud sl loadbal routing-methods
```

## ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

列出遞送類型。
```
ibmcloud sl loadbal routing-types
```

## ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

新增負載平衡器服務。
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--disabled</dt>
<dd>選用。將服務建立為 disabled，如果未指定，則預設為 enabled。</dd>
<dt>-p, --port</dt>
<dd>必要。服務的埠號。</dd>
<dt>-w, --weight</dt>
<dd>必要。服務的加權。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>必要。性能檢查類型。</dd>
<dt>-i, --ip-address</dt>
<dd>必要。服務的 IP 位址。</dd>
</dl>

## ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

刪除現有負載平衡器服務。
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

編輯服務群組的內容。
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--disabled</dt>
<dd>停用服務。</dd>
<dt>--enabled</dt>
<dd>啟用服務。</dd>
<dt>-p, --port</dt>
<dd>變更服務的埠號。</dd>
<dt>-w, --weight</dt>
<dd>變更服務的加權。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>變更性能檢查類型。</dd>
<dt>-i, --ip-address</dt>
<dd>變更服務的 IP 位址。</dd>
</dl>

## ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

切換現有負載平衡器服務的狀態。
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>
