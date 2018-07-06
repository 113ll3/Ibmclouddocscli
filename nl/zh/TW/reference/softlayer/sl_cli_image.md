---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 映像檔 CLI 指令

<table summary="按字母順序排序的一般 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令，其鏈結提供指令的相關資訊">
<caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} 基礎架構 image 指令</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 基礎架構 image 指令</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/softlayer/sl_cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl image delete
{: #sl_image_delete}

刪除映像檔。
```
ibmcloud sl image delete IDENTIFIER
```
**範例**：
```
   ibmcloud sl image delete 12345678
```
這個指令會刪除 ID 為 `12345678` 的映像檔。


### ibmcloud sl image detail
{: #sl_image_detail}

取得映像檔的詳細資料。
```
ibmcloud sl image detail IDENTIFIER
```
**範例**：
```
 ibmcloud sl image detail 12345678
```
這個指令會取得 ID 為 12345678 的映像檔的詳細資料。

### ibmcloud sl image edit
{: #sl_image_edit}

編輯映像檔的詳細資料。
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--name</dt>
<dd>映像檔的名稱。</dd>
<dt>--note</dt>
<dd>映像檔的其他附註。</dd>
<dt>--tag</dt>
<dd>映像檔的標籤。</dd>
</dl>

*範例**：
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
這個指令會編輯 ID 為 `12345678` 的映像檔、將名稱設為 `ubuntu16`、將附註設為 `testing`，並將標籤設為 `staging`。


### ibmcloud sl image list
{: #sl_image_list}

列出您帳戶上的所有映像檔。
```
ibmcloud sl image list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--name</dt>
<dd>依映像檔名稱過濾。</dd>
<dt>--public</dt>
<dd>僅顯示公用映像檔。</dd>
<dt>--private</dt>
<dd>僅顯示專用映像檔。</dd>
</dl>
