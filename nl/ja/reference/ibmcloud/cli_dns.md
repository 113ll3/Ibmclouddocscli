---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} インフラストラクチャー DNS の管理

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.Bluemix_notm}} インフラストラクチャー・コマンド">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} インフラストラクチャー DNS コマンド</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.Bluemix_notm}} インフラストラクチャー DNS コマンド</th>
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

## ibmcloud sl dns import
{: #sl_dns_import}

BIND ゾーン・ファイルに基づいてゾーンをインポートします。
```
ibmcloud sl dns import ZONEFILE [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--dry-run</dt>
<dd>実際にはレコードを作成しません。</dd>
</dl>

**例**:
```
ibmcloud sl dns import ~/ibm.com.txt
```
このコマンドは、ファイル ~/ibm.com.txt からゾーンとそのリソース・レコードをインポートします。

## ibmcloud sl dns record-add
{: #sl_dns_record_add}

ゾーン内のリソース・レコードを追加します。
```
ibmcloud sl dns record-add ZONE RECORD TYPE DATA [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--ttl</dt>
<dd>TTL(Time-To-Live (存続時間)) (秒)。例えば、86400 など。デフォルト: 7200。</dd>
</dl>

**例**:
```
ibmcloud sl dns record-add ibm.com ftp A 127.0.0.1 --ttl 86400
```
このコマンドは、A レコードをゾーン ibm.com に追加します。ホストは「ftp」、データは「127.0.0.1」、および ttl は 86400 秒です。

## ibmcloud sl dns record-edit
{: #sl_dns_record_edit}

ゾーン内のリソース・レコードを更新します
```
ibmcloud sl dns record-edit ZONE [OPTIONS]
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
ibmcloud sl dns record-edit ibm.com --by-id 12345678 --data 127.0.0.2 --ttl 3600
```
このコマンドは、ゾーン ibm.com のレコードを編集します。ID は 12345678 です。データを「127.0.0.2」に設定し、ttl を 3600 に設定します。

## ibmcloud sl dns record-list
{: #sl_dns_record_list}

ゾーン内のすべてのリソース・レコードをリストします。
```
ibmcloud sl dns record-list ZONE [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--data</dt>
<dd>レコード・データ (IP アドレスなど) を基準にフィルター操作します。</dd>
<dt>--record</dt>
<dd>ホスト・レコード (www など) を基準にフィルター操作します。</dd>
<dt>--ttl</dt>
<dd>TTL 値 (秒) (例: 86400) を基準にフィルター操作します。</dd>
<dt>--type</dt>
<dd>レコード・タイプ (A または CNAME など) を基準にフィルター操作します。</dd>
</dl>

**例**:
```
ibmcloud sl dns record-list ibm.com --record elasticsearch --type A --ttl 900
```
このコマンドは、ゾーン ibm.com のすべての A レコードをリストします。フィルター基準ホストは elasticsearch で TTL は 900 秒です。

## ibmcloud sl dns record-remove
{: #sl_dns_record_remove}

ゾーンからリソース・レコードを削除します。
```
ibmcloud sl dns record-remove RECORD_ID
```


**例**:
```
ibmcloud sl dns record-remove 12345678
```
このコマンドは、ID 12345678 のリソース・レコードを削除します。

## ibmcloud sl dns zone-create
{: #sl_dns_zone_create}

ゾーンを作成します。
```
ibmcloud sl dns zone-create ZONE
```


**例**:
```
ibmcloud sl dns zone-create ibm.com
```
このコマンドは、ibm.com という名前のゾーンを作成します。

## ibmcloud sl dns zone-delete
{: #sl_dns_zone_delete}

ゾーンを削除します。
```
ibmcloud sl dns zone-delete ZONE
```


**例**:
```
ibmcloud sl dns zone-delete ibm.com
```
このコマンドは、ibm.com という名前のゾーンを削除します。

## ibmcloud sl dns zone-list
{: #sl_dns_zone_list}

ユーザーのアカウントのすべてのゾーンをリストします。
```
ibmcloud sl dns zone-list
```


**例**:
```
ibmcloud sl dns zone-list
```
このコマンドは、現行アカウントにあるすべてのゾーンをリストします。

## ibmcloud sl dns zone-print
{: #sl_dns_zone_print}

ゾーンおよびリソース・レコードを BIND フォーマットで出力します。
```
ibmcloud sl dns zone-print ZONE
```


**例**:
```
ibmcloud sl dns zone-print ibm.com
```
このコマンドは、ibm.com という名前のゾーンを BIND フォーマットで出力します。
