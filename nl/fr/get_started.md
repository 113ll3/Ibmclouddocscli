---



copyright:

  years: 2015, 2019
lastupdated: "2019-01-03"

---


{:shortdesc: .shortdesc}
{:gif: data-image-type='gif'}
{:new_window: target="_blank"}
{:tip: .tip}



# Initiation à l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}
{: #getting-started}

Il est recommandé d'installer l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} et toutes les dépendances suggérées en utilisant la méthode décrite [ici.](/docs/cli/index.html)
{: tip}


L'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} permet de gérer des applications, des conteneurs, des infrastructures, des services et d'autres ressources dans {{site.data.keyword.Bluemix_notm}}.


Pour vous initier en utilisant uniquement l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} :

1. Sélectionnez le programme d'installation de votre système d'exploitation afin de le télécharger

   Mac OS X 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 bits (ppc64le) : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

   **Les éditions 32 bits et les versions antérieures sont disponibles [ici](/docs/cli/reference/ibmcloud/all_versions.html).

1. Exécutez le programme d'installation
   * Pour Mac OS et Windows, exécutez le programme d'installation.
   * Pour Linux, procédez à l'extraction du contenu du package et exécutez le script `install_bluemix_cli`.

1. Ciblez un noeud final d'API et connectez-vous à {{site.data.keyword.Bluemix_notm}}

  ![Exemple](example.gif){: gif}

Vous êtes maintenant prêt à gérer des ressources {{site.data.keyword.Bluemix_notm}}. Entrez `ibmcloud help` pour examiner les descriptions des commandes.

Si vous utilisez un ID fédéré, suivez les instructions décrites [ici](/docs/iam/login_fedid.html#federated_id) pour vous connecter avec un code d'accès unique ou une clé d'API.
{: tip}

## Autres liens permettant d'explorer davantage l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}

* [Autres options de téléchargement et d'installation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud/download_cli.html)
* [Extension des fonctions de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} avec des plug-in](/docs/cli/reference/ibmcloud/extend_cli.html)
* [Toutes les versions de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} et notes sur l'édition](/docs/cli/reference/ibmcloud/all_versions.html)
* [Document sur l'utilisation des commandes de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/ibmcloud/bx_cli.html)


## Signaler des problèmes et soumettre des commentaires en retour
{: #issues}

Utilisez les options suivantes pour signaler des problèmes ou soumettre des demandes de nouvelle fonction :
 * Signalez des problèmes dans [GitHub](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg)
 * Laissez des messages sur le [canal Slack](https://dwopen.slack.com/messages/bluemix-cli/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg)
