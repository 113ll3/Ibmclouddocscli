---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理 {{site.data.keyword.Bluemix_notm}} 基础架构块存储器

 <table summary="按字母顺序排序的常规 {{site.data.keyword.Bluemix_notm}} 基础架构命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} 基础架构块存储器</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} 基础架构块存储器</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl block access-authorize](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_authorize)</td>
  <td>[ibmcloud sl block access-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_list)</td>
  <td>[ibmcloud sl block access-password](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_password)</td>
  <td>[ibmcloud sl block access-revoke](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_access_revoke)</td>
  <td>[ibmcloud sl block replica-failback](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failback)</td>
  <td>[ibmcloud sl block replica-failover](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_failover)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl block replica-locations](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_locations)</td>
  <td>[ibmcloud sl block replica-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_order)</td>
  <td>[ibmcloud sl block replica-partners](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_replica_partners)</td>
  <td>[ibmcloud sl block snapshot-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_cancel)</td>
  <td>[ibmcloud sl block snapshot-create](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_create)</td>
  <td>[ibmcloud sl block snapshot-disable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_disable)</td>
</tr>
<tr>
  <td>[ibmcloud sl block snapshot-enable](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_enable)</td>
  <td>[ibmcloud sl block snapshot-delete](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_delete)</td>
  <td>[ibmcloud sl block snapshot-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_list)</td>
  <td>[ibmcloud sl block snapshot-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_order)</td>
  <td>[ibmcloud sl block snapshot-restore](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_snapshot_restore)</td>
  <td>[ibmcloud sl block volume-cancel](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_cancel)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-count](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_count)</td>    <td>[ibmcloud sl block volume-detail](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_detail)</td>
   <td>[ibmcloud sl block volume-duplicate](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_duplicate)</td>
   <td>[ibmcloud sl block volume-list](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_list)</td>
   <td>[ibmcloud sl block volume-order](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_order)</td>
   <td>[ibmcloud sl block volume-options](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_options)</td>
