---



copyright:

  years: 2015, 2018
lastupdated: "2018-07-23"

---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}


# Installation de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} autonome
{: #install_use}

L'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} fournit l'interface de ligne de commande permettant de gérer des applications, des conteneurs, des infrastructures, des services et d'autres ressources dans {{site.data.keyword.Bluemix_notm}}.

Si vous souhaitez installer l'interface de ligne de commande {{site.data.keyword.Bluemix}} ainsi que d'autres outils et plug-in recommandés pour le développement d'applications pour {{site.data.keyword.Bluemix_notm}}, suivez la méthode décrite [ici](/docs/cli/index.html).
{: tip}

Procédez comme suit pour installer l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} autonome :

1. Sélectionnez le programme d'installation de votre système d'exploitation afin de le télécharger

   Mac OS X 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/checksum){: new_window} <br>
   Windows 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/checksum){: new_window} <br>
   Linux X86 64 bits : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/checksum){: new_window} <br>
   Linux LE 64 bits (ppc64le) : [installer](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le){: new_window} / [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/checksum){: new_window} <br>

1. Exécutez le programme d'installation
   * Pour Mac OS et Windows, exécutez simplement le programme d'installation.
   * Pour Linux, procédez à l'extraction du contenu du package et exécutez le script `install_bluemix_cli`.

1. Ciblez un noeud final d'API et connectez-vous à {{site.data.keyword.Bluemix_notm}}

   ```
   ibmcloud login
   ```
   {: codeblock}
   
Vous êtes maintenant prêt à gérer des ressources {{site.data.keyword.Bluemix_notm}}. Entrez `ibmcloud help` pour examiner les descriptions des commandes.

