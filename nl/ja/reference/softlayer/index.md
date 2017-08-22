---

copyright:

  years: 2016,2017

lastupdated: "2017-06-27"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# {{site.data.keyword.BluSoftlayer_notm}} (bluemix sl) コマンド
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} プラグインは、{{site.data.keyword.Bluemix_notm}} CLI にマージされました。このプラグインのインストールは必要なくなりました。

{{site.data.keyword.Bluemix_notm}} コマンド・ライン・インターフェース (CLI) で {{site.data.keyword.BluSoftlayer_notm}} コマンドを使用して、SoftLayer のサービスを管理および構成します。


まず、IBM {{site.data.keyword.Bluemix_notm}} CLI をインストールします。 詳しくは、『[Bluemix CLI ![「外部リンク」アイコン](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}』を参照してください。

{{site.data.keyword.Bluemix_notm}} コマンドの完全リストについては、[{{site.data.keyword.Bluemix_notm}} (bx) コマンド](docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_cli)を参照してください。


## {{site.data.keyword.BluSoftlayer_notm}} の汎用コマンド

以下のコマンドがサポートされます。使用可能なコマンドのリストを表示するには、`bluemix sl` コマンドを使用します。

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用コマンド">
<caption>表 1. 汎用 Softlayer コマンド</caption>
 <thead>
 <th colspan="6">汎用 Softlayer コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[bluemix sl init](/docs/cli/reference/softlayer/index.html#sl_init)</td>
 <td>[bluemix sl help](/docs/cli/reference/softlayer/index.html#sl_help)</td>
   </tbody>
 </table>


## {{site.data.keyword.BluSoftlayer_notm}} ブロック・ストレージ・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 2. Softlayer ブロック・ストレージ</caption>
 <thead>
 <th colspan="6">Softlayer ブロック・ストレージ</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} dns コマンド

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>Table 3. Softlayer dns コマンド</caption>
 <thead>
 <th colspan="6">Softlayer dns コマンド</th>
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

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 4. Softlayer グローバル IP アドレス</caption>
 <thead>
 <th colspan="6">Softlayer グローバル IP アドレス</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} イメージ・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 5. Softlayer イメージ・コマンド</caption>
 <thead>
 <th colspan="6">Softlayer イメージ・コマンド</th>
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
 
## {{site.data.keyword.BluSoftlayer_notm}} レガシー ISCSI ストレージ・コマンド

  <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 6. Softlayer レガシー ISCSI ストレージ・コマンド</caption>
 <thead>
 <th colspan="6">Softlayer レガシー ISCSI ストレージ・コマンド</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} セキュリティー・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 7. Softlayer セキュリティー・コマンド</caption>
 <thead>
 <th colspan="5">Softlayer セキュリティー・コマンド</th>
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

## {{site.data.keyword.BluSoftlayer_notm}} サブネット・コマンド
 
 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 8. Softlayer サブネット・コマンド</caption>
 <thead>
 <th colspan="5">Softlayer サブネット・コマンド</th>
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
 
## {{site.data.keyword.BluSoftlayer_notm}} 仮想サーバー・コマンド

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 9. Softlayer 仮想サーバー・コマンド</caption>
 <thead>
 <th colspan="6">Softlayer 仮想サーバー・コマンド</th>
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
 
## {{site.data.keyword.BluSoftlayer_notm}} VLAN コマンド

  <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 Softlayer コマンド">
<caption>表 10. Softlayer VLAN コマンド</caption>
 <thead>
 <th colspan="6">Softlayer VLAN コマンド</th>
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

### コマンドの使用法
コマンドのヘルプ情報を表示するには、`bluemix sl [command] -h` を実行します。

