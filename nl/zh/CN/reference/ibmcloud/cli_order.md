---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic cli, orders, quotes, ibmcloud sl order, item-list, package-locations, manage orders cli, manage quotes cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 管理经典基础架构订购和报价
{: #sl-manage-classic-orders}

使用以下命令可管理经典基础架构订购和报价。

## ibmcloud sl order package-locations
{: #sl_order_category_list}

列出软件包的类别
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>命令选项</strong>：
<dl>
<dt>--required</dt>
<dd>仅列出软件包的必需类别</dd>
</dl>

**示例**：
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
此命令会列出裸机服务器的类别。

## ibmcloud sl order item-list
{: #sl_order_item_list}

列出用于订购的软件包项
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>命令选项</strong>：
<dl>
<dt>--keyword</dt>
<dd>用于过滤项名称的字或字符串</dd>
<dt>--category</dt>
<dd>用于过滤项的类别代码</dd>
</dl>

**示例**：
```
ibmcloud sl order item-list CLOUD_SERVER
```
此命令会列出 VSI 软件包中的所有项。

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

列出可在其中订购软件包的数据中心
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

下订单或验证订单
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--preset</dt>
<dd>订单预设（如果软件包需要）</dd>
<dt>--verify</dt>
<dd>表示是否仅验证订单而不下订单的标志</dd>
<dt>--billing</dt>
<dd>计费费率 [hourly|monthly]，[缺省值：hourly]</dd>
<dt>--complex-type</dt>
<dd>订单的复杂类型。通常以“SoftLayer_Container_Product_Order_”开头</dd>
<dt>--extras</dt>
<dd>表示需要随订单发送的额外数据的 JSON 字符串</dd>
<dt>-f, --force</dt>
<dd>无需确认即强制执行操作</dd>
</dl>

**示例**：
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
此命令会订购按小时计费的 VSI，具有 4 个 CPU、16 GB RAM、100 GB SAN 磁盘、Ubuntu 16.04 以及 dal13 中的 1 Gbps 公共和专用上行链路

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

提供报价
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>命令选项</strong>：
<dl>
<dt>--preset</dt>
<dd>订单预设（如果软件包需要）</dd>
<dt>--verify</dt>
<dd>表示是否仅验证订单而不下订单的标志</dd>
<dt>--billing</dt>
<dd>计费费率 [hourly|monthly]，[缺省值：hourly]</dd>
<dt>--complex-type</dt>
<dd>订单的复杂类型。通常以“SoftLayer_Container_Product_Order_”开头</dd>
<dt>--extras</dt>
<dd>表示需要随订单发送的额外数据的 JSON 字符串</dd>
<dt>-f, --force</dt>
<dd>无需确认即强制执行操作</dd>
</dl>

**示例**：
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
此命令会提供 VSI 的报价，具有 4 个 CPU、16 GB RAM、100 GB SAN 磁盘、Ubuntu 16.04 以及 dal13 中的 1 Gbps 公共和专用行链路

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

列出软件包预设
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>命令选项</strong>：
<dl>
<dt>--keyword</dt>
<dd>用于过滤项名称的字或字符串</dd>
</dl>

**示例**：
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
此命令会列出裸机服务器的预设
