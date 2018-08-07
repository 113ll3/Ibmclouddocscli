---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Commandes pour la gestion de la sécurité de l'infrastructure {{site.data.keyword.Bluemix_notm}}

<table summary="Commandes générales de l'infrastructure {{site.data.keyword.Bluemix_notm}}, classées par ordre alphabétique avec des liens vers des informations supplémentaires">
<caption>Tableau 1. Commandes de sécurité de l'infrastructure {{site.data.keyword.Bluemix_notm}}</caption>

 <thead>
 <th colspan="5">Commandes de sécurité de l'infrastructure {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl security sshkey-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_add)</td>
  <td>[ibmcloud sl security sshkey-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_edit)</td>
  <td>[ibmcloud sl security sshkey-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_list)</td>
  <td>[ibmcloud sl security sshkey-print](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_print)</td>
  <td>[ibmcloud sl security sshkey-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl security cert-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_add)</td>
  <td>[ibmcloud sl security cert-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_edit)</td>
  <td>[ibmcloud sl security cert-download](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_download)</td>
  <td>[ibmcloud sl security cert-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_list)</td>
  <td>[ibmcloud sl security cert-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

 ### ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

Permet d'ajouter une nouvelle clé SSH.
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --in-file</dt>
<dd>Fichier id_rsa.pub à importer pour cette clé.</dd>
<dt>-k, --key</dt>
<dd>Clé SSH réelle.</dd>
<dt>--note</dt>
<dd>Note supplémentaire qui sera associée à la clé.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
Cette commande ajoute une clé SSH à partir d'un fichier : ~/.ssh/id_rsa.pub with a note "mykey".

### ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

Permet d'éditer une clé SSH.
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--label</dt>
<dd>Nouveau libellé de la clé.</dd>
<dt>--note</dt>
<dd>Nouvelles notes pour la clé.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
Cette commande met à jour la clé SSH portant l'ID 12345678 et lui affecte le libellé "Bluemix" et la note "testing".

### ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

Permet de répertorier les clés SSH sur votre compte.
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,label,fingerprint,notes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-list --sortby label
```
Cette commande répertorie toutes les clés SSH sur le compte en cours et les trie par libellé.

### ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

Permet d'imprimer une clé SSH sur l'écran.
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --out-file</dt>
<dd>La clé SSH publique sera écrite sur ce fichier.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
Cette commande affiche l'ID, le libellé et les notes de la clé SSH portant l'ID 12345678 et écrit la clé publique dans le fichier : ~/mykey.pub.

### ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

Permet de retirer définitivement une clé SSH.
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security sshkey-remove 12345678 -f
```
Cette commande retire la clé SSH portant l'ID 12345678 sans demander de confirmation.

### ibmcloud sl security cert-add
{: #sl_security_cert_add}

Permet d'ajouter et de télécharger les détails relatifs au certificat SSL.
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--crt</dt>
<dd>Fichier de certificat.</dd>
<dt>--csr</dt>
<dd>Fichier de demande de signature de certificat.</dd>
<dt>--icc</dt>
<dd>Fichier de certificat intermédiaire.</dd>
<dt>--key</dt>
<dd>Fichier de clé privée.</dd>
<dt>--notes</dt>
<dd>Notes supplémentaires.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
Cette commande ajoute le fichier certificat ~/ibm.com.cert et le fichier de clé privée ~/ibm.com.key pour le domaine ibm.com.

### ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

Permet d'éditer un certificat SSL.
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--crt</dt>
<dd>Fichier de certificat.</dd>
<dt>--csr</dt>
<dd>Fichier de demande de signature de certificat.</dd>
<dt>--icc</dt>
<dd>Fichier de certificat intermédiaire.</dd>
<dt>--key</dt>
<dd>Fichier de clé privée.</dd>
<dt>--notes</dt>
<dd>Notes supplémentaires.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
Cette commande modifie le certificat portant l'ID 12345678 et met à jour sa clé privée avec le fichier ~/ibm.com.key.

### ibmcloud sl security cert-download
{: #sl_security_cert_download}

Permet de télécharger des fichiers de certificat et de clé SSL.
```
ibmcloud sl security cert-download IDENTIFIER
```


**Exemples** :
```
ibmcloud sl security cert-download 12345678
```
Cette commande télécharge 4 fichiers sur le répertoire de travail pour le certificat portant l'ID 12345678. Ces 4 fichiers sont : le fichier certificat, le fichier de demande de signature de certificat, le fichier de certificat intermédiaire et le fichier de clé privée.

### ibmcloud sl security cert-list
{: #sl_security_cert_list}

Permet de répertorier les certificats SSL présents sur votre compte.
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--status</dt>
<dd>Afficher les certificats avec ce statut. La valeur par défaut est all, les options possibles sont les suivantes : all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>Options de tri des colonnes : id,common_name,days_until_expire,notes.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
Cette commande répertorie tous les certificats valides sur le compte en cours et les trie par jours de validité.

### ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

Permet de retirer un certificat SSL.
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>-f, --force</dt>
<dd>Forcer l'opération sans qu'aucune confirmation ne soit demandée.</dd>
</dl>

**Exemples** :
```
ibmcloud sl security cert-remove 12345678
```
Cette commande retire le certificat portant l'ID 12345678.
