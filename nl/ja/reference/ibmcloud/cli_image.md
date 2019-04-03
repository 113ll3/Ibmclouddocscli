---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl image, manage compute images, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# コンピュート・イメージの作成、編集、および削除
{: #sl-manage-compute-images}

以下のコマンドを使用して、{{site.data.keyword.cloud}} コンピュート・イメージを管理します。
{: shortdesc}

## ibmcloud sl image delete
{: #sl_image_delete}

イメージを削除します。
```
ibmcloud sl image delete IDENTIFIER
```

**例**:
```
ibmcloud sl image delete 12345678
```

このコマンドは、ID `12345678` のイメージを削除します。

## ibmcloud sl image detail
{: #sl_image_detail}

イメージの詳細を取得します。
```
ibmcloud sl image detail IDENTIFIER
```

**例**:
```
 ibmcloud sl image detail 12345678
```

このコマンドは、ID `12345678` のイメージの詳細を取得します。

## ibmcloud sl image edit
{: #sl_image_edit}

イメージの詳細を編集します。
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--name</dt>
<dd>イメージの名前。</dd>
<dt>--note</dt>
<dd>イメージの追加のメモ。</dd>
<dt>--tag</dt>
<dd>イメージのタグ。</dd>
</dl>

*例**:
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```

このコマンドは、ID `12345678` のイメージを編集し、名前を「`ubuntu16`」に設定し、メモを「`testing`」に設定し、タグを「`staging`」に設定します。

## ibmcloud sl image list
{: #sl_image_list}

ご使用のアカウントのすべてのイメージをリストします。
```
ibmcloud sl image list [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--name</dt>
<dd>イメージ名を基準にフィルター操作します。</dd>
<dt>--public</dt>
<dd>パブリック・イメージのみを表示します。</dd>
<dt>--private</dt>
<dd>プライベート・イメージのみを表示します。</dd>
</dl>
