---

copyright:

  years: 2018


lastupdated: "2018-09-06"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 全局 IP

使用以下命令可管理 {{site.data.keyword.Bluemix_notm}} 基础架构全局 IP 服务中的全局 IP。
{: shortdesc}

<table summary="按字母顺序排序的 {{site.data.keyword.Bluemix_notm}} 基础架构全局 IP 命令（命令带有可获取命令更多信息的链接）">
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/ibmcloud/cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl globalip assign
{: #sl_globalip_assign}

为目标路由器或设备分配全局 IP。
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**示例**：
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
此命令将标识为 12345678 的 IP 地址分配给 IP 地址为 9.111.123.456 的目标设备。




## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

取消全局 IP。
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl globalip cancel 12345678
```
此命令取消标识为 12345678 的 IP 地址。



 ## ibmcloud sl globalip create
{: #sl_globalip_create}

创建全局 IP。
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--v6</dt>
<dd>订购 IPv6 IP 地址。</dd>
<dt>--test</dt>
<dd>测试订单。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl globalip create --v6
```
此命令创建 IP V6 地址。



## ibmcloud sl globalip list
{: #sl_globalip_list}

列出帐户的所有全局 IP。
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--v4</dt>
<dd>仅显示 IPv4。</dd>
<dt>--v6</dt>
<dd>仅显示 IPv6。</dd>
<dt>--order</dt>
<dd>按购买此 IP 地址的订单的标识过滤。</dd>
</dl>

**示例**：
```
ibmcloud sl globalip list --v4
```
此命令列出当前帐户的所有 IP V4 地址。



## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

从目标路由器或设备取消分配全局 IP。
```
ibmcloud sl globalip unassign IDENTIFIER
```


**示例**：
```
ibmcloud sl globalip unassign 12345678
```
此命令从目标设备取消分配标识为 12345678 的 IP 地址。
