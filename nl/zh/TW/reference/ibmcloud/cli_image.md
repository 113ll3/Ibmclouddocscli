---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic infrastructure, ibmcloud sl image, manage compute images, create compute image cli, compute image cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 建立、編輯及刪除運算映像檔
{: #sl-manage-compute-images}

請使用下列指令管理 {{site.data.keyword.cloud}} 運算映像檔。
{: shortdesc}

## ibmcloud sl image delete
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


## ibmcloud sl image detail
{: #sl_image_detail}

取得映像檔的詳細資料。
```
ibmcloud sl image detail IDENTIFIER
```

**範例**：
```
 ibmcloud sl image detail 12345678
```

這個指令會取得 ID 為 `12345678` 的映像檔的詳細資料。

## ibmcloud sl image edit
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


## ibmcloud sl image list
{: #sl_image_list}

列出您帳戶上的所有映像檔。
```
ibmcloud sl image list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--name</dt>
<dd>依映像檔名稱進行過濾。</dd>
<dt>--public</dt>
<dd>僅顯示公用映像檔。</dd>
<dt>--private</dt>
<dd>僅顯示專用映像檔。</dd>
</dl>
