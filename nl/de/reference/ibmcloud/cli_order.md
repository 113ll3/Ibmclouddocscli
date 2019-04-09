---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, orders, quotes, ibmcloud sl order, item-list, package-locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Bestellungen und Angebote verwalten - klassische Infrastruktur
{: #sl-manage-classic-orders}

Verwenden Sie die folgenden Befehle, um Bestellungen und Angebote in Ihrer klassischen Infrastruktur zu verwalten.

## ibmcloud sl order package-locations
{: #sl_order_category_list}

Kategorien eines Pakets auflisten
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--required</dt>
<dd>Nur die erforderlichen Kategorien für das Paket auflisten</dd>
</dl>

**Beispiele**:
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
Dieser Befehl listet die Kategorien der Bare-Metal-Server auf.

## ibmcloud sl order item-list
{: #sl_order_item_list}

Für die Bestellung verwendete Paketartikel auflisten
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--keyword</dt>
<dd>Wort (oder Zeichenfolge) zum Filtern von Artikelnamen</dd>
<dt>--category</dt>
<dd>Kategoriecode für das Filtern von Artikeln</dd>
</dl>

**Beispiele**:
```
ibmcloud sl order item-list CLOUD_SERVER
```
Mit diesem Befehl werden alle Artikel im VSI-Paket aufgelistet.

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

Rechenzentren auflisten, in denen ein Paket bestellt werden kann
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

Bestellung aufgeben oder überprüfen
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--preset</dt>
<dd>Voreinstellung der Bestellung (falls für das Paket erforderlich)</dd>
<dt>--verify</dt>
<dd>Flag zur Angabe, ob die Bestellung nur überprüft werden soll, ohne sie zu senden.</dd>
<dt>--billing</dt>
<dd>Abrechnungssatz [stündlich|monatlich], [Standardeinstellung: stündlich]</dd>
<dt>--complex-type</dt>
<dd>Der komplexe Typ der Bestellung. Dieser beginnt normalerweise mit 'SoftLayer_Container_Product_Order_'.</dd>
<dt>--extras</dt>
<dd>JSON-Zeichenfolge zur Angabe zusätzlicher Daten, die mit der Bestellung gesendet werden sollen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen</dd>
</dl>

**Beispiele**:
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
Mit diesem Befehl wird eine VSI auf Stundenbasis mit 4 CPUs, 16 GB RAM, SAN-Platte mit 100 GB, Ubuntu 16.04 und 1 Gbps öffentlicher & privater Uplink in dal13 bestellt.

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Angebot senden
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--preset</dt>
<dd>Voreinstellung der Bestellung (falls für das Paket erforderlich)</dd>
<dt>--verify</dt>
<dd>Flag zur Angabe, ob die Bestellung nur überprüft werden soll, ohne sie zu senden.</dd>
<dt>--billing</dt>
<dd>Abrechnungssatz [stündlich|monatlich], [Standardeinstellung: stündlich]</dd>
<dt>--complex-type</dt>
<dd>Der komplexe Typ der Bestellung. Dieser beginnt normalerweise mit 'SoftLayer_Container_Product_Order_'.</dd>
<dt>--extras</dt>
<dd>JSON-Zeichenfolge zur Angabe zusätzlicher Daten, die mit der Bestellung gesendet werden sollen.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen</dd>
</dl>

**Beispiele**:
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
Mit diesem Beispiel wird ein Angebot für eine VSI mit 4 CPUs, 16 GB RAM, SAN-Platte mi 100, Ubuntu 16.04 und 1 Gbps öffentlicher & privater Uplink in dal13 abgegeben.

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

Paketvoreinstellungen auflisten
```
ibmcloud sl order preset-list [OPTIONEN] PACKAGE_KEYNAME
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--keyword</dt>
<dd>Wort (oder Zeichenfolge) zum Filtern von Artikelnamen</dd>
</dl>

**Beispiele**:
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
Dieser Befehl listet die Voreinstellungen für Bare-Metal-Server auf.
