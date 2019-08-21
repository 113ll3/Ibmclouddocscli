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

# 使用 CDN 服務
{: #sl-cdn-service}

Content Delivery Network (CDN) 服務會將內容分散在需要內容之處。第一次要求內容時，會將內容從主伺服器取回到網路，然後留在那裡供其他使用者存取。

請使用下列指令來管理 {{site.data.keyword.cloud_notm}} 標準基礎架構 CDN 服務。
{: shortdesc}

## ibmcloud sl cdn cancel
{: #sl_cdn_cancel}

取消 CDN 帳戶。
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl cdn detail
{: #sl_cdn_detail}

詳述 CDN 帳戶。
```
ibmcloud sl cdn detail ACCOUNT_ID
```

## ibmcloud sl cdn list
{: #sl_cdn_list}

列出所有 CDN 帳戶。
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、name、type、created。</dd>
<dt>--order</dt>
<dd>依訂單 ID 進行過濾。</dd>
</dl>

## ibmcloud sl cdn load
{: #sl_cdn_load}

在所有邊緣節點上快取一個以上的檔案。
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

## ibmcloud sl cdn order
{: #sl_cdn_order}

訂購 CDN 帳戶。
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN 頻寬，如果未指定，將使用「隨收隨付制」價格。</dd>
<dt>-s, --storage</dt>
<dd>CDN 儲存空間，如果未指定，將使用「隨收隨付制」價格。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl cdn options
{: #sl_cdn_options}

訂購 CDN 帳戶的頻寬及儲存空間選項。
```
ibmcloud sl cdn options
```

## ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

建立原始取回對映。
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-t, --type</dt>
<dd>此對映的媒體類型（http、flash、wm 等），預設值為：http。</dd>
<dt>-c, --cname</dt>
<dd>要連接至對映的選用 CNAME。</dd>
</dl>

## ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

列出原始取回對映。
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

## ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

移除原始取回對映。
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

## ibmcloud sl cdn purge
{: #sl_cdn_purge}

從所有邊緣節點清除快取的檔案。
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>
