---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# VLAN

使用以下命令可管理 {{site.data.keyword.Bluemix_notm}} 基础架构 VLAN。
{: shortdesc}

<table summary="按字母顺序排序的 {{site.data.keyword.Bluemix_notm}} 基础架构 VLAN 命令（命令带有可获取命令更多信息的链接）">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_detail)</td>
 <td>[ibmcloud sl vlan edit](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_edit)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl vlan create
{: #sl_vlan_create}

创建新的 VLAN。
```
ibmcloud sl vlan create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-t, --vlan-type</dt>
<dd>VLAN 的类型：public 或 private。</dd>
<dt>-r, --router</dt>
<dd>路由器的主机名。</dd>
<dt>-d, --datacenter</dt>
<dd>数据中心的短名称。</dd>
<dt>-s, --size</dt>
<dd>子网的大小，选项为：8（5 个可用 IP）、16（13 个可用 IP）或 32（29 个可用 IP）。</dd>
<dt>-n, --name</dt>
<dd>VLAN 的名称。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
此命令创建公共 VLAN，它位于具有 16 个 IP 地址的数据中心 dal09，名称为 myvlan。


## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

取消 VLAN。
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vlan cancel 12345678 -f
```
此命令取消标识为 12345678 的 VLAN，而不要求确认。





## ibmcloud sl vlan detail
{: #sl_vlan_detail}

获取有关 VLAN 的详细信息。
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--no-vs</dt>
<dd>隐藏虚拟服务器列表。</dd>
<dt>--no-hardware</dt>
<dd>隐藏硬件列表。</dd>
</dl>

**示例**：
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
此命令显示标识为 12345678 的 VLAN 的详细信息，但不列出虚拟服务器或硬件服务器。





## ibmcloud sl vlan edit
{: #sl_vlan_edit}

编辑有关 VLAN 的详细信息。
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --name</dt>
<dd>VLAN 的名称。</dd>
</dl>

**示例**：
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
此命令更新标识为 12345678 的 VLAN，并将其命名为新名称“myvlan-rename”。




## ibmcloud sl vlan list
{: #sl_vlan_list}

列出帐户的所有 VLAN。
```
ibmcloud sl vlan list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要按其排序的列，选项为：id、number、name、firewall、datacenter、hardware、virtual_servers 或 public_ips。</dd>
<dt>-d, --datacenter</dt>
<dd>按数据中心短名称过滤。</dd>
<dt>-n, --number</dt>
<dd>按 VLAN 编号过滤。</dd>
<dt>--name</dt>
<dd>按 VLAN 名称过滤。</dd>
<dt>--order</dt>
<dd>按购买了 VLAN 的订单的标识过滤。</dd>
</dl>

**示例**：
```
ibmcloud sl vlan list -d dal09 --sortby number
```
此命令列出当前帐户的所有 VLAN，依据其过滤的数据中心为 dal09，并按 VLAN 编号对其排序。






## ibmcloud sl vlan options
{: #sl_vlan_options}

列出用于创建 VLAN 的所有选项。
```
ibmcloud sl vlan options
```


**示例**：
```
ibmcloud sl vlan options
```
此命令列出用于创建 VLAN 的所有选项，例如 VLAN 类型、数据中心、子网大小、路由器等。
