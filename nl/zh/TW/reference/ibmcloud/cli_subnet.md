---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, manage subnet cli, classic infrastructure cli, subnet cli, ibmcloud sl subnet, subnet cli, newtork cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 建立、取消及檢視子網路
{: #sl-manage-subnets}

子網路是將 IP 網路分成多個較小網路區段的邏輯分割區。請使用下列指令來管理 {{site.data.keyword.cloud}} 標準基礎架構子網路。
{: shortdesc}

## ibmcloud sl subnet cancel
{: #sl_subnet_cancel}

取消子網路。
```
ibmcloud sl subnet cancel IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl subnet cancel 12345678 -f
```
這個指令會取消 ID 為 `12345678` 的子網路，而不要求確認。

## ibmcloud sl subnet create
{: #sl_subnet_create}

將新子網路新增至您的帳戶。
```
ibmcloud sl subnet create NETWORK QUANTITY VLAN_ID [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--v6, --ipv6</dt>
<dd>訂購 IPv6 位址。</dd>
<dt>--test</dt>
<dd>不要訂購子網路；只要取得報價。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl subnet create public 16 567
```
{: codeblock}

這個指令會建立含有 16 個 IP V4 位址的公用子網路，並將其放在 ID 為 `567` 的 VLAN 上。

## ibmcloud sl subnet detail
{: #sl_subnet_detail}

取得子網路的詳細資料。
```
ibmcloud sl subnet detail IDENTIFIER [OPTIONS]
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
ibmcloud sl subnet detail 12345678
```
{: codeblock}

這個指令會顯示 ID 為 `12345678` 的子網路的詳細資訊，包括虛擬伺服器及硬體伺服器資訊。

## ibmcloud sl subnet list
{: #sl_subnet_list}

列出您帳戶上的所有子網路。
```
ibmcloud sl subnet list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--sortby</dt>
<dd>直欄排序方式。選項包含：id、identifier、type、network_space、datacenter、vlan_id、IPs、hardware、vs。</dd>
<dt>-d, --datacenter</dt>
<dd>依資料中心簡稱進行過濾。</dd>
<dt>--identifier</dt>
<dd>依網路 ID 進行過濾。</dd>
<dt>-t, --subnet-type</dt>
<dd>依子網路類型進行過濾。</dd>
<dt>--network-space</dt>
<dd>依網路空間進行過濾。</dd>
<dt>--v4, --ipv4</dt>
<dd>僅顯示 IPv4 子網路。</dd>
<dt>--v6, --ipv6</dt>
<dd>僅顯示 IPv6 子網路。</dd>
<dt>--order</dt>
<dd>依購買子網路的訂單 ID 進行過濾。</dd>
</dl>

**範例**：
```
ibmcloud sl subnet list -d dal09 -t PRIMARY --network-space PUBLIC --v4
```
{: codeblock}

這個指令會列出現行帳戶上的 IP V4 子網路，用來過濾的資料中心為 `dal09`、子網路類型為 `PRIMARY`，而網路空間為 `PUBLIC`。

## ibmcloud sl subnet lookup
{: #sl_subnet_lookup}

尋找 IP 位址，並顯示其子網路及裝置資訊。
```
ibmcloud sl subnet lookup IP_ADDRESS
```

**範例**：
```
ibmcloud sl subnet lookup 9.125.235.255
```
{: codeblock}

這個指令會尋找 IP 位址為 `9.125.235.255` 的 IP 位址記錄，並顯示其子網路及裝置資訊。
