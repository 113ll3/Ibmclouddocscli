---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・ブロック・ストレージの管理

 <table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・コマンド">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・ブロック・ストレージ</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} インフラストラクチャー・ブロック・ストレージ</th>
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

指定されたボリュームへのホストのアクセスを許可します。
```
ibmcloud sl block access-authorize VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>許可する 1 つのハードウェア・サーバーの ID。</dd>
<dt>-v, --virtual-id</dt>
<dd>許可する 1 つの仮想サーバーの ID。</dd>
<dt>-i, --ip-address-id</dt>
<dd>許可する 1 つの IP アドレスの ID。</dd>
<dt>-p, --ip-address</dt>
<dd>許可する IP アドレス。</dd>
</dl>

**例**:
```
ibmcloud sl block access-authorize 12345678 --virtual-id 87654321
```
このコマンドは、ID 87654321 の仮想サーバーが、ID 12345678 のボリュームにアクセスすることを許可します。

## ibmcloud sl block access-list
{: #sl_block_access_list}

ACL をリストします。
```
ibmcloud sl block access-list VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、type、private_ip_address、host_iqn、username、password。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: id、name、type、private_ip_address、host_iqn、username、password。</dd>
</dl>

**例**:
```
ibmcloud sl block access-list 12345678 --sortby id
```
このコマンドは、ID 12345678 のボリュームへのアクセスを許可されているすべてのホストをリストし、それらを ID によってソートします。

