---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: classic infrastructure, ibmcloud sl image, manage compute images, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Création, édition et suppression d'images de calcul
{: #sl-manage-compute-images}

Les commandes suivantes permettent de gérer les images de calcul {{site.data.keyword.cloud}} :
{: shortdesc}

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

Cette commande permet d'obtenir les détails relatifs à l'image portant l'ID `12345678`.

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
