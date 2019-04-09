---

copyright:

  years: 2015, 2017

lastupdated: "2017-01-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}


# Plug-in d'interface de ligne de commande VPN pour l'interface de ligne de commande cf
{: #vpn_cli_for_cf}


Vous pouvez utiliser l'interface de ligne de commande pour configurer et gérer votre service {{site.data.keyword.vpn_full}}. Le plug-in d'interface de ligne de commande {{site.data.keyword.vpn_short}} est disponible en deux versions, l'une est destinée à être utilisée avec le plug-in d'interface de ligne de commande Cloud Foundry et l'autre avec le plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix}}. Les deux versions du plug-in fournissent la même fonctionnalité.
{:shortdesc}

Le plug-in {{site.data.keyword.vpn_short}} est disponible pour les systèmes d'exploitation Windows, MAC et Linux. Assurez-vous d'utiliser celui qui vous correspond.

Les instructions qui suivent s'appliquent au plug-in d'interface de ligne de commande Cloud Foundry (cf). Pour utiliser le plug-in avec le plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, voir [Plug-in {{site.data.keyword.vpn_short}} pour l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} ![Icône de lien externe](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/plugins/bx_vpn/index.html){: new_window}.

## Installation du plug-in d'interface de ligne de commande cf
Avant de commencer, installez l'interface de ligne de commande cf. Voir [Plug-in de l'interface de ligne de commande Cloud Foundry ![Icône de lien externe](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window} pour plus de détails.

## Installation du plug-in d'interface de ligne de commande VPN
**Remarque :** si une version précédente du plug-in d'interface de ligne de commande {{site.data.keyword.vpn_short}} est installée, vous devez la désinstaller. Utilisez la commande suivante :

```
cf uninstall-plugin vpn
```

### Installation locale

1. Téléchargez le plug-in {{site.data.keyword.vpn_short}} pour votre plateforme depuis le [ référentiel de plug-in de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} ![Icône de lien externe](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/repository.html#cf-plugins){: new_window}.
2. Installez le plug-in {{site.data.keyword.vpn_short}} à l'aide de la commande suivante :
**Remarque :** placez-vous sur l'emplacement du plug-in {{site.data.keyword.vpn_short}} ou spécifiez le chemin d'accès à l'emplacement du plug-in.

	- Pour le système d'exploitation MS Windows :

	```
	cf install-plugin vpn_windows64.exe
	```

	- Pour le système d'exploitation MAC OS :

	```
	cf install-plugin vpn_mac_os_amd64
	```

	- Pour le système d'exploitation Linux :

	```
	cf install-plugin vpn_linuxamd64
	```


### Installation depuis le référentiel {{site.data.keyword.Bluemix_notm}}

1. Ajoutez le référentiel {{site.data.keyword.Bluemix_notm}} aux référentiels de l'interface de ligne de commande Cloud Foundry. Exécutez la commandes suivante :

	```
	cf add-plugin-repo bluemix http://plugins.ng.bluemix.net
	```
2. Exécutez la commande suivante :

	```
	cf install-plugin vpn -r bluemix
	```
##Liste des commandes de service VPN

### cf vpn-create connection

Crée une connexion de réseau privé virtuel.

```
cf vpn-create connection <connection name> -g <gateway name> -k <preshared key> -subnets ["<subnet/mask>"] -cip <customer gateway IP address> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```
#### Paramètres
{: #p1}

**connection name :** nom de la connexion.

**gateway name :** nom de la passerelle.

**-k :** clé pré-partagée.

**subnet/mask :** adresse de sous-réseau distant au format CIDR.

**customer gateway IP address :** adresse IP de noeud final distant du tunnel VPN.

##### Paramètres facultatifs :
{: #op1}

**-d :** description des paramètres spécifiés.

**-peer_id :** ID de l'homologue distant. Autre noeud final du tunnel VPN.

**-admin_state :** statut de la connexion VPN. Valeurs : UP ou DOWN.

**-dpd-action :** action à effectuer lorsque l'homologue est identifié comme non opérationnel. Valeurs : hold ; clear ; disabled ; restart ; restart-by-peer. Valeur par défaut : hold

**-gateway_ip :** adresse IP du noeud final du tunnel VPN local.

**-i :** état de l'initiateur. Valeur par défaut : bi-directional.

**-dpd-timeout :** valeur de délai d'attente (en secondes) au bout duquel la session est terminée.  Plage : 6 à 86400 secondes. Valeur par défaut : 120 secondes. La valeur du délai d'attente de l'intervalle de signal de présence doit être supérieure à la valeur de l'intervalle de signal de présence.

**-dpd-interval :** intervalle de signal de présence, en secondes. Envoyez des messages d'état actif à la fréquence
configurée afin de vérifier l'état opérationnel de l'homologue. Plage : 5 à 86399 secondes. Valeur par défaut : 15 secondes

**-ike :** nom de la règle IKE.

**-ipsec :** nom de la règle IPsec.


### cf vpn-create ike

Crée une règle IKE (Internet Key Exchange).

```
cf vpn-create ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Paramètres
{: #p2}

**policy name :** nom de la règle IKE.

**gateway name :** nom de la passerelle.

##### Paramètres facultatifs :
{: #op2}

**-d :** description des paramètres spécifiés.

**-pfs :** identificateur de groupe Diffie-Hellman (DH). Valeurs : Group2 ; Group5 ; Group14. Valeur par défaut : Group2

**-e :** algorithme de chiffrement. Valeurs : aes-128 ; aes-192 ; aes-256 ; 3des. Valeur par défaut : aes-128

**-lv :** valeur de durée de vie de l'association de sécurité IKE. Plage : 60 à 86400 secondes. Valeur par défaut : 86400 secondes

**-auth :** algorithme d'autorisation. Valeurs : sha1 ou sha256


### cf vpn-create ipsec

Crée une règle IPsec.

```
cf vpn-create ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Paramètres
{: #p3}

**policy name :** nom de la règle IPsec.

**gateway name :** nom de la passerelle.

##### Paramètres facultatifs :
{: #op3}

**-d :** description des paramètres spécifiés.

**-pfs :** identificateur de groupe Diffie-Hellman (DH). Valeurs : Group2 ; Group5 ; Group14. Valeur par défaut : Group2

**-e :** algorithme de chiffrement. Valeurs : aes-128 ; aes-192 ; aes-256 ; 3des. Valeur par défaut : aes-128

**-lv:** valeur de durée de vie de l'association de sécurité. Plage : 60 à 86400 secondes. Valeur par défaut : 3600 secondes

**-auth :** algorithme d'autorisation. Valeurs : sha1 ou sha256

### cf vpn-create gateway

Crée une passerelle de réseau privé virtuel.

```
cf vpn-create gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### Paramètres
{: #p4}

**gateway name :** nom de la passerelle.

**-t :** conteneurs pour lesquels vous souhaitez activer le service. Valeurs : allSingleContainers ; allContainerGroups ; allContainers. Valeur par défaut : aucune
valeur par défaut. Vous devez spécifier un type.

#####Paramètres facultatifs :
{: #op4}

**-gateway_ip :** adresse IP de la passerelle.

**-subnets :** adresse de sous-réseau au format CIDR.

### cf vpn-show gateways

Affiche des informations sur les passerelles en cours.

```
cf vpn-show gateways
```
### cf vpn-show ikes

Affiche des informations sur les connexions IKE (Internet Key Exchange) en cours.

```
cf vpn-show ikes
```
### cf vpn-show ipsecs

Affiche des informations sur les connexions IPsec en cours.

```
cf vpn-show ipsecs
```
### cf vpn-show connections

Affiche des informations sur toutes les connexions en cours.

```
cf vpn-show connections
```
### cf vpn-show ike

Affiche des informations sur une connexion IKE (Internet Key Exchange).

```
cf vpn-show ike <policy name>
```
### cf vpn-show ipsec

Affiche des informations sur une connexion IPsec.

```
cf vpn-show ipsec <policy name>
```
### cf vpn-show gateway

Affiche les informations de connexion d'une passerelle.

```
cf vpn-show gateway <gateway name>
```
### cf vpn-show connection

Affiche toutes les informations sur une connexion particulière.

```
cf vpn-show connection <connection name>
```
### cf vpn-delete

Supprime une connexion, une règle ou une passerelle existante.

```
cf vpn-delete ike <policy name>
```

```
cf vpn-delete ipsec <policy name>
```

```
cf vpn-delete connection <connection name>
```

```
cf vpn-delete gateway <gateway name>
```


### cf vpn-update connection

Met à jour une connexion de réseau privé virtuel existante.

```
cf vpn-update connection <connection name> -g <gateway name> -cip <customer gateway IP address> -subnets ["<subnet/mask>"] -k <preshared key> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```
#### Paramètres
{: #p5}

**connection name :** nom de la connexion.


##### Paramètres facultatifs :
{: #op5}

**gateway name :** nom de la passerelle.

**customer gateway IP address :** adresse IP de noeud final distant du tunnel VPN.

**subnet/mask :** adresse de sous-réseau au format CIDR.

**-k :** clé pré-partagée.

**-d :** description des paramètres spécifiés.

**-peer_id :** ID de l'homologue distant. Autre noeud final du tunnel VPN.

**-admin_state :** statut de la connexion VPN. Valeurs : UP ou DOWN.

**-dpd-action :** action à effectuer lorsque l'homologue est identifié comme non opérationnel. Valeurs : hold ; clear ; disabled ; restart ; restart-by-peer. Valeur par défaut : hold

**-gateway_ip :** adresse IP du noeud final du tunnel VPN local.

**-i :** état de l'initiateur. Valeur par défaut : bi-directional.

**-dpd-timeout :** valeur de délai d'attente (en secondes) au bout duquel la session est terminée. Plage : 6 à 86400 secondes. Valeur par défaut : 120
secondes

**-dpd-interval :** intervalle de signal de présence, en secondes. Envoyez des messages d'état actif à la fréquence
configurée afin de vérifier l'état opérationnel de l'homologue. Plage : 5 à 86399 secondes. Valeur par défaut : 15 secondes

**-ike :** nom de la règle IKE.

**-ipsec :** nom de la règle IPsec.


### cf vpn-update ike

Met à jour une règle IKE (Internet Key Exchange).

```
cf vpn-update ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Paramètres
{: #p6}

**policy name :** nom de la règle IKE.

##### Paramètres facultatifs :
{: #op6}

**gateway name :** nom de la passerelle.

**-d :** description des paramètres spécifiés.

**-pfs :** identificateur de groupe Diffie-Hellman (DH). Valeurs : Group2 ; Group5 ; Group14. Valeur par défaut : Group2

**-e :** algorithme de chiffrement. Valeurs : aes-128 ; aes-192 ; aes-256 ; 3des. Valeur par défaut : aes-128

**-lv :** valeur de durée de vie de l'association de sécurité IKE. Plage : 60 à 86400 secondes. Valeur par défaut : 86400 secondes

**-auth :** algorithme d'autorisation. Valeurs : sha1 ou sha256


### cf vpn-update ipsec

Met à jour une règle IPsec;

```
cf vpn-update ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Paramètres
{: #p7}

**policy name :** nom de la règle IPsec.


##### Paramètres facultatifs :
{: #op7}

**gateway name :** nom de la passerelle.

**-d :** description des paramètres spécifiés.

**-pfs :** identificateur de groupe Diffie-Hellman (DH). Valeurs : Group2 ; Group5 ; Group14. Valeur par défaut : Group2

**-e :** algorithme de chiffrement. Valeurs : aes-128 ; aes-192 ; aes-256 ; 3des. Valeur par défaut : aes-128

**-lv:** valeur de durée de vie de l'association de sécurité. Plage : 60 à 86400 secondes. Valeur par défaut : 3600 secondes

**-auth :** algorithme d'autorisation. Valeurs : sha1 ou sha256

### cf vpn-update gateway

Met à jour une passerelle de réseau privé virtuel existante.

```
cf vpn-update gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### Paramètres
{: #p8}

**gateway name :** nom de la passerelle.

#####Paramètres facultatifs :
{: #op8}

**-t :** conteneurs pour lesquels vous souhaitez activer le service. Valeurs : allSingleContainers ; allContainerGroups ; allContainers. Valeur par défaut : aucune
valeur par défaut. Vous devez spécifier un type.

**-gateway_ip :** adresse IP de la passerelle.

**-subnets :** adresse de sous-réseau au format CIDR.

# rellinks
## general
{: #general}
* [Service IBM VPN](/docs/services/vpn/index.html)
* [Interface de ligne de commande Cloud Foundry ![Icône de lien externe](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}
