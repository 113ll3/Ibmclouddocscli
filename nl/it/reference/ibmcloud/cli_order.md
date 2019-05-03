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

# Gestione degli ordini e dei preventivi dell'infrastruttura classica
{: #sl-manage-classic-orders}

Utilizza i seguenti comandi per gestire gli ordini e i preventivi nella tua infrastruttura classica.

## ibmcloud sl order package-locations
{: #sl_order_category_list}

Elenca le categorie di un pacchetto
```
ibmcloud sl order package-locations [OPZIONI] NOMECHIAVE_PACCHETTO
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--required</dt>
<dd>Elenca solo le categorie obbligatorie per il pacchetto</dd>
</dl>

**Esempi**:
```
ibmcloud sl order package-locations SERVER_BARE_METAL
```
Questo comando elenca le categorie dei server Bare Metal.

## ibmcloud sl order item-list
{: #sl_order_item_list}

Elenca gli elementi del pacchetto utilizzati per l'ordinamento
```
ibmcloud sl order item-list [OPZIONI] NOMECHIAVE_PACCHETTO
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--keyword</dt>
<dd>Una parola (o una stringa) utilizzata per filtrare i nomi degli elementi</dd>
<dt>--category</dt>
<dd>Codice della categoria con cui filtrare gli elementi</dd>
</dl>

**Esempi**:
```
ibmcloud sl order item-list SERVER_CLOUD
```
Questo comando elenca tutti gli elementi del pacchetto VSI.

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

Elenca i data center in cui può essere ordinato un pacchetto
```
ibmcloud sl order package-locations NOMECHIAVE_PACCHETTO
```

## ibmcloud sl order place
{: #sl_order_place}

Inserisce o verifica un ordine
```
ibmcloud sl order place NOMECHIAVE_PACCHETTO UBICAZIONE ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--preset</dt>
<dd>L'ordine preimpostato (se richiesto dal pacchetto)</dd>
<dt>--verify</dt>
<dd>Indicatore che denota solo se verificare o meno l'ordine, non lo inserisce</dd>
<dt>--billing</dt>
<dd>Frequenza di fatturazione [hourly|monthly], [default: hourly]</dd>
<dt>--complex-type</dt>
<dd>Il tipo complesso dell'ordine. Normalmente inizia con 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Stringa JSON che denota gli ulteriori dati che devono essere inviati con l'ordine</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma</dd>
</dl>

**Esempi**:
```
ibmcloud sl order place SERVER_CLOUD DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
Questo comando ordina una VSI oraria con 4 CPU, 16 GB RAM, disco SAN da 100 GB, Ubuntu 16.04 e un uplink privato e pubblico da 1 Gbps in dal13

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Inserisce una quota
```
ibmcloud sl order place-quote NOMECHIAVE_PACCHETTO UBICAZIONE ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--preset</dt>
<dd>L'ordine preimpostato (se richiesto dal pacchetto)</dd>
<dt>--verify</dt>
<dd>Indicatore che denota solo se verificare o meno l'ordine, non lo inserisce</dd>
<dt>--billing</dt>
<dd>Frequenza di fatturazione [hourly|monthly], [default: hourly]</dd>
<dt>--complex-type</dt>
<dd>Il tipo complesso dell'ordine. Normalmente inizia con 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Stringa JSON che denota gli ulteriori dati che devono essere inviati con l'ordine</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma</dd>
</dl>

**Esempi**:
```
sl order place-quote SERVER_CLOUD DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
Questo comando inserisce la quota di una VSI oraria con 4 CPU, 16 GB RAM, disco SAN da 100 GB, Ubuntu 16.04 e un uplink privato e pubblico da 1 Gbps in dal13

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

Elenca i pacchetti preimpostati
```
ibmcloud sl order preset-list [OPZIONI] NOMECHIAVE_PACCHETTO
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--keyword</dt>
<dd>Una parola (o una stringa) utilizzata per filtrare i nomi degli elementi</dd>
</dl>

**Esempi**:
```
ibmcloud sl order preset-list SERVER_BARE_METAL
```
Questo comando elenca le preimpostazioni dei server Bare Metal
