---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing classic infrastructure orders and quotes

<table summary="Alphabetically ordered general {{site.data.keyword.BluSoftlayer_notm}} infrastructure commands that have links that bring you to more info for the command">
 <caption>Table 1. Classic instrastructure orders</caption>
 <thead>
 <th colspan="6">Classic instrastructure orders</th>
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

List the categories of a package
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>Command options</strong>:
<dl>
<dt>--required</dt>
<dd>List only the required categories for the package</dd>
</dl>

**Examples**:
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
This command list the categories of Bare Metal servers.

## ibmcloud sl order item-list
{: #sl_order_item_list}

List package items used for ordering
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Command options</strong>:
<dl>
<dt>--keyword</dt>
<dd>A word (or string) used to filter item names</dd>
<dt>--category</dt>
<dd>Category code to filter items by</dd>
</dl>

**Examples**:
```
ibmcloud sl order item-list CLOUD_SERVER
```
This command list all items in the VSI package.

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

List Datacenters a package can be ordered in
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

Place or verify an order
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--preset</dt>
<dd>The order preset (if required by the package)</dd>
<dt>--verify</dt>
<dd>Flag denoting whether or not to only verify the order, not place it</dd>
<dt>--billing</dt>
<dd>Billing rate [hourly|monthly], [default: hourly]</dd>
<dt>--complex-type</dt>
<dd>The complex type of the order. This typically begins with 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>JSON string denoting extra data that needs to be sent with the order</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation</dd>
</dl>

**Examples**:
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
This command order an hourly VSI with 4 CPU, 16 GB RAM, 100 GB SAN disk, Ubuntu 16.04, and 1 Gbps public & private uplink in dal13

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Place a quote
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Command options</strong>:
<dl>
<dt>--preset</dt>
<dd>The order preset (if required by the package)</dd>
<dt>--verify</dt>
<dd>Flag denoting whether or not to only verify the order, not place it</dd>
<dt>--billing</dt>
<dd>Billing rate [hourly|monthly], [default: hourly]</dd>
<dt>--complex-type</dt>
<dd>The complex type of the order. This typically begins with 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>JSON string denoting extra data that needs to be sent with the order</dd>
<dt>-f, --force</dt>
<dd>Force operation without confirmation</dd>
</dl>

**Examples**:
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
This command place quote a VSI with 4 CPU, 16 GB RAM, 100 GB SAN disk, Ubuntu 16.04, and 1 Gbps public & private uplink in dal13

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

List package presets
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Command options</strong>:
<dl>
<dt>--keyword</dt>
<dd>A word (or string) used to filter item names</dd>
</dl>

**Examples**:
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
This command list the presets for Bare Metal servers
