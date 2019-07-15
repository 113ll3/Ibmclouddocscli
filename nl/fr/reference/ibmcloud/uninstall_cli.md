---

copyright:
  years: 2019
lastupdated: "2019-04-26"

keywords: uninstall, stand-alone cli, install cli, uninstall cli, cli, command line, command-line, windows powershell, linux, macos, installer, standalone cli

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:screen: .screen}
{:note: .note}
{:tip: .tip}

# Désinstallation de l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome
{: #uninstall-ibmcloud-cli}

Procédez comme suit pour désinstaller l'interface de ligne de commande {{site.data.keyword.cloud_notm}} autonome sur des plateformes spécifiques :
{: shortdesc}

## Désinstallation sous Windows
{: #uninstall-cli-windows}

1. Cliquez sur le bouton **Démarrer**, puis sélectionnez **Panneau de configuration**.
2. Dans la fenêtre en incrustation, cliquez sur **Désinstaller un programme**.
3. Dans la liste d'applications en incrustation, recherchez **IBM Cloud Command Line Interface**.
4. Avec le bouton droit de la souris, cliquez sur **IBM Cloud Command Line Interface** et sélectionnez **Désinstaller**.
5. Le programme de désinstallation est démarré. Suivez les instructions pour mener à terme la désinstallation.

## Désinstallation sur Linux et macOS
{: #uninstall-cli-linux-macos}

Les étapes de désinstallation sont différentes selon la version de l'interface de ligne de commande qui est installée.

Pour déterminer votre version d'interface de ligne de commande {{site.data.keyword.cloud_notm}}, exécutez la commande suivante :
```
ibmcloud -v
```
{: codeblock}

Pour désinstaller les versions antérieures à `0.9.0`, exécutez les commandes suivantes :
  ```
  rm -rf /usr/local/ibmcloud
  rm -f /usr/local/bin/ibmcloud
  rm -f /usr/local/bin/bluemix
  rm -f /usr/local/bin/bx
  rm -f /usr/local/bin/ibmcloud-analytics
  ```
  {: codeblock}

Nettoyez les scripts d'exécution automatique si vous les avez configurés. Pour plus d'informations, voir [Activation de l'exécution automatique de shell pour l'interface CLI {{site.data.keyword.cloud_notm}} (Linux et Mac uniquement)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).

Pour désinstaller la version `0.9.0` et les versions ultérieures, exécutez la commande suivante :
  ```
  /usr/local/ibmcloud/uninstall
  ```
  {: codeblock}

Nettoyez les scripts d'exécution automatique personnalisés. Pour plus d'informations, voir [Activation de l'exécution automatique de shell pour l'interface CLI {{site.data.keyword.cloud_notm}} (Linux et Mac uniquement)](/docs/cli/reference/ibmcloud?topic=cloud-cli-shell-autocomplete#shell-autocomplete).
