---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-04"

keywords: cli, add cli plug-in, remove cli plug-in, cli plug-in, ibmcloud plugin, repo-add, repo-remove, plugin uninstall, plugin update

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Ajout et retrait de plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}}
{: #ibmcloud_commands_settings}

{{site.data.keyword.cloud}} prend en charge une infrastructure de plug-in permettant d'étendre sa capacité. Les commandes suivantes permettent de gérer les plug-in d'interface de ligne de commande {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Répertorier tous les référentiels de plug-in enregistrés dans l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin repos
```
{: codeblock}

<strong>Prérequis</strong> : Aucun

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Ajouter un nouveau référentiel de plug-in dans l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à ajouter. Vous pouvez définir votre propre nom pour chaque référentiel.</dd>
   <dt>REPO_URL (obligatoire)</dt>
   <dd>URL du référentiel à ajouter. Elle doit contenir le protocole (par exemple https://plugins.cloud.ibm.com et non plugins.cloud.ibm.com). https://plugins.cloud.ibm.com est le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.</dd>
    </dl>


<strong>Exemples</strong> :

Ajouter le référentiel de plug-in officiel de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} sous la forme `ibmcloud-repo` :
```
ibmcloud plugin repo-add ibmcloud-repo https://plugins.cloud.ibm.com
```
{: codeblock}

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Retirer un référentiel de plug-in de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin repo-remove REPO_NAME
```
{: codeblock}

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
   <dl>
   <dt>REPO_NAME (obligatoire)</dt>
   <dd>Nom du référentiel à supprimer.</dd>
   </dl>

<strong>Exemples</strong> :

Retirer le référentiel `ibmcloud-repo` de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} :
```
ibmcloud plugin repo-remove ibmcloud-repo
```
{: codeblock}

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Répertorier tous les plug-in disponibles dans tous les référentiels ajoutés ou dans un référentiel spécifique.
```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Répertorier uniquement les plug-in dans le référentiel spécifié.</dd>
   </dl>

<strong>Exemples</strong> :

Répertorier tous les plug-in dans tous les référentiels ajoutés :

```
ibmcloud plugin repo-plugins
```

Répertorier tous les plug-in du référentiel `ibmcloud-repo` :

```
ibmcloud plugin repo-plugins -r ibmcloud-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Afficher les détails d'un plug-in dans le référentiel

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut.</dd>
   </dl>

<strong>Exemples</strong> :

Afficher les détails du plug-in "IBM-Containers" dans le référentiel "sample-repo" :

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Afficher les détails du plug-in "IBM-Containers" dans le référentiel par défaut

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Répertorier tous les plug-in installés dans l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin list
```
{: codeblock}

<strong>Prérequis</strong> : Aucun

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Afficher les détails d'un plug-in installé
```
ibmcloud plugin show PLUGIN-NAME
```

<strong>Prérequis</strong> : Aucun

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Installer la version de plug-in spécifique dans l'interface de ligne de commande {{site.data.keyword.cloud_notm}} à partir du chemin ou du référentiel spécifié.
```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (obligatoire)</dt>
   <dd>Si -r <i>REPO_NAME</i> n'est pas spécifié, le plug-in est installé depuis le chemin local spécifié ou depuis l'URL distante.</dd>
   <dt>-r <i>REPO_NAME</i> (facultatif)</dt>
   <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.</dd>
   <dt>-v <i>VERSION</i> (facultatif)</dt>
   <dd>Version du plug-in à installer. Si elle n'est pas fournie, la dernière version du plug-in est installée. Cette option n'est valide que si vous installez le plug-in à partir du référentiel.</dd>
   <dt>-f </dt>
   <dd>Forcer l'installation du plug-in sans confirmation.</dd>
    </dl>


Le nom de référentiel officiel de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} est `Bluemix`.

<strong>Exemples</strong> :

Installer un plug-in depuis le fichier local :

```
ibmcloud plugin install /downloads/new_plugin
```

Installer un plug-in depuis l'adresse URL distante :

```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/new_plugin
```

Installer la dernière version du plug-in 'container-service' à partir du référentiel 'Bluemix' :

```
ibmcloud plugin install container-service -r Bluemix
```

ou simplement :

```
ibmcloud plugin install container-service
```

Installer la version '0.1.425' du plug-in 'container-service' à partir du référentiel de plug-in officiel :

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Mettre à niveau le plug-in à partir d'un référentiel

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.
Si aucune version n'est indiquée, la commande sélectionne la version la plus récente disponible pour l'installation.

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>Nom du plug-in à mettre à jour. Si ce paramètre n'est pas spécifié, la commande recherche des mises à niveau pour tous les plug-in installés.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>Nom du référentiel hébergeant le fichier binaire du plug-in. Si aucun référentiel n'est spécifié, la commande utilise le référentiel de plug-in par défaut 'Bluemix'.</dd>
 <dt>-v <i>VERSION</i> (facultatif)</dt>
 <dd>Version du plug-in vers laquelle effectuer la mise à jour. Si elle n'est pas indiquée, le plug-in est mis à jour vers la version disponible la plus récente.</dd>
 <dt>--all</dt>
 <dd>Mettre à jour tous les plug-in disponibles</dd>
</dl>

<strong>Exemples</strong> :

Rechercher toutes les mises à niveau disponibles dans le référentiel de plug-in officiel 'Bluemix' :

```
ibmcloud plugin update -r Bluemix
```

ou simplement :

```
ibmcloud plugin update
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la dernière version :

```
ibmcloud plugin update container-service
```

Mettre à niveau le plug-in 'container-service' dans le référentiel de plug-in officiel vers la version '0.1.440' :

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Désinstaller le plug-in spécifié de l'interface de ligne de commande {{site.data.keyword.cloud_notm}}.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>Prérequis</strong> : Aucun

<strong>Options de commande</strong> :

   <dl>
   <dt>PLUGIN_NAME (obligatoire)</dt>
   <dd>Nom du plug-in à désinstaller.</dd>
    </dl>

<strong>Exemples</strong> :

Désinstaller le plug-in 'container-service' précédemment installé :

```
ibmcloud plugin uninstall container-service
```
