---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl globalip, globalip, global ip addresses, assign global ip

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理廣域 IP
{: #sl-manage-global-ip}

廣域 IP 位址是特殊化的靜態次要子網路。它以 /32 子網路（換句話說，單一 IP 位址）的形式交付給您，可以遞送至您帳戶上的任何其他 IP 位址。

請使用下列指令在 {{site.data.keyword.Bluemix}} 標準基礎架構 Global IP 服務中管理廣域 IP。
{: shortdesc}

## ibmcloud sl globalip assign
{: #sl_globalip_assign}

將廣域 IP 指派給目標路由器或裝置。
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```

**範例**：
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```

這個指令會將 ID 為 `12345678` 的 IP 位址指派給 IP 位址為 `9.111.123.456` 的目標裝置。

## ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

取消廣域 IP。
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl globalip cancel 12345678
```

這個指令會取消 ID 為 `12345678` 的 IP 位址。

 ## ibmcloud sl globalip create
{: #sl_globalip_create}

建立廣域 IP。
```
ibmcloud sl globalip create [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--v6</dt>
<dd>訂購 IPv6 IP 位址。</dd>
<dt>--test</dt>
<dd>測試訂購。</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認。</dd>
</dl>

**範例**：
```
ibmcloud sl globalip create --v6
```

這個指令會建立 IP V6 位址。

## ibmcloud sl globalip list
{: #sl_globalip_list}

列出您帳戶上的所有廣域 IP。
```
ibmcloud sl globalip list [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--v4</dt>
<dd>僅顯示 IPv4。</dd>
<dt>--v6</dt>
<dd>僅顯示 IPv6。</dd>
<dt>--order</dt>
<dd>依購買此 IP 位址的訂單 ID 進行過濾。</dd>
</dl>

**範例**：
```
ibmcloud sl globalip list --v4
```

這個指令會列出現行帳戶上的所有 IPV4 位址。

## ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

取消指派目標路由器或裝置中的廣域 IP。
```
ibmcloud sl globalip unassign IDENTIFIER
```


**範例**：
```
ibmcloud sl globalip unassign 12345678
```

這個指令會取消指派目標裝置中 ID 為 `12345678` 的 IP 位址。