## ibmcloud sl block access-password
{: #sl_block_access_password}

ボリュームのアクセスのためのパスワードを変更します。
```
ibmcloud sl block access-password ACCESS_ID PASSWORD
```

## ibmcloud sl block access-revoke
{: #sl_block_access_revoke}

指定されたボリュームにアクセスするホストの許可を取り消します。
```
ibmcloud sl block access-revoke VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --hardware-id</dt>
<dd>取り消す 1 つのハードウェア・サーバーの ID。</dd>
<dt>-v, --virtual-id</dt>
<dd>取り消す 1 つの仮想サーバーの ID。</dd>
<dt>-i, --ip-address-id</dt>
<dd>取り消す 1 つの IP アドレスの ID。</dd>
<dt>-p, --ip-address</dt>
<dd>取り消す IP アドレス。</dd>
</dl>

**例**:
```
ibmcloud sl block access-revoke 12345678 --virtual-id 87654321
```
このコマンドは、ID 87654321 の仮想サーバーの、ID 12345678 のボリュームへのアクセスを取り消します。

## ibmcloud sl block replica-failback
{: #sl_block_replica_failback}

レプリカからブロック・ボリュームをフェイルバックします。
```
ibmcloud sl block replica-failback VOLUME_ID
```


**例**:
```
ibmcloud sl block replica-failback 12345678
```
このコマンドは、ID 12345678 のボリュームのフェイルバック操作を実行します。

## ibmcloud sl block replica-failover
{: #sl_block_replica_failover}

ブロック・ボリュームを、指定されたレプリカ・ボリュームにフェイルオーバーします。
```
ibmcloud sl block replica-failover VOLUME_ID REPLICA_ID
```


**例**:
```
ibmcloud sl block replica-failover 12345678 87654321
```
このコマンドは、ID 12345678 のボリュームの、ID 87654321 のレプリカ・ボリュームへのフェイルオーバー操作を実行します。

## ibmcloud sl block replica-locations
{: #sl_block_replica_locations}

指定されたボリュームに適切な複製データ・センターをリストします。
```
ibmcloud sl block replica-locations VOLUME_ID
```


**例**:
```
ibmcloud sl block replica-locations 12345678
```
このコマンドは、ID 12345678 のブロック・ボリュームの適切な複製データ・センターをリストします。

## ibmcloud sl block replica-order
{: #sl_block_replica_order}

ブロック・ストレージ・レプリカ・ボリュームを注文します。
```
ibmcloud sl block replica-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --snapshot-schedule</dt>
<dd>必須。 複製に使用するスナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 複製用のデータ・センターの短縮名。例えば、dal09 など。</dd>
<dt>-t, --tier</dt>
<dd>オプション。 レプリカを注文する 1 次ボリュームのエンデュランス・ストレージ層 (GB 当たりの IOPS)。オプション: 0.25、2、4、10。層が指定されない場合、元のボリュームの層が使用されます。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。IOPS が指定されない場合、元のボリュームの IOPS が使用されます。</dd>
<dt>-o, --os-type</dt>
<dd>オプション。 レプリカを注文する 1 次ボリュームのオペレーティング・システム・タイプ (例: LINUX)。オプション: HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS、XEN。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block replica-order 12345678 -s DAILY -d dal09 --tier 4 --os-type LINUX
```
このコマンドは、ID 12345678 のボリュームのレプリカを注文します。このレプリカは、毎日の複製を実行し、dal09 にあり、層レベルは 4、OS タイプは Linux です。

## ibmcloud sl block replica-partners
{: #sl_block_replica_partners}

ブロック・ボリュームの既存のレプリカ・ボリュームをリストします。
```
ibmcloud sl block replica-partners VOLUME_ID [OPTIONS]
```


**例**:
```
ibmcloud sl block replica-partners 12345678
```
このコマンドは、ID 12345678 のブロック・ボリュームの既存のレプリカ・ボリュームをリストします。

## ibmcloud sl block snapshot-cancel
{: #sl_block_snapshot_cancel}

指定されたボリュームの既存のスナップショット・スペースを取り消します。
```
ibmcloud sl block snapshot-cancel SNAPSHOT_ID [OPTIONS]
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
ibmcloud sl block snapshot-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のスナップショットを、確認を要求せず、即時に取り消します。

## ibmcloud sl block snapshot-create
{: #sl_block_snapshot_create}

指定されたボリュームにスナップショットを作成します。
```
ibmcloud sl block snapshot-create VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-n, --note</dt>
<dd>新規スナップショットに設定するメモ。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-create 12345678 --note snapshotforibmcloud
```
このコマンドは、ID 12345678 のボリュームのスナップショットを、snapshotforibmcloud の追加メモと共に作成します。

## ibmcloud sl block snapshot-disable
{: #sl_block_snapshot_disable}

指定されたスケジュールでの指定されたボリュームのスナップショットを無効にします。
```
ibmcloud sl block snapshot-disable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>必須。 スナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-disable 12345678 -s DAILY
```
このコマンドは、ID 12345678 のボリュームの毎日のスナップショットを無効にします。

## ibmcloud sl block snapshot-enable
{: #sl_block_snapshot_enable}

指定されたスケジュールで指定されたボリュームのスナップショットを有効にします。
```
ibmcloud sl block snapshot-enable VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --schedule-type</dt>
<dd>必須。 スナップショット・スケジュール。オプション: HOURLY、DAILY、WEEKLY。</dd>
<dt>-c, --retention-count</dt>
<dd>必須。 保持するスナップショットの数。</dd>
<dt>-m, --minute</dt>
<dd>スナップショットを作成する時刻の分の部分。0 から 59 までの整数。</dd>
<dt>-r, --hour</dt>
<dd>スナップショットを作成する時刻の時の部分。0 から 23 までの整数。</dd>
<dt>-d, --day-of-week</dt>
<dd>スナップショットを作成する曜日。0 から 6 までの整数。 0 は日曜、1 は月曜、2 は火曜、3 は水曜、4 は木曜、5 は金曜、6 は土曜を表します。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-enable 12345678 -s WEEKLY -c 5 -m 0 --hour 2 -d 0
```
このコマンドは、ID 12345678 のボリュームのスナップショットを有効にします。スナップショットは、毎週日曜日の 2:00 に取られ、最高 5 個のスナップショットが保持されます。

## ibmcloud sl block snapshot-delete
{: #sl_block_snapshot_delete}

指定されたボリュームのスナップショットを削除します。
```
ibmcloud sl block snapshot-delete SNAPSHOT_ID
```


**例**:
```
ibmcloud sl block snapshot-delete 12345678
```
このコマンドは、ID 12345678 のスナップショットを削除します。

## ibmcloud sl block snapshot-list
{: #sl_block_snapshot_list}

ブロック・ストレージ・スナップショットをリストします。
```
ibmcloud sl block snapshot-list VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、created、size_bytes。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-list 12345678 --sortby id
```
このコマンドは、ID 12345678 のボリュームのすべてのスナップショットをリストし、それらを ID によってソートします。

## ibmcloud sl block snapshot-order
{: #sl_block_snapshot_order}

ブロック・ストレージ・ボリュームのスナップショット・スペースを注文します。
```
ibmcloud sl block snapshot-order VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-s, --size</dt>
<dd>必須。 作成するスナップショット・スペースのサイズ (GB 単位)。</dd>
<dt>-t, --tier</dt>
<dd>オプション。 スペースを注文するブロック・ボリュームのエンデュランス・ストレージ層 (GB 当たりの IOPS)。オプション: 0.25、2、4、10。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。</dd>
<dt>-u, --upgrade</dt>
<dd>この注文がアップグレードであることを示すフラグを立てます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block snapshot-order 12345678 -s 1000 -t 4
```
このコマンドは、ID 12345678 のボリュームのスナップショット・スペースを注文します。サイズは 1000 GB、階層レベルは 1 GB 当たり 4 IOPS です。

## ibmcloud sl block snapshot-restore
{: #sl_block_snapshot_restore}

指定されたスナップショットを使用してブロック・ボリュームをリストアします。
```
ibmcloud sl block snapshot-restore VOLUME_ID SNAPSHOT_ID
```


**例**:
```
ibmcloud sl block snapshot-restore 12345678 87654321
```
このコマンドは、ID 12345678 のボリュームを、ID 87654321 のスナップショットからリストアします。

## ibmcloud sl block volume-cancel
{: #sl_block_volume_cancel}

既存のブロック・ストレージ・ボリュームを取り消します。
```
ibmcloud sl block volume-cancel VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--reason</dt>
<dd>取り消しの理由 (オプション)。</dd>
<dt>--immediate</dt>
<dd>請求応答日ではなく即時、ブロック・ストレージ・ボリュームを取り消します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-cancel 12345678 --immediate -f
```
このコマンドは、ID 12345678 のボリュームを、確認を要求せず、即時に取り消します。

## ibmcloud sl block volume-count
{: #sl_block_volume_count}

データ・センターごとのブロック・ストレージ・ボリュームの数をリストします。
```
ibmcloud sl block volume-count [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
</dl>

## ibmcloud sl block volume-list
{: #sl_block_volume_list}

ブロック・ストレージをリストします。
```
ibmcloud sl block volume-list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-u, --username</dt>
<dd>ボリュームのユーザー名を基準にフィルター操作します。</dd>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-t, --storage-type</dt>
<dd>ストレージ・ボリュームのタイプを基準にフィルター操作します。オプション: performance、endurance。</dd>
<dt>-o, --order</dt>
<dd>ブロック・ストレージを購入した注文の ID を基準にフィルター操作します。</dd>
<dt>--sortby</dt>
<dd>ソートの基準にする列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、active_transactions、created_by。</dd>
<dt>--columns</dt>
<dd>表示する列。オプション: id、username、datacenter、storage_type、capacity_gb、bytes_used、ip_addr、created_by。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-list -d dal09 -t endurance --sortby capacity_gb
```
このコマンドは、dal09 にある、現行アカウントのすべてのエンデュランス・ボリュームをリストし、それらを容量によってソートします。

## ibmcloud sl block volume-set-lun-id
{: #sl_block_volume_set_lun_id}

既存のブロック・ストレージ・ボリュームで LUN ID を設定します。
```
ibmcloud sl block volume-set-lun-id VOLUME_ID LUN_ID
```

## ibmcloud sl block volume-detail
{: #sl_block_volume_detail}

指定されたボリュームの詳細を表示します。
```
ibmcloud sl block volume-detail VOLUME_ID
```


**例**:
```
ibmcloud sl block volume-detail 12345678
```
このコマンドは、ID 12345678 のボリュームの詳細を表示します。

## ibmcloud sl block volume-duplicate
{: #sl_block_volume_duplicate}

既存のボリュームを複写してブロック・ボリュームを注文します。
```
ibmcloud sl block volume-duplicate VOLUME_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-o, --origin-snapshot-id</dt>
<dd>重複に使用する元のボリュームのスナップショットの ID。</dd>
<dt>-s, --duplicate-size</dt>
<dd>重複ブロック・ボリュームのサイズ (GB)。サイズが指定されない場合、元のボリュームのサイズが使用されます。</dd>
<dt>-i, --duplicate-iops</dt>
<dd>パフォーマンス・ストレージ IOPS (100 から 6000 までの範囲内の 100 の倍数)。IOPS が指定されない場合、元のボリュームの IOPS が使用されます。</dd>
<dt>-t, --duplicate-tier</dt>
<dd>エンデュランス・ストレージ層。層が指定されない場合、元のボリュームの層が使用されます。</dd>
<dt>-n, --duplicate-snapshot-size</dt>
<dd>重複用に注文するスナップショット・スペースのサイズ。スナップショット・スペース・サイズが指定されない場合、元のボリュームのスナップショット・スペース・サイズが使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-duplicate 12345678
```
このコマンドは、ID 12345678 のボリュームを複写して新規ボリュームを注文します。

## ibmcloud sl block volume-order
{: #sl_block_volume_order}

ブロック・ストレージ・ボリュームを注文します。
```
ibmcloud sl block volume-order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-t, --storage-type</dt>
<dd>必須。 ストレージ・ボリュームのタイプ。オプション: performance、endurance。</dd>
<dt>-s, --size</dt>
<dd>必須。 ストレージ・ボリュームのサイズ (GB)。</dd>
<dt>-i, --iops</dt>
<dd>パフォーマンス・ストレージの IOP (100 から 6000 までの範囲内の 100 の倍数) [storage-type が performance の場合は必須]。</dd>
<dt>-e, --tier</dt>
<dd>エンデュランス・ストレージ層 (GB 当たりの IOP) [storage-type が endurance の場合は必須]。オプションは、0.25、2、4、10 です。</dd>
<dt>-o, --os-type</dt>
<dd>必須。 オペレーティング・システム。オプション: HYPER_V、LINUX、VMWARE、WINDOWS_2008、WINDOWS_GPT、WINDOWS、XEN。</dd>
<dt>-d, --datacenter</dt>
<dd>必須。 データ・センターの短縮名。</dd>
<dt>-n, --snapshot-size</dt>
<dd>エンデュランス・ブロック・ストレージと共にスナップショット・スペースを注文するためのオプション・パラメーター。注文するスナップショット・スペースのサイズ (GB) を指定します。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

**例**:
```
ibmcloud sl block volume-order --storage-type performance --size 1000 --iops 4000 --os-type LINUX -d dal09
```
このコマンドは、サイズが 1000 GB、IOPS が 4000、OS タイプが LINUX、ロケーションが dal09 のパフォーマンス・ボリュームを注文します。

## ibmcloud sl block volume-options
{: #sl_block_volume_options}

ブロック・ストレージの注文に関するすべてのオプションをリストします。
```
ibmcloud sl block volume-options
```


**例**:
```
ibmcloud sl block volume-options
```
このコマンドは、ブロック・ストレージ・ボリュームの作成に関するすべてのオプション (ストレージ・タイプ、ボリューム・サイズ、OS タイプ、IOPS、階層レベル、データ・センター、およびスナップショット・サイズ) をリストします。
