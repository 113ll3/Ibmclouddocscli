---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 用于管理 {{site.data.keyword.Bluemix_notm}} 基础架构 DNS 的命令

<table summary="按字母顺序排序的常规 {{site.data.keyword.Bluemix_notm}} 基础架构命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} 基础架构 DNS 命令</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} 基础架构 DNS 命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl dns import](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_import)</td>
 <td>[ibmcloud sl dns record-add](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_add)</td>
 <td>[ibmcloud sl dns record-edit](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_edit)</td>
 <td>[ibmcloud sl dns record-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_list)</td>
 <td>[ibmcloud sl dns record-remove](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_record_remove)</td>
 <td>[ibmcloud sl dns zone-create](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[ibmcloud sl dns zone-delete](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_delete)</td>
   <td>[ibmcloud sl dns zone-list](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_list)</td>
   <td>[ibmcloud sl dns zone-print](/docs/cli/reference/ibmcloud/cli_dns.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

### ibmcloud sl dns import
{: #sl_dns_import}

导入基于 BIND 区域文件的区域。
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--dry-run</dt>
<dd>实际不创建记录。</dd>
</dl>

**示例**：
```
ibmcloud sl dns import ~/ibm.com.txt
```
此命令从 ~/ibm.com.txt 文件导入区域及其资源记录。

### ibmcloud sl dns record-add
{: #sl_dns_record_add}

将资源记录添加到区域中。
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--ttl</dt>
<dd>TTL（生存时间）（以秒为单位），例如：86400，缺省值为 7200。</dd>
</dl>

**示例**：
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
此命令将 A 记录添加到区域 ibm.com，其主机为“ftp”，数据为“127.0.0.1”，ttl 为 86400 秒。

### ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

更新区域中的资源记录。
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--by-record</dt>
<dd>按主机记录（例如 www）编辑。</dd>
<dt>--by-id</dt>
<dd>按标识编辑单个记录。</dd>
<dt>--data</dt>
<dd>记录数据，例如 IP 地址。</dd>
<dt>--ttl</dt>
<dd>TTL 值（以秒为单位），例如：86400。</dd>
</dl>

**示例**：
```
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
此命令编辑区域 ibm.com 下标识为 12345678 的记录，并将其数据设置为“127.0.0.2”，ttl 设置为 3600。

### ibmcloud sl dns record-list
{: #sl_dns_record_list}

列出区域中的所有资源记录。
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--data</dt>
<dd>按记录数据（例如，IP 地址）过滤。</dd>
<dt>--record</dt>
<dd>按主机记录（例如 www）过滤。</dd>
<dt>--ttl</dt>
<dd>按 TTL 值（以秒为单位，例如 86400）过滤。</dd>
<dt>--type</dt>
<dd>按记录类型（例如，A 或 CNAME）过滤。</dd>
</dl>

**示例**：
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
此命令列出区域 ibm.com 下的所有 A 记录，要作为过滤依据的主机为 elasticsearch，ttl 为 900 秒。

### ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

除去区域中的资源记录。
```
ibmcloud sl dns record-remove RECORD_ID
```


**示例**：
```
ibmcloud sl dns record-remove 12345678
```
此命令除去标识为 12345678 的资源记录。



### ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

创建区域。
```
ibmcloud sl dns zone-create ZONE
```


**示例**：
```
ibmcloud sl dns zone-create ibm.com
```
此命令创建名为 ibm.com 的区域。

### ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

删除区域。
```
ibmcloud sl dns zone-delete ZONE
```


**示例**：
```
ibmcloud sl dns zone-delete ibm.com
```
此命令删除名为 ibm.com 的区域。

### ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

列出帐户的所有区域。
```
ibmcloud sl dns zone-list
```


**示例**：
```
ibmcloud sl dns zone-list
```
此命令列出当前帐户下的所有区域。



### ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

以 BIND 格式打印区域和资源记录。
```
ibmcloud sl dns zone-print ZONE
```


**示例**：
```
ibmcloud sl dns zone-print ibm.com
```
此命令以 BIND 格式显示名为 ibm.com 的区域。
