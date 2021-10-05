---

copyright:
  years: 2018, 2021
lastupdated: "2021-09-09"

keywords: cli, classic cli, orders, quotes, ibmcloud sl order, item-list, package-locations, manage orders cli, manage quotes cli

subcollection: cli

---


{:shortdesc: .shortdesc}
{:tip: .tip}

# Managing classic infrastructure orders and quotes (ibmcloud sl order)
{: #sl-manage-classic-orders}

Use the following commands from the {{site.data.keyword.cloud}} Command Line Interface to manage orders and quotes in your classic infrastructure.

## ibmcloud sl order category-list
{: #sl_order_category_list}

List the categories of a package:

```bash
ibmcloud sl order category-list [OPTIONS] PACKAGE_KEYNAME
```
{: codeblock}

### Command options

--required<
:   List only the required categories for the package.

### Examples

This command lists the categories of Bare Metal servers.

```bash
ibmcloud sl order category-list BARE_METAL_SERVER
```
{: codeblock}



## ibmcloud sl order item-list
{: #sl_order_item_list}

List package items that are used for ordering:

```bash
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

### Command options

--keyword
:   A word (or string) that is used to filter item names.

--category
:   Category code that is used to filter items.

### Examples

This command lists all items in the VSI package.

```bash
ibmcloud sl order item-list CLOUD_SERVER
```
{: codeblock}


## ibmcloud sl order package-list
{: #sl_order_package_list}

List packages that can be ordered with the placeOrder API:

```bash
ibmcloud sl order package-list [OPTIONS]
```

### Command options

--keyword
:   A word (or string) that is used to filter package names.

--package-type
:   The keyname for the type of package. For example, BARE_METAL_CPU.

### Examples

This command list out all packages for ordering.

```bash
ibmcloud sl order package-list
```
{: codeblock}


## ibmcloud sl order package-locations
{: #sl_order_package_locations}

List datacenters a package can be ordered in:

```bash
ibmcloud sl order package-locations PACKAGE_KEYNAME
```
{: codeblock}

## ibmcloud sl order place
{: #sl_order_place}

Place or verify an order:
```bash
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```
{: codeblock}


### Command options

--preset
:   The order preset (if required by the package).<

--verify
:   Flag denoting whether to verify the order, or not place it.

--quantity
:   The quantity of the item being ordered. This value defaults to 1.

--billing<
:   Billing rate [hourly|monthly], [default: hourly].

--complex-type
:   The complex type of the order. The type begins with `SoftLayer_Container_Product_Order_`.


--extras
:   JSON string that denotes extra data needs to be sent with the order.

-f, --force
:   Force operation without confirmation.

### Examples

This command orders an hourly VSI with 4 CPU, 16 GB RAM, 100 GB SAN disk, Ubuntu 16.04, and 1 Gbps public & private uplink in datacenter `dal13`.

```bash
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
{: codeblock}

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Place a quote:
```bash
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

### Command options


--preset
:   The order preset (if required by the package).

--name
:   A custom name to be assigned to the quote (optional).

--send-email
:   The quote will be sent to the associated email address.

--complex-type
:   The complex type of the order. The type begins with `SoftLayer_Container_Product_Order_`.

--extras
:   JSON string that denotes extra data needs to be sent with the order.


### Examples**

This command places a quote for a VSI with 4 CPU, 16 GB RAM, 100 GB SAN disk, Ubuntu 16.04, and 1 Gbps public & private uplink in datacenter `dal13`.

```bash
ibmcloud sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
{: codeblock}

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

List package presets:
```bash
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

### Command options

--keyword
:   A word (or string) used to filter presets.


### Examples

This command lists the presets for Bare Metal servers.

```bash
ibmcloud sl order preset-list BARE_METAL_SERVER
```
{: codeblock}
