---

copyright:

  years: 2018


lastupdated: "2018-11-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestion des devis et des commandes de l'infrastructure classique

<table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
 <caption>Tableau 1. Commandes de l'infrastructure classique</caption>
 <thead>
 <th colspan="6">Commandes de l'infrastructure classique</th>
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

Répertorier les catégories d'un package
```
ibmcloud sl order package-locations [OPTIONS] PACKAGE_KEYNAME
```

<strong>Options de commande</strong> :
<dl>
<dt>--required</dt>
<dd>Répertorier uniquement les catégories requises pour le package</dd>
</dl>

**Exemples** :
```
ibmcloud sl order package-locations BARE_METAL_SERVER
```
Cette commande répertorie les catégories de serveurs bare metal.

## ibmcloud sl order item-list
{: #sl_order_item_list}

Répertorier les éléments de package utilisés pour la commande
```
ibmcloud sl order item-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Options de commande</strong> :
<dl>
<dt>--keyword</dt>
<dd>Mot (ou chaîne) à utiliser pour filtrer les noms d'élément</dd>
<dt>--category</dt>
<dd>Code de catégorie à l'aide duquel filtrer les éléments</dd>
</dl>

**Exemples** :
```
ibmcloud sl order item-list CLOUD_SERVER
```
Cette commande répertorie tous les éléments inclus dans le package d'instance de serveur virtuel.

## ibmcloud sl order package-locations
{: #sl_order_package_locations}

Répertorier les centres de données dans lesquels un package peut être commandé
```
ibmcloud sl order package-locations PACKAGE_KEYNAME
```

## ibmcloud sl order place
{: #sl_order_place}

Passer ou vérifier une commande
```
ibmcloud sl order place PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--preset</dt>
<dd>Préréglage de la commande (si requis par le package)</dd>
<dt>--verify</dt>
<dd>Indicateur déterminant si la commande doit être uniquement vérifiée, sans la passer</dd>
<dt>--billing</dt>
<dd>Taux de facturation [hourly|monthly], [par défaut : hourly]</dd>
<dt>--complex-type</dt>
<dd>Type complexe de la commande. Commence généralement par 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Chaîne JSON indiquant que des données supplémentaires doivent être envoyées avec la commande</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans confirmation</dd>
</dl>

**Exemples** :
```
ibmcloud sl order place CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --billing hourly --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest
```
Cette commande permet de commander une instance de serveur virtuel horaire avec 4 UC, 16 Go de mémoire RAM, un disque SAN de 100 Go, Ubuntu 16.04 et une liaison montante publique et privée de 1 Gbit/s sur dal13

## ibmcloud sl order place-quote
{: #sl_order_place_quote}

Faire un devis
```
ibmcloud sl order place-quote PACKAGE_KEYNAME LOCATION ORDER_ITEM1,ORDER_ITEM2,ORDER_ITEM3,ORDER_ITEM4... [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--preset</dt>
<dd>Préréglage de la commande (si requis par le package)</dd>
<dt>--verify</dt>
<dd>Indicateur déterminant si la commande doit être uniquement vérifiée, sans la passer</dd>
<dt>--billing</dt>
<dd>Taux de facturation [hourly|monthly], [par défaut : hourly]</dd>
<dt>--complex-type</dt>
<dd>Type complexe de la commande. Commence généralement par 'SoftLayer_Container_Product_Order_'</dd>
<dt>--extras</dt>
<dd>Chaîne JSON indiquant que des données supplémentaires doivent être envoyées avec la commande</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans confirmation</dd>
</dl>

**Exemples** :
```
sl order place-quote CLOUD_SERVER DALLAS13 GUEST_CORES_4,RAM_16_GB,REBOOT_REMOTE_CONSOLE,1_GBPS_PUBLIC_PRIVATE_NETWORK_UPLINKS,BANDWIDTH_0_GB_2,1_IP_ADDRESS,GUEST_DISK_100_GB_SAN,OS_UBUNTU_16_04_LTS_XENIAL_XERUS_MINIMAL_64_BIT_FOR_VSI,MONITORING_HOST_PING,NOTIFICATION_EMAIL_AND_TICKET,AUTOMATED_NOTIFICATION,UNLIMITED_SSL_VPN_USERS_1_PPTP_VPN_USER_PER_ACCOUNT,NESSUS_VULNERABILITY_ASSESSMENT_REPORTING --extras '{"virtualGuests": [{"hostname": "test", "domain": "softlayer.com"}]}' --complex-type SoftLayer_Container_Product_Order_Virtual_Guest --name "foobar" --send-email
```
Cette commande permet de réaliser un devis pour une instance de serveur virtuel horaire avec 4 UC, 16 Go de mémoire RAM, un disque SAN de 100 Go, Ubuntu 16.04 et une liaison montante publique et privée de 1 Gbit/s sur dal13

## ibmcloud sl order preset-list
{: #sl_order_preset_list}

Répertorier les préréglages de package
```
ibmcloud sl order preset-list [OPTIONS] PACKAGE_KEYNAME
```

<strong>Options de commande</strong> :
<dl>
<dt>--keyword</dt>
<dd>Mot (ou chaîne) à utiliser pour filtrer les noms d'élément</dd>
</dl>

**Exemples** :
```
ibmcloud sl order preset-list BARE_METAL_SERVER
```
Cette commande répertorie les préréglages pour les serveurs bare metal
