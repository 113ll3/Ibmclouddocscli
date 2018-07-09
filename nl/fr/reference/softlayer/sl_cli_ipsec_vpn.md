---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes de l'interface CLI pour le réseau privé virtuel IPSec

<table summary="Commandes générales de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">

<caption>Tableau 1. Commandes pour le réseau privé virtuel IPSec de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Commandes pour le réseau privé virtuel IPSec de l'infrastructure {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl ipsec cancel](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_cancel)</td>
 <td>[ibmcloud sl ipsec config](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_config)</td>
 <td>[ibmcloud sl ipsec detail](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_detail)</td>
 <td>[ibmcloud sl ipsec list](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_list)</td>
 <td>[ibmcloud sl ipsec order](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_order)</td>
 <td>[ibmcloud sl ipsec subnet-add](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_subnet_add)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl ipsec subnet-remove](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_subnet_remove)</td>
 <td>[ibmcloud sl ipsec translation-add](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_translation_add)</td>
 <td>[ibmcloud sl ipsec translation-remove](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_translation_remove)</td>
 <td>[ibmcloud sl ipsec translation-update](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_translation_update)</td>
 <td>[ibmcloud sl ipsec update](/docs/cli/reference/softlayer/sl_cli_ipsec_vpn.html#sl_ipsec_update)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl ipsec cancel
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

### ibmcloud sl ipsec config
{: #sl_ipsec_config}

Permet de demander la configuration d'un contexte de tunnel.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONS]
```

### ibmcloud sl ipsec detail
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

### ibmcloud sl ipsec list
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

### ibmcloud sl ipsec order
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

### ibmcloud sl ipsec subnet-add
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

### ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Permet de retirer un sous-réseau d'un contexte de tunnel IPSEC.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONS]
```

### ibmcloud sl ipsec translation-add
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

### ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Permet de retirer une entrée de conversion d'un tunnel IPSec.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONS]
```

### ibmcloud sl ipsec translation-update
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

### ibmcloud sl ipsec update
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
