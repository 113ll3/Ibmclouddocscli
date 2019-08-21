---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, content delivery network, cdn service, cdn, classic infrastructure, ibmcloud sl cdn

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CDN サービスの操作
{: #sl-cdn-service}

コンテンツ配信ネットワーク (CDN) サービスは、必要とされる場所にコンテンツを配信します。 コンテンツは、初めて要求されたときにホスト・サーバーからネットワークにプルされて、他のユーザーがアクセスできるようにネットワークに留まります。

以下のコマンドを使用して、{{site.data.keyword.cloud_notm}} クラシック・インフラストラクチャーの CDN サービスを管理します。
{: shortdesc}

## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

CDN アカウントを取り消します。
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

CDN アカウントの詳細を表示します。
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

すべての CDN アカウントをリストします。
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--sortby</dt>
<dd>ソートの基準となる列。オプション: id、name、type、created。</dd>
<dt>--order</dt>
<dd>注文 ID でフィルター操作します。</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

すべてのエッジ・ノード上で 1 つ以上のファイルをキャッシュに入れます。
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

CDN アカウントを注文します。
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN 処理能力。指定されていなければ、「従量課金 (PAYG)」価格が使用されます。</dd>
<dt>-s, --storage</dt>
<dd>CDN ストレージ。指定されていなければ、「従量課金 (PAYG)」価格が使用されます。</dd>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

CDN アカウントを注文する際の処理能力とストレージのオプション。
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

Origin Pull マッピングを作成します。
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-t, --type</dt>
<dd>このマッピングのメディア・タイプ (http、flash、wm、...)。デフォルト: http。</dd>
<dt>-c, --cname</dt>
<dd>マッピングに付加する CNAME (オプション)。</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

Origin Pull マッピングをリストします。
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

Origin Pull マッピングを削除します。
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

すべてのエッジ・ノードからキャッシュされているファイルをパージします。
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>-f, --force</dt>
<dd>確認なしで操作を強制します。</dd>
</dl>
