---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 用來管理 {{site.data.keyword.Bluemix_notm}} 基礎架構安全群組的指令

<table summary="按字母順序排序的一般 {{site.data.keyword.Bluemix_notm}} 基礎架構指令，其鏈結提供指令的相關資訊">
<caption>表 1. {{site.data.keyword.Bluemix_notm}} 基礎架構 securitygroup 指令</caption>
 <thead>
 <th colspan="5">{{site.data.keyword.Bluemix_notm}} 基礎架構 securitygroup 指令</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl securitygroup create](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_create)</td>
  <td>[ibmcloud sl securitygroup delete](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_delete)</td>
  <td>[ibmcloud sl securitygroup detail](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_detail)</td>
  <td>[ibmcloud sl securitygroup edit](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_edit)</td>   
  <td>[ibmcloud sl securitygroup interface-add](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_interface_add)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl securitygroup interface-list](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_interace_list)</td>
  <td>[ibmcloud sl securitygroup interface-remove](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_interface_remove)</td>
  <td>[ibmcloud sl securitygroup list](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_list)</td>
  <td>[ibmcloud sl securitygroup rule-add](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_add)</td>
  <td>[ibmcloud sl securitygroup rule-edit](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_edit)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl securitygroup rule-list](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_list)</td>
  <td>[ibmcloud sl securitygroup rule-remove](/docs/cli/reference/ibmcloud/cli_securitygroup.html#sl_securitygroup_rule_remove)</td>
 </tr>
   </tbody>
 </table>

 ### ibmcloud sl securitygroup create
{: #sl_securitygroup_create}

建立安全群組。
```
ibmcloud sl securitygroup create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --name</dt>
<dd>安全群組的名稱。</dd>
<dt>-d, --description</dt>
<dd>安全群組的說明。</dd>
</dl>

### ibmcloud sl securitygroup delete
{: #sl_securitygroup_delete}

刪除給定的安全群組。
```
ibmcloud sl securitygroup delete SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

### ibmcloud sl securitygroup detail
{: #sl_securitygroup_detail}

取得安全群組的詳細資料。
```
ibmcloud sl securitygroup detail SECURITYGROUP_ID [OPTIONS]
```

### ibmcloud sl securitygroup edit
{: #sl_securitygroup_edit}

編輯安全群組的詳細資料。
```
ibmcloud sl securitygroup edit SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --name</dt>
<dd>安全群組的名稱。</dd>
<dt>-d, --description</dt>
<dd>安全群組的說明。</dd>
</dl>

### ibmcloud sl securitygroup interface-add
{: #sl_securitygroup_interface_add}

將介面連接到安全群組。
```
ibmcloud sl securitygroup interface-add SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --network-component</dt>
<dd>要與安全群組相關聯的網路元件 ID。</dd>
<dt>-s, --server</dt>
<dd>要與安全群組相關聯的伺服器 ID。</dd>
<dt>-i, --interface</dt>
<dd>要關聯的伺服器介面（公用/專用）。</dd>
</dl>

### ibmcloud sl securitygroup interface-list
{: #sl_securitygroup_interface_list}

列出與安全群組相關聯的介面。
```
ibmcloud sl securitygroup interface-list SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、virtualServerId、hostname。</dd>
</dl>

### ibmcloud sl securitygroup interface-remove
{: #sl_securitygroup_interface_remove}

將介面從安全群組分離。
```
ibmcloud sl securitygroup interface-remove SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-n, --network-component</dt>
<dd>要從安全群組移除的網路元件 ID。</dd>
<dt>-s, --server</dt>
<dd>要從安全群組移除的伺服器 ID。</dd>
<dt>-i, --interface</dt>
<dd>要移除的伺服器介面（公用/專用）。</dd>
</dl>

### ibmcloud sl securitygroup list
{: #sl_securitygroup_list}

列出安全群組。
```
List security groups
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、name、description、created。</dd>
</dl>

### ibmcloud sl securitygroup rule-add
{: #sl_securitygroup_rule_add}

將安全群組規則新增至安全群組。
```
ibmcloud sl securitygroup rule-add SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-r, --remote-ip</dt>
<dd>要施行的遠端 IP/CIDR。</dd>
<dt>-s, --remote-group</dt>
<dd>要施行之遠端安全群組的 ID。</dd>
<dt>-d, --direction</dt>
<dd>要施行的資料流量方向（進入、輸出）。</dd>
<dt>-e, --ether-type</dt>
<dd>要施行的 ethertype（IPv4 或 IPv6），如果未指定，則預設值為 IPv4。</dd>
<dt>-M, --port-max</dt>
<dd>要施行的埠上限。</dd>
<dt>-m, --port-min</dt>
<dd>要施行的埠下限。</dd>
<dt>-p, --protocol</dt>
<dd>要施行的通訊協定（icmp、tcp、udp）。</dd>
</dl>

### ibmcloud sl securitygroup rule-edit
{: #sl_securitygroup_rule_edit}

編輯安全群組中的安全群組規則。
```
ibmcloud sl securitygroup rule-edit SECURITYGROUP_ID RULE_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-r, --remote-ip</dt>
<dd>要施行的遠端 IP/CIDR。</dd>
<dt>-s, --remote-group</dt>
<dd>要施行之遠端安全群組的 ID。</dd>
<dt>-d, --direction</dt>
<dd>要施行的資料流量方向（進入、輸出）。</dd>
<dt>-e, --ether-type</dt>
<dd>要施行的 ethertype（IPv4 或 IPv6），如果未指定，則預設值為 IPv4。</dd>
<dt>-M, --port-max</dt>
<dd>要施行的埠上限。</dd>
<dt>-m, --port-min</dt>
<dd>要施行的埠下限。</dd>
<dt>-p, --protocol</dt>
<dd>要施行的通訊協定（icmp、tcp、udp）。</dd>
</dl>

### ibmcloud sl securitygroup rule-list
{: #sl_securitygroup_rule_list}

列出安全群組規則。
```
ibmcloud sl securitygroup rule-list SECURITYGROUP_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式，選項包含：id、remoteIp、remoteGroupId、direction、ethertype、portRangeMin、portRangeMax、protocol。</dd>
</dl>

### ibmcloud sl securitygroup rule-remove
{: #sl_securitygroup_rule_remove}

從安全群組移除規則。
```
ibmcloud sl securitygroup rule-remove SECURITYGROUP_ID RULE_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>
