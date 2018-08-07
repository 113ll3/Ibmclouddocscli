---



copyright:

  years: 2018
lastupdated: "2018-07-24"

---

{:codeblock: .codeblock} 
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}

# Désinstallation de l'interface CLI {{site.data.keyword.Bluemix_notm}}

Consultez les sections suivantes pour obtenir des instructions sur la désinstallation d'{{site.data.keyword.Bluemix_notm}} sur des plateformes spécifiques.

## Désinstallation sous Windows

* Cliquez sur le bouton `Démarrer` puis sélectionnez `Panneau de configuration`
* Dans la fenêtre en incrustation, cliquez sur `Désinstaller un programme`
* Dans la liste d'applications, recherchez `IBM Cloud Command Line Interface`
* Cliquez à l'aide du bouton droit de la souris sur `IBM Cloud Command Line Interface` et sélectionnez `Désinstaller`
* Le programme d'installation est alors lancé. Suivez les instructions pour mener à terme la désinstallation.

## Désinstallation sur Linux/macOS

### Avant la version `0.9.0`

* Ouvrez un terminal et exécutez les commandes suivantes
  * `rm -rf /usr/local/ibmcloud`
  * `rm -f /usr/local/bin/ibmcloud`
  * `rm -f /usr/local/bin/bluemix`
  * `rm -f /usr/local/bin/bx`
  * `rm -f /usr/local/bin/ibmcloud-analytics`
* Nettoyez les scripts d'exécution automatique si vous les avez configurés. Pour plus de détails, voir [Activation de l'exécution automatique de l'interface CLI](enable_cli_autocompletion.html).

### Version `0.9.0` et versions ultérieures

* Ouvrez un terminal et exécutez la commande suivante
  * `/usr/local/ibmcloud/uninstall`
* Nettoyez les scripts d'exécution automatique si vous les avez configurés. Pour plus de détails, voir [Activation de l'exécution automatique de l'interface CLI](enable_cli_autocompletion.html).
