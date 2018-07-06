---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 廣域 IP CLI 指令

<table summary="按字母順序排序的一般 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令，其鏈結提供指令的相關資訊">
<caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} 基礎架構廣域 IP 指令</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} 基礎架構廣域 IP 指令</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl globalip assign
{: #sl_globalip_assign}

將廣域 IP 指派給目標路由器或裝置。
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**範例**：
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
這個指令會將 ID 為 12345678 的 IP 位址指派給 IP 位址為 9.111.123.456 的目標裝置。


### ibmcloud sl globalip cancel
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
這個指令會取消 ID 為 12345678 的 IP 位址。
 
 ### ibmcloud sl globalip create
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

### ibmcloud sl globalip list
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
<dd>依購買此 IP 位址的訂單 ID 過濾。</dd>
</dl>

**範例**：
```
ibmcloud sl globalip list --v4
```
這個指令會列出現行帳戶上的所有 IPV4 位址。

### ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

取消指派目標路由器或裝置中的廣域 IP。
```
ibmcloud sl globalip unassign IDENTIFIER
```


**範例**：
```
ibmcloud sl globalip unassign 12345678
```
這個指令會取消指派目標裝置中 ID 為 12345678 的 IP 位址。
