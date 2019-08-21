---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic infrastructure cli, vlan cli, classic vlan cli, ibmcloud sl vlan, manage virtual network cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 管理经典基础架构 VLAN
{: #manage-classic-vlans}

{{site.data.keyword.cloud}} 使用虚拟局域网 (VLAN) 来隔离公用和专用网络上的广播流量。VLAN 可根据需要进行分配，以满足其他产品的要求。

使用以下命令可管理经典基础架构 VLAN。
{: shortdesc}

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
<dt>-n, --name</dt>
<dd>VLAN 的名称。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
{: codeblock}

此命令创建公用 VLAN，其位于具有 16 个 IP 地址的数据中心 `dal09`，名称为 `myvlan`。

## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

取消 VLAN：
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
{: codeblock}

此命令取消标识为 `12345678` 的 VLAN，而不要求确认。

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
{: codeblock}

此命令显示标识为 `12345678` 的 VLAN 的详细信息，但不列出虚拟服务器或硬件服务器。

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
{: codeblock}

此命令更新标识为 `12345678` 的 VLAN，并为其指定新名称 `myvlan-rename`。

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
此命令列出当前帐户的所有 VLAN，按数据中心 `dal09` 过滤，并按 VLAN 编号排序。

## ibmcloud sl vlan options
{: #sl_vlan_options}

列出用于创建 VLAN 的所有选项。
```
ibmcloud sl vlan options
```
{: codeblock}

**示例**：
```
ibmcloud sl vlan options
```
{: codeblock}

此命令列出用于创建 VLAN 的所有选项，例如 VLAN 类型、数据中心、子网大小、路由器等。

