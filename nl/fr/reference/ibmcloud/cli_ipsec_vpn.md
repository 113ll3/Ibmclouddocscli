---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, datacenter, encryption

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestion des tunnels VPN IPSec
{: #sl-manage-ipsec-vpn-tunnels}

L'accès VPN {{site.data.keyword.cloud}} permet aux utilisateurs de gérer tous les serveurs à distance et en toute sécurité sur le réseau privé {{site.data.keyword.cloud_notm}}. Une connexion VPN de votre site vers le réseau privé permet une gestion externe et la récupération de serveurs via un tunnel VPN chiffré.

Les commandes suivantes permettent de gérer les tunnels VPN IPSec dans le service correspondant de l'infrastructure classique {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Permet d'annuler un contexte de tunnel VPN IPSec.
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--immediate</dt>
<dd>Annuler le contexte IPSec immédiatement sans attendre la date anniversaire de facturation.</dd>
<dt>--reason</dt>
<dd>Motif (facultatif) de l'annulation.</dd>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

Permet de demander la configuration d'un contexte de tunnel.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Permet de répertorier les détails relatifs à un contexte de tunnel VPN IPSec.
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-i, --include</dt>
<dd>Permet d'ajouter des ressources supplémentaires. Les options possibles sont les suivantes : at,is,rs,sr,ss.</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

Permet de répertorier les contextes de tunnel VPN IPSec.
```
ibmcloud sl ipsec list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--order</dt>
<dd>Filtrer par ID de commande utilisé pour acheter le contexte IPSec.</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

Permet de commander un tunnel VPN IPSec.
```
ibmcloud sl ipsec order [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-d, --datacenter</dt>
<dd>Obligatoire. Nom abrégé du centre de données pour IPSec, par exemple, dal09.</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Permet d'ajouter un sous-réseau à un contexte de tunnel IPSEC.
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --subnet-id</dt>
<dd>Identificateur de sous-réseau à ajouter (obligatoire).</dd>
<dt>-t, --subnet-type</dt>
<dd>Type de sous-réseau à ajouter (obligatoire). Les options possibles sont les suivantes : internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>Identificateur de sous-réseau à créer.</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Permet de retirer un sous-réseau d'un contexte de tunnel IPSEC.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Permet d'ajouter une conversion d'adresse à un tunnel IPSec.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --static-ip</dt>
<dd>Adresse IP statique (obligatoire).</dd>
<dt>-r, --remote-ip</dt>
<dd>Adresse IP distante (obligatoire).</dd>
<dt>-n, --note</dt>
<dd>Remarque.</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Permet de retirer une entrée de conversion d'un tunnel IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Permet de mettre à jour une conversion d'adresse pour un tunnel IPSec.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-s, --static-ip</dt>
<dd>Adresse IP statique (obligatoire).</dd>
<dt>-r, --remote-ip</dt>
<dd>Adresse IP distante (obligatoire).</dd>
<dt>-n, --note</dt>
<dd>Remarque.</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

Permet de mettre à jour des propriétés de contexte de tunnel.
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-n, --name</dt>
<dd>Nom usuel.</dd>
<dt>-r, --remote-peer</dt>
<dd>Adresse IP de l'homologue distant.</dd>
<dt>-k, --preshared-key</dt>
<dd>Clé pré-partagée.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Authentification phase 1. Les options possibles sont les suivantes : MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Chiffrement phase 1. Les options possibles sont les suivantes : DES,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Groupe diffie hellman phase 1. Les options possibles sont les suivantes : 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Durée de vie de la clé phase 1. Les valeurs possibles sont comprises entre 120 et 172800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Authentification phase 2. Les options possibles sont les suivantes : MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Chiffrement phase 2. Les options possibles sont les suivantes : DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Groupe diffie hellman phase 2. Les options possibles sont les suivantes : 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Confidentialité de transmission parfaite phase 2. Les valeurs possibles sont comprises entre 0 et 1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Durée de vie de la clé phase 2. Les valeurs possibles sont comprises entre 120 et 172800.</dd>
</dl>
