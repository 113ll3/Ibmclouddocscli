---



copyright:

  years: 2015，2018

lastupdated: "2018-05-23"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Plug-in VPN pour l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}

*Version :* 1.4.0

Vous pouvez utiliser l'interface de ligne de commande pour configurer et gérer votre service {{site.data.keyword.vpn_full}}. Le plug-in VPN d'interface de ligne de commande est disponible dans deux versions, l'une est destinée à être utilisée avec le plug-in d'interface de ligne de commande Cloud Foundry et l'autre avec le plug-in d'interface de ligne de commande {{site.data.keyword.Bluemix}}. Les deux versions du plug-in fournissent la même fonctionnalité.
{:shortdesc}

Le plug-in VPN est disponible pour les systèmes d'exploitation Windows, MAC et Linux. Assurez-vous d'utiliser celui qui vous correspond.

Les instructions qui suivent s'appliquent au plug-in CLI {{site.data.keyword.Bluemix_notm}}. Pour utiliser le plug-in avec le plug-in d'interface de ligne de commande Cloud Foundry (cf), voir [Plug-in d'interface de ligne de commande VPN pour l'interface de ligne de commande cf](../vpn/index.html).


Vous trouverez ci-après la liste de toutes les commandes qui sont prises en charge par le plug-in VPN pour l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}, ainsi que leurs noms, leurs options, leur syntaxe, leurs prérequis, leurs descriptions et des exemples. Pour savoir comment installer le plug-in VPN, voir [Etendez votre interface de ligne de commande Bluemix](../../index.html#cli_bluemix_ext).

**Remarque :** la zone *Prérequis* répertorie les actions qui sont requises avant l'utilisation de la commande. Il
peut s'agir d'une ou de plusieurs des actions suivantes :
<dl>
<dt>**Noeud final**</dt>
<dd>Un noeud final d'API doit être défini via `ibmcloud api` avant l'utilisation de la commande.</dd>
<dt>**Connexion**</dt>
<dd>Vous devez vous connecter avec la commande `ibmcloud login` avant d'utiliser cette commande.
</dd>
<dt>**Cible**</dt>
<dd>La commande `ibmcloud target` doit être utilisée pour configurer une organisation et un espace avant d'appeler cette commande.</dd>
</dl>


## ibmcloud vpn connection-create
Crée une connexion de réseau privé virtuel.

```
ibmcloud vpn connection-create CONNECTION_NAME -g GATEWAY_NAME -k PRESHARED_KEY -subnets "SUBNET/MASK" -cip CUSTOMER_GATEWAY_IP_ADDRESS [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state ADMIN_STATE] [-dpd-action ACTION] [-gateway_ip IP_ADDRESS] [-i INITIATOR_STATE] [-dpd-timeout VALUE] [-dpd-interval VALUE] [-ike NAME] [-ipsec NAME]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*CONNECTION_NAME* (requis) : nom de la connexion.

-g *GATEWAY_NAME* (requis) : nom de la passerelle.

-k *PRESHARED_KEY* (requis) : clé pré-partagée.

-subnets "*SUBNET*/*MASK*" (requis) : adresse de sous-réseau distant au format CIDR. 

-cip *CUSTOMER_GATEWAY_IP_ADDRESS* requis) : adresse IP de noeud final distant du tunnel VPN. 

-d *DESCRIPTION* (facultatif) : description des paramètres spécifiés.

-peer_id *PEER_ID* (facultatif) : ID de l'homologue distant. Autre noeud final du tunnel VPN.

-admin_state *ADMIN_STATE* (facultatif) : statut de la connexion de réseau privé virtuel. Les valeurs admises sont `UP`
et `DOWN`.

-dpd-action *ACTION*  (facultatif) :  action à effectuer lorsque l'homologue est identifié comme non opérationnel. Les valeurs admises sont
`hold`, `clear`, `disabled`, `restart` et `restart-by-peer`. La
valeur par défaut est `hold`.

-gateway_ip *IP_ADDRESS* (facultatif) : adresse IP du noeud final de tunnel VPN local.

-i *INITIATOR_STATE* (facultatif) : état de l'initiateur. La valeur par défaut est `bi-directional`.

-dpd-timeout *VALUE* (facultatif) : valeur de délai en secondes au bout duquel la session est terminée. Plage : 6 à 86400 secondes. La
valeur par défaut est `120` secondes.

-dpd-interval *VALUE* (facultatif) : intervalle de signal de présence en secondes. Envoyez des messages d'état actif à la fréquence
configurée afin de vérifier l'état opérationnel de l'homologue. Plage : 5 à 86399 secondes. La valeur par défaut est `15` secondes.

-ike *NAME* (facultatif) : nom de la règle IKE (Internet Key Exchange).

-ipsec *NAME* (facultatif) : nom de la règle IPSec (Internet Protocol Security).

**Exemples** :

Créez une connexion de réseau privé virtuel dont le nom est `ma_connexion` :
```
ibmcloud vpn connection-create my_connection -g my_gateway -k 123456 -subnets "192.168.10.0/24" -cip 162.135.1.1
```


## ibmcloud vpn ike-create
Crée une règle IKE (Internet Key Exchange).

```
ibmcloud vpn ike-create POLICY_NAME -g GATEWAY_NAME [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IKE (Internet Key Exchange).

-g *GATEWAY_NAME* (requis) : nom de la passerelle.

-d *DESCRIPTION* (facultatif) : description des paramètres spécifiés.

-pfs *GROUP* (facultatif) : identificateur de groupe Diffie-Hellman (DH). Les valeurs admises sont `Group2`,
`Group5` et `Group14`. La valeur par défaut est `Group2`.

-e *ENCRYPTION_ALGORITHM* (facultatif) : algorithme de chiffrement. Les valeurs admises sont `aes-128`,
`aes-192`, `aes-256` et `3des`. La valeur par défaut est `aes-128`.

-lv *LIFETIME_VALUE* (facultatif) : valeur de durée de vie de l'association de sécurité IKE (Internet Key Exchange). Plage : 60 à 86400 secondes. La valeur par défaut est `86400` secondes.

**Exemples** :

Créez une règle IKE (Internet Key Exchange) dont le nom est `mon_ike` :
```
ibmcloud vpn ike-create my_ike -g my_gateway
```


## ibmcloud vpn ipsec-create
Crée une règle IPSec (Internet Protocol Security).

```
ibmcloud vpn ipsec-create POLICY_NAME -g GATEWAY_NAME [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IPSec (Internet Protocol Security).

-g *GATEWAY_NAME* (requis) : nom de la passerelle.

-d *DESCRIPTION* (facultatif) : description des paramètres spécifiés.

-pfs *GROUP* (facultatif) : identificateur de groupe Diffie-Hellman (DH). Les valeurs admises sont `Group2`,
`Group5` et `Group14`. La valeur par défaut est `Group2`.

-e *ENCRYPTION_ALGORITHM* (facultatif) : algorithme de chiffrement. Les valeurs admises sont `aes-128`,
`aes-192`, `aes-256` et `3des`. La valeur par défaut est `aes-128`.

-lv *LIFETIME_VALUE* (facultatif) : valeur de durée de vie de l'association de sécurité. Plage : 60 à 86400 secondes. La valeur par
défaut est `3600` secondes.

**Exemples** :

Créez une règle IPSec (Internet Protocol Security) dont le nom est `ma_règle` :
```
ibmcloud vpn ipsec-create my_policy -g my_gateway
```


## ibmcloud vpn gateway-create
Crée une passerelle de réseau privé virtuel.

```
ibmcloud vpn gateway-create GATEWAY_NAME -t TYPE [-gateway_ip IP_ADDRESS] [-subnets SUBNET_ADDRESS]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*GATEWAY_NAME* (requis) : nom de la passerelle.

-t *TYPE* (requis) : conteneurs pour lesquels activer le service. Les valeurs admises sont `allSingleContainers`,
`allContainerGroups` et `allContainers`. Aucune valeur par défaut ; vous devez spécifier un type.

-gateway_ip *IP_ADDRESS* (facultatif) : adresse IP de la passerelle.

-subnets *SUBNET_ADDRESS* (facultatif) : adresse de sous-réseau au format CIDR.

**Exemples** :

Créez une passerelle dont le nom est `ma_passerelle` et le type `allContainerGroups` :
```
ibmcloud vpn gateway-create my_gateway -t allContainerGroups
```


## ibmcloud vpn connections
Affiche des informations sur toutes les connexions en cours.

```
ibmcloud vpn connections
```

**Prérequis** : Noeud final, Connexion, Cible


## ibmcloud vpn ikes
Affiche des informations sur les connexions IKE (Internet Key Exchange) en cours.

```
ibmcloud vpn ikes
```

**Prérequis** : Noeud final, Connexion, Cible


## ibmcloud vpn ipsecs
Affiche des informations sur les connexions IPSec (Internet Protocol Security) en cours.

```
ibmcloud vpn ipsecs
```

**Prérequis** : Noeud final, Connexion, Cible


## ibmcloud vpn gateways
Affiche des informations sur les passerelles en cours.

```
ibmcloud vpn gateways
```

**Prérequis** : Noeud final, Connexion, Cible


## ibmcloud vpn connection
Affiche toutes les informations sur une connexion particulière.

```
ibmcloud vpn connection CONNECTION_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*CONNECTION_NAME* (requis) : nom de la connexion à afficher.


## ibmcloud vpn ike
Affiche des informations sur une connexion IKE (Internet Key Exchange).

```
ibmcloud vpn ike POLICY_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IKE (Internet Key Exchange) à afficher.


## ibmcloud vpn ipsec
Affiche des informations sur une connexion IPSec (Internet Protocol Security).

```
ibmcloud vpn ipsec POLICY_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IPSec (Internet Protocol Security) à afficher.


## ibmcloud vpn gateway
Affiche les informations de connexion d'une passerelle.

```
ibmcloud vpn gateway GATEWAY_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*GATEWAY_NAME* (requis) : nom de la passerelle à afficher.


## ibmcloud vpn connection-delete
Supprime une connexion existante.

```
ibmcloud vpn connection-delete CONNECTION_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*CONNECTION_NAME* (requis) : nom de la connexion à supprimer.


## ibmcloud vpn ike-delete
Supprime une règle IKE (Internet Key Exchange) existante.

```
ibmcloud vpn ike-delete POLICY_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IKE (Internet Key Exchange) à supprimer.


## ibmcloud vpn ipsec-delete
Supprime une règle IPSec (Internet Protocol Security) existante.

```
ibmcloud vpn ipsec-delete POLICY_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IPSec (Internet Protocol Security) à supprimer.


## ibmcloud vpn gateway-delete
Supprime une passerelle existante.

```
ibmcloud vpn gateway-delete GATEWAY_NAME
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*GATEWAY_NAME* (requis) : nom de la passerelle à supprimer.


## ibmcloud vpn connection-update
Met à jour une connexion de réseau privé virtuel existante.

```
ibmcloud vpn connection-update CONNECTION_NAME [-g GATEWAY_NAME] [-k PRESHARED_KEY] [-subnets "SUBNET/MASK"] [-cip CUSTOMER_GATEWAY_IP_ADDRESS] [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state ADMIN_STATE] [-dpd-action ACTION] [-gateway_ip IP_ADDRESS] [-i INITIATOR_STATE] [-dpd-timeout VALUE] [-dpd-interval VALUE] [-ike NAME] [-ipsec NAME]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*CONNECTION_NAME* (requis) : nom de la connexion.

-g *GATEWAY_NAME* (facultatif) : nom de la passerelle.

-k *PRESHARED_KEY* (facultatif) : clé pré-partagée.

-subnets "*SUBNET*/*MASQUE*" (facultatif) : adresse de sous-réseau au format CIDR.

-cip *CUSTOMER_GATEWAY_IP_ADDRESS* (facultatif) : adresse IP de noeud final distant du tunnel VPN.

-d *DESCRIPTION* (facultatif) : description des paramètres spécifiés.

-peer_id *PEER_ID* (facultatif) : ID de l'homologue distant. Autre noeud final du tunnel VPN.

-admin_state *ADMIN_STATE* (facultatif) : statut de la connexion de réseau privé virtuel. Les valeurs admises sont `UP`
et `DOWN`.

-dpd-action *ACTION*  (facultatif) :  action à effectuer lorsque l'homologue est identifié comme non opérationnel. Les valeurs admises sont
`hold`, `clear`, `disabled`, `restart` et `restart-by-peer`.

-gateway_ip *IP_ADDRESS* (facultatif) : adresse IP du noeud final de tunnel VPN local.

-i *INITIATOR_STATE* (facultatif) : état de l'initiateur.

-dpd-timeout *VALUE* (facultatif) : valeur de délai en secondes au bout duquel la session est terminée. Plage : 6 à 86400 secondes.

-dpd-interval *VALUE* (facultatif) : intervalle de signal de présence en secondes. Envoyez des messages d'état actif à la fréquence
configurée afin de vérifier l'état opérationnel de l'homologue. Plage : 5 à 86399 secondes.

-ike *NAME* (facultatif) : nom de la règle IKE (Internet Key Exchange).

-ipsec *NAME* (facultatif) : nom de la règle IPSec (Internet Protocol Security).


## ibmcloud vpn ike-update
Met à jour une règle IKE (Internet Key Exchange).

```
ibmcloud vpn ike-update POLICY_NAME [-g GATEWAY_NAME] [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IKE (Internet Key Exchange).

-g *GATEWAY_NAME* (facultatif) : nom de la passerelle.

-d *DESCRIPTION* (facultatif) : description des paramètres spécifiés.

-pfs *GROUP* (facultatif) : identificateur de groupe Diffie-Hellman (DH). Les valeurs admises sont `Group2`,
`Group5` et `Group14`.

-e *ENCRYPTION_ALGORITHM* (facultatif) : algorithme de chiffrement. Les valeurs admises sont `aes-128`,
`aes-192`, `aes-256` et `3des`.

-lv *LIFETIME_VALUE* (facultatif) : valeur de durée de vie de l'association de sécurité IKE (Internet Key Exchange). Plage : 60 à 86400 secondes.


## ibmcloud vpn ipsec-update
Met à jour une règle IPSec (Internet Protocol Security).

```
ibmcloud vpn ipsec-update POLICY_NAME [-g GATEWAY_NAME] [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*POLICY_NAME* (requis) : nom de la règle IPSec (Internet Protocol Security).

-g *GATEWAY_NAME* (facultatif) : nom de la passerelle.

-d *DESCRIPTION* (facultatif) : description des paramètres spécifiés.

-pfs *GROUP* (facultatif) : identificateur de groupe Diffie-Hellman (DH). Les valeurs admises sont `Group2`,
`Group5` et `Group14`.

-e *ENCRYPTION_ALGORITHM* (facultatif) : algorithme de chiffrement. Les valeurs admises sont `aes-128`,
`aes-192`, `aes-256` et `3des`.

-lv *LIFETIME_VALUE* (facultatif) : valeur de durée de vie de l'association de sécurité. Plage : 60 à 86400 secondes.


## ibmcloud vpn gateway-update
Met à jour une passerelle de réseau privé virtuel existante.

```
ibmcloud vpn gateway-update GATEWAY_NAME [-t TYPE] [-gateway_ip IP_ADDRESS] [-subnets SUBNET_ADDRESS]
```

**Prérequis** : Noeud final, Connexion, Cible

**Options de commande** :

*GATEWAY_NAME* (requis) : nom de la passerelle.

-t *TYPE* (facultatif) : conteneurs pour lesquels activer le service. Les valeurs admises sont `allSingleContainers`,
`allContainerGroups` et `allContainers`.

-gateway_ip *IP_ADDRESS* (facultatif) : adresse IP de la passerelle.

-subnets *SUBNET_ADDRESS* (facultatif) : adresse de sous-réseau au format CIDR.
