---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, domain management, dns service, ibmcloud sl dns, classic infrastructure, management interface, dns, dns cli, manage dns cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 使用 DNS 服务管理域
{: #sl-manage-domains}

{{site.data.keyword.cloud}} 域名服务 (DNS) 为客户提供了一个中心位置，可通过基本 DNS 管理界面来查看和管理自己的域，此外还为用户提供了用于免费管理同一位置中的逆向和辅助 DNS 的选项。

使用以下命令可管理 {{site.data.keyword.cloud_notm}} 经典基础架构 DNS 服务。
{: shortdesc}

## ibmcloud sl dns import
{: #sl_dns_import}

基于 BIND 专区文件导入专区。
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
此命令从 ~/ibm.com.txt 文件导入专区及其资源记录。


## ibmcloud sl dns record-add
{: #sl_dns_record_add}

将资源记录添加到专区中。
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
此命令将 A 记录添加到专区 ibm.com，其主机为“ftp”，数据为“127.0.0.1”，ttl 为 86400 秒。


## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

更新专区中的资源记录。
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
此命令编辑专区 ibm.com 下标识为 12345678 的记录，并将其数据设置为“127.0.0.2”，ttl 设置为 3600。


## ibmcloud sl dns record-list
{: #sl_dns_record_list}

列出专区中的所有资源记录。
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
此命令列出专区 ibm.com 下的所有 A 记录，要作为过滤依据的主机为 elasticsearch，ttl 为 900 秒。


## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

除去专区中的资源记录。
```
ibmcloud sl dns record-remove RECORD_ID
```

**示例**：
```
ibmcloud sl dns record-remove 12345678
```
此命令除去标识为 12345678 的资源记录。




## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

创建专区。
```
ibmcloud sl dns zone-create ZONE
```

**示例**：
```
ibmcloud sl dns zone-create ibm.com
```
此命令创建名为 ibm.com 的专区。


## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

删除专区。
```
ibmcloud sl dns zone-delete ZONE
```

**示例**：
```
ibmcloud sl dns zone-delete ibm.com
```
此命令删除名为 ibm.com 的专区。


## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

列出帐户的所有专区。
```
ibmcloud sl dns zone-list
```

**示例**：
```
ibmcloud sl dns zone-list
```
此命令列出当前帐户下的所有专区。




## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

以 BIND 格式打印专区和资源记录。
```
ibmcloud sl dns zone-print ZONE
```

**示例**：
```
ibmcloud sl dns zone-print ibm.com
```
此命令以 BIND 格式显示名为 ibm.com 的专区。
