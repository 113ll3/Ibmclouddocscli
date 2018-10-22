---

copyright:

  years: 2018


lastupdated: "2018-10-17"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Image

Les commandes suivantes permettent de gérer les images de calcul {{site.data.keyword.Bluemix}} :
{: shortdesc}

<table summary="Commandes d'image de l'infrastructure {{site.data.keyword.Bluemix_notm}} classées par ordre alphabétique avec des liens vers des informations supplémentaires sur la commande">
 <tbody>
 <tr>
 <td>[ibmcloud sl image delete](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_delete)</td>
 <td>[ibmcloud sl image detail](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_detail)</td>
 <td>[ibmcloud sl image edit](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_edit)</td>
 <td>[ibmcloud sl image list](/docs/cli/reference/ibmcloud/cli_image.html#sl_image_list)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl image delete
{: #sl_image_delete}

Permet de supprimer une image.
```
ibmcloud sl image delete IDENTIFIER
```
**Exemples** :
```
   ibmcloud sl image delete 12345678
```
Cette commande supprime l'image portant l'ID `12345678`.

## ibmcloud sl image detail
{: #sl_image_detail}

Permet d'obtenir les détails relatifs à une image.
```
ibmcloud sl image detail IDENTIFIER
```
**Exemples** :
```
 ibmcloud sl image detail 12345678
```
Cette commande permet d'obtenir les détails relatifs à l'image portant l'ID 12345678.

## ibmcloud sl image edit
{: #sl_image_edit}

Permet d'éditer les détails relatifs à une image.
```
ibmcloud sl image edit IDENTIFIER [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--name</dt>
<dd>Nom de l'image.</dd>
<dt>--note</dt>
<dd>Note supplémentaire au sujet de l'image.</dd>
<dt>--tag</dt>
<dd>Etiquettes de l'image.</dd>
</dl>

*Exemples** :
```  
ibmcloud sl image edit 12345678 --name ubuntu16 --note testing --tag staging
```
Cette commande édite l'image portant l'ID `12345678` en la nommant `ubuntu16` et en lui affectant la note `testing` ainsi que l'étiquette `staging`.

## ibmcloud sl image list
{: #sl_image_list}

Permet de répertorier toutes les images de votre compte.
```
ibmcloud sl image list [OPTIONS]
```

<strong>Options de commande</strong> :
<dl>
<dt>--name</dt>
<dd>Filtrer par nom d'image.</dd>
<dt>--public</dt>
<dd>Afficher uniquement les images publiques.</dd>
<dt>--private</dt>
<dd>Afficher uniquement les images privées.</dd>
</dl>
