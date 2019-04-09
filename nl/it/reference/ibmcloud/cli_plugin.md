---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-26"

keywords: add cli plug-in, remove cli plug-in, cli plug-in, ibmcloud plugin, repo-add, repo-remove, plugin uninstall, plugin update

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Aggiunta e rimozione di plug-in della CLI {{site.data.keyword.cloud_notm}}
{: #ibmcloud_commands_settings}

{{site.data.keyword.cloud}} supporta un framework di plug-in per estendere la sua funzionalità. Utilizza i seguenti comandi per gestire i plugin della CLI {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Elenca tutti i repository di plug-in registrati nella CLI {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin repos
```
{: codeblock}

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Aggiungi un nuovo repository di plug-in alla CLI {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin repo-add NOME_REPOSITORY URL_REPOSITORY
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_REPOSITORY (obbligatorio)</dt>
   <dd>Il nome del repository da aggiungere. Puoi definire un tuo nome per ciascun repository.</dd>
   <dt>URL_REPOSITORY (obbligatorio)</dt>
   <dd>L'URL del repository da aggiungere. L'URL del repository deve contenere il protocollo (ad esempio, http://plugins.ng.bluemix.net invece di plugins.ng.bluemix.net). http://plugins.ng.bluemix.net è il repository di plug-in ufficiale della CLI {{site.data.keyword.cloud_notm}}.</dd>
    </dl>


<strong>Esempi</strong>:

Aggiungi il repository di plug-in ufficiale della CLI {{site.data.keyword.Bluemix_notm}} come `bluemix-repo`:
```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```
{: codeblock}

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Rimuovi un repository di plug-in dalla CLI {{site.data.keyword.cloud_notm}}.
```
ibmcloud plugin repo-remove NOME_REPOSITORY
```
{: codeblock}

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_REPOSITORY (obbligatorio)</dt>
   <dd>Il nome del repository da rimuovere.</dd>
   </dl>

<strong>Esempi</strong>:

Rimuove il repository `bluemix-repo` dalla CLI {{site.data.keyword.cloud_notm}}:
```
ibmcloud plugin repo-remove bluemix-repo
```
{: codeblock}

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

Elenca tutti i plug-in disponibili in tutti i repository aggiunti o in uno specifico repository.
```
ibmcloud plugin repo-plugins [-r NOME_REPOSITORY]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-r <i>NOME_REPOSITORY</i> (facoltativo)</dt>
   <dd>Elenca solo i plug-in del repository specificato.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca tutti i plug-in in tutti i repository aggiunti:

```
ibmcloud plugin repo-plugins
```

Elenca tutti i plug-in nel repository `bluemix-repo`:

```
ibmcloud plugin repo-plugins -r bluemix-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

Mostra i dettagli di un plug-in nel repository.

```
ibmcloud plugin repo-plugin NOME_PLUGIN [-r NOME_REPOSITORY]
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-r <i>NOME_REPOSITORY</i> (facoltativo)</dt>
   <dd>Il nome del repository. Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito.</dd>
   </dl>

<strong>Esempi</strong>:

Elenca i dettagli del plugin "IBM-Containers" nel repository "sample-repo":

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

Elenca i dettagli del plugin "IBM-Containers" nel repository predefinito.

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

Elenca tutti i plug-in installati nella CLI {{site.data.keyword.Bluemix_notm}}.
```
ibmcloud plugin list
```
{: codeblock}

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

Visualizza i dettagli di un plugin installato.
```
ibmcloud plugin show NOME-PLUGIN
```

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

Installa la versione specifica del plug-in nella CLI {{site.data.keyword.Bluemix_notm}} dal percorso o repository specificato.
```
ibmcloud plugin install PERCORSO_PLUGIN|NOME_PLUGIN [-r NOME_REPOSITORY] [-v VERSIONE]
```

```
ibmcloud plugin install PERCORSO-LOCALE/A/PLUGIN | URL [-f]
```

Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito 'Bluemix'.
Se non viene specificata alcuna versione, il comando seleziona l'ultima versione disponibile da installare.

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>PERCORSO_PLUGIN|NOME_PLUGIN (obbligatorio)</dt>
   <dd>Se -r <i>NOME_REPOSITORY</i> non viene specificato, il plug-in viene installato dal percorso locale o dall'URL remoto specificato.</dd>
   <dt>-r <i>NOME_REPOSITORY</i> (facoltativo)</dt>
   <dd>Il nome del repository in cui si trova il file binario del plug-in. Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito 'Bluemix'.</dd>
   <dt>-v <i>VERSIONE</i> (facoltativo)</dt>
   <dd>La versione del plug-in da installare. Se non fornita, viene installata l'ultima versione del plug-in. Questa opzione è valida solo quando si installa il plug-in dal repository.</dd>
   <dt>-f </dt>
   <dd>Forza l'installazione del plug-in senza conferma.</dd>
    </dl>


La CLI {{site.data.keyword.Bluemix_notm}} ha il nome repository ufficiale di `Bluemix`.

<strong>Esempi</strong>:

Installa un plug-in dal file locale:

```
ibmcloud plugin install /downloads/new_plugin
```

Installa un plug-in dall'URL remoto:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

Installa il plug-in 'container-service' dell'ultima versione dal repository 'Bluemix':

```
ibmcloud plugin install container-service -r Bluemix
```

o semplicemente:

```
ibmcloud plugin install container-service
```

Installa il plug-in 'container-service' con la versione '0.1.425' dal repository di plugin ufficiale:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

Aggiorna il plug-in da un repository.

```
ibmcloud plugin update [NOME PLUGIN] [-r NOME_REPOSITORY] [-v VERSIONE] [--all]
```

Se non viene specificato alcun repository, il comando utilizza il repository di plug-in predefinito 'Bluemix'.
Se non viene specificata alcuna versione, il comando seleziona l'ultima versione disponibile da installare.

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
<dl>
 <dt>NOME PLUGIN</dt>
 <dd>Nome del plug-in da aggiornare. Se non specificato, il comando ricerca gli aggiornamenti per tutti i plug-in installati.</dd>
 <dt>-r NOME_REPOSITORY</dt>
 <dd>Il nome del repository in cui si trova il file binario del plug-in. Se non specificato, il comando utilizza il repository di plugin predefinito 'Bluemix'.</dd>
 <dt>-v <i>VERSIONE</i> (facoltativo)</dt>
 <dd>La versione a cui aggiornare il plug-in. Se non viene fornita, aggiorna il plug-in all'ultima versione disponibile.</dd>
 <dt>--all</dt>
 <dd>Aggiorna tutti i plug-in disponibili.</dd>
</dl>

<strong>Esempi</strong>:

controlla tutti gli aggiornamenti disponibili nel repository di plugin 'Bluemix':

```
ibmcloud plugin update -r Bluemix
```

o semplicemente:

```
ibmcloud plugin update
```

Aggiorna il plug-in 'container-service' nel repository di plug-in ufficiale all'ultima versione:

```
ibmcloud plugin update container-service
```

Aggiorna il plug-in 'container-service' nel repository di plug-in ufficiale alla versione '0.1.440':

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

Disinstalla il plug-in specificato dalla CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin uninstall NOME_PLUGIN
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_PLUGIN (obbligatorio)</dt>
   <dd>Il nome del plug-in da disinstallare.</dd>
    </dl>

<strong>Esempi</strong>:

Disinstalla il plug-in 'container-service' precedentemente installato:

```
ibmcloud plugin uninstall container-service
```
