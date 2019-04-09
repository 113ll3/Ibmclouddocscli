---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理標準基礎架構訂單和報價

<table summary="按字母順序排序的一般 {{site.data.keyword.BluSoftlayer_notm}} 基礎架構指令，其鏈結提供指令的相關資訊">
<caption>表 1. 標準基礎架構訂單</caption>
 <thead>
 <th colspan="6">標準基礎架構訂單</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl order package-locations](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_category_list)</td>
  <td>[ibmcloud sl order item-list](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_item_list)</td>
  <td>[ibmcloud sl order package-locations](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_package_locations)</td>
  <td>[ibmcloud sl order place](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_place)</td>
  <td>[ibmcloud sl order place-quote](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_place_quote)</td>
  <td>[ibmcloud sl order preset-list](/docs/cli/reference/ibmcloud/cli_order.html#sl_order_preset_list)</td>
 </tr>
 </tbody>
</table>

## ibmcloud sl order package-locations
{: #sl_order_category_list}

列出套件的種類。
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>指令選項</strong>：
<dl>
<dt>--required</dt>
<dd>只列出套件的必要種類。</dd>
</dl>

**範例**：
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
這個指令會列出 Bare Metal Server 的種類。

## ibmcloud sl order item-list
{: #sl_order_item_list}

列出用於訂購的套件項目
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>指令選項</strong>：
<dl>
<dt>--keyword</dt>
<dd>用來過濾項目名稱的單字（或字串）</dd>
<dt>--category</dt>
<dd>用來過濾項目的種類代碼</dd>
</dl>

**範例**：
```
ibmcloud sl order item-list CLOUD_SERVER
```
這個指令會列出 VSI 套件中的所有項目。

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

列出可在其中訂購套件的資料中心
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

下訂單或驗證訂單
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--preset</dt>
<dd>訂單預設值（如果套件需要的話）</dd>
<dt>--verify</dt>
<dd>表示是否只要驗證訂單，而不下訂單的旗標</dd>
<dt>--billing</dt>
<dd>計費頻率 [每小時|每月]，[預設值：每小時]</dd>
<dt>--complex-type</dt>
<dd>訂單的複式類型。這通常是以 'SoftLayer_Container_Product_Order_' 開頭</dd>
<dt>--extras</dt>
<dd>表示需要與訂單一起傳送之額外資料的 JSON 字串</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認</dd>
</dl>

**範例**：
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
這個指令會訂購 dal13 中以每小時計費的 VSI（內含 4 個 CPU、16 GB RAM、100 GB SAN 磁碟、Ubuntu 16.04 及 1 Gbps 的公用與專用上行鏈路）

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

報價
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>指令選項</strong>：
<dl>
<dt>--preset</dt>
<dd>訂單預設值（如果套件需要的話）</dd>
<dt>--verify</dt>
<dd>表示是否只要驗證訂單，而不下訂單的旗標</dd>
<dt>--billing</dt>
<dd>計費頻率 [每小時|每月]，[預設值：每小時]</dd>
<dt>--complex-type</dt>
<dd>訂單的複式類型。這通常是以 'SoftLayer_Container_Product_Order_' 開頭</dd>
<dt>--extras</dt>
<dd>表示需要與訂單一起傳送之額外資料的 JSON 字串</dd>
<dt>-f, --force</dt>
<dd>強制執行作業，而不進行確認</dd>
</dl>

**範例**：
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
這個指令會對 dal13 中的 VSI（內含 4 個 CPU、16 GB RAM、100 GB SAN 磁碟、Ubuntu 16.04 及 1 Gbps 的公用與專用上行鏈路）進行報價

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

列出套件預設值
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>指令選項</strong>：
<dl>
<dt>--keyword</dt>
<dd>用來過濾項目名稱的單字（或字串）</dd>
</dl>

**範例**：
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
這個指令會列出 Bare Metal Server 的預設值。
