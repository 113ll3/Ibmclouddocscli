---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# VLAN

{{site.data.keyword.cloud}} 使用虛擬區域網路 (VLAN) 來隔離公用及專用網路上的廣播資料流量。VLAN 會視需要指派，以實現其他供應項目。

請使用下列指令管理 {{site.data.keyword.Bluemix_notm}} 基礎架構 VLAN。
{: shortdesc}

<table summary="按字母順序排序的 {{site.data.keyword.Bluemix_notm}} 基礎架構 VLAN 指令，其鏈結提供指令的相關資訊">
 <thead>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vlan create](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_create)</td>
 <td>[ibmcloud sl vlan cancel](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_cancel)</td>
 <td>[ibmcloud sl vlan detail](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_detail)</td>
 <td>[ibmcloud sl vlan edit](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_edit)</td>
 <td>[ibmcloud sl vlan list](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_list)</td>
 <td>[ibmcloud sl vlan options](/docs/cli/reference/ibmcloud/cli_vlan.html#sl_vlan_options)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl vlan create
{: #sl_vlan_create}

建立新的 VLAN。
```
ibmcloud sl vlan create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-t, --vlan-type</dt>
<dd>VLAN 的類型，可以是公用或專用。</dd>
<dt>-r, --router</dt>
<dd>路由器的主機名稱。</dd>
<dt>-d, --datacenter</dt>
<dd>資料中心的簡稱。</dd>
<dt>-n, --name</dt>
<dd>VLAN 的名稱。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vlan create -t public -d dal09 -s 16 -n myvlan
```
這個指令會建立一個公用 VLAN：位於資料中心 dal09、包含 16 個 IP 位址，且名稱為 myvlan。


## ibmcloud sl vlan cancel
{: #sl_vlan_cancel}

取消 VLAN。
```
ibmcloud sl vlan cancel IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl vlan cancel 12345678 -f
```
這個指令會取消 ID 為 12345678 的 VLAN，而不要求確認。

## ibmcloud sl vlan detail
{: #sl_vlan_detail}

取得 VLAN 的詳細資料。
```
ibmcloud sl vlan detail IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--no-vs</dt>
<dd>隱藏虛擬伺服器清單。</dd>
<dt>--no-hardware</dt>
<dd>隱藏硬體清單。</dd>
</dl>

**範例**：
```
ibmcloud sl vlan detail 12345678  --no-vs --no-hardware
```
這個指令會顯示 ID 為 12345678 的 VLAN 詳細資料，而不會列出虛擬伺服器或硬體伺服器。


## ibmcloud sl vlan edit
{: #sl_vlan_edit}

編輯 VLAN 的詳細資料。
```
ibmcloud sl vlan edit IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --name</dt>
<dd>VLAN 的名稱。</dd>
</dl>

**範例**：
```
ibmcloud sl vlan edit 12345678 -n myvlan-rename
```
這個指令會更新 ID 為 12345678 的 VLAN，並為其指定新名稱 "myvlan-rename"。


## ibmcloud sl vlan list
{: #sl_vlan_list}

列出您帳戶上的所有 VLAN。
```
ibmcloud sl vlan list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、number、name、firewall、datacenter、hardware、virtual_servers、public_ips。</dd>
<dt>-d, --datacenter</dt>
<dd>依資料中心簡稱過濾。</dd>
<dt>-n, --number</dt>
<dd>依 VLAN 號碼過濾。</dd>
<dt>--name</dt>
<dd>依 VLAN 名稱過濾。</dd>
<dt>--order</dt>
<dd>依購買 VLAN 的訂單 ID 過濾。</dd>
</dl>

**範例**：
```
ibmcloud sl vlan list -d dal09 --sortby number
```
這個指令會列出現行帳戶上的所有 VLAN，用來過濾的資料中心為 dal09，並依 VLAN 號碼排序。


## ibmcloud sl vlan options
{: #sl_vlan_options}

列出用來建立 VLAN 的所有選項。
```
ibmcloud sl vlan options
```


**範例**：
```
ibmcloud sl vlan options
```
這個指令會列出用來建立 VLAN 的所有選項，例如 VLAN 類型、資料中心、子網路大小、路由器等等。
