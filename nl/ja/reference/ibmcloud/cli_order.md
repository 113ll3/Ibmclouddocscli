---

copyright:

  years: 2018


lastupdated: "2018-11-05"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# オーダー

<table summary="コマンドの詳細情報を表示するリンクが含まれたアルファベット順の汎用 {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー・コマンド">
 <caption>表 1. {{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー注文</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}} インフラストラクチャー注文</th>
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

パッケージのカテゴリーをリストします
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--required</dt>
<dd>パッケージに必要なカテゴリーのみをリストします</dd>
</dl>

**例**:
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
このコマンドは、ベアメタル・サーバーのカテゴリーをリストします。

## ibmcloud sl order item-list
{: #sl_order_item_list}

注文に使用されるパッケージ項目をリストします
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--keyword</dt>
<dd>項目名をフィルター操作するために使用される単語 (またはストリング)</dd>
<dt>--category</dt>
<dd>項目のフィルター操作で使用するカテゴリー・コード</dd>
</dl>

**例**:
```
ibmcloud sl order item-list CLOUD_SERVER
```
このコマンドは、VSI パッケージ内のすべての項目をリストします。

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

パッケージを注文できるデータ・センターをリストします
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

注文の実行または検証
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--preset</dt>
<dd>注文の事前設定 (パッケージで必要な場合)</dd>
<dt>--verify</dt>
<dd>注文の実行ではなく、注文の検証のみを行うかどうかを示すフラグ</dd>
<dt>--billing</dt>
<dd>請求レート [hourly|monthly]、[デフォルト: hourly]</dd>
<dt>--complex-type</dt>
<dd>注文の複合タイプ。 これは通常、「SoftLayer_Container_Product_Order_」で始まります</dd>
<dt>--extras</dt>
<dd>注文とともに送信する必要がある追加のデータを示す JSON ストリング</dd>
<dt>-f, --force</dt>
<dd>確認を求めずに操作を強制します</dd>
</dl>

**例**:
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
このコマンドは、4 つの CPU、16 GB RAM、100 GB SAN ディスク、Ubuntu 16.04 が搭載され、パブリック・アップリンクとプライベート・アップリンクが 1 Gbps で、dal13 にある時間単位の VSI を注文します

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

見積もり
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--preset</dt>
<dd>注文の事前設定 (パッケージで必要な場合)</dd>
<dt>--verify</dt>
<dd>注文の実行ではなく、注文の検証のみを行うかどうかを示すフラグ</dd>
<dt>--billing</dt>
<dd>請求レート [hourly|monthly]、[デフォルト: hourly]</dd>
<dt>--complex-type</dt>
<dd>注文の複合タイプ。 これは通常、「SoftLayer_Container_Product_Order_」で始まります</dd>
<dt>--extras</dt>
<dd>注文とともに送信する必要がある追加のデータを示す JSON ストリング</dd>
<dt>-f, --force</dt>
<dd>確認を求めずに操作を強制します</dd>
</dl>

**例**:
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
このコマンドは、4 つの CPU、16 GB RAM、100 GB SAN ディスク、Ubuntu 16.04 が搭載され、パブリック・アップリンクとプライベート・アップリンクが 1 Gbps で、dal13 にある VSI の見積もりを行います

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

パッケージの事前設定をリストします
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>コマンド・オプション</strong>:
<dl>
<dt>--keyword</dt>
<dd>項目名をフィルター操作するために使用される単語 (またはストリング)</dd>
</dl>

**例**:
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
このコマンドは、ベアメタル・サーバーの事前設定をリストします
