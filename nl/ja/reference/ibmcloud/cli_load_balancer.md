---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} インフラストラクチャーのロード・バランサーを管理するためのコマンド

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・コマンド">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・ロード・バランサー・コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} インフラストラクチャー・ロード・バランサー・コマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl loadbal cancel](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_cancel)</td>
 <td>[ibmcloud sl loadbal create](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create)</td>
 <td>[ibmcloud sl loadbal create-options](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_create_options)</td>
 <td>[ibmcloud sl loadbal detail](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_detail)</td>
 <td>[ibmcloud sl loadbal group-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_add)</td>
 <td>[ibmcloud sl loadbal group-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_delete)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal group-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_edit)</td>
 <td>[ibmcloud sl loadbal group-reset](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_group_reset)</td>
 <td>[ibmcloud sl loadbal health-checks](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_health_checks)</td>
 <td>[ibmcloud sl loadbal list](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_list)</td>
 <td>[ibmcloud sl loadbal routing-methods](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_methods)</td>
 <td>[ibmcloud sl loadbal routing-types](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_routing_types)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl loadbal service-add](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_add)</td>
 <td>[ibmcloud sl loadbal service-delete](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_delete)</td>
 <td>[ibmcloud sl loadbal service-edit](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_edit)</td>
 <td>[ibmcloud sl loadbal service-toggle](/docs/cli/reference/ibmcloud/cli_load_balancer.html#sl_loadbal_service_toggle)</td>
 </tr>
</tbody>
 </table>

 ### ibmcloud sl loadbal cancel
{: #sl_loadbal_cancel}

既存のロード・バランサーを取り消します。
```
ibmcloud sl loadbal cancel LOADBAL_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal create
{: #sl_loadbal_create}

create-options から返された ID を指定してロード・バランサーを追加します。
```
ibmcloud sl loadbal create PRICE_ID LOCATION [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal create-options
{: #sl_loadbal_create_options}

ロード・バランサーの作成に使用する価格オプションを取得します。
```
ibmcloud sl loadbal create-options
```

### ibmcloud sl loadbal detail
{: #sl_loadbal_detail}

ロード・バランサーの詳細を取得します。
```
ibmcloud sl loadbal detail LOADBAL_ID
```

### ibmcloud sl loadbal group-add
{: #sl_loadbal_group_add}

新規ロード・バランサー・サービスを追加します。
```
ibmcloud sl loadbal group-add LOADBAL_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>必須。 接続の割り振り済みパーセント。</dd>
<dt>-p, --port</dt>
<dd>必須。 ポート番号。</dd>
<dt>-t, --routing-type</dt>
<dd>必須。 ルーティング・タイプの ID。 ID を検出するには、「ibmcloud sl loadbal routing-types」を実行します。</dd>
<dt>-m, --routing-method</dt>
<dd>必須。 ルーティング・メソッドの ID。 ID を検出するには、「ibmcloud sl loadbal routing-methods」を実行します。</dd>
</dl>

### ibmcloud sl loadbal group-delete
{: #sl_loadbal_group_delete}

既存のロード・バランサー・サービス・グループを削除します。
```
ibmcloud sl loadbal group-delete GROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal group-edit
{: #sl_loadbal_group_edit}

既存のロード・バランサー・サービス・グループを編集します。
```
ibmcloud sl loadbal group-edit LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-a, --allocation</dt>
<dd>接続の割り振り済みパーセントを変更します。</dd>
<dt>-p, --port</dt>
<dd>ポート番号を変更します。</dd>
<dt>-t, --routing-type</dt>
<dd>ルーティング・タイプの ID を変更します。 ID を検出するには、「ibmcloud sl loadbal routing-types」を実行します。</dd>
<dt>-m, --routing-method</dt>
<dd>ルーティング方式の ID を変更します。 ID を検出するには、「ibmcloud sl loadbal routing-methods」を実行します。</dd>
</dl>

### ibmcloud sl loadbal group-reset
{: #sl_loadbal_group_reset}

特定のサービス・グループでの接続をリセットします。
```
ibmcloud sl loadbal group-reset LOADBAL_ID GROUP_ID
```

### ibmcloud sl loadbal health-checks
{: #sl_loadbal_health_checks}

ヘルス・チェック・タイプをリストします。
```
ibmcloud sl loadbal health-checks
```

### ibmcloud sl loadbal list
{: #sl_loadbal_list}

アクティブなロード・バランサーをリストします。
```
ibmcloud sl loadbal list
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>データ・センターの短縮名を基準にフィルター操作します。</dd>
<dt>-o, --order</dt>
<dd>ロード・バランサーを購入した注文の ID を基準にフィルター操作します。</dd>
<dt>-p, --ip-address</dt>
<dd>IP アドレスを基準にしてフィルター操作します。</dd>
</dl>

### ibmcloud sl loadbal routing-methods
{: #sl_loadbal_routing_methods}

ルーティング・メソッドをリストします。
```
ibmcloud sl loadbal routing-methods
```

### ibmcloud sl loadbal routing-types
{: #sl_loadbal_routing_types}

ルーティング・タイプをリストします。
```
ibmcloud sl loadbal routing-types
```

### ibmcloud sl loadbal service-add
{: #sl_loadbal_service_add}

新規のロード・バランサー・サービスを追加します。
```
ibmcloud sl loadbal service-add LOADBAL_ID GROUP_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--disabled</dt>
<dd>オプション。 disabled としてサービスを作成します。指定されていない場合、デフォルトは enabled です。</dd>
<dt>-p, --port</dt>
<dd>必須。 サービスのポート番号。</dd>
<dt>-w, --weight</dt>
<dd>必須。 サービスの重み。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>必須。 ヘルス・チェック・タイプ。</dd>
<dt>-i, --ip-address</dt>
<dd>必須。 サービスの IP アドレス。</dd>
</dl>

### ibmcloud sl loadbal service-delete
{: #sl_loadbal_service_delete}

既存のロード・バランサー・サービスを削除します。
```
ibmcloud sl loadbal service-delete SERVICE_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

### ibmcloud sl loadbal service-edit
{: #sl_loadbal_service_edit}

サービス・グループのプロパティーを編集します。
```
ibmcloud sl loadbal service-edit LOADBAL_ID SERVICE_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--disabled</dt>
<dd>サービスを無効にします。</dd>
<dt>--enabled</dt>
<dd>サービスを有効にします。</dd>
<dt>-p, --port</dt>
<dd>サービスのポート番号を変更します。</dd>
<dt>-w, --weight</dt>
<dd>サービスの重みを変更します。</dd>
<dt>-t, --healthcheck-type</dt>
<dd>ヘルス・チェック・タイプを変更します。</dd>
<dt>-i, --ip-address</dt>
<dd>サービスの IP アドレスを変更します。</dd>
</dl>

### ibmcloud sl loadbal service-toggle
{: #sl_loadbal_service_toggle}

既存のロード・バランサー・サービスの状況を切り替えます。
```
ibmcloud sl loadbal service-toggle SERVICE_ID
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
