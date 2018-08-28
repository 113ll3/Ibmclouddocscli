---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理 {{site.data.keyword.Bluemix_notm}} 基础架构子网

<table summary="按字母顺序排序的常规 {{site.data.keyword.Bluemix_notm}} 基础架构命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} 基础架构子网命令</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} 基础架构子网命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl subnet cancel](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_cancel)</td>
 <td>[ibmcloud sl subnet create](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_create)</td>
 <td>[ibmcloud sl subnet detail](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_detail)</td>
 <td>[ibmcloud sl subnet list](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_list)</td>
 <td>[ibmcloud sl subnet lookup](/docs/cli/reference/ibmcloud/cli_subnet.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

取消子网。
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl subnet cancel 12345678 -f
```
此命令取消标识为 12345678 的子网，而不要求确认。



## ibmcloud sl subnet create
{: #sl_subnet_create}

向帐户添加新的子网。
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--v6, --ipv6</dt>
<dd>订购 IPv6 地址。</dd>
<dt>--test</dt>
<dd>不订购子网；只获取报价。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl subnet create public 16 567
```
此命令创建具有 16 个 IP v4 地址的公共子网，并会将其放在标识为 567 的 VLAN 上。




## ibmcloud sl subnet detail
{: #sl_subnet_detail}

获取子网的详细信息。
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
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
ibmcloud sl subnet detail 12345678
```
此命令显示有关标识为 12345678 的子网的详细信息，包括虚拟服务器和硬件服务器信息。




## ibmcloud sl subnet list
{: #sl_subnet_list}

列出帐户的所有子网。
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要按其排序的列。选项为：id、identifier、type、network_space、datacenter、vlan_id、IP、hardware 和 vs。</dd>
<dt>-d, --datacenter</dt>
<dd>按数据中心短名称过滤。</dd>
<dt>--identifier</dt>
<dd>按网络标识过滤。</dd>
<dt>-t, --subnet-type</dt>
<dd>按子网类型过滤。</dd>
<dt>--network-space</dt>
<dd>按网络空间过滤。</dd>
<dt>--v4, --ipv4</dt>
<dd>仅显示 IPv4 子网。</dd>
<dt>--v6, --ipv6</dt>
<dd>仅显示 IPv6 子网。</dd>
<dt>--order</dt>
<dd>按购买子网的订单的标识过滤。</dd>
</dl>

**示例**：
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
此命令列出当前帐户的 IP V4 子网，依据以下条件进行过滤：数据中心为 dal09，子网类型为 PRIMARY，网络空间为 PUBLIC。





## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

查找 IP 地址并显示其子网和设备信息。
```
ibmcloud sl subnet lookup IP_ADDRESS
```


**示例**：
```
ibmcloud sl subnet lookup 9.125.235.255
```
此命令查找地址为 9.125.235.255 的 IP 地址记录，并显示其子网和设备信息。
