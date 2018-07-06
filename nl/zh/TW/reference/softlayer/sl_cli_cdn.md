---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CDN CLI 指令

 <table summary="按字母順序排序的一般 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令，其鏈結提供指令的相關資訊">
<caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} 基礎架構 CDN</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 基礎架構 CDN</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl cdn cancel](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_cancel)</td>
  <td>[ibmcloud sl cdn detail](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_detail)</td>
  <td>[ibmcloud sl cdn list](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_list)</td>
  <td>[ibmcloud sl cdn load](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_load)</td>
  <td>[ibmcloud sl cdn order](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_order)</td>
  <td>[ibmcloud sl cdn options](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_options)</td>
   </tr>
 <tr>
  <td>[ibmcloud sl cdn origin-add](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_origin_add)</td>
  <td>[ibmcloud sl cdn origin-list](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_origin_list)</td>
  <td>[ibmcloud sl cdn origin-remove](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_origin_remove)</td>
  <td>[ibmcloud sl cdn purge](/docs/cli/reference/softlayer/sl_cli_cdn.html#sl_cdn_purge)</td>
  </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl cdn cancel
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

### ibmcloud sl cdn detail
{: #sl_cdn_detail}

詳述 CDN 帳戶。
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### ibmcloud sl cdn list
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
<dd>依訂單 ID 過濾。</dd>
</dl>

### ibmcloud sl cdn load
{: #sl_cdn_load}

在所有邊緣節點上快取一個以上的檔案。
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### ibmcloud sl cdn order
{: #sl_cdn_order}

訂購 CDN 帳戶。
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-b, --bandwidth</dt>
<dd>如果未指定，將會使用 CDN 頻寬「隨收隨付制」價格。</dd>
<dt>-s, --storage</dt>
<dd>如果未指定，將會使用 CDN 儲存空間「隨收隨付制」價格。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

### ibmcloud sl cdn options
{: #sl_cdn_options}

訂購 CDN 帳戶的頻寬及儲存空間選項。
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
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

### ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

列出原始取回對映。
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

### ibmcloud sl cdn origin-remove
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

### ibmcloud sl cdn purge
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
