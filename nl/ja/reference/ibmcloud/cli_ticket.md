---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# クラシック・インフラストラクチャーのチケットの管理
{: #manage-sl-tickets}

以下のコマンドを使用して、{{site.data.keyword.cloud}} クラシック・インフラストラクチャーのチケットを管理します。
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

デバイスをチケットに接続するには、次のようにします。
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--hardware</dt>
<dd>接続するハードウェアの ID。</dd>
<dt>--virtual</dt>
<dd>接続する仮想サーバーの ID。</dd>
</dl>

**例**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

サポート・チケットを作成するには、次のようにします。
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--attachment</dt>
<dd>チケットにアタッチする初期オブジェクト ID 番号。</dd>
<dt>--rootpwd</dt>
<dd>アタッチされるデバイス ID に関連付けられるルート・パスワード。</dd>
<dt>--subject-id</dt>
<dd>必須。 チケットに使用するサブジェクト ID。リストを取得するには `ibmcloudsl ticket subjects` を実行してください。</dd>
<dt>--title</dt>
<dd>必須。 チケットのタイトル。</dd>
<dt>--body</dt>
<dd>チケット本体。</dd>
<dt>--priority</dt>
<dd>1 (重大) から 4 (最小の影響) までの、チケットの優先順位 [1|2|3|4]。 アドバンスト・サポートとプレミアム・サポートの場合に限り設定できます。 https://www.ibm.com/cloud/support を参照してください。</dd>
<dt>--attachment-type</dt>
<dd>接続、ハードウェア、または仮想のタイプを指定します。 デフォルトはハードウェアです。</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

チケットからデバイスを切り離すには、次のようにします。
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--hardware</dt>
<dd>切り離すハードウェアの ID。</dd>
<dt>--virtual</dt>
<dd>切り離す仮想サーバーの ID。</dd>
</dl>

**例**:
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

チケットの詳細を表示するには、次のようにします。
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--count</dt>
<dd>更新の数。</dd>
</dl>

**例**:
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

チケットをリストするには、次のようにします。
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--open</dt>
<dd>オープンしているチケットのみを表示します。</dd>
<dt>--closed</dt>
<dd>クローズ済みチケットのみを表示します。</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

チケット作成のサブジェクト ID をリストするには、次のようにします。
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

チケットに関する要約情報を表示するには、次のようにします。
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

既存のチケットに更新を追加するには、次のようにします。
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**例**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

既存のチケットに添付を追加するには、次のようにします。
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--name</dt>
<dd>チケットで示される添付の名前。</dd>
</dl>

**例**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