Si vous utilisez un ID fédéré, suivez les instructions décrites [ici](https://console.bluemix.net/docs/iam/login_fedid.html#federated_id) pour vous connecter avec un code d'accès unique ou une clé d'API.  
{: tip}

## Toutes les versions du programme d'installation de l'interface CLI {{site.data.keyword.Bluemix_notm}}

Assurez-vous que vous utilisez toujours la dernière version de l'interface CLI {{site.data.keyword.Bluemix_notm}}. Cependant, si vous avez besoin d'utiliser une version 32 bits ou une version antérieure, consultez le tableau suivant.

| Version |  Mis à jour  | Téléchargements de programme d'installation | Archives binaires |
|---------|-----------|-----------|----------|
| [0.8.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.8.0) | 13/07/2018 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le/checksum) | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/osx/archive/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux64/archive/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win64/archive/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/linux32/archive/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/win32/archive/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le/archive)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.8.0/ppc64le/archive/checksum) |
| [0.7.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.7.1) | 07/06/2018 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.1/ppc64le/checksum) | |
| [0.7.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.7.0) | 31/05/2018 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.7.0/ppc64le/checksum) | |
| [0.6.7](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.7) | 15/05/2018 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/win32/checksum) [ppc64le](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.7/ppc64le/checksum) | |
| [0.6.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.6) | 19/03/2018 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.6/win32/checksum) | |
| [0.6.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.5) | 05/02/2018 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.5/win32/checksum) | |
| [0.6.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.4) | 19/12/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.4/win32/checksum) | |
| [0.6.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.3) | 12/12/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.3/win32/checksum) | |
| [0.6.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.2) | 16/11/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.2/win32/checksum) | |
| [0.6.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.1) | 05/10/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.1/win32/checksum) | |
| [0.6.0](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.6.0) | 30/09/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.6.0/win32/checksum) | |
| [0.5.6](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.6) | 17/08/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.6/win32/checksum) | |
| [0.5.5](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.5) | 03/07/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.5/win32/checksum) | |
| [0.5.4](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.4) | 18/05/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.4/win32/checksum) | |
| [0.5.3](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.3) | 16/05/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.3/win32/checksum) | |
| [0.5.2](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.2) | 10/04/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux64/checksum)  [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.2/win32/checksum) | |
| [0.5.1](https://github.com/IBM-Bluemix/bluemix-cli-release/releases/tag/v0.5.1) | 18/03/2017 | [macOS](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/osx/checksum)  [linux64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux64/checksum) [win64](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win64/checksum) <br> [linux32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/linux32/checksum)  [win32](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32)/[sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/0.5.1/win32/checksum) | |


Outre les programmes d'installation, vous disposez d'autres options pour installer l'interface CLI {{site.data.keyword.Bluemix_notm}} :

* Installation à partir du shell
* Téléchargement du package binaire et installation dans un répertoire personnalisé

## Installation à partir du shell
{: #shell_install}

### MacOS

Copiez et collez la commande suivante dans un terminal de votre système Mac OS et exécutez-la :

```
curl -fsSL https://clis.ng.bluemix.net/install/osx | sh
```
{: codeblock}

### Linux

Copiez et collez la commande suivante dans un terminal de votre système Linux OS et exécutez-la :

```
curl -fsSL https://clis.ng.bluemix.net/install/linux | sh
```
{: codeblock}

### Windows PowerShell

Copiez et collez la commande suivante dans une console de terminal [Windows PowerShell](https://msdn.microsoft.com/en-us/powershell/scripting/getting-started/getting-started-with-windows-powershell){: new_window} et exécutez-la :

```
iex(New-Object Net.WebClient).DownloadString('https://clis.ng.bluemix.net/install/powershell')
```
{: codeblock}

## Installation dans un répertoire personnalisé

Lorsque vous utilisez des programmes d'installation ou un script shell pour installer l'interface CLI {{site.data.keyword.Bluemix_notm}}, les fichiers binaires sont placés dans les répertoires système. Si vous souhaitez indiquer un autre répertoire, procédez comme suit.

### Etape 1 : Téléchargement du package binaire en utilisant les liens suivants en fonction de votre système d'exploitation.

| Plateforme | Téléchargements | Somme de contrôle |
|---------|----------|---------|
| macOS | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/osx/archive/checksum) |
| linux32 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux32/archive/checksum) |
| linux64 | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/linux64/archive/checksum) |
| ppc64le | [tgz](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/ppc64le/archive/checksum) |
| win32 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win32/archive/checksum) |
| win64 | [zip](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive) | [sha1sums](https://clis.ng.bluemix.net/download/bluemix-cli/latest/win64/archive/checksum) |

### Etape 2 : Extraction du package dans un répertoire défini.

   Une fois le package extrait, le contenu est similaire à l'exemple suivant :

   Pour Linux et MacOS

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── autocomplete
   │   ├── bash_autocomplete
   │   └── zsh_autocomplete
   ├── cfcli
   │   └── cf
   ├── ibmcloud
   └── ibmcloud-analytics
   ```
   {: codeblock}

   Pour Windows

   ```
   IBM_Cloud_CLI
   ├── LICENSE
   ├── NOTICE
   ├── cfcli
   │   └── cf.exe
   ├── ibmcloud-analytics.exe
   └── ibmcloud.exe
   ```
   {: codeblock}

### Etape 3 : Ajout à la variable d'environnement `PATH` et activer l'exécution automatique de shell

   * Ajoutez `{YOUR_DIRECTORY}/IBM_CLOUD_CLI` à la variable d'environnement `PATH`.
   * Pour le support de l'exécution automatique de shell (MacOS et Linux uniquement), consultez [ce guide](enable_cli_autocompletion.html).

## Autres liens permettant d'explorer davantage l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}}

* [Activation de l'exécution automatique de shell](/docs/cli/reference/bluemix_cli/enable_cli_autocompletion.html)
* [Extension de l'interface de ligne de commande {{site.data.keyword.Bluemix_notm}} avec des plug-in](/docs/cli/reference/bluemix_cli/extend_cli.html)
* [Utilisation des commandes générales de l'interface CLI {{site.data.keyword.Bluemix_notm}}](/docs/cli/reference/bluemix_cli/bx_cli.html)
* [Utilisation des commandes générales {{site.data.keyword.Bluemix_notm}} (ibmcloud sl)](/docs/cli/reference/softlayer/index.html)

## Signaler des problèmes et soumettre des commentaires en retour
{: #issues}

Utilisez les options suivantes pour signaler des problèmes ou soumettre des demandes de nouvelle fonction :
 * Créez des problèmes dans [Github](https://github.com/IBM-Bluemix/bluemix-cli-release/issues){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg).
 * Laissez des messages dans le [canal IBM Cloud Tech's Slack - #developer-tools](https://ibm-cloud-tech.slack.com). Pour demander l'accès à l'équipe, cliquez [ici](https://slack-invite-ibm-cloud-tech.mybluemix.net/){: new_window} ![Icône de lien externe](../../../icons/launch-glyph.svg).
