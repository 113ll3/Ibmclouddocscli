---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CDN CLI 命令

 <table summary="按字母顺序排序的常规 {{site.data.keyword.BluSoftlayer_notm}} 基础架构命令（命令带有可获取命令更多信息的链接）">
<caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} 基础架构 CDN</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 基础架构 CDN</th>
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

取消 CDN 帐户。
```
ibmcloud sl cdn cancel ACCOUNT_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl cdn detail
{: #sl_cdn_detail}

详细描述 CDN 帐户。
```
ibmcloud sl cdn detail ACCOUNT_ID
```

### ibmcloud sl cdn list
{: #sl_cdn_list}

列出所有 CDN 帐户。
```
ibmcloud sl cdn list [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--sortby</dt>
<dd>要作为排序依据的列，选项为：id、name、type 或 created。</dd>
<dt>--order</dt>
<dd>按订单标识过滤。</dd>
</dl>

### ibmcloud sl cdn load
{: #sl_cdn_load}

在所有边缘节点上高速缓存一个或多个文件。
```
ibmcloud sl cdn load ACCOUNT_ID CONTENT_URL [CONTENT_URL...]
```

### ibmcloud sl cdn order
{: #sl_cdn_order}

订购 CDN 帐户。
```
ibmcloud sl cdn order [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-b, --bandwidth</dt>
<dd>CDN 带宽，如果未指定，将使用“现买现付”价格。</dd>
<dt>-s, --storage</dt>
<dd>CDN 存储器，如果未指定，将使用“现买现付”价格。</dd>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl cdn options
{: #sl_cdn_options}

用于订购 CDN 帐户的带宽和存储选项。
```
ibmcloud sl cdn options
```

### ibmcloud sl cdn origin-add
{: #sl_cdn_origin_add}

创建源提取映射。
```
ibmcloud sl cdn origin-add ACCOUNT_ID CONTENT_URL [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-t, --type</dt>
<dd>此映射的介质类型 (http、flash、wm、...)，缺省值为 http。</dd>
<dt>-c, --cname</dt>
<dd>连接到映射的可选 CNAME。</dd>
</dl>

### ibmcloud sl cdn origin-list
{: #sl_cdn_origin_list}

列出源提取映射。
```
ibmcloud sl cdn origin-list ACCOUNT_ID
```

### ibmcloud sl cdn origin-remove
{: #sl_cdn_origin_remove}

除去源提取映射。
```
ibmcloud sl cdn origin-remove ACCOUNT_ID ORIGIN_ID [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>

### ibmcloud sl cdn purge
{: #sl_cdn_purge}

清除所有边缘节点中高速缓存的文件。
```
ibmcloud sl cdn purge ACCOUNT_ID CONTENT_URL [CONTENT_URL...] [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>-f, --force</dt>
<dd>强制操作而不确认。</dd>
</dl>
