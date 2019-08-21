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

# DNS サービスを使用したドメインの管理
{: #sl-manage-domains}

{{site.data.keyword.cloud}} Domain Name Service (DNS) は、お客様が基本 DNS 管理インターフェースを使用して 1 カ所でドメインを表示したり管理したりできるようにします。また、同一の場所でリバース DNS と 2 次 DNS を管理するオプションも無料で提供しています。

以下のコマンドを使用して、{{site.data.keyword.cloud_notm}} クラシック・インフラストラクチャーの DNS サービスを管理します。
{: shortdesc}

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
