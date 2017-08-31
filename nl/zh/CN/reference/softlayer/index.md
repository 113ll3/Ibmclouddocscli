---

copyright:

  years: 2016,2017

lastupdated: "2017-06-27"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl) 命令
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} 插件已合并到 {{site.data.keyword.Bluemix_notm}} CLI 中。您不再需要安装该插件。

使用 {{site.data.keyword.Bluemix_notm}} 命令行界面 (CLI) 中的 {{site.data.keyword.BluSoftlayer_notm}} 命令来配置和管理 SoftLayer 服务。


首先，请安装 IBM {{site.data.keyword.Bluemix_notm}} CLI。有关详细信息，请参阅 [Bluemix CLI ![外部链接图标](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}。

要获取 {{site.data.keyword.Bluemix_notm}} 命令的完整列表，请参阅：[{{site.data.keyword.Bluemix_notm}} (bx) 命令](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli)


## 常规 {{site.data.keyword.BluSoftlayer_notm}} 命令

支持以下命令。使用 `bluemix sl` 命令可查看可用命令的列表：

<table summary="按字母顺序列出的常规命令（命令具有可获取命令更多信息的链接）">
<caption>表 1. 常规 Softlayer 命令</caption>
 <thead>
 <th colspan="6">常规 Softlayer 命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## {{site.data.keyword.BluSoftlayer_notm}} 块存储器命令

 <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 2. Softlayer 块存储器</caption>
 <thead>
 <th colspan="6">Softlayer 块存储器</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl block access-authorize](/docs/cli/reference/softlayer/index.html#sl_block_access_authorize)</td>
  <td>[bluemix sl block access-list](/docs/cli/reference/softlayer/index.html#sl_block_access_list)</td>
  <td>[bluemix sl block access-revoke](/docs/cli/reference/softlayer/index.html#sl_block_access_revoke)</td>
  <td>[bluemix sl block replica-failback](/docs/cli/reference/softlayer/index.html#sl_block_replica_failback)</td>
  <td>[bluemix sl block replica-failover](/docs/cli/reference/softlayer/index.html#sl_block_replica_failover)</td>
  <td>[bluemix sl block replica-order](/docs/cli/reference/softlayer/index.html#sl_block_replica_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_cancel)</td>
 <td>[bluemix sl block snapshot-create](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_create)</td>
 <td>[bluemix sl block snapshot-disable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_disable)</td>
 <td>[bluemix sl block snapshot-enable](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_enable)</td>
 <td>[bluemix sl block snapshot-delete](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_delete)</td>
 <td>[bluemix sl block snapshot-list](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_list)</td>
  </tr>
 <tr>
 <td>[bluemix sl block snapshot-order](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_order)</td>
  <td>[bluemix sl block snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_block_snapshot_restore)</td>
  <td>[bluemix sl block volume-cancel](/docs/cli/reference/softlayer/index.html#sl_block_volume_cancel)</td>  
  <td>[bluemix sl block volume-detail](/docs/cli/reference/softlayer/index.html#sl_block_volume_detail)</td>
  <td>[bluemix sl block volume-list](/docs/cli/reference/softlayer/index.html#sl_block_volume_list)</td>
  <td>[bluemix sl block volume-order](/docs/cli/reference/softlayer/index.html#sl_block_volume_order)</td>
   </tr>
 <tr>
  <td>[bluemix sl block volume-options](/docs/cli/reference/softlayer/index.html#sl_block_volume_options)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} dns 命令

<table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 3. Softlayer dns 命令</caption>
 <thead>
 <th colspan="6">Softlayer dns 命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl dns import](/docs/cli/reference/softlayer/index.html#sl_dns_import)</td>
 <td>[bluemix sl dns record-add](/docs/cli/reference/softlayer/index.html#sl_dns_record_add)</td>
 <td>[bluemix sl dns record-edit](/docs/cli/reference/softlayer/index.html#sl_dns_record_edit)</td>
 <td>[bluemix sl dns record-list](/docs/cli/reference/softlayer/index.html#sl_dns_record_list)</td>
 <td>[bluemix sl dns record-remove](/docs/cli/reference/softlayer/index.html#sl_dns_record_remove)</td>
  <td>[bluemix sl dns zone-create](/docs/cli/reference/softlayer/index.html#sl_dns_zone_create)</td>
 </tr>
 <tr>
   <td>[bluemix sl dns zone-delete](/docs/cli/reference/softlayer/index.html#sl_dns_zone_delete)</td>
   <td>[bluemix sl dns zone-list](/docs/cli/reference/softlayer/index.html#sl_dns_zone_list)</td>
   <td>[bluemix sl dns zone-print](/docs/cli/reference/softlayer/index.html#sl_dns_zone_print)</td>
 </tr>
   </tbody>
 </table>

<table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 4. Softlayer 全局 IP 地址</caption>
 <thead>
 <th colspan="6">Softlayer 全局 IP 地址</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl globalip assign](/docs/cli/reference/softlayer/index.html#sl_globalip_assign)</td>
  <td>[bluemix sl globalip cancel](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
  <td>[bluemix sl globalip create](/docs/cli/reference/softlayer/index.html#sl_globalip_create)</td>
 <td>[bluemix sl globalip list](/docs/cli/reference/softlayer/index.html#sl_globalip_list)</td>
 <td>[bluemix sl globalip unassign](/docs/cli/reference/softlayer/index.html#sl_globalip_cancel)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} 映像命令

 <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 5. Softlayer 映像命令</caption>
 <thead>
 <th colspan="6">Softlayer 映像命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl image delete](/docs/cli/reference/softlayer/index.html#sl_image_delete)</td>
 <td>[bluemix sl image detail](/docs/cli/reference/softlayer/index.html#sl_image_detail)</td>
 <td>[bluemix sl image edit](/docs/cli/reference/softlayer/index.html#sl_image_edit)</td>
 <td>[bluemix sl image list](/docs/cli/reference/softlayer/index.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}} 旧 ISCSI 存储器命令

  <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 6. Softlayer 旧 ISCSI 存储器命令</caption>
 <thead>
 <th colspan="6">Softlayer 旧 ISCSI 存储器命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl iscsi cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_cancel)</td>
 <td>[bluemix sl iscsi create](/docs/cli/reference/softlayer/index.html#sl_iscsi_create)</td>
 <td>[bluemix sl iscsi detail](/docs/cli/reference/softlayer/index.html#sl_iscsi_detail)</td>
 <td>[bluemix sl iscsi list](/docs/cli/reference/softlayer/index.html#sl_iscsi_list)</td>
 <td>[bluemix sl iscsi snapshot-cancel](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_cancel)</td>
 <td>[bluemix sl iscsi snapshot-create](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create)</td>
 </tr>
 <tr>
 <td>[bluemix sl iscsi snapshot-create-space](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_create-space)</td>
 <td>[bluemix sl iscsi snapshot-list](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_list)</td>
 <td>[bluemix sl iscsi snapshot-restore](/docs/cli/reference/softlayer/index.html#sl_iscsi_snapshot_restore)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} 安全命令

 <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 7. Softlayer 安全命令</caption>
 <thead>
 <th colspan="5">Softlayer 安全命令</th>
 </thead>
 <tbody>
 <tr>
  <td>[bluemix sl security sshkey-add](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_add)</td>
  <td>[bluemix sl security sshkey-edit](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_edit)</td>
  <td>[bluemix sl security sshkey-list](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_list)</td>
  <td>[bluemix sl security sshkey-print](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_print)</td>   
  <td>[bluemix sl security sshkey-remove](/docs/cli/reference/softlayer/index.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[bluemix sl security cert-add](/docs/cli/reference/softlayer/index.html#sl_security_cert_add)</td>
  <td>[bluemix sl security cert-edit](/docs/cli/reference/softlayer/index.html#sl_security_cert_edit)</td>
  <td>[bluemix sl security cert-download](/docs/cli/reference/softlayer/index.html#sl_security_cert_download)</td>
  <td>[bluemix sl security cert-list](/docs/cli/reference/softlayer/index.html#sl_security_cert_list)</td>
  <td>[bluemix sl security cert-remove](/docs/cli/reference/softlayer/index.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

## {{site.data.keyword.BluSoftlayer_notm}} 子网命令
 
 <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 8. Softlayer 子网命令</caption>
 <thead>
 <th colspan="5">Softlayer 子网命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl subnet cancel](/docs/cli/reference/softlayer/index.html#sl_subnet_cancel)</td>
 <td>[bluemix sl subnet create](/docs/cli/reference/softlayer/index.html#sl_subnet_create)</td>
 <td>[bluemix sl subnet detail](/docs/cli/reference/softlayer/index.html#sl_subnet_detail)</td>
 <td>[bluemix sl subnet list](/docs/cli/reference/softlayer/index.html#sl_subnet_list)</td>
 <td>[bluemix sl subnet lookup](/docs/cli/reference/softlayer/index.html#sl_subnet_lookup)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}} 虚拟服务器命令

 <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 9. Softlayer 虚拟服务器命令</caption>
 <thead>
 <th colspan="6">Softlayer 虚拟服务器命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vs cancel](/docs/cli/reference/softlayer/index.html#sl_vs_cancel)</td>
 <td>[bluemix sl vs capture](/docs/cli/reference/softlayer/index.html#sl_vs_capture)</td>
 <td>[bluemix sl vs create](/docs/cli/reference/softlayer/index.html#sl_vs_create)</td>
 <td>[bluemix sl vs options](/docs/cli/reference/softlayer/index.html#sl_vs_options)</td>
 <td>[bluemix sl vs credentials](/docs/cli/reference/softlayer/index.html#sl_vs_credentials)</td>
 <td>[bluemix sl vs detail](/docs/cli/reference/softlayer/index.html#sl_vs_detail)</td>
 </tr><tr>
 <td>[bluemix sl vs dns-sync](/docs/cli/reference/softlayer/index.html#sl_vs_dns_sync)</td>
 <td>[bluemix sl vs edit](/docs/cli/reference/softlayer/index.html#sl_vs_edit)</td>
 <td>[bluemix sl vs list](/docs/cli/reference/softlayer/index.html#sl_vs_list)</td>
 <td>[bluemix sl vs pause](/docs/cli/reference/softlayer/index.html#sl_vs_pause)</td>
 <td>[bluemix sl vs power-off](/docs/cli/reference/softlayer/index.html#sl_vs_power_off)</td>
 <td>[bluemix sl vs power-on](/docs/cli/reference/softlayer/index.html#sl_vs_power_on)
 </tr><tr>
 <td>[bluemix sl vs ready](/docs/cli/reference/softlayer/index.html#sl_vs_ready)</td>
 <td>[bluemix sl vs reboot](/docs/cli/reference/softlayer/index.html#sl_vs_reboot)</td>
 <td>[bluemix sl vs reload](/docs/cli/reference/softlayer/index.html#sl_vs_reload)</td>
 <td>[bluemix sl vs rescure](/docs/cli/reference/softlayer/index.html#sl_vs_rescure)</td>
 <td>[bluemix sl vs resume](/docs/cli/reference/softlayer/index.html#sl_vs_resume)</td>
 <td>[bluemix sl vs upgrade](/docs/cli/reference/softlayer/index.html#sl_vs_upgrade)</td>
 </tr>
   </tbody>
 </table>
 
## {{site.data.keyword.BluSoftlayer_notm}} VLAN 命令

  <table summary="按字母顺序列出的常规 Softlayer 命令（命令具有可获取命令更多信息的链接）">
<caption>表 10. Softlayer VLAN 命令</caption>
 <thead>
 <th colspan="6">Softlayer VLAN 命令</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl vlan create](/docs/cli/reference/softlayer/index.html#sl_vlan_create)</td>
 <td>[bluemix sl vlan cancel](/docs/cli/reference/softlayer/index.html#sl_vlan_cancel)</td>
 <td>[bluemix sl vlan detail](/docs/cli/reference/softlayer/index.html#sl_vlan_detail)</td>
 <td>[bluemix sl vlan edit](/docs/cli/reference/softlayer/index.html#sl_vlan_edite)</td>
 <td>[bluemix sl vlan list](/docs/cli/reference/softlayer/index.html#sl_vlan_list)</td>
 <td>[bluemix sl vlan options](/docs/cli/reference/softlayer/index.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

### 命令用法
要查看命令的帮助信息，请运行：`bluemix sl [command] -h`。

### bluemix sl init
{: #sl_init}

初始化用于连接到 SoftLayer 环境的配置设置。该配置包括用户名、API 密钥或密码、帐户和端点。
```
bluemix sl init [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-a,--api-endpoint</dt>
   <dd>Softlayer API 端点 URL，缺省值为：https://api.softlayer.com/rest/v3.1</dd>
   <dt>-u,--sl-user</dt>
   <dd>Softlayer 用户名</dd>
   <dt>-p,--sl-password</dt>
   <dd>Softlayer 密码或 API 密钥</dd>
   <dt>-c,--account-id</dt>
   <dd>Softlayer 帐户标识</dd>
   </dl>

例如，使用 Softlayer 用户名和密码/API 密钥登录
```
$ bluemix sl config
Choose how to configure Softlayer authentication: 
1. Login with Softlayer user name and password/API key
2. Use Bluemix Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> wangjunl@cn.ibm.com
API key or password: []> abcd

Softlayer API endpoint:    https://api.softlayer.com/rest/v3.1   
Account ID:                278444   
User ID:                   wangjunl@cn.ibm.com   
API Key:                   xxxxxxxxxx
```
例如，使用 Bluemix Single-Sign-On 登录 Softlayer
```
$ bx login -a api.ng.bluemix.net -u wangjunl@cn.ibm.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account Wilma's Account (65ce8074c6c62b5)

Targeted org wangjunl@cn.ibm.com

Targeted space Wilma
                  
API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           wangjunl@cn.ibm.com   
Account:        Wilma's Account (65ce8074c6c62b5)   
Org:            wangjunl@cn.ibm.com   
Space:          Wilma 

$ bx sl init
Choose how to configure Softlayer authentication: 
1. Login with Softlayer user name and password/API key
2. Use Bluemix Single-Sign-On
Enter a number> 2
Softlayer API endpoint URL: [https://api.softlayer.com/mobile/v3.1]> 
Setting account to: 278444
OK
                              
Softlayer API endpoint:    https://api.softlayer.com/mobile/v3.1   
Account ID:                278444   
User ID:                   12345678   
IMS token:                 xxxxxxxxxx
```

### bluemix sl help
{: #sl_help}

查看所有命令的帮助信息以操作 Softlayer 环境。
```
bluemix sl help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

授权主机访问给定卷。
```
bluemix sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--hardware-id</dt>
   <dd>要授权的一个硬件服务器的标识。</dd>
   <dt>--virtual-id</dt>
   <dd>要授权的一个虚拟服务器的标识。</dd>
   <dt>--ip-address-id</dt>
   <dd>要授权的一个 IP 地址的标识。</dd>
   <dt>--ip-address</dt>
   <dd>要授权的 IP 地址。</dd>
    </dl>

**示例**：
```
bluemix sl block access-authorize 12345678 --virtual-id 87654321
```
此命令授权标识为 `87654321` 的虚拟服务器访问标识为 `12345678` 的卷。

### bluemix sl block access-list
{: #sl_block_access_list}

列出 ACL。
```
bluemix sl block access-list VOLUME_ID [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--sortby</dt>
   <dd>要按其排序的列，选项为：`id`、`name`、`type`、`private_ip_address`、`host_iqn`、`username` 或 `password`。</dd>
   <dt>--columns</dt>
   <dd>  要显示的列，选项为：`id`、`name`、`type`、`private_ip_address`、`host_iqn`、`username` 或 `password`。</dd>
</dl>

**示例**：
```
bluemix sl block access-list 12345678 --sortby id
```
此命令列出有权访问标识为 `12345678` 的卷的所有主机，并按标识对其排序。

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

撤销主机访问给定卷的授权。
```
 bluemix sl block access-revoke VOLUME_ID [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--hardware-id</dt>
   <dd>要撤销其授权的一个硬件服务器的标识。</dd>
   <dt>--virtual-id</dt>
   <dd>要撤销其授权的一个虚拟服务器的标识。</dd>
   <dt>--ip-address-id</dt>
   <dd>要撤销其授权的一个 IP 地址的标识。</dd>
   <dt>--ip-address</dt>
   <dd>要撤销其授权的 IP 地址。</dd>
    </dl>

**示例**：
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```
此命令撤销标识为 `87654321` 的虚拟服务器对标识为 `12345678` 的卷的访问权。

### bluemix sl block replica-failback
{: #sl_block_replica_failback}

从副本对块卷执行故障恢复操作。
```
 bluemix sl block replica-failback VOLUME_ID
```
**示例**：
```
 bluemix sl block replica-failback 12345678
```
此命令对标识为 `12345678` 的卷执行故障恢复操作。

### bluemix sl block replica-failover
{: #sl_block_replica_failover}

从块卷故障转移到给定的副本卷。
```
bluemix sl block replica-failover VOLUME_ID REPLICA_ID
```

**示例**：
```
 bluemix sl block replica-failover 12345678 87654321
```
此命令对标识为 `12345678` 的卷执行到标识为 `87654321` 的副本卷的故障转移操作。

### bluemix sl block replica-order
{: #sl_block_replica_order}

订购块存储器副本卷。
```
 bluemix sl block replica-order VOLUME_ID [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>必需。用于复制的快照安排。选项为：`HOURLY`、`DAILY` 或 `WEEKLY`。</dd>
   <dt>-d, --datacenter</dt>
   <dd>必需。副本的数据中心的短名称。例如，`dal09`。</dd>
   <dt>--tier</dt>
   <dd>可选。为其订购副本的主卷的耐久性存储器层 (IOPS/GB)。选项为：`0.25`、`2`、`4` 或 `10`。</dd>
   <dt>--os-type</dt>
   <dd>可选。为其订购副本的主卷的操作系统类型。选项为：`HYPER_V`、`LINUX`、`VMWARE`、`WINDOWS_2008`、`WINDOWS_GPT`、`WINDOWS` 或 `XEN`。</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
    </dl>

**示例**：
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
此命令为标识为 `12345678` 的卷订购副本，此副本执行 DAILY 复制，位于 dal09，层级为 `4`，操作系统类型为 `Linux`。

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

取消给定卷的现有快照空间。
```
 bluemix sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```
此命令立即取消标识为 12345678 的快照，而不要求确认。

### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

创建给定卷的快照。
```
 bluemix sl block snapshot-create VOLUME_ID [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt> -n, --note</dt>
   <dd>要对新快照设置的注释</dd>
	</dl>

**示例**：
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```
此命令创建标识为 `12345678` 的卷的快照，并添加注释 `snapshotforbluemix`。

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

禁止按指定安排生成给定卷的快照。
```
 bluemix sl block snapshot-disable VOLUME_ID [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>必需。快照安排：`HOURLY`、`DAILY` 或 `WEEKLY`。</dd>
	</dl>

**示例**：
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```
此命令禁止为标识为 `12345678` 的卷生成每日快照。

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

允许按指定安排生成给定卷的快照。
```
 bluemix sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>必需。快照安排：`HOURLY`、`DAILY` 或 `WEEKLY`。</dd>
   <dt>-c, --retention-count</dt>
   <dd>必需。要保留的快照数。</dd>
   <dt>-m, --minute</dt>
   <dd>应生成快照的时刻（分钟，0 到 59 之间的整数）。</dd>
   <dt>--hour</dt>
   <dd>应生成快照的时刻（小时，0 到 23 之间的整数）。</dd>
   <dt>-d, --day-of-week</dt>
   <dd>应生成快照的日期（星期，0 到 6 之间的整数）。0 表示周日，1 表示周一，2 表示周二，3 表示周三，4 表示周四，5 表示周五，6 表示周六。</dd>
	</dl>

**示例**：
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
此命令允许为标识为 `12345678` 的卷生成快照。快照将在每周日 2:00 生成，最多保留 5 个快照。

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

删除给定卷的快照。
```
  bluemix sl block snapshot-delete SNAPSHOT_ID
```

**示例**：
```
 bluemix sl block snapshot-delete 12345678
```
此命令删除标识为 `12345678` 的快照。

### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

列出块存储器快照
```
 bluemix sl block snapshot-list VOLUME_ID [OPTIONS]

```

<strong>命令选项</strong>：
   <dl>
   <dt>--sortby</dt>
   <dd>要按其排序的列。选项为：`id`、`name`、`created` 和 `size_bytes`。</dd>
	</dl>

**示例**：
```
 bluemix sl block snapshot-list 12345678 --sortby id
```
此命令列出标识为 `12345678` 的卷的所有快照，并按标识对其排序。

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

为块存储卷订购快照空间。
```
 bluemix sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-s, --size</dt>
   <dd>必需。要创建的快照空间的大小（以 GB 为单位）。</dd>
   <dt>-t, --tier</dt>
   <dd>可选。为其订购空间的块卷的耐久性存储器层 (IOPS/GB)。选项为：0.25、2、4 或 10</dd>
   <dt>-u, --upgrade</dt>
   <dd>指示订单是升级的标志。</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
	</dl>

**示例**：
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```
此命令为标识为 `12345678` 的卷订购快照空间，大小为 1000 GB，层级为 4 IOPS/GB。


### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

使用给定快照复原块卷
```
 bluemix sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**示例**：
```
 bluemix sl block snapshot-restore 12345678 87654321
```
此命令通过标识为 `87654321` 的快照复原标识为 `12345678` 的卷。

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

取消现有块存储卷
```
 bluemix sl block volume-cancel VOLUME_ID [OPTIONS]
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
 bluemix sl block volume-cancel 12345678 --immediate -f
```
此命令立即取消标识为 `12345678` 的卷，而不要求确认。

### bluemix sl block volume-detail
{: #sl_block_volume_detail}

显示指定卷的详细信息
```
 bluemix sl block volume-detail VOLUME_ID
```

**示例**：
```
 bluemix sl block volume-detail 12345678
```
此命令显示标识为 `12345678` 的卷的详细信息。

### bluemix sl block volume-list
{: #sl_block_volume_list}

列出块存储器。
```
 bluemix sl block volume-list [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-u, --username</dt>
   <dd>按卷用户名过滤。</dd>
   <dt>-d, --datacenter</dt>
   <dd>按数据中心短名称过滤。</dd>
   <dt>-t, --storage-type</dt>
   <dd>按存储卷类型过滤。选项为：`performance` 和 `endurance`。</dd>
   <dt>--order</dt>
   <dd>按购买了块存储器的订单的标识过滤。</dd>
   <dt>--sortby</dt>
   <dd>要按其排序的列，选项为：id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、active_transactions 或 created_by。</dd>
   <dt>--columns</dt>
   <dd>要显示的列，选项为：id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr 或 created_by。</dd>
   </dl>

**示例**：
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
此命令列出当前帐户中位于 dal09 的所有耐久性卷，并按容量对其排序。


### bluemix sl block volume-order
{: #sl_block_volume_order}

订购块存储卷
```
   bluemix sl block volume-order [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--storage-type</dt>
   <dd>存储卷的类型 [必需]，选项为：performance 或 endurance。</dd>
   <dt>--size</dt>
   <dd>存储卷大小 (GB)[必需]</dd>
   <dt>--iops</dt>
   <dd>性能存储器 IOPs，介于 100 到 6000 之间，是 100 的倍数 [storage-type 为 performance 时是必需的]</dd>
   <dt>--tier</dt>
   <dd>耐久性存储器层 (IOP/GB) [storage-type 为 endurance 时是必需的]，选项为：0.25、2、4 或 10</dd>
   <dt>--os-type</dt>
   <dd>操作系统 [必需]，选项为：HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS 或 XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>数据中心短名称 [必需]</dd>
   <dt>--snapshot-size</dt>
   <dd>用于随耐久性块存储器一起订购快照空间的可选参数；指定要订购的快照空间大小（以 GB 为单位）</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>


**示例**：

```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
此命令订购性能卷，大小为 1000 GB，IOPS 为 4000，操作系统类型为 LINUX，位于 dal09。
```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```
此命令订购耐久性卷，卷的大小为 500 GB，层级为 4 IOPS/GB，操作系统为 XEN，位于 dal09，还有额外快照空间大小 500 GB。


### bluemix sl block volume-options
{: #sl_block_volume_options}

列出用于订购块存储器的所有选项
```
 bluemix sl block volume-options
```

**示例**：
```
 bluemix sl block volume-options
```
此命令列出用于创建块存储卷的所有选项，包括存储器类型、卷大小、操作系统类型、IOPS、层级、数据中心和快照大小。


### bluemix sl dns import
{: #sl_dns_import}

导入基于 BIND 区域文件的区域。
```
bluemix sl dns import [OPTIONS] ZONEFILE
```
<strong>命令选项</strong>：

   <dl>
   <dt>--dry-run</dt>
   <dd>实际不创建记录。</dd>
    </dl>

**示例**：
```
 bluemix sl dns import ~/blumix.net.txt
```
此命令从 `~/blumix.net.txt` 文件导入区域及其资源记录。

### bluemix sl dns record-add
{: #sl_dns_record_add}
添加资源记录。

```
bluemix sl dns record-add [OPTIONS] ZONE RECORD TYPE DATA
```
<strong>命令选项</strong>：

   <dl>
   <dt>--ttl</dt>
   <dd>TTL 值（以秒为单位），例如 86400 [缺省值：7200]。</dd>
    </dl>

**示例**：
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
此命令将 A 记录添加到区域 bluemix.net，其主机为 `ftp`，数据为 `127.0.0.1`，ttl 为 86400 秒。

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

更新区域中的资源记录。
```
   bluemix sl dns record-edit ZONE [OPTIONS]
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
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
此命令编辑区域 `bluemix.net` 下标识为 `12345678` 的记录，并将其数据设置为 `127.0.0.2`，ttl 设置为 3600。

```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```
此命令编辑区域 `bluemix.net` 下主机名为 `kibana` 的记录，并将 ttl 全部设置为 3600。

### bluemix sl dns record-list
{: #sl_dns_record_list}

列出区域中的所有资源记录

```
   bluemix sl dns record-list ZONE [OPTIONS]
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
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
此命令列出区域 `bluemix.net` 下的所有 A 记录，依据其过滤的主机为 `elasticsearch`，ttl 为 900 秒。

### bluemix sl dns record-remove
{: #sl_dns_record_remove}

除去区域中的资源记录
```
 bluemix sl dns record-remove RECORD_ID
```

**示例**：
```   
 bluemix sl dns record-remove 12345678
```
此命令除去标识为 `12345678` 的资源记录。

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

创建区域。
```
 bluemix sl dns zone-create ZONE
```
**示例**：
```
 bluemix sl dns zone-create bluemix.net
```
此命令创建名为 `bluemix.net` 的区域。

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

删除区域。
```
 bluemix sl dns zone-delete ZONE
```
**示例**：
```
 bluemix sl dns zone-delete bluemix.net
```
此命令删除名为 `bluemix.net` 的区域。

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

列出帐户的所有区域
```
   bluemix sl dns zone-list
```
**示例**：
```
   bluemix sl dns zone-list
```
此命令列出当前帐户下的所有区域。

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

以 BIND 格式显示区域和资源记录
```
 bluemix sl dns zone-print ZONE
```

**示例**：
```
 bluemix sl dns zone-print bluemix.net
```
此命令以 BIND 格式显示名为 bluemix.net 的区域。


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

为目标路由器或设备分配全局 IP。
```
 bluemix sl globalip assign [OPTIONS] IDENTIFIER TARGET
```
**示例**：
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
此命令将标识为 12345678 的 IP 地址分配给 IP 地址为 9.111.123.456 的目标设备。


### bluemix sl globalip-create
{: #sl_globalip_create}

创建全局 IP。
```
bluemix sl globalip-create [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--v6</dt>
   <dd>订购 IPv6 IP。</dd>
   <dt>--test</dt>
   <dd>测试订单。</dd>
    <dt>-f, --force</dt>
   <dd>创建全局 IP 而不确认。</dd>
    </dl>

**示例**：
```
     bluemix sl globalip create --v6
```
此命令创建 IP V6 地址。

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

取消全局 IP。
```
bluemix sl globalip-cancel [OPTIONS] IDENTIFIER
```
<strong>命令选项</strong>：

   <dl>
    <dt>-f, --force</dt>
   <dd>取消全局 IP 而不确认。</dd>
    </dl>

**示例**：
```
 bluemix sl globalip cancel 12345678
```
此命令取消标识为 `12345678` 的 IP 地址。

### bluemix sl globalip-list
{: #sl_globalip_list}

列出所有全局 IP。
```
bluemix sl globalip-list [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--v4</dt>
   <dd>仅显示 IPv4 IP。</dd>
   <dt>--v6</dt>
   <dd>仅显示 IPv6 IP。</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

从目标路由器或设备取消分配全局 IP
```
 bluemix sl globalip unassign IDENTIFIER
```
**示例**：
```
 bluemix sl globalip unassign 12345678
```
此命令从目标设备取消分配标识为 `12345678` 的 IP 地址。


### bluemix sl image delete
{: #sl_dns_image_delete}

删除映像。
```
   bluemix sl image delete IDENTIFIER
```
**示例**：
```
   bluemix sl image delete 12345678
```
此命令删除标识为 `12345678` 的映像。

### bluemix sl image detail
{: #sl_dns_image_detail}

获取映像的详细信息。
```
 bluemix sl image detail IDENTIFIER
```
**示例**：
```
 bluemix sl image detail 12345678
```
此命令获取标识为 12345678 的映像的详细信息。

### bluemix sl image edit
{: #sl_dns_image_edit}

编辑映像的详细信息
```
   bluemix sl image edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--name</dt>
   <dd>映像的名称。</dd>
   <dt>--note</dt>
   <dd>映像的其他注释。</dd>
   <dt>--tag</dt>
   <dd>映像的标记。</dd>
   </dl>


**示例**：
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
此命令编辑标识为 `12345678` 的映像，并将其名称设置为 `ubuntu16`，注释设置为 `testing`，标记设置为 `staging`。


### bluemix sl image edit
{: #sl_dns_image_edit}

编辑映像的详细信息
```
   bluemix sl image edit [OPTIONS] IDENTIFIER
```

<strong>命令选项</strong>：
   <dl>
   <dt>--name</dt>
   <dd>映像的名称。</dd>
   <dt>--note</dt>
   <dd>映像的其他注释。</dd>
   <dt>--tag</dt>
   <dd>映像的标记。</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

列出帐户的所有映像
```
   bluemix sl image list [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--name</dt>
   <dd>过滤映像名称。</dt>
   <dd>--public</dt>
   <dd>仅显示公用映像。</dd>
   <dt>--private</dt>
   <dd>仅显示专用映像。</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

取消现有 iSCSI 卷
```
   bluemix sl iscsi cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--reason</dt>
   <dd>可选的取消原因。</dd>
   <dt>--immediate</dt>
   <dd>立即取消 iSCSI，而不是在计费周年取消。</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

创建 iSCSI 卷
```
   bluemix sl iscsi create [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--size</dt>
   <dd>要创建的 iSCSI 卷的大小（以吉比字节为单位）[必需]</dd>
   <dt>--datacenter</dt>
   <dd>数据中心短名称 [必需]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

获取 iSCSI 卷的详细信息
```
   bluemix sl iscsi detail IDENTIFIER [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--password</dt>
   <dd>显示用于访问 iSCSI 目标的凭证。</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

列出 iSCSI 卷
```
 bluemix sl iscsi list [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--order</dt>
   <dd>购买此 iSCSI 存储器的订单的标识</dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

取消/删除 iSCSI 快照
```
 bluemix sl iscsi snapshot-cancel IDENTIFIER [OPTIONS]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

创建 iSCSI 卷的快照
```
   bluemix sl iscsi snapshot-create IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--notes</dt>
   <dd>快照的可选注释。</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

为给定 iSCSI 卷订购快照空间
```
 bluemix sl iscsi snapshot-create-space IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--capacity</dt>
   <dd>要创建的快照空间的大小。</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

列出 iSCSI 卷的快照
```
 bluemix sl iscsi snapshot-list IDENTIFIER [OPTIONS]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

添加新的 SSH 密钥
```
 bluemix sl security sshkey-add LABEL [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --in-file</dt>
   <dd>要为此密钥导入的 id_rsa.pub 文件</dd>
   <dt>-k, --key</dt>
   <dd>实际 SSH 密钥</dd>
   <dt>--note</dt>
   <dd>将与密钥关联的额外注释</dd>
   </dl>


**示例**：
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
此命令从 ~/.ssh/id_rsa.pub 文件添加 SSH 密钥，注释为“mykey”。

### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

编辑 SSH 密钥
```
 bluemix sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--label</dt>
   <dd>密钥的新标签</dd>
   <dt>--note</dt>
   <dd>密钥的新注释</dd>
   </dl>


**示例**：
```
 bluemix sl security sshkey-edit 12345678 --label Bluemix --note testing
```
此命令更新标识为 12345678 的 SSH 密钥，并将标签设置为“Bluemix”，注释设置为“testing”。

### bluemix sl security sshkey-list
{: #sl_security_sshkey_list}

列出帐户的 SSH 密钥
```
 bluemix sl security sshkey-list [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--sortby</dt>
   <dd>要按其排序的列，选项为：`id`、`label`、`fingerprint` 或 `notes`。</dd>
   </dl>


**示例**：
```
 bluemix sl security sshkey-list --sortby label
```
此命令列出当前帐户的所有 SSH 密钥，并按标签对其排序。

### bluemix sl security sshkey-print
{: #sl_security_sshkey_print}

将 SSH 密钥输出到屏幕
```
 bluemix sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --out-file</dt>
   <dd>公用 SSH 密钥将写入此文件。</dd>
   </dl>


**示例**：
```
 bluemix sl security sshkey-print 12345678 -f ~/mykey.pub
```
此命令显示标识为 12345678 的 SSH 密钥的标识、标签和注释，并将公用密钥写入 ~/mykey.pub 文件。

### bluemix sl security sshkey-remove
{: #sl_security_sshkey_remove}

永久除去 SSH 密钥
```
 bluemix sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>


**示例**：
```
 bluemix sl security sshkey-remove 12345678 -f
```
此命令除去标识为 12345678 的 SSH 密钥，而不要求确认。

### bluemix sl security cert-add
{: #sl_security_cert_add}

添加和上传 SSL 证书详细信息
```
 bluemix sl security cert-add [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--crt</dt>
   <dd>证书文件</dd>
   <dt>--csr</dt>
   <dd>证书签名请求文件</dd>
   <dt>--icc</dt>
   <dd>中间证书文件</dd>
   <dt>--key</dt>
   <dd>专用密钥文件</dd>
   <dt>--notes</dt>
   <dd>其他注释</dd>
   </dl>


**示例**：
```
 bluemix sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key 
```
此命令为域 bluemix.net 添加证书文件 ~/bluemix.net.cert 和专用密钥文件 ~/bluemix.net.key。

### bluemix sl security cert-edit
{: #sl_security_cert_edit}

编辑 SSL 证书
```
 bluemix sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--crt</dt>
   <dd>证书文件</dd>
   <dt>--csr</dt>
   <dd>证书签名请求文件</dd>
   <dt>--icc</dt>
   <dd>中间证书文件</dd>
   <dt>--key</dt>
   <dd>专用密钥文件</dd>
   <dt>--notes</dt>
   <dd>其他注释</dd>
   </dl>


**示例**：
```
 bluemix sl security cert-edit 12345678 --key ~/bluemix.net.key
```
此命令编辑标识为 12345678 的证书，并使用 ~/bluemix.net.key 文件更新其专用密钥。

### bluemix sl security cert-download
{: #sl_security_cert_download}

下载 SSL 证书和密钥文件
```
 bluemix sl security cert-download IDENTIFIER
```

**示例**：
```
 bluemix sl security cert-download 12345678
```
此命令将 4 个文件下载到标识为 12345678 的证书所在的当前目录。这 4 个文件为：证书文件、证书签名请求文件、中间证书文件和专用密钥文件。

### bluemix sl security cert-list
{: #sl_security_cert_list}

列出帐户的 SSL 证书
```
 bluemix sl security cert-list [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--status</dt>
   <dd>显示具有此状态的证书，缺省值为：all，选项为：`all`、`valid` 或 `expired`</dd>
   <dt>--sortby</dt>
   <dd>要按其排序的列，选项为：`id`、`common_name`、`days_until_expire` 或 `notes`</dd>
   </dl>


**示例**：
```
 bluemix sl security cert-list --status valid --sortby days_until_expire
```
此命令列出当前帐户的所有有效证书，并按有效天数对其排序。

### bluemix sl security cert-remove
{: #sl_security_cert_remove}

除去 SSL 证书
```
 bluemix sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt> -f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>


**示例**：
```
 bluemix sl security cert-remove 12345678
```
此命令除去标识为 12345678 的证书。

### bluemix sl subnet cancel
{: #sl_subnet_cancel}

取消子网。
```
 bluemix sl subnet cancel [OPTIONS] IDENTIFIER
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
    </dl>


**示例**：
```
 bluemix sl subnet cancel 12345678 -f
```
此命令取消标识为 12345678 的子网，而不要求确认。

### bluemix sl subnet create
{: #sl_subnet_create}

向帐户添加新的子网。
```
   bluemix sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

有效数量根据类型而变化。

 * Type - 有效数量 (IPv4)**，public - 4、8、16 或 32**，private - 4、8、16、32 或 64
 * Type - 有效数量 (IPv6)，** public - 64

<strong>命令选项</strong>：
   <dl>
   <dt>--v6, --ipv6</dt>
   <dd>订购 IPv6 地址。</dd>
   <dt>--test</dt>
   <dd>不订购子网；只获取报价。</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>

**示例**：
```
 bluemix sl subnet create public 16 567
```
此命令创建具有 16 个 IP v4 地址的公共子网，并会将其放在标识为 567 的 VLAN 上。


### bluemix sl subnet detail
{: #sl_subnet_detail}

获取子网的详细信息。
```
   bluemix sl subnet detail IDENTIFIER [OPTIONS]
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
 bluemix sl subnet detail 12345678
```
此命令显示有关标识为 12345678 的子网的详细信息，包括虚拟服务器和硬件服务器信息。


### bluemix sl subnet-list
{: #sl_subnet_list}

列出帐户的所有子网
```
   bluemix sl subnet list [OPTIONS]
```


<strong>命令选项</strong>：
   <dl>
   <dt>--sortby</dt>
   <dd>要按其排序的列。选项为：id、identifier、type、network_space、datacenter、vlan_id、IPs、hardware 或 vs。</dd>
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
   <dd>按购买子网的订单的标识过滤</dd>
   </dl>

**示例**：
```
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
此命令列出当前帐户的 IP V4 子网，依据以下条件进行过滤：数据中心为 dal09，子网类型为 PRIMARY，网络空间为 PUBLIC。



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

查找 IP 地址并显示其子网和设备信息
```
   bluemix sl subnet lookup IP_ADDRESS
```

**示例**：
```
 bluemix sl subnet lookup 9.125.235.255
```
此命令查找地址为 9.125.235.255 的 IP 地址记录，并显示其子网和设备信息。


### bluemix sl vs cancel
{: #sl_vs_cancel}

取消虚拟服务器实例
```
   bluemix sl vs cancel IDENTIFIER [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>

**示例**：
```
 bluemix sl vs cancel 12345678
```
此命令取消标识为 12345678 的虚拟服务器实例。


### bluemix sl vs capture
{: #sl_vs_capture}

将虚拟服务器实例捕获到映像中
```
 bluemix sl vs capture IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-n, --name</dt>
   <dd>映像的名称 [必需]。</dd>
   <dt>--all</dt>
   <dd>捕获属于 VS 的所有磁盘。</dd>
   <dt>--note</dt>
   <dd>添加要与映像关联的注释。</dd>
   </dl>

**示例**：
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
此命令将标识为 12345678 的虚拟服务器实例中的所有磁盘捕获到映像“mybluemix”中，注释为“testing”。



### bluemix sl vs create
{: #sl_vs_create}

创建虚拟服务器实例
```
   bluemix sl vs create [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-H, --hostname</dt>
   <dd>FQDN 的主机部分 [必需]</dd>
   <dt>-D, --domain</dt>
   <dd>FQDN 的域部分 [必需]</dd>
   <dt>-c, --cpu</dt>
   <dd>CPU 核心数 [必需]</dd>
   <dt>-m, --memory</dt>
   <dd>内存（以兆字节为单位）[必需]</dd>
   <dt>-d, --datacenter</dt>
   <dd>数据中心短名称 [必需]</dd>
   <dt>-o, --os</dt>
   <dd>操作系统安装代码。提示：可以指定 <OS>_LATEST</dd>
   <dt>--image</dt>
   <dd>映像标识。请参阅 [bluemix sl image list](#bluemix_sl_image_list) 以获取参考信息</dd>
   <dt>--billing</dt>
   <dd>计费费率。缺省值为：hourly。选项为：hourly 或 monthly。</dd>
   <dt>--dedicated</dt>
   <dd>创建专用虚拟服务器（专用节点）</dd>
   <dt>--san</dt>
   <dd>使用 SAN 存储器（而非本地磁盘）</dd>
   <dt>--test</dt>
   <dd>实际不创建虚拟服务器</dd>
   <dt>--export</dt>
   <dd>将选项导出到模板文件</dd>
   <dt>-i, --postinstall</dt>
   <dd>要下载的安装后脚本</dd>
   <dt>-k, --key</dt>
   <dd>要添加到 root 用户的 SSH 密钥的标识（允许多次出现）</dd>
   <dt>--disk</dt>
   <dd>磁盘大小（允许多次出现）</dd>
   <dt>--private</dt>
   <dd>强制虚拟服务器只有权访问专用网络</dd>
   <dt>--like</dt>
   <dd>使用现有虚拟服务器中的配置</dd>
   <dt>-n, --network</dt>
   <dd>网络端口速度（以 Mbps 为单位）</dd>
   <dt>--tag</dt>
   <dd>要添加到实例的标记（允许多次出现）</dd>
   <dt>-t, --template</dt>
   <dd>对命令行选项使用缺省值的模板文件</dd>
   <dt>-u, --userdata</dt>
   <dd>用户定义的元数据字符串</dd>
   <dt>-F, --userfile</dt>
   <dd>从文件中读取用户数据</dd>
   <dt>--vlan-public</dt>
   <dd>要将虚拟服务器放到其中的公共 VLAN 的标识</dd>
   <dt>--vlan-private</dt>
   <dd>要将虚拟服务器放到其中的专用 VLAN 的标识</dd>
   <dt>--wait</dt>
   <dd>等待虚拟服务器完成供应（最长 X 秒）后再返回</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
	</dl>

**示例**：
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
此命令订购虚拟服务器实例，其中主机名为 myvsi，域为 bluemix.net，4 个 CPU 核心，4096M 内存，位于数据中心 dal10，操作系统为 UBUNTU 16（64 位），2 个磁盘（一个 100G，另一个 1000G），位于标识为 413 的公共 VLAN 上。
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
此命令用于在实际下达使用上述选项的订单之前，测试该订单是否有效。
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

此命令将上述选项导出到用户主目录下的文件 myvsi.txt 中，以供以后使用。


### bluemix sl vs options
{: #sl_vs_options}

列出用于创建虚拟服务器实例的选项
```
   bluemix sl vs options [OPTIONS]
```

**示例**：
```
 bluemix sl vs options
```
此命令列出用于创建虚拟服务器实例的所有选项，例如，数据中心、CPU、内存、操作系统、磁盘、网络速度等。



### bluemix sl vs credentials
{: #sl_vs_credentials}

列出虚拟服务器实例凭证
```
   bluemix sl vs credentials IDENTIFIER [OPTIONS]
```
**示例**：
```
 bluemix sl vs credentials 12345678
```
此命令列出标识为 12345678 的虚拟服务器实例的所有用户名和密码对。

### bluemix sl vs detail
{: #sl_vs_detail}

获取虚拟服务器实例的详细信息
```
   bluemix sl vs detail IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--passwords</dt>
   <dd>显示密码。</dd>
   <dt>--price</dt>
   <dd>显示关联的价格。</dd>
   </dl>


**示例**：
```
   bluemix sl vs details 12345678
```
此命令列出有关标识为 12345678 的虚拟服务器实例的详细信息。


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

同步虚拟服务器实例的 DNS 记录
```
   bluemix sl vs dns-sync IDENTIFIER [OPTIONS]
```
注：如果未指定任何自变量，那么此命令将试图同时更新 A 和 PTR 记录。如果不想同时更新这两个记录，可使用 -a 或 --ptr 自变量来限制更新的记录。

<strong>命令选项</strong>：
   <dl>
   <dt>-a, --a-record</dt>
   <dd>同步主机的 A 记录</dd>
   <dt>--aaaa-record</dt>
   <dd>同步主机的 AAAA 记录</dd>
   <dt>--ptr</dt>
   <dd>同步主机的 PTR 记录</dd>
   <dt>--ttl</dt>
   <dd>为 A 和/或 PTR 记录设置 TTL，缺省值为：7200</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>


**示例**：
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
此命令将标识为 12345678 的虚拟服务器实例的 A 记录（IP V4 地址）与 DNS 服务器同步，并将此 A 记录的 ttl 设置为 3600。
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
此命令将标识为 12345678 的虚拟服务器实例的 AAAA 记录（IP V6 地址）和 PTR 记录同时与 DNS 服务器同步。


### bluemix sl vs edit
{: #sl_vs_edit}

编辑虚拟服务器实例的详细信息
```
   bluemix sl vs edit IDENTIFIER [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>-D, --domain</dt>
   <dd>FQDN 的域部分</dd>
   <dt>-H, --hostname</dt>
   <dd>FQDN 的主机部分。示例：server</dd>
   <dt>--tag</dt>
   <dd>要设置的标记，或使用空字符串表示全部除去</dd>
   <dt>-u, --userdata</dt>
   <dd>用户定义的元数据字符串</dd>
   <dt>-F, --userfile</dt>
   <dd>从文件中读取用户数据</dd>
   <dt>--public-speed</dt>
   <dd>公用端口速度，选项为：0、10、100、1000 或 10000</dd>
   <dt>--private-speed</dt>
   <dd>专用端口速度，选项为：0、10、100、1000 或 10000</dd>
   </dl>

**示例**：
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
此命令更新标识为 `12345678` 的虚拟服务器实例，并将其域设置为 `bluemix.net`，主机名设置为 `myapp`，标记设置为 `testcli`，公用网络端口速度设置为 1000 Mbps。



### bluemix sl vs list
{: #sl_vs_list}
列出帐户的虚拟服务器实例
```
   bluemix sl vs list [OPTIONS]
```


<strong>命令选项</strong>：
   <dl>
   <dt>-c, --cpu</dt>
   <dd>CPU 核心数</dd>
   <dt>-D, --domain</dt>
   <dd>FQDN 的域部分</dd>
   <dt>-d, --datacenter</dt>
   <dd>数据中心短名称</dd>
   <dt>-H, --hostname</dt>
   <dd>FQDN 的主机部分</dd>
   <dt>-m, --memory</dt>
   <dd>内存（以兆字节为单位）</dd>
   <dt>-n, --network</dt>
   <dd>网络端口速度（以 Mbps 为单位）</dd>
   <dt>--hourly</dt>
   <dd>仅显示每小时实例</dd>
   <dt>--monthly</dt>
   <dd>仅显示每月实例</dd>
   <dt>--tag</dt>
   <dd>按标记过滤（允许多次出现）</dd>
   <dt>--sortby</dt>
   <dd>要按其排序的列，选项为：id、hostname、domain、datacenter、cpu、memory、primary_ip 或 backend_ip。缺省值为：hostname</dd>
   <dt>--columns</dt>
   <dd>要显示的列，选项为：guid、primary_ip、backend_ip、datacenter、action、power_state、created_by 或 tags。缺省值为：id、hostname、primary_ip、backend_ip、datacenter 或 action</dd>
    </dl>

**示例**：
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
此命令列出当前帐户的所有每小时计费的虚拟服务器实例，依据其过滤的域为“bluemix.net”域，并按内存对其排序。



### bluemix sl vs-pause
{: #sl_vs_pause}

暂停活动的虚拟服务器实例
```
   bluemix sl vs pause IDENTIFIER [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
    </dl>

**示例**：
```
 bluemix sl vs pause 12345678 -f
```
此命令暂停标识为 12345678 的虚拟服务器实例，而不要求确认。



### bluemix sl vs power-off
{: #sl_vs_power_off}

关闭活动虚拟服务器实例的电源
```
   bluemix sl vs power-off IDENTIFIER [OPTIONS]
```

**示例**：
```
   bluemix sl vs power-off 12345678 --soft
```
此命令对标识为 12345678 的虚拟服务器实例执行软电源关闭操作。

<strong>命令选项</strong>：
   <dl>
   <dt>--hard</dt>
   <dd>执行硬关闭</dd>
   <dt>--soft</dt>
   <dd>执行软关闭</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

打开虚拟服务器实例的电源
```
 bluemix sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
    </dl>

**示例**：
```
 bluemix sl vs power-on 12345678
```
此命令对标识为 12345678 的虚拟服务器实例执行打开电源操作。


### bluemix sl vs ready
{: #sl_vs_ready}

检查虚拟服务器实例是否准备就绪可供使用
```
 bluemix sl vs ready IDENTIFIER [OPTIONS]
```

**示例**：
```
 bluemix sl vs ready 12345678 --wait 30
```
此命令检查标识为 12345678 的虚拟服务器实例的状态以确定其是否准备就绪可持续使用，并且最长等待 30 秒。

<strong>命令选项</strong>：
   <dl>
   <dt>--wait</dt>
   <dd>等待虚拟服务器完成供应（最长 X 秒）后再返回</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

重新引导活动的虚拟服务器实例
```
 bluemix sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--hard</dt>
   <dd>执行硬重新引导</dd>
   <dt>--soft</dt>
   <dd>执行软重新引导</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
    </dl>

**示例**：
```
 bluemix sl vs reboot 12345678 --hard
```
此命令对标识为 12345678 的虚拟服务器实例执行硬重新引导。



### bluemix sl vs reload
{: #sl_vs_reload}

在虚拟服务器实例上重新装入操作系统
```
 bluemix sl vs reload IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>要下载的安装后脚本</dd>
   <dt>--image</dt>
   <dd>映像标识。缺省值为使用当前操作系统。请参阅“bluemix sl image list”以获取参考信息</dd>
   <dt>-k, --key</dt>
   <dd>要添加到 root 用户的 SSH 密钥的标识（允许多次出现）</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
    </dl>

**示例**：
```
   bluemix sl vs reload 12345678
```
此命令为标识为 12345678 的虚拟服务器实例重新装入当前操作系统。
```
 bluemix sl vs reload 12345678 --image 1234
```
此命令为标识为 12345678 的虚拟服务器实例从标识为 1234 的映像重新装入操作系统。



### bluemix sl vs rescure
{: #sl_vs_rescure}

将虚拟服务器实例重新引导到拯救映像
```
 bluemix sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
   </dl>
   
**示例**：
```
 bluemix sl vs rescue 12345678
```
此命令将标识为 12345678 的虚拟服务器实例重新引导到拯救映像。


### bluemix sl vs resume
{: #sl_vs_resume}

恢复暂停的虚拟服务器实例
```
   bluemix sl vs resume IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
    </dl>

**示例**：
```
 bluemix sl vs resume 12345678
```
此命令恢复标识为 12345678 的虚拟服务器实例。


### bluemix sl vs upgrade
{: #sl_vs_upgrade}

升级虚拟服务器实例
```
   bluemix sl vs upgrade IDENTIFIER [OPTIONS]
```
注：一旦发出升级请求后，SoftLayer 会自动重新引导实例。此实例在升级事务完成之前会一直停止。但是，对于网络，无需重新引导。

<strong>命令选项</strong>：
   <dl>
   <dt>-c, --cpu</dt>
   <dd>CPU 核心数</dd>
   <dt>--private</dt>
   <dd>CPU 核心将位于专用主机服务器上。</dd>
   <dt>-m, --memory</dt>
   <dd>内存（以兆字节为单位）。</dd>
   <dt>--network</dt>
   <dd>网络端口速度（以 Mbps 为单位）。</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认。</dd>
    </dl>

**示例**：
```
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
此命令升级标识为 12345678 的虚拟服务器实例，并将 CPU 核心数设置为 8，内存设置为 8192M，网络端口速度设置为 1000 Mbps。



### bluemix sl vlan create
{: #sl_vlan_create}

创建新的 VLAN
```
   bluemix sl vlan create [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>VLAN 的类型：public 或 private</dd>
   <dt>-r, --router</dt>
   <dd>路由器的主机名</dd>
   <dt>-d, --datacenter</dt>
   <dd>数据中心的短名称</dd>
   <dt>-s, --size</dt>
   <dd>子网的大小，选项为：8（5 个可用 IP）、16（13 个可用 IP）或 32（29 个可用 IP）</dd>
   <dt>-n, --name</dt>
   <dd>VLAN 的名称</dd>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
    </dl>

**示例**：
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
此命令创建公共 VLAN，它位于具有 16 个 IP 地址的数据中心 dal09，名称为 myvlan。
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
此命令创建 VLAN，它位于具有 16 个 IP 地址的路由器 bcr01a.dal09 上，名称为 myvlan。



### bluemix sl vlan cancel
{: #sl_vlan_cancel}

取消 VLAN
```
   bluemix sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>-f, --force</dt>
   <dd>强制操作而不确认</dd>
    </dl>

**示例**：
```
   bluemix sl vlan cancel 12345678 -f
```
此命令取消标识为 12345678 的 VLAN，而不要求确认。



### bluemix sl vlan detail
{: #sl_vlan_detail}

获取有关 VLAN 的详细信息。
```
   bluemix sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>命令选项</strong>：
   <dl>
   <dt>--no-vs</dt>
   <dd>隐藏虚拟服务器列表</dd>
   <dt>--no-hardware</dt>
   <dd>隐藏硬件列表</dd>
   </dl>

**示例**：
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
此命令显示标识为 12345678 的 VLAN 的详细信息，但不列出虚拟服务器或硬件服务器。



### bluemix sl vlan edit
{: #sl_vlan_edite}

编辑有关 VLAN 的详细信息
```
   bluemix sl vlan edit IDENTIFIER [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--n, --name</dt>
   <dd>VLAN 的名称</dd>
    </dl>

**示例**：
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
此命令更新标识为 12345678 的 VLAN，并将其命名为新名称“myvlan-rename”。


### bluemix sl vlan list
{: #sl_vlan_list}

列出帐户的所有 VLAN
```
 bluemix sl vlan list [OPTIONS]
```
<strong>命令选项</strong>：

   <dl>
   <dt>--sortby</dt>
   <dd>要按其排序的列，选项为：id、number、name、firewall、datacenter、hardware、virtual_servers 或 public_ips。</dd>
   <dt>-d, --datacenter</dt>
   <dd>按数据中心短名称过滤</dd>
   <dt>-n, --number</dt>
   <dd>按 VLAN 编号过滤</dd>
   <dt>--name</dt>
   <dd>按 VLAN 名称过滤</dd>
   <dt>--order</dt>
   <dd>按购买 VLAN 的订单的标识过滤</dd>
   </dl>

**示例**：
```
 bluemix sl vlan list -d dal09 --sortby number
```
此命令列出当前帐户的所有 VLAN，依据其过滤的数据中心为 dal09，并按 VLAN 编号对其排序。




### bluemix sl vlan options
{: #sl_vlan_options}

列出用于创建 VLAN 的所有选项
```
   bluemix sl vlan options
```
**示例**：
```
 bluemix sl vlan options
```
此命令列出用于创建 VLAN 的所有选项，例如 VLAN 类型、数据中心、子网大小、路由器等。
