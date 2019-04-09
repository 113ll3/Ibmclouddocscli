---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理虚拟服务器流量的安全组

安全组是一组 IP 过滤规则，用于定义如何处理虚拟服务器实例的公共和专用接口的传入（流入）和传出（流出）流量。向安全组中添加的规则称为安全组规则。

使用以下命令可通过 {{site.data.keyword.Bluemix}} 经典基础架构安全组服务来管理安全组。
{: shortdesc}

<table summary="按字母顺序排序的 {{site.data.keyword.Bluemix_notm}} 经典基础架构安全组命令（带有可获取命令的更多信息的链接）">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl securitygroup create](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_create)</td>
  <td>[ibmcloud sl securitygroup delete](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_delete)</td>
  <td>[ibmcloud sl securitygroup detail](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_detail)</td>
  <td>[ibmcloud sl securitygroup edit](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_edit)</td>   
  <td>[ibmcloud sl securitygroup interface-add](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_interface_add)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl securitygroup interface-list](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_interace_list)</td>
  <td>[ibmcloud sl securitygroup interface-remove](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_interface_remove)</td>
  <td>[ibmcloud sl securitygroup list](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_list)</td>
  <td>[ibmcloud sl securitygroup rule-add](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_add)</td>
  <td>[ibmcloud sl securitygroup rule-edit](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_edit)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl securitygroup rule-list](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_list)</td>
  <td>[ibmcloud sl securitygroup rule-remove](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_remove)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl securitygroup create
{: #sl_securitygroup_create}

创建安全组。
```
ibmcloud sl securitygroup create [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --name</dt>
<dd>安全组的名称。</dd>
<dt>-d, --description</dt>
<dd>安全组的描述。</dd>
</dl>

## ibmcloud sl securitygroup delete
{: #sl_securitygroup_delete}

删除给定的安全组。
```
ibmcloud sl securitygroup delete SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

## ibmcloud sl securitygroup detail
{: #sl_securitygroup_detail}

获取有关安全组的详细信息。
```
ibmcloud sl securitygroup detail SECURITYGROUP_ID [OPTIONS]
```

## ibmcloud sl securitygroup edit
{: #sl_securitygroup_edit}

编辑安全组的详细信息。
```
ibmcloud sl securitygroup edit SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --name</dt>
<dd>安全组的名称。</dd>
<dt>-d, --description</dt>
<dd>安全组的描述。</dd>
</dl>

## ibmcloud sl securitygroup interface-add
{: #sl_securitygroup_interface_add}

将接口连接到安全组。
```
ibmcloud sl securitygroup interface-add SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --network-component</dt>
<dd>要与安全组关联的网络组件标识。</dd>
<dt>-s, --server</dt>
<dd>要与安全组关联的服务器标识。</dd>
<dt>-i, --interface</dt>
<dd>要关联的服务器的接口 (public/private)。</dd>
</dl>

## ibmcloud sl securitygroup interface-list
{: #sl_securitygroup_interface_list}

列出与安全组关联的接口。
```
ibmcloud sl securitygroup interface-list SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、virtualServerId 或 hostname。</dd>
</dl>

## ibmcloud sl securitygroup interface-remove
{: #sl_securitygroup_interface_remove}

从安全组拆离接口。
```
ibmcloud sl securitygroup interface-remove SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --network-component</dt>
<dd>要从安全组中除去的网络组件。</dd>
<dt>-s, --server</dt>
<dd>要从安全组中除去的服务器标识。</dd>
<dt>-i, --interface</dt>
<dd>要除去的服务器的接口 (public/private)。</dd>
</dl>

## ibmcloud sl securitygroup list
{: #sl_securitygroup_list}

列出安全组。
```
List security groups
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、name、description 或 created。</dd>
</dl>

## ibmcloud sl securitygroup rule-add
{: #sl_securitygroup_rule_add}

将安全组规则添加到安全组。
```
ibmcloud sl securitygroup rule-add SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-r, --remote-ip</dt>
<dd>要强制实施的远程 IP/CIDR。</dd>
<dt>-s, --remote-group</dt>
<dd>要强制实施的远程安全组的标识。</dd>
<dt>-d, --direction</dt>
<dd>要强制实施的流量方向（ingress 或 egress）（必需）。</dd>
<dt>-e, --ether-type</dt>
<dd>要强制实施的以太类型（IPv4 或 IPv6），如果未指定，缺省值为 IPv4。</dd>
<dt>-M, --port-max</dt>
<dd>要强制实施的端口上限。</dd>
<dt>-m, --port-min</dt>
<dd>要强制实施的端口下限。</dd>
<dt>-p, --protocol</dt>
<dd>要强制实施的协议（icmp、tcp 或 udp）。</dd>
</dl>

## ibmcloud sl securitygroup rule-edit
{: #sl_securitygroup_rule_edit}

编辑安全组中的安全组规则。
```
ibmcloud sl securitygroup rule-edit SECURITYGROUP_ID RULE_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-r, --remote-ip</dt>
<dd>要强制实施的远程 IP/CIDR。</dd>
<dt>-s, --remote-group</dt>
<dd>要强制实施的远程安全组的标识。</dd>
<dt>-d, --direction</dt>
<dd>要强制实施的流量方向（ingress 或 egress）（必需）。</dd>
<dt>-e, --ether-type</dt>
<dd>要强制实施的以太类型（IPv4 或 IPv6），如果未指定，缺省值为 IPv4。</dd>
<dt>-M, --port-max</dt>
<dd>要强制实施的端口上限。</dd>
<dt>-m, --port-min</dt>
<dd>要强制实施的端口下限。</dd>
<dt>-p, --protocol</dt>
<dd>要强制实施的协议（icmp、tcp 或 udp）。</dd>
</dl>

## ibmcloud sl securitygroup rule-list
{: #sl_securitygroup_rule_list}

列出安全组规则。
```
ibmcloud sl securitygroup rule-list SECURITYGROUP_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、remoteIp、remoteGroupId、direction、ethertype、portRangeMin、portRangeMax 或 protocol。</dd>
</dl>

## ibmcloud sl securitygroup rule-remove
{: #sl_securitygroup_rule_remove}

从安全组中除去规则。
```
ibmcloud sl securitygroup rule-remove SECURITYGROUP_ID RULE_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>