### bluemix sl init
{: #sl_init}

SoftLayer 環境への接続に使用される構成設定を初期化します。この構成には、ユーザー名、API キーまたはパスワード、アカウント、およびエンドポイントが含まれます。
```
bluemix sl init [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-a,--api-endpoint</dt>
   <dd>Softlayer API エンドポイント URL (デフォルト: https://api.softlayer.com/rest/v3.1)</dd>
   <dt>-u,--sl-user</dt>
   <dd>Softlayer ユーザー名</dd>
   <dt>-p,--sl-password</dt>
   <dd>Softlayer パスワードまたは API キー</dd>
   <dt>-c,--account-id</dt>
   <dd>Softlayer アカウント ID</dd>
   </dl>

例えば、Softlayer のユーザー名とパスワード/API キーを使用してログインします
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
例えば、Bluemix の Single-Sign-On を使用して Softlayer にログインします
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

Softlayer 環境で作動するすべてのコマンドのヘルプ情報を表示します。
```
bluemix sl help

```

### bluemix sl block access-authorize
{: #sl_block_access_authorize}

指定されたボリュームへのホストのアクセスを許可します。
```
bluemix sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--hardware-id</dt>
   <dd>許可する 1 つのハードウェア・サーバーの ID。</dd>
   <dt>--virtual-id</dt>
   <dd>許可する 1 つの仮想サーバーの ID。</dd>
   <dt>--ip-address-id</dt>
   <dd>許可する 1 つの IP アドレスの ID。</dd>
   <dt>--ip-address</dt>
   <dd>許可する IP アドレス。</dd>
    </dl>

**例**:
```
bluemix sl block access-authorize 12345678 --virtual-id 87654321
```
このコマンドは、ID `87654321` の仮想サーバーが、ID `12345678` のボリュームにアクセスすることを許可します。

### bluemix sl block access-list
{: #sl_block_access_list}

ACL をリストします。
```
bluemix sl block access-list VOLUME_ID [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--sortby</dt>
   <dd>ソートの基準とする列。オプション: `id`、`name`、`type`、`private_ip_address`、`host_iqn`、`username`、または `password`。</dd>
   <dt>--columns</dt>
   <dd>  表示する列。オプション:  `id`、`name`、`type`、`private_ip_address`、`host_iqn`、`username`、または `password`。</dd>
</dl>

**例**:
```
bluemix sl block access-list 12345678 --sortby id
```
このコマンドは、ID `12345678` のボリュームへのアクセスを許可されているすべてのホストをリストし、それらを ID によってソートします。

### bluemix sl block access-revoke
{: #sl_block_access_revoke}

指定されたボリュームにアクセスするホストの許可を取り消します。
```
 bluemix sl block access-revoke VOLUME_ID [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--hardware-id</dt>
   <dd>許可する 1 つのハードウェア・サーバーの ID。</dd>
   <dt>--virtual-id</dt>
   <dd>許可する 1 つの仮想サーバーの ID。</dd>
   <dt>--ip-address-id</dt>
   <dd>許可する 1 つの IP アドレスの ID。</dd>
   <dt>--ip-address</dt>
   <dd>許可する IP アドレス。</dd>
    </dl>

**例**:
```
bluemix sl block access-revoke 12345678 --virtual-id 87654321
```
このコマンドは、ID `87654321` の仮想サーバーの、ID  `12345678` のボリュームへのアクセスを取り消します。

### bluemix sl block replica-failback
{: #sl_block_replica_failback}

レプリカからブロック・ボリュームをフェイルバックします。
```
 bluemix sl block replica-failback VOLUME_ID
```
**例**:
```
 bluemix sl block replica-failback 12345678
```
このコマンドは、ID `12345678` のボリュームのフェイルバック操作を実行します。

### bluemix sl block replica-failover
{: #sl_block_replica_failover}

ブロック・ボリュームを、指定されたレプリカ・ボリュームにフェイルオーバーします。
```
bluemix sl block replica-failover VOLUME_ID REPLICA_ID
```

**例**:
```
 bluemix sl block replica-failover 12345678 87654321
```
このコマンドは、ID `12345678` のボリュームの、ID `87654321` のレプリカ・ボリュームへのフェイルオーバー操作を実行します。

### bluemix sl block replica-order
{: #sl_block_replica_order}

ブロック・ストレージ・レプリカ・ボリュームを注文します。
```
 bluemix sl block replica-order VOLUME_ID [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>-s, --snapshot-schedule</dt>
   <dd>必須。レプリカ生成に使用するスナップショット・スケジュール。オプション: `HOURLY`、`DAILY`、または `WEEKLY`。</dd>
   <dt>-d, --datacenter</dt>
   <dd>必須。レプリカ用のデータ・センターの短縮名。例えば、`dal09` など。</dd>
   <dt>--tier</dt>
   <dd>オプション。レプリカが注文されている 1 次ボリュームのエンデュランス・ストレージ層 (1 GB 当たりの IOPS)。オプション: `0.25`、`2`、`4`、または `10`。</dd>
   <dt>--os-type</dt>
   <dd>オプション。レプリカが注文されている 1 次ボリュームのオペレーティング・システム・タイプ。オプション: `HYPER_V`、`LINUX`、`VMWARE`、`WINDOWS_2008`、`WINDOWS_GPT`、`WINDOWS`、または `XEN`。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
    </dl>

**例**:
```
bluemix sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
このコマンドは、ID `12345678` のボリュームのレプリカを注文します。そのレプリカは、毎日の複製を実行し、dal09 にあり、階層レベルは `4` で、OS タイプは `Linux` です。

### bluemix sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

指定されたボリュームの既存のスナップショット・スペースを取り消します。
```
 bluemix sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>取り消しの理由 (オプション)。</dd>
   <dt>--immediate</dt>
   <dd>請求応答日ではなく即時、スナップショット・スペースを取り消します。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
	</dl>

**例**:
```
 bluemix sl block snapshot-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のスナップショットを、確認を要求せず、即時に取り消します。

### bluemix sl block snapshot-create
{: #sl_block_snapshot_create}

指定されたボリュームにスナップショットを作成します。
```
 bluemix sl block snapshot-create VOLUME_ID [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt> -n, --note</dt>
   <dd>新規スナップショットに設定するメモ</dd>
	</dl>

**例**:
```
bluemix sl block snapshot-create 12345678 --note snapshotforbluemix
```
このコマンドは、ID `12345678` のボリュームのスナップショットを、`snapshotforbluemix` の追加メモと共に作成します。

### bluemix sl block snapshot-disable
{: #sl_block_snapshot_disable}

指定されたスケジュールでの指定されたボリュームのスナップショットを無効にします。
```
 bluemix sl block snapshot-disable VOLUME_ID [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>-s, --schedule-type</dt>
   <dd>必須。スナップショットのスケジュール: `HOURLY`、`DAILY`、または `WEEKLY`。</dd>
	</dl>

**例**:
```
 bluemix sl block snapshot-disable 12345678 -s DAILY
```
このコマンドは、ID `12345678` のボリュームの毎日のスナップショットを無効にします。

### bluemix sl block snapshot-enable
{: #sl_block_snapshot_enable}

指定されたスケジュールで指定されたボリュームのスナップショットを有効にします。
```
 bluemix sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-s, --schedule-type</dt>
   <dd>必須。スナップショットのスケジュール: `HOURLY`、`DAILY`、または `WEEKLY`。</dd>
   <dt>-c, --retention-count</dt>
   <dd>必須。保持するスナップショットの数。</dd>
   <dt>-m, --minute</dt>
   <dd>スナップショットを作成する時刻の分の部分。0 から 59 までの整数。</dd>
   <dt>--hour</dt>
   <dd>スナップショットを作成する時刻の時の部分。0 から 23 までの整数。</dd>
   <dt>-d, --day-of-week</dt>
   <dd>スナップショットを作成する曜日。0 から 6 までの整数。0 は日曜、1 は月曜、2 は火曜、3 は水曜、4 は木曜、5 は金曜、6 は土曜を表します。</dd>
	</dl>

**例**:
```
 bluemix sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
このコマンドは、ID `12345678` のボリュームのスナップショットを有効にします。スナップショットは、毎週日曜日の 2:00 に作成され、最大 5 個のスナップショットが保持されます。

### bluemix sl block snapshot-delete
{: #sl_block_snapshot_delete}

指定されたボリュームのスナップショットを削除します。
```
  bluemix sl block snapshot-delete SNAPSHOT_ID
```

**例**:
```
 bluemix sl block snapshot-delete 12345678
```
このコマンドは、ID `12345678` のスナップショットを削除します。

### bluemix sl block snapshot-list
{: #sl_block_snapshot_list}

ブロック・ストレージ・スナップショットをリストします
```
 bluemix sl block snapshot-list VOLUME_ID [OPTIONS]

```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>ソートの基準にする列。オプション: `id`、`name`、`created`、および `size_bytes`。</dd>
	</dl>

**例**:
```
 bluemix sl block snapshot-list 12345678 --sortby id
```
このコマンドは、ID `12345678` のボリュームのすべてのスナップショットをリストし、それらを ID によってソートします。

### bluemix sl block snapshot-order
{: #sl_block_snapshot_order}

ブロック・ストレージ・ボリュームのスナップショット・スペースを注文します。
```
 bluemix sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-s, --size</dt>
   <dd>必須。作成するスナップショット・スペースのサイズ (GB 単位)。</dd>
   <dt>-t, --tier</dt>
   <dd>オプション。スペースが注文されているブロック・ボリュームのエンデュランス・ストレージ層 (1 GB 当たりの IOPS)。オプション: 0.25、2、4、10</dd>
   <dt>-u, --upgrade</dt>
   <dd>この注文がアップグレードであることを示すフラグを立てます。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
	</dl>

**例**:
```
   bluemix sl block snapshot-order 12345678 -s 1000 -t 4
```
このコマンドは、ID `12345678` のボリュームのスナップショット・スペースを注文します。サイズは 1000 GB、階層レベルは 1 GB 当たり 4 IOPS です。


### bluemix sl block snapshot-restore
{: #sl_block_snapshot_restore}

指定されたスナップショットを使用してブロック・ボリュームをリストアします
```
 bluemix sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```

**例**:
```
 bluemix sl block snapshot-restore 12345678 87654321
```
このコマンドは、ID `12345678` のボリュームを、ID `87654321` のスナップショットからリストアします。

### bluemix sl block volume-cancel
{: #sl_block_volume_cancel}

既存のブロック・ストレージ・ボリュームを取り消します
```
 bluemix sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>取り消しの理由 (オプション)。</dd>
   <dt>--immediate</dt>
   <dd>請求応答日ではなく即時、スナップショット・スペースを取り消します。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
	</dl>

**例**:
```
 bluemix sl block volume-cancel 12345678 --immediate -f
```
このコマンドは、ID `12345678` のボリュームを、確認を要求せず、即時に取り消します。

### bluemix sl block volume-detail
{: #sl_block_volume_detail}

指定されたボリュームの詳細を表示します
```
 bluemix sl block volume-detail VOLUME_ID
```

**例**:
```
 bluemix sl block volume-detail 12345678
```
このコマンドは、ID `12345678` のボリュームの詳細を表示します。

### bluemix sl block volume-list
{: #sl_block_volume_list}

ブロック・ストレージをリストします。
```
 bluemix sl block volume-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-u, --username</dt>
   <dd>ボリュームのユーザー名を基準にフィルター操作します。</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
   <dt>-t, --storage-type</dt>
   <dd>ストレージ・ボリュームのタイプを基準にフィルター操作します。オプション: `performance` および `endurance` です。</dd>
   <dt>--order</dt>
   <dd>ブロック・ストレージを購入した注文の ID を基準にフィルター操作します。</dd>
   <dt>--sortby</dt>
   <dd>ソートの基準にする列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、active_transactions、created_by。</dd>
   <dt>--columns</dt>
   <dd>表示する列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、created_by。</dd>
   </dl>

**例**:
```
 bluemix sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
このコマンドは、dal09 にある、現行アカウントのすべてのエンデュランス・ボリュームをリストし、それらを容量によってソートします。


### bluemix sl block volume-order
{: #sl_block_volume_order}

ブロック・ストレージ・ボリュームを注文します
```
   bluemix sl block volume-order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--storage-type</dt>
   <dd>ストレージ・ボリュームのタイプ [必須]。オプション: performance、endurance。</dd>
   <dt>--size</dt>
   <dd>ストレージ・ボリュームのサイズ (GB) [必須]</dd>
   <dt>--iops</dt>
   <dd>パフォーマンス・ストレージの IOP (100 から 6000 までの範囲内の 100 の倍数) [storage-type が performance の場合は必須]</dd>
   <dt>--tier</dt>
   <dd>エンデュランス・ストレージ層 (GB 当たりの IOP) [storage-type が endurance の場合は必須]。オプションは、0.25、2、4、10 です</dd>
   <dt>--os-type</dt>
   <dd>オペレーティング・システム [必須]。オプション: HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS、XEN</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名 [必須]</dd>
   <dt>--snapshot-size</dt>
   <dd>エンデュランス・ブロック・ストレージと共にスナップショット・スペースを注文するためのオプション・パラメーター。注文するスナップショット・スペースのサイズ (GB) を指定します</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>


**例**:

```
 bluemix sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
このコマンドは、サイズが 1000 GB、IOPS が 4000、OS タイプが LINUX、ロケーションが dal09 のパフォーマンス・ボリュームを注文します。

```
 bluemix sl block volume-order --storage-type endurance --size 500 --tier 4 --os-type XEN -d dal09 --snapshot-size 500
```
このコマンドは、サイズが 500 GB、階層レベルが GB 当たり 4 IOPS、OS タイプが XEN、ロケーションが dal09 で、追加スナップショット・スペース・サイズが 500 GB のエンデュランス・ボリュームを注文します。


### bluemix sl block volume-options
{: #sl_block_volume_options}

ブロック・ストレージの注文に関するすべてのオプションをリストします
```
 bluemix sl block volume-options
```

**例**:
```
 bluemix sl block volume-options
```
このコマンドは、ブロック・ストレージ・ボリュームの作成に関するすべてのオプション (ストレージ・タイプ、ボリューム・サイズ、OS タイプ、IOPS、階層レベル、データ・センター、およびスナップショット・サイズ) をリストします。


### bluemix sl dns import
{: #sl_dns_import}

BIND ゾーン・ファイルに基づいてゾーンをインポートします。
```
bluemix sl dns-import [OPTIONS] ZONEFILE
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--dry-run</dt>
   <dd>実際にはレコードを作成しません。</dd>
    </dl>

**例**:
```
 bluemix sl dns import ~/blumix.net.txt
```
このコマンドは、ファイル `~/blumix.net.txt` からゾーンとそのリソース・レコードをインポートします。

### bluemix sl dns record-add
{: #sl_dns_record_add}
リソース・レコードを追加します。

```
bluemix sl dns-record-add [OPTIONS] ZONE RECORD TYPE DATA
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--ttl</dt>
   <dd>TTL 値 (秒)。例えば、86400 [デフォルト: 7200]。</dd>
    </dl>

**例**:
```
 bluemix sl dns record-add bluemix.net ftp A 127.0.0.1 --ttl 86400
```
このコマンドは、A レコードをゾーン bluemix.net に追加します。そのホストは `ftp`、データは `127.0.0.1`、TTL は 86400 秒です。

### bluemix sl dns record-edit
{: #sl_dns_record_edit}

ゾーン内のリソース・レコードを更新します
```
   bluemix sl dns record-edit ZONE [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--by-record</dt>
   <dd>ホスト・レコード (www など) で編集します。</dd>
   <dt>--by-id</dt>
   <dd>単一レコードをその ID で編集します。</dd>
   <dt>--data</dt>
   <dd>レコード・データ (IP アドレスなど)。</dd>
   <dt>--ttl</dt>
   <dd>TTL 値 (秒) (例: 86400)。</dd>
   </dl>

**例**:
```
 bluemix sl dns record-edit bluemix.net --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
このコマンドは、ゾーン `bluemix.net` のレコードを `12345678` で編集し、そのデータを `127.0.0.2` に設定し、TTL を 3600 に設定します。

```
 bluemix sl dns record-edit bluemix.net --by-record kibana --ttl 3600
```
このコマンドは、ゾーン `bluemix.net` のレコードをホスト名 `kibana` で編集し、それらの TTL をすべて 3600 に設定します。


### bluemix sl dns record-list
{: #sl_dns_record_list}

ゾーン内のすべてのリソース・レコードをリストします

```
   bluemix sl dns record-list ZONE [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--data</dt>
   <dd>レコード・データ (IP アドレスなど) を基準にフィルター操作します。</dd>
   <dt>--record</dt>
   <dd>ホスト・レコード (www など) を基準にフィルター操作します。</dd>
   <dt>--ttl</dt>
   <dd>TTL 値 (秒) (例: 86400) を基準にフィルター操作します。</dd>
   <dt>--type</dt>
   <dd>レコード・タイプ (A または CNAME など) を基準にフィルター操作します</dd>
   </dl>

**例**:
```
 bluemix sl dns record-list bluemix.net --record elasticsearch --type A --ttl 900
```
このコマンドは、ゾーン `bluemix.net` のすべての A レコードをリストします。フィルター基準ホストは `elasticsearch` で、TTL は 900 秒です。


### bluemix sl dns record-remove
{: #sl_dns_record_remove}

ゾーンからリソース・レコードを削除します
```
 bluemix sl dns record-remove RECORD_ID
```

**例**:
```   
 bluemix sl dns record-remove 12345678
```
このコマンドは、ID `12345678` のリソース・レコードを削除します。

### bluemix sl dns zone-create
{: #sl_dns_zone_create}

ゾーンを作成します。
```
 bluemix sl dns zone-create ZONE
```
**例**:
```
 bluemix sl dns zone-create bluemix.net
```
このコマンドは、`bluemix.net` という名前のゾーンを作成します。

### bluemix sl dns zone-delete
{: #sl_dns_zone_delete}

ゾーンを削除します。
```
 bluemix sl dns zone-delete ZONE
```
**例**:
```
 bluemix sl dns zone-delete bluemix.net
```
このコマンドは、`bluemix.net` という名前のゾーンを削除します。

### bluemix sl dns zone-list
{: #sl_dns_zone_list}

ユーザーのアカウントのすべてのゾーンをリストします
```
   bluemix sl dns zone-list
```
**例**:
```
   bluemix sl dns zone-list
```
このコマンドは、現行アカウントにあるすべてのゾーンをリストします。

### bluemix sl dns zone-print
{: #sl_dns_zone_print}

ゾーンおよびリソース・レコードを BIND フォーマットで出力します
```
 bluemix sl dns zone-print ZONE
```

**例**:
```
 bluemix sl dns zone-print bluemix.net
```
このコマンドは、bluemix.net という名前のゾーンを BIND フォーマットで出力します。


### bluemix sl globalip assign
{: #sl_globalip_assign)</td>

グローバル IP をターゲットのルーターまたはデバイスに割り当てます。
```
 bluemix sl globalip assign [OPTIONS] IDENTIFIER TARGET
```
**例**:
```
 bluemix sl globalip assign 12345678 9.111.123.456
```
このコマンドは、ID 12345678 の IP アドレスを、IP アドレス 9.111.123.456 のターゲット・デバイスに割り当てます。


### bluemix sl globalip-create
{: #sl_globalip_create}

グローバル IP を作成します。
```
bluemix sl globalip-create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--v6</dt>
   <dd>IPv6 IP を注文します。</dd>
   <dt>--test</dt>
   <dd>テストの注文。</dd>
    <dt>-f, --force</dt>
   <dd>確認なしでグローバル IP を作成します。</dd>
    </dl>

**例**:
```
     bluemix sl globalip create --v6
```
このコマンドは、IP V6 アドレスを作成します。

### bluemix sl globalip-cancel
{: #sl_globalip_cancel}

グローバル IP を取り消します。
```
bluemix sl globalip-cancel [OPTIONS] IDENTIFIER
```
<strong>コマンド・オプション</strong>:<dl>
    <dt>-f, --force</dt>
   <dd>確認なしでグローバル IP を作成します。</dd>
    </dl>

**例**:
```
 bluemix sl globalip cancel 12345678
```
このコマンドは、ID `12345678` の IP アドレスを取り消します。

### bluemix sl globalip-list
{: #sl_globalip_list}

すべてのグローバル IP をリストします。
```
bluemix sl globalip-list [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--v4</dt>
   <dd>IPv4 IP のみを表示します。</dd>
   <dt>--v6</dt>
   <dd>IPv6 IP のみを表示します。</dd>
    </dl>


### bluemix sl globalip unassign
{: #sl_globalip_unassign}

ターゲットのルーターまたはデバイスからグローバル IP を割り当て解除します
```
 bluemix sl globalip unassign IDENTIFIER
```
**例**:
```
 bluemix sl globalip unassign 12345678
```
このコマンドは、ID `12345678` の IP アドレスをターゲット・デバイスから割り当て解除します。


### bluemix sl image delete
{: #sl_dns_image_delete}

イメージを削除します。
```
   bluemix sl image delete IDENTIFIER
```
**例**:
```
   bluemix sl image delete 12345678
```
このコマンドは、ID `12345678` のイメージを削除します。


### bluemix sl image detail
{: #sl_dns_image_detail}

イメージの詳細を取得します。
```
 bluemix sl image detail IDENTIFIER
```
**例**:
```
 bluemix sl image detail 12345678
```
このコマンドは、ID 12345678 のイメージの詳細を取得します。

### bluemix sl image edit
{: #sl_dns_image_edit}

イメージの詳細を編集します
```
   bluemix sl image edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--name</dt>
   <dd>イメージの名前。</dd>
   <dt>--note</dt>
   <dd>イメージの追加のメモ。</dd>
   <dt>--tag</dt>
   <dd>イメージのタグ</dd>
   </dl>


**例**:
```  
bluemix sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
このコマンドは、ID `12345678` のイメージを編集し、その名前を `ubuntu16` に設定し、メモを `testing` に設定し、タグを `staging` に設定します。


### bluemix sl image edit
{: #sl_dns_image_edit}

イメージの詳細を編集します
```
   bluemix sl image edit [OPTIONS] IDENTIFIER
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--name</dt>
   <dd>イメージの名前。</dd>
   <dt>--note</dt>
   <dd>イメージの追加のメモ。</dd>
   <dt>--tag</dt>
   <dd>イメージのタグ</dd>
   </dl>

### bluemix sl image list
{: #sl_dns_image_list}

ご使用のアカウントのすべてのイメージをリストします
```
   bluemix sl image list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--name</dt>
   <dd>イメージ名を基準にフィルター操作します。</dt>
   <dd>--public</dt>
   <dd>パブリック・イメージのみを表示します。</dd>
   <dt>--private</dt>
   <dd>プライベート・イメージのみを表示します。</dd>
    </dl>

### bluemix sl iscsi cancel
{: #sl_iscsi_cancel}

既存の iSCSI ボリュームを取り消します
```
   bluemix sl iscsi cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--reason</dt>
   <dd>取り消しの理由 (オプション)。</dd>
   <dt>--immediate</dt>
   <dd>請求応答日ではなく即時、iSCSI を取り消します。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
    </dl>

### bluemix sl iscsi create
{: #sl_iscsi_create}

iSCSI ボリュームを作成します
```
   bluemix sl iscsi create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--size</dt>
   <dd>作成する iSCSI ボリュームのサイズ (ギビバイト) [必須]</dd>
   <dt>--datacenter</dt>
   <dd>データ・センターの短縮名 [必須]</dd>
	</dl>

### bluemix sl iscsi detail
{: #sl_iscsi_detail}

iSCSI ボリュームの詳細を取得します
```
   bluemix sl iscsi detail IDENTIFIER [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--password</dt>
   <dd>iSCSI ターゲットにアクセスするための資格情報を表示します。</dd>
   </dl>


### bluemix sl iscsi list
{: #sl_iscsi_list}

iSCSI ボリュームをリストします
```
 bluemix sl iscsi list [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--order</dt>
   <dd>この iscsi ストレージを購入した注文の ID</dd>
   </dl>


### bluemix sl iscsi snapshot-cancel
{: #sl_iscsi_snapshot_cancel}

iSCSI スナップショットを取り消し/削除します
```
 bluemix sl iscsi snapshot-cancel IDENTIFIER [OPTIONS]
```


### bluemix sl iscsi snapshot-create
{: #sl_iscsi_snapshot_create}

iSCSI ボリュームのスナップショットを作成します
```
   bluemix sl iscsi snapshot-create IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--notes</dt>
   <dd>スナップショットのメモ (オプション)。</dd>
   </dl>


### bluemix sl iscsi snapshot-create-space
{: #sl_iscsi_snapshot_create-space}

指定された iSCSI ボリューム用のスナップショット・スペースを注文します
```
 bluemix sl iscsi snapshot-create-space IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--capacity</dt>
   <dd>作成するスナップショット・スペースのサイズ。</dd>
   </dl>

### bluemix sl iscsi snapshot-list
{: #sl_iscsi_snapshot_list}

iSCSI ボリュームのスナップショットをリストします
```
 bluemix sl iscsi snapshot-list IDENTIFIER [OPTIONS]
```

### bluemix sl security sshkey-add
{: #sl_security_sshkey_add}

新規 SSH 鍵を追加します
```
 bluemix sl security sshkey-add LABEL [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --in-file</dt>
   <dd>この鍵のためにインポートする id_rsa.pub ファイル</dd>
   <dt>-k, --key</dt>
   <dd>実際の SSH 鍵</dd>
   <dt>--note</dt>
   <dd>鍵に関連付けられる追加のメモ</dd>
   </dl>


**例**:
```
 bluemix sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
このコマンドは、ファイル ~/.ssh/id_rsa.pub から SSH 鍵を、メモ「mykey」を付けて追加します。


### bluemix sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH 鍵を編集します
```
 bluemix sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--label</dt>
   <dd>鍵の新しいラベル</dd>
   <dt>--note</dt>
   <dd>鍵についての新しいメモ</dd>
   </dl>


**例**:
```
 bluemix sl security sshkey-edit 12345678 --label Bluemix --note testing
```
このコマンドは、ID 12345678 の SSH 鍵を更新し、ラベルを「Bluemix」に設定し、メモを「testing」に設定します。

### bluemix sl security sshkey-list
{: #sl_security_sshkey_list}

ご使用のアカウントの SSH 鍵をリストします
```
 bluemix sl security sshkey-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>ソートの基準となる列。オプション: `id`、`label`、`fingerprint`、`notes`。</dd>
   </dl>


**例**:
```
 bluemix sl security sshkey-list --sortby label
```
このコマンドは、現行アカウントのすべての SSH 鍵をリストし、それらをラベルによってソートします。

### bluemix sl security sshkey-print
{: #sl_security_sshkey_print}

SSH 鍵を画面に出力します
```
 bluemix sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --out-file</dt>
   <dd>SSH 公開鍵は、このファイルに書き込まれます。</dd>
   </dl>


**例**:
```
 bluemix sl security sshkey-print 12345678 -f ~/mykey.pub
```
このコマンドは、ID 12345678 の SSH 鍵の ID、ラベル、およびメモを表示し、公開鍵をファイル ~/mykey.pub に書き込みます。

### bluemix sl security sshkey-remove
{: #sl_security_sshkey_remove}

SSH 鍵を永久に削除します
```
 bluemix sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>


**例**:
```
 bluemix sl security sshkey-remove 12345678 -f
```
このコマンドは、ID 12345678 の SSH 鍵を、確認を求めずに削除します。

### bluemix sl security cert-add
{: #sl_security_cert_add}

SSL 証明書の詳細を追加してアップロードします
```
 bluemix sl security cert-add [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>証明書ファイル</dd>
   <dt>--csr</dt>
   <dd>証明書署名要求ファイル</dd>
   <dt>--icc</dt>
   <dd>中間証明書ファイル</dd>
   <dt>--key</dt>
   <dd>秘密鍵ファイル</dd>
   <dt>--notes</dt>
   <dd>追加のメモ</dd>
   </dl>


**例**:
```
 bluemix sl security cert-add --crt ~/bluemix.net.cert --key ~/bluemix.net.key 
```
このコマンドは、ドメイン bluemix.net の証明書ファイル ~/bluemix.net.cert と秘密鍵ファイル ~/bluemix.net.key を追加します。

### bluemix sl security cert-edit
{: #sl_security_cert_edit}

SSL 証明書の編集
```
 bluemix sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--crt</dt>
   <dd>証明書ファイル</dd>
   <dt>--csr</dt>
   <dd>証明書署名要求ファイル</dd>
   <dt>--icc</dt>
   <dd>中間証明書ファイル</dd>
   <dt>--key</dt>
   <dd>秘密鍵ファイル</dd>
   <dt>--notes</dt>
   <dd>追加のメモ</dd>
   </dl>


**例**:
```
 bluemix sl security cert-edit 12345678 --key ~/bluemix.net.key
```
このコマンドは、ID 12345678 の証明書を編集し、ファイル ~/bluemix.net.key でその秘密鍵を更新します。

### bluemix sl security cert-download
{: #sl_security_cert_download}

SSL 証明書および鍵ファイルをダウンロードします
```
 bluemix sl security cert-download IDENTIFIER
```

**例**:
```
 bluemix sl security cert-download 12345678
```
このコマンドは、現行ディレクトリーに ID 12345678 の証明書に関する 4 つのファイルをダウンロードします。4 つのファイルというのは、証明書ファイル、証明書署名要求ファイル、中間証明書ファイル、および秘密鍵ファイルです。

### bluemix sl security cert-list
{: #sl_security_cert_list}

ご使用のアカウントの SSL 証明書をリストします
```
 bluemix sl security cert-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--status</dt>
   <dd>指定の状況の証明書を表示します。デフォルトは all です。オプション: `all`、`valid`、`expired`</dd>
   <dt>--sortby</dt>
   <dd>ソートの基準となる列。オプション: `id`、`common_name`、`days_until_expire`、`notes`</dd>
   </dl>


**例**:
```
 bluemix sl security cert-list --status valid --sortby days_until_expire
```
このコマンドは、現行アカウントのすべての有効な証明書をリストし、それらを有効期限日によってソートします。

### bluemix sl security cert-remove
{: #sl_security_cert_remove}

SSL 証明書の削除
```
 bluemix sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt> -f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>


**例**:
```
 bluemix sl security cert-remove 12345678
```
このコマンドは、ID 12345678 の証明書を削除します。

### bluemix sl subnet cancel
{: #sl_subnet_cancel}

サブネットを取り消します。
```
 bluemix sl subnet cancel [OPTIONS] IDENTIFIER
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
    </dl>


**例**:
```
 bluemix sl subnet cancel 12345678 -f
```
このコマンドは、ID 12345678 のサブネットを、確認を求めずに取り消します。

### bluemix sl subnet create
{: #sl_subnet_create}

ご使用のアカウントに新規サブネットを追加します。
```
   bluemix sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

有効な数量は、タイプによって異なります。

 * タイプ    - 有効な数量 (IPv4)
    ** パブリック  - 4、8、16、32
    ** プライベート - 4、8、16、32、64
 * タイプ    - 有効な数量 (IPv6)
    ** パブリック  - 64

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--v6, --ipv6</dt>
   <dd>IPv6 アドレスを注文します。</dd>
   <dt>--test</dt>
   <dd>サブネットを注文せず、見積もりを取るだけです。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>

**例**:
```
 bluemix sl subnet create public 16 567
```
このコマンドは、16 個の IPv4 アドレスを持つパブリック・サブネットを作成し、ID 567 の VLAN に配置します。



### bluemix sl subnet detail
{: #sl_subnet_detail}

サブネットの詳細を取得します。
```
   bluemix sl subnet detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>仮想サーバー・リストを非表示にします。</dd>
   <dt>--no-hardware</dt>
   <dd>ハードウェア・リストを非表示にします。</dd>
   </dl>


**例**:
```
 bluemix sl subnet detail 12345678
```
このコマンドは、仮想サーバーおよびハードウェア・サーバーの情報を含め、ID 12345678 のサブネットに関する詳細情報を表示します。


### bluemix sl subnet-list
{: #sl_subnet_list}

ご使用のアカウントのすべてのサブネットをリストします
```
   bluemix sl subnet list [OPTIONS]
```


<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--sortby</dt>
   <dd>ソートの基準にする列。オプション: id、identifier、type、network_space、datacenter、vlan_id、IPs、hardware、vs。</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
   <dt>--identifier</dt>
   <dd>ネットワーク ID を基準にフィルター操作します。</dd>
   <dt>-t, --subnet-type</dt>
   <dd>サブネット・タイプを基準にフィルター操作します。</dd>
   <dt>--network-space</dt>
   <dd>ネットワーク・スペースを基準にフィルター操作します。</dd>
   <dt>--v4, --ipv4</dt>
   <dd>IPv4 サブネットのみを表示します。</dd>
   <dt>--v6, --ipv6</dt>
   <dd>IPv6 サブネットのみを表示します。</dd>
   <dt>--order</dt>
   <dd>サブネットを購入した注文の ID を基準にフィルター操作します</dd>
   </dl>

**例**:
```
 bluemix sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
このコマンドは、現行アカウントの IP V4 サブネットをリストします。フィルター基準のデータ・センターは dal09、サブネット・タイプは PRIMARY、およびネットワーク・スペースは PUBLIC です。



### bluemix sl subnet-lookup
{: #sl_subnet_lookup}

IP アドレスを検出し、そのサブネットとデバイスの情報を表示します
```
   bluemix sl subnet lookup IP_ADDRESS
```

**例**:
```
 bluemix sl subnet lookup 9.125.235.255
```
このコマンドは、アドレス 9.125.235.255 の IP アドレス・レコードを検出し、そのサブネットとデバイスの情報を表示します。


### bluemix sl vs cancel
{: #sl_vs_cancel}

仮想サーバー・インスタンスを取り消します
```
   bluemix sl vs cancel IDENTIFIER [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>

**例**:
```
 bluemix sl vs cancel 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを取り消します。


### bluemix sl vs capture
{: #sl_vs_capture}

仮想サーバー・インスタンスをイメージに取り込みます
```
 bluemix sl vs capture IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-n, --name</dt>
   <dd>イメージの名前 [必須]。</dd>
   <dt>--all</dt>
   <dd>この VS に属しているすべてのディスクを取り込みます。</dd>
   <dt>--note</dt>
   <dd>このイメージに関連付けるメモを追加します。</dd>
   </dl>

**例**:
```
 bluemix sl vs capture 12345678 -n mybluemix --all --note testing
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスをすべてのディスクと共に、「mybluemix」という名前のイメージに、「testing」というメモを付けて取り込みます。



### bluemix sl vs create
{: #sl_vs_create}

仮想サーバー・インスタンスを作成します
```
   bluemix sl vs create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-H, --hostname</dt>
   <dd>FQDN のホスト部分 [必須]</dd>
   <dt>-D, --domain</dt>
   <dd>FQDN のドメイン部分 [必須]</dd>
   <dt>-c, --cpu</dt>
   <dd>CPU コアの数 [必須]</dd>
   <dt>-m, --memory</dt>
   <dd>メモリー (M バイト) [必須]</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名 [必須]</dd>
   <dt>-o, --os</dt>
   <dd>OS インストール・コード。ヒント: <OS>_LATEST を指定できます。</dd>
   <dt>--image</dt>
   <dd>イメージ ID。[bluemix sl image list](#bluemix_sl_image_list) を参照してください。</dd>
   <dt>--billing</dt>
   <dd>請求レート。デフォルトは hourly です。 オプション: hourly、monthly</dd>
   <dt>--dedicated</dt>
   <dd>専用仮想サーバー (プライベート・ノード) を作成します</dd>
   <dt>--san</dt>
   <dd>ローカル・ディスクの代わりに SAN ストレージを使用します</dd>
   <dt>--test</dt>
   <dd>実際には仮想サーバーを作成しません</dd>
   <dt>--export</dt>
   <dd>オプションをテンプレート・ファイルにエクスポートします</dd>
   <dt>-i, --postinstall</dt>
   <dd>ダウンロードするインストール後スクリプト</dd>
   <dt>-k, --key</dt>
   <dd>root ユーザーに追加する SSH 鍵の ID (複数のオカレンスが許可されます)</dd>
   <dt>--disk</dt>
   <dd>ディスク・サイズ (複数のオカレンスが許可されます)</dd>
   <dt>--private</dt>
   <dd>仮想サーバーがプライベート・ネットワークのみにアクセスすることを強制します</dd>
   <dt>--like</dt>
   <dd>既存の仮想サーバーからの構成を使用します</dd>
   <dt>-n, --network</dt>
   <dd>ネットワーク・ポート速度 (Mbps)</dd>
   <dt>--tag</dt>
   <dd>インスタンスに追加するタグ (複数のオカレンスが許可されます)</dd>
   <dt>-t, --template</dt>
   <dd>コマンド・ライン・オプションをデフォルト設定するテンプレート・ファイル</dd>
   <dt>-u, --userdata</dt>
   <dd>ユーザー定義のメタデータ・ストリング</dd>
   <dt>-F, --userfile</dt>
   <dd>ユーザー・データをファイルから読み取ります</dd>
   <dt>--vlan-public</dt>
   <dd>仮想サーバーを配置するパブリック VLAN の ID</dd>
   <dt>--vlan-private</dt>
   <dd>仮想サーバーを配置するプライベート VLAN の ID</dd>
   <dt>--wait</dt>
   <dd>仮想サーバーでのプロビジョニング終了を最大 X 秒待ってから戻ります</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
	</dl>

**例**:
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
このコマンドは、ホスト名 myvsi、ドメイン bluemix.net、4 つの CPU コア、4096 M のメモリー、データ・センター dal10、オペレーション・システム UBUNTU 16 64 ビット、2 つのディスク (1 つは 100 G、もう 1 つは 1000 G) で、ID 413 のパブリック VLAN に配置される仮想サーバー・インスタンスを注文します。
```
  bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --test
```
このコマンドは、注文が実際に処理される前に、上記のオプションの注文が有効かどうかテストします。
```
bluemix sl vs create -H myvsi -D bluemix.net -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413 --export ~/myvis.txt
```

このコマンドは、後で使用するために、上記のオプションをホーム・ディレクトリーの myvsi.txt ファイルにエクスポートします。


### bluemix sl vs options
{: #sl_vs_options}

仮想サーバー・インスタンスの作成に関するオプションをリストします
```
   bluemix sl vs options [OPTIONS]
```

**例**:
```
 bluemix sl vs options
```
このコマンドは、仮想サーバー・インスタンスを作成するためのすべてのオプション (例えば、データ・センター、CPU、メモリー、OS、ディスク、ネットワーク速度など) をリストします。


### bluemix sl vs credentials
{: #sl_vs_credentials}

仮想サーバー・インスタンスの資格情報をリストします
```
   bluemix sl vs credentials IDENTIFIER [OPTIONS]
```
**例**:
```
 bluemix sl vs credentials 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのユーザー名とパスワードのすべてのペアをリストします。

### bluemix sl vs detail
{: #sl_vs_detail}

仮想サーバー・インスタンスの詳細を取得します
```
   bluemix sl vs detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--passwords</dt>
   <dd>パスワードを表示します。</dd>
   <dt>--price</dt>
   <dd>関連付けられた価格を表示します。</dd>
   </dl>


**例**:
```
   bluemix sl vs details 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスに関する詳細情報をリストします。


### bluemix sl vs dns-sync
{: #sl_vs_dns_sync}

仮想サーバー・インスタンスの DNS レコードを同期します
```
   bluemix sl vs dns-sync IDENTIFIER [OPTIONS]
```
注: 引数をまったく指定しないと、A レコードと PTR レコード両方の更新が試行されます。両方のレコードを更新したくない場合は、-a または --ptr の引数を使用して、更新されるレコードを制限できます。

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-a, --a-record</dt>
   <dd>ホストの A レコードを同期します</dd>
   <dt>--aaaa-record</dt>
   <dd>ホストの AAAA レコードを同期します</dd>
   <dt>--ptr</dt>
   <dd>ホストの PTR レコードを同期します</dd>
   <dt>--ttl</dt>
   <dd>A レコードまたは PTR レコード、あるいは両方の TTL を設定します。デフォルトは 7200 です</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>


**例**:
```
 bluemix sl vs dns-sync 12345678 --a-record --ttl 3600
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの A レコード (IP V4 アドレス) を DNS サーバーに同期し、この A レコードの TTL を 3600 に設定します。
```
 bluemix sl vs dns-sync 12345678 --aaaa-record --ptr
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの AAAA レコード (IP V6 アドレス) と PTR レコードの両方を DNS サーバーに同期します。

### bluemix sl vs edit
{: #sl_vs_edit}

仮想サーバー・インスタンスの詳細を編集します
```
   bluemix sl vs edit IDENTIFIER [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>-D, --domain</dt>
   <dd>FQDN のドメイン部分</dd>
   <dt>-H, --hostname</dt>
   <dd>FQDN のホスト部分。例: server</dd>
   <dt>--tag</dt>
   <dd>設定するタグ、または、すべて削除する場合は空ストリング</dd>
   <dt>-u, --userdata</dt>
   <dd>ユーザー定義のメタデータ・ストリング</dd>
   <dt>-F, --userfile</dt>
   <dd>ユーザー・データをファイルから読み取ります</dd>
   <dt>--public-speed</dt>
   <dd>パブリック・ポート速度。オプション: 0、10、100、1000、10000</dd>
   <dt>--private-speed</dt>
   <dd>プライベート・ポート速度。オプション: 0、10、100、1000、10000</dd>
   </dl>

**例**:
```
 bluemix sl vs edit 12345678 -D bluemix.net -H myapp --tag testcli --public-speed 1000
```
このコマンドは、ID `12345678` の仮想サーバー・インスタンスを更新し、そのドメインを `bluemix.net`、ホスト名を `myapp`、タグを `testcli`、およびパブリック・ネットワーク・ポート速度を 1000 Mbps に設定します。



### bluemix sl vs list
{: #sl_vs_list}
ご使用のアカウントの仮想サーバー・インスタンスをリストします
```
   bluemix sl vs list [OPTIONS]
```


<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>CPU コアの数</dd>
   <dt>-D, --domain</dt>
   <dd>FQDN のドメイン部分</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名</dd>
   <dt>-H, --hostname</dt>
   <dd>FQDN のホスト部分</dd>
   <dt>-m, --memory</dt>
   <dd>メモリー (M バイト)</dd>
   <dt>-n, --network</dt>
   <dd>ネットワーク・ポート速度 (Mbps)</dd>
   <dt>--hourly</dt>
   <dd>時間単位のインスタンスのみを表示します</dd>
   <dt>--monthly</dt>
   <dd>月単位のインスタンスのみを表示します</dd>
   <dt>--tag</dt>
   <dd>タグを基準にフィルター操作します (複数のオカレンスが許可されます)</dd>
   <dt>--sortby</dt>
   <dd>ソートの基準にする列。オプション: id、hostname、domain、datacenter、cpu、memory、primary_ip、backend_ip。デフォルト: hostname</dd>
   <dt>--columns</dt>
   <dd>表示する列。オプション: guid、primary_ip、backend_ip、datacenter、action、power_state、created_by、tags。デフォルト: id、hostname、primary_ip、backend_ip、datacenter、action</dd>
    </dl>

**例**:
```
 bluemix sl vs list --domain bluemix.net --hourly --sortby memory
```
このコマンドは、現行アカウントの、時間ごとに請求されるすべての仮想サーバー・インスタンスをリストします。フィルター基準のドメインは「bluemix.net」で、それらをメモリーによってソートします。



### bluemix sl vs-pause
{: #sl_vs_pause}

アクティブな仮想サーバー・インスタンスを一時停止します
```
   bluemix sl vs pause IDENTIFIER [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
    </dl>

**例**:
```
 bluemix sl vs pause 12345678 -f
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを、確認を求めずに一時停止します。



### bluemix sl vs power-off
{: #sl_vs_power_off}

アクティブな仮想サーバー・インスタンスをパワーオフします
```
   bluemix sl vs power-off IDENTIFIER [OPTIONS]
```

**例**:
```
   bluemix sl vs power-off 12345678 --soft
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのソフト・パワーオフを実行します。

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>ハード・シャットダウンを実行します</dd>
   <dt>--soft</dt>
   <dd>ソフト・シャットダウンを実行します</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
    </dl>


### bluemix sl vs power-on
{: #sl_vs_power_on}

仮想サーバー・インスタンスをパワーオンします
```
 bluemix sl vs power-on IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
    </dl>

**例**:
```
 bluemix sl vs power-on 12345678
```
このコマンドは、ID 12345678 の仮想サーバーのパワーオンを実行します。


### bluemix sl vs ready
{: #sl_vs_ready}

仮想サーバー・インスタンスの使用準備ができているかどうかをチェックします
```
 bluemix sl vs ready IDENTIFIER [OPTIONS]
```

**例**:
```
 bluemix sl vs ready 12345678 --wait 30
```
このコマンドは、ID 12345678 の仮想サーバーの状況をチェックして、そのインスタンスが、連続して使用する準備ができているかどうか確認し、最大 30 秒待機します。

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--wait</dt>
   <dd>仮想サーバーでのプロビジョニング終了を最大 X 秒待ってから戻ります</dd>
    </dl>

### bluemix sl vs reboot
{: #sl_vs_reboot}

アクティブな仮想サーバー・インスタンスをリブートします
```
 bluemix sl vs reboot IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--hard</dt>
   <dd>ハード・リブートを実行します</dd>
   <dt>--soft</dt>
   <dd>ソフト・リブートを実行します</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
    </dl>

**例**:
```
 bluemix sl vs reboot 12345678 --hard
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスのハード・リブートを実行します。



### bluemix sl vs reload
{: #sl_vs_reload}

仮想サーバー・インスタンス上でオペレーティング・システムを再ロードします
```
 bluemix sl vs reload IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-i, --postinstall</dt>
   <dd>ダウンロードするインストール後スクリプト</dd>
   <dt>--image</dt>
   <dd>イメージ ID。デフォルトは、現行オペレーティング・システムを使用することです。「bluemix sl image list」を参照してください</dd>
   <dt>-k, --key</dt>
   <dd>root ユーザーに追加する SSH 鍵の ID (複数のオカレンスが許可されます)</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
    </dl>

**例**:
```
   bluemix sl vs reload 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスの現行オペレーティング・システムを再ロードします。
```
 bluemix sl vs reload 12345678 --image 1234
```
このコマンドは、ID 1234 のイメージから、ID 12345678 の仮想サーバー・インスタンスのオペレーティング・システムを再ロードします。



### bluemix sl vs rescure
{: #sl_vs_rescure}

仮想サーバー・インスタンスをレスキュー・イメージでリブートします
```
 bluemix sl vs rescue IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
   </dl>
   
**例**:
```
 bluemix sl vs rescue 12345678
```
このコマンドは、ID 12345678 の仮想サーバーをレスキュー・イメージでリブートします。


### bluemix sl vs resume
{: #sl_vs_resume}

一時停止された仮想サーバー・インスタンスを再開します
```
   bluemix sl vs resume IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
    </dl>

**例**:
```
 bluemix sl vs resume 12345678
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスを再開します。


### bluemix sl vs upgrade
{: #sl_vs_upgrade}

仮想サーバー・インスタンスを更新します
```
   bluemix sl vs upgrade IDENTIFIER [OPTIONS]
```
注: SoftLayer は、アップグレード要求が実行されると自動的にインスタンスをリブートします。インスタンスは、アップグレード・トランザクションが完了するまで停止されます。ただし、ネットワークの場合、リブートは必要ありません。
<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-c, --cpu</dt>
   <dd>CPU コアの数</dd>
   <dt>--private</dt>
   <dd>CPU コアは、専用ホスト・サーバーに置かれます。</dd>
   <dt>-m, --memory</dt>
   <dd>メモリー (M バイト)。</dd>
   <dt>--network</dt>
   <dd>ネットワーク・ポート速度 (Mbps)。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します。</dd>
    </dl>

**例**:
```
 bluemix sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
このコマンドは、ID 12345678 の仮想サーバー・インスタンスをアップグレードし、CPU コア数を 8、メモリーを 8192 M、ネットワーク・ポート速度を 1000 Mbps に設定します。



### bluemix sl vlan create
{: #sl_vlan_create}

新規 VLAN を作成します
```
   bluemix sl vlan create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-t, --vlan-type</dt>
   <dd>VLAN のタイプ。public または private のいずれか</dd>
   <dt>-r, --router</dt>
   <dd>ルーターのホスト名</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名</dd>
   <dt>-s, --size</dt>
   <dd>サブネットのサイズ。オプションは、8 (5 個の使用可能な IP)、16 (13 個の使用可能な IP)、または 32 (29 個の使用可能な IP) です</dd>
   <dt>-n, --name</dt>
   <dd>VLAN の名前。</dd>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
    </dl>

**例**:
```
 bluemix sl vlan create -t public -d dal09 -s 16 -n myvlan
```
このコマンドは、データ・センター dal09 に、16 個の IP アドレスを持ち、myvlan という名前のパブリック VLAN を作成します。
```
 bluemix sl vlan create -r bcr01a.dal09 -s 16 -n myvlan
```
このコマンドは、ルーター bcr01a.dal09 に配置される、16 個の IP アドレスを持ち、myvlan という名前の VLAN を作成します。



### bluemix sl vlan cancel
{: #sl_vlan_cancel}

VLAN を取り消します
```
   bluemix sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>-f, --force</dt>
   <dd>確認なしで操作を強制します</dd>
    </dl>

**例**:
```
   bluemix sl vlan cancel 12345678 -f
```
このコマンドは、ID 12345678 の VLAN を、確認を求めずに取り消します。



### bluemix sl vlan detail
{: #sl_vlan_detail}

VLAN についての詳細を取得します。
```
   bluemix sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>--no-vs</dt>
   <dd>仮想サーバー・リストを非表示にします</dd>
   <dt>--no-hardware</dt>
   <dd>ハードウェア・リストを非表示にします</dd>
   </dl>

**例**:
```
 bluemix sl vlan detail 12345678  --no-vs --no-hardware
```
このコマンドは、ID 12345678 の VLAN の詳細を表示し、仮想サーバーおよびハードウェア・サーバーをリストしません。

### bluemix sl vlan edit
{: #sl_vlan_edite}

VLAN についての詳細を編集します
```
   bluemix sl vlan edit IDENTIFIER [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--n, --name</dt>
   <dd>VLAN の名前。</dd>
    </dl>

**例**:
```
 bluemix sl vlan edit 12345678 -n myvlan-rename
```
このコマンドは、ID 12345678 の VLAN を更新し、それに新しい名前「myvlan-rename」を付けます。


### bluemix sl vlan list
{: #sl_vlan_list}

ご使用のアカウントのすべての VLAN をリストします
```
 bluemix sl vlan list [OPTIONS]
```
<strong>コマンド・オプション</strong>:<dl>
   <dt>--sortby</dt>
   <dd>ソートの基準にする列。オプション: id、number、name、firewall、datacenter、hardware、virtual_servers、public_ips。</dd>
   <dt>-d, --datacenter</dt>
   <dd>データ・センターの短縮名を基準にフィルター操作します</dd>
   <dt>-n, --number</dt>
   <dd>VLAN 番号を基準にフィルター操作します</dd>
   <dt>--name</dt>
   <dd>VLAN 名を基準にフィルター操作します</dd>
   <dt>--order</dt>
   <dd>VLAN を購入した注文の ID を基準にフィルター操作します</dd>
   </dl>

**例**:
```
 bluemix sl vlan list -d dal09 --sortby number
```
このコマンドは、現行アカウントのすべての VLAN をリストします。フィルター基準のデータ・センターは dal09 で、VLAN 番号によってソートします。


### bluemix sl vlan options
{: #sl_vlan_options}

VLAN の作成に関するすべてのオプションをリストします
```
   bluemix sl vlan options
```
**例**:
```
 bluemix sl vlan options
```
このコマンドは、VLAN を作成するためのすべてのオプション (例えば、VLAN タイプ、データ・センター、サブネット・サイズ、ルーターなど) をリストします。