</tr>
<tr>
   <td>[ibmcloud sl block volume-set-lun-id](/docs/cli/reference/ibmcloud/cli_block_storage.html#sl_block_volume_set_lun_id)</td>  
</tr>
</tbody>
</table>

## ibmcloud sl block access-authorize
{: #sl_block_access_authorize}

授权主机访问给定卷。
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-d, --hardware-id</dt>
<dd>要授权的一个硬件服务器的标识。</dd>
<dt>-v, --virtual-id</dt>
<dd>要授权的一个虚拟服务器的标识。</dd>
<dt>-i, --ip-address-id</dt>
<dd>要授权的一个 IP 地址的标识。</dd>
<dt>-p, --ip-address</dt>
<dd>要授权的 IP 地址。</dd>
</dl>

**示例**：
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
此命令授权标识为 87654321 的虚拟服务器访问标识为 12345678 的卷。



## ibmcloud sl block access-list
{: #sl_block_access_list}

列出 ACL。
```
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、name、type、private_ip_address、host_iqn、username 或 password。</dd>
<dt>--columns</dt>
<dd>要显示的列，选项为：id、name、type、private_ip_address、host_iqn、username 或 password。</dd>
</dl>

**示例**：
```
ibmcloud sl block access-list 12345678 --sortby id
```
此命令列出有权访问标识为 12345678 的卷的所有主机，并按标识对其排序。



## ibmcloud sl block access-password
{: #sl_block_access_password}

更改卷访问的密码。
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

## ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

撤销主机访问给定卷的授权。
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-d, --hardware-id</dt>
<dd>要撤销的一个硬件服务器的标识。</dd>
<dt>-v, --virtual-id</dt>
<dd>要撤销的一个虚拟服务器的标识。</dd>
<dt>-i, --ip-address-id</dt>
<dd>要撤销的一个 IP 地址的标识。</dd>
<dt>-p, --ip-address</dt>
<dd>要撤销的 IP 地址。</dd>
</dl>

**示例**：
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
此命令撤销标识为 87654321 的虚拟服务器对标识为 12345678 的卷的访问权。



## ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

从副本对块卷执行故障恢复操作。
```
ibmcloud sl block replica-failback VOLUME_ID
```


**示例**：
```
ibmcloud sl block replica-failback 12345678
```
此命令对标识为 12345678 的卷执行故障恢复操作。



## ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

从块卷故障转移到给定的副本卷。
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**示例**：
```
ibmcloud sl block replica-failover 12345678 87654321
```
此命令对标识为 12345678 的卷执行到标识为 87654321 的副本卷的故障转移操作。



## ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

列出给定卷的适用复制数据中心。
```
ibmcloud sl block replica-locations VOLUME_ID
```


**示例**：
```
ibmcloud sl block replica-locations 12345678
```
此命令列出标识为 12345678 的块卷的适用复制数据中心。



## ibmcloud sl block replica-order
{: #sl_block_replica_order}

订购块存储器副本卷。
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>必需。针对复制的快照安排，选项为：HOURLY、DAILY 或 WEEKLY。</dd>
<dt>-d, --datacenter</dt>
<dd>必需。副本的数据中心的短名称，例如 dal09。</dd>
<dt>-t, --tier</dt>
<dd>可选。为其订购副本的主卷的耐久性存储器层 (IOPS/GB)，选项为：0.25、2、4 或 10；如果未指定任何层，那么将使用原始卷的层。</dd>
<dt>-i, --iops</dt>
<dd>性能存储器 IOPS，介于 100 到 6000 之间，是 100 的倍数；如果未指定 IOPS，那么将使用原始卷的 IOPS。</dd>
<dt>-o, --os-type</dt>
<dd>可选。为其订购副本的主卷的操作系统类型，选项为：HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS 或 XEN。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
此命令为标识为 12345678 的卷订购副本，此副本执行 DAILY 复制，位于 dal09，层级为 4，操作系统类型为 Linux。



## ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

列出块卷的现有副本卷。
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONS]
```


**示例**：
```
ibmcloud sl block replica-partners 12345678
```
此命令列出标识为 12345678 的块卷的现有复制卷。



## ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

取消给定卷的现有快照空间。
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--reason</dt>
<dd>可选的取消原因。</dd>
<dt>--immediate</dt>
<dd>立即取消快照空间，而不是在计费周年取消。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
此命令立即取消标识为 12345678 的快照，而不要求确认。



## ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

创建给定卷的快照。
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-n, --note</dt>
<dd>要对新快照设置的注释。</dd>
</dl>

**示例**：
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
此命令创建标识为 12345678 的卷的快照，并添加注释 snapshotforibmcloud。

## ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

禁止按指定安排生成给定卷的快照。
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --schedule-type</dt>
<dd>必需。快照安排，选项为：HOURLY、DAILY 或 WEEKLY。</dd>
</dl>

**示例**：
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
此命令禁止为标识为 12345678 的卷生成每日快照。



## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

允许按指定安排生成给定卷的快照。
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --schedule-type</dt>
<dd>必需。快照安排，选项为：HOURLY、DAILY 或 WEEKLY。</dd>
<dt>-c, --retention-count</dt>
<dd>必需。要保留的快照数。</dd>
<dt>-m, --minute</dt>
<dd>应生成快照的时刻（分钟，0 到 59 之间的整数）。</dd>
<dt>-r, --hour</dt>
<dd>应生成快照的时刻（小时，0 到 23 之间的整数）。</dd>
<dt>-d, --day-of-week</dt>
<dd>应生成快照的日期（星期，0 到 6 之间的整数）。0 表示周日，1 表示周一，2 表示周二，3 表示周三，4 表示周四，5 表示周五，6 表示周六。</dd>
</dl>

**示例**：
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
此命令允许为标识为 12345678 的卷生成快照。快照将在每周日 2:00 生成，最多保留 5 个快照。



## ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

删除给定卷的快照。
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**示例**：
```
ibmcloud sl block snapshot-delete 12345678
```
此命令删除标识为 12345678 的快照。



## ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

列出块存储器快照。
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、name、created 或 size_bytes。</dd>
</dl>

**示例**：
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
此命令列出标识为 12345678 的卷的所有快照，并按标识对其排序。



## ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

为块存储卷订购快照空间。
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-s, --size</dt>
<dd>必需。要创建的快照空间的大小（以 GB 为单位）。</dd>
<dt>-t, --tier</dt>
<dd>可选。为其订购空间的块卷的耐久性存储器层 (IOPS/GB)，选项为：0.25、2、4 或 10。</dd>
<dt>-i, --iops</dt>
<dd>性能存储器 IOPS，介于 100 到 6000 之间，是 100 的倍数。</dd>
<dt>-u, --upgrade</dt>
<dd>指示订单是升级的标志。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
此命令为标识为 12345678 的卷订购快照空间，大小为 1000 GB，层级为 4 IOPS/GB。



## ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

使用给定快照复原块卷。
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**示例**：
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
此命令通过标识为 87654321 的快照复原标识为 12345678 的卷。



## ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

取消现有块存储卷。
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--reason</dt>
<dd>可选的取消原因。</dd>
<dt>--immediate</dt>
<dd>立即取消块存储卷，而不是在计费周年取消。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
此命令立即取消标识为 12345678 的卷，而不要求确认。



## ibmcloud sl block volume-count
{: #sl_block_volume_count}

列出每个数据中心的块存储卷数。
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-d, --datacenter</dt>
<dd>按数据中心短名称过滤。</dd>
</dl>

## ibmcloud sl block volume-list
{: #sl_block_volume_list}

列出块存储器。
```
ibmcloud sl block volume-list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-u, --username</dt>
<dd>按卷用户名过滤。</dd>
<dt>-d, --datacenter</dt>
<dd>按数据中心短名称过滤。</dd>
<dt>-t, --storage-type</dt>
<dd>按存储卷类型过滤，选项为：performance 或 endurance。</dd>
<dt>-o, --order</dt>
<dd>按购买了块存储器的订单的标识过滤。</dd>
<dt>--sortby</dt>
<dd>要按其排序的列，选项为：id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、active_transactions 或 created_by。</dd>
<dt>--columns</dt>
<dd>要显示的列，选项为：id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr 或 created_by。</dd>
</dl>

**示例**：
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
此命令列出当前帐户中位于 dal09 的所有耐久性卷，并按容量对其排序。




## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

在现有块存储卷上设置 LUN 标识。
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

## ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

显示指定卷的详细信息。
```
ibmcloud sl block volume-detail VOLUME_ID
```


**示例**：
```
ibmcloud sl block volume-detail 12345678
```
此命令显示标识为 12345678 的卷的详细信息。



## ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

通过复制现有卷来订购块卷。
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>用于复制的源卷快照的标识。</dd>
<dt>-s, --duplicate-size</dt>
<dd>复制块卷的大小（以 GB 为单位），如果未指定大小，那么将使用原始卷的大小。</dd>
<dt>-i, --duplicate-iops</dt>
<dd>性能存储器 IOPS，介于 100 到 6000 之间，是 100 的倍数；如果未指定 IOPS，那么将使用原始卷的 IOPS。</dd>
<dt>-t, --duplicate-tier</dt>
<dd>耐久性存储器层，如果未指定层，那么将使用原始卷的层。</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>订购用于复制的快照空间的大小，如果未指定快照空间大小，那么将使用源卷的快照空间大小。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl block volume-duplicate 12345678
```
此命令显示通过复制标识为 12345678 的卷来订购新卷。



## ibmcloud sl block volume-order
{: #sl_block_volume_order}

订购块存储卷。
```
ibmcloud sl block volume-order [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-t, --storage-type</dt>
<dd>必需。存储卷的类型，选项为：performance 或 endurance。</dd>
<dt>-s, --size</dt>
<dd>必需。存储卷大小 (GB)</dd>
<dt>-i, --iops</dt>
<dd>性能存储器 IOPS，介于 100 到 6000 之间，是 100 的倍数 [storage-type 为 performance 时是必需的]。</dd>
<dt>-e, --tier</dt>
<dd>耐久性存储器层 (IOP/GB) [storage-type 为 endurance 时是必需的]，选项为：0.25、2、4 或 10。</dd>
<dt>-o, --os-type</dt>
<dd>必需。操作系统，选项为：HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS 和 XEN。</dd>
<dt>-d, --datacenter</dt>
<dd>必需。数据中心短名称。</dd>
<dt>-n, --snapshot-size</dt>
<dd>用于随耐久性块存储器一起订购快照空间的可选参数；指定要订购的快照空间大小（以 GB 为单位）。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

**示例**：
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
此命令订购性能卷，大小为 1000 GB，IOPS 为 4000，操作系统类型为 LINUX，位于 dal09。


## ibmcloud sl block volume-options
{: #sl_block_volume_options}

列出用于订购块存储器的所有选项。
```
ibmcloud sl block volume-options
```


**示例**：
```
ibmcloud sl block volume-options
```
此命令列出用于创建块存储卷的所有选项，包括存储器类型、卷大小、操作系统类型、IOPS、层级、数据中心和快照大小。
