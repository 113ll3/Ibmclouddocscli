---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, manage security groups, ingress, egress, traffic, virtual server cli, classic infrastructure cli, securitygroup, ibmcloud sl securitygroup, security group cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理虛擬伺服器資料流量的安全群組
{: #sl-manage-securitygroups}

安全群組是一組 IP 過濾器規則，定義如何處理虛擬伺服器實例公用和專用介面的送入（進入）和送出（輸出）資料流量。您新增至安全群組的規則稱為「安全群組規則」。

請使用下列指令來管理採用 {{site.data.keyword.cloud}} 標準基礎架構 Security Group 服務的安全群組。
{: shortdesc}

## ibmcloud sl securitygroup create
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

## ibmcloud sl securitygroup delete
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

## ibmcloud sl securitygroup detail
{: #sl_securitygroup_detail}

取得安全群組的詳細資料。
```
ibmcloud sl securitygroup detail SECURITYGROUP_ID [OPTIONS]
```

## ibmcloud sl securitygroup edit
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

## ibmcloud sl securitygroup interface-add
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

## ibmcloud sl securitygroup interface-list
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

## ibmcloud sl securitygroup interface-remove
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

## ibmcloud sl securitygroup list
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

## ibmcloud sl securitygroup rule-add
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

## ibmcloud sl securitygroup rule-edit
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

## ibmcloud sl securitygroup rule-list
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

## ibmcloud sl securitygroup rule-remove
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
