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

# 管理標準基礎架構問題單
{: #manage-sl-tickets}

請使用下列指令來管理 {{site.data.keyword.cloud}} 標準基礎架構問題單。
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

若要將裝置連接至問題單，請執行：
```
ibmcloud sl ticket attach TICKETID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--hardware</dt>
<dd>要連接的硬體 ID。</dd>
<dt>--virtual</dt>
<dd>要連接的虛擬伺服器 ID。</dd>
</dl>

**範例**：
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

若要建立支援問題單，請執行：
```
ibmcloud sl ticket create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--attachment</dt>
<dd>要連接至問題單的起始物件 ID 號碼。</dd>
<dt>--rootpwd</dt>
<dd>與連接的裝置 ID 相關聯的 root 密碼。</dd>
<dt>--subject-id</dt>
<dd>必要。用於問題單的主旨 ID，發出 `ibmcloudsl ticket subjects` 可取得清單。</dd>
<dt>--title</dt>
<dd>必要。問題單的標題。</dd>
<dt>--body</dt>
<dd>問題單內文。</dd>
<dt>--priority</dt>
<dd>問題單優先順序 [1|2|3|4]，從 1（嚴重）到 4（最低影響）。只有具有「進階」及「超值」支援才能設定。請參閱 https://www.ibm.com/cloud/support</dd>
<dt>--attachment-type</dt>
<dd>指定附件的類型是 hardware 或 virtual。預設值為 hardware。</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

若要從問題單分離裝置，請執行：
```
ibmcloud sl ticket detach TICKETID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--hardware</dt>
<dd>要分離的硬體 ID。</dd>
<dt>--virtual</dt>
<dd>要分離的虛擬伺服器 ID。</dd>
</dl>

**範例**：
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

若要檢視問題單詳細資料，請執行：
```
ibmcloud sl ticket detail TICKETID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--count</dt>
<dd>更新數目。</dd>
</dl>

**範例**：
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

若要列出問題單，請執行：
```
ibmcloud sl ticket list[OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--open</dt>
<dd>只顯示已開立的問題單。</dd>
<dt>--closed</dt>
<dd>只顯示已關閉的問題單。</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

若要列出「主旨 ID」以建立問題單，請執行：
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

若要檢視問題單的摘要資訊，請執行：
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

若要將更新新增至現有的問題單，請執行：
```
ibmcloud sl ticket update TICKETID ["CONTENTS"]
```

**範例**：
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

若要將附件新增至現有的問題單，請執行：
```
ibmcloud sl ticket upload TICKETID FILEPATH
```

<strong>指令選項</strong>：
<dl>
<dt>--name</dt>
<dd>問題單中顯示的附件名稱。</dd>
</dl>

**範例**：
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

