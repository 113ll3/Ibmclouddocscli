---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione delle impostazioni di fatturazione, plug-in e catalogo
{: #ibmcloud_commands_settings}

<table summary="Comandi ibmcloud che puoi utilizzare per gestire le impostazioni di sicurezza, dei plug-in, della fatturazione e del catalogo {{site.data.keyword.Bluemix_notm}}.">
<caption>Tabella 1. Comandi per la gestione delle impostazioni di sicurezza, dei plug-in, della fatturazione e del catalogo {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="5">Comandi per la gestione delle impostazioni di sicurezza, dei plug-in, della fatturazione e del catalogo {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud catalog search](cli_cat_plugin_billing.html#ibmcloud_catalog_search)</td>
  <td>[ibmcloud catalog entry](cli_cat_plugin_billing.html#ibmcloud_catalog_entry)</td>
  <td>[ibmcloud catalog entry-create](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_create)</td>
  <td>[ibmcloud catalog entry-update](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_update)</td>
  <td>[ibmcloud catalog entry-delete](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog entry-visibility](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility)</td>
  <td>[ibmcloud catalog service-marketplace](cli_cat_plugin_billing.html#ibmcloud_catalog_service_marketplace)</td>
  <td>[ibmcloud catalog entry-visibility-set](cli_cat_plugin_billing.html#ibmcloud_catalog_entry_visibility_set)</td>
  <td>[ibmcloud catalog templates](cli_cat_plugin_billing.html#ibmcloud_catalog_templates)</td>
  <td>[ibmcloud catalog template](cli_cat_plugin_billing.html#ibmcloud_catalog_template)</td>
 </tr>
 <tr>
  <td>[ibmcloud catalog template-run](cli_cat_plugin_billing.html#ibmcloud_catalog_template_run)</td>
  <td>[ibmcloud catalog locations](cli_cat_plugin_billing.html#ibmcloud_catalog_locations)</td>
  <td>[ibmcloud catalog runtime](cli_cat_plugin_billing.html#ibmcloud_catalog_runtime)</td>
  <td>[ibmcloud catalog runtimes](cli_cat_plugin_billing.html#ibmcloud_catalog_runtimes)</td>
  <td>[ibmcloud plugin repos](cli_cat_plugin_billing.html#ibmcloud_plugin_repos)</td>
</tr>
<tr>
  <td>[ibmcloud plugin repo-add](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_cat_plugin_billing.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list
](cli_cat_plugin_billing.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_cat_plugin_billing.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_cat_plugin_billing.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_cat_plugin_billing.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update
](cli_cat_plugin_billing.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud billing account-usage](cli_cat_plugin_billing.html#ibmcloud_billing_account_usage)</td>
</tr>
<tr>
  <td>[ibmcloud billing org-usage](cli_cat_plugin_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_cat_plugin_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Cerca voci del catalogo

```
ibmcloud catalog search <QUERY> [-r, --region REGIONE] [-k, --kind TIPO] [-p, --price PREZZO] [-t, --tag TAG] [--sort-by PROPRIETÀ] [--col COLONNE] [--reverse] [--json] [--csv] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Specifica la regione geografica in cui cercare. Attualmente sono supportate solo "us-south" e "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>Filtra in base al tipo di risorse. Attualmente sono supportati solo "service-cf", "iaas", "runtime", "template" e "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>Filtra in base al prezzo. Attualmente sono supportati solo "free", "paygo" e "bluemix-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>Filtra in base alla tag.</dd>
  <dt>--sort-by</dt>
  <dd>Proprietà in base a cui ordinare</dd>
  <dt>--col</dt>
  <dd>Specifica colonne aggiuntive per la tabella. Attualmente "group", "provider" e "tags"</dd>
  <dt>--reverse</dt>
  <dd>Indica se invertire la sequenza di ordinamento</dd>
  <dt>--json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>--csv</dt>
  <dd>File CSV di output</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Cerca il servizio `Automation test`:

```
ibmcloud catalog search -k service -q 'Automation test'
```

## ibmcloud catalog entry
{: #ibmcloud_catalog_entry}

Ottiene una voce di catalogo

```
ibmcloud catalog entry ID [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--children</dt>
  <dd>Ottieni tutti gli elementi secondari per la voce di catalogo</dd>
  <dt>--json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Ottieni la voce con ID `a0ef1-d3b4j0`:

```
ibmcloud catalog entry 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-create
{: #ibmcloud_catalog_entry_create}
Crea una nuova voce di catalogo (solo amministratore catalogo di un account)

```
ibmcloud catalog entry-create [-c PARAMETERI_COME_JSON] [-p, --parent ELEMENTO_PRINCIPALE] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-p, --parent</dt>
  <dd>ID elemento principale dell'oggetto</dd>
  <dt>-c</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per il catalogo, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, consulta la documentazione per la specifica voce di catalogo.</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Crea risorsa dal file JSON con l'ID di elemento principale `a0ef1-d3b4j0`:

```
ibmcloud catalog entry-create -c @entry.json -p 'a0ef1-d3b4j0'
```

## ibmcloud catalog entry-update
{: #ibmcloud_catalog_entry_update}
Aggiorna una voce di catalogo esistente (solo editor o amministratore di catalogo di un account)

```
ibmcloud catalog entry-update ID [-c PARAMETRI_COME_JSON] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-c</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per il catalogo, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, consulta la documentazione per la specifica voce di catalogo.</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Aggiorna la risorsa `j402-dnf1i` dal file JSON:

```
ibmcloud catalog entry-update 'j402-dnf1i' -c @update.json
```

## ibmcloud catalog entry-delete
{: #ibmcloud_catalog_entry_delete}
Elimina una voce di catalogo (solo amministratore di catalogo di un account)
```
ibmcloud catalog entry-delete ID [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Elimina risorsa `j402-dnf1i`:

```
ibmcloud catalog delete 'j402-dnf1i'
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}
Ottieni la visibilità per una voce di catalogo (solo amministratore di catalogo di un account)

```
ibmcloud catalog entry-visibility ID [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>-global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Ottiene la visibilità della risorsa `j402-dnf1i` in ambito globale:

```
ibmcloud catalog entry-visibility 'j402-dnf1i' --global
```

## ibmcloud catalog entry-visibility-set
{: #ibmcloud_catalog_entry_visibility_set}
Aggiorna la visibilità di una voce di catalogo esistente (solo amministratore di catalogo di un account)

```
ibmcloud catalog entry-visibility-set ID [--includes-add ELENCO] [--includes-remove ELENCO] [--excludes-add ELENCO] [--excludes-remove ELENCO] [--owner ID o Email] [--restrict] [--unrestrict] [-c PARAMETRI_COME_JSON] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>

  <dt>--includes-add</dt>
  <dd>Aggiunta di un account (o elenco di account separati da virgole) all'elenco di inclusione, concedendo la visibilità alla voce. GUID Email o Account sono accettabili</dd>
  <dt>--includes-remove</dt>
  <dd>Rimozione di un account (o elenco di account separati da virgole) dall'elenco di inclusione, revocando la visibilità alla voce. GUID Email o Account sono accettabili</dd>  
  <dt>--excludes-add</dt>
  <dd>Aggiunta di un account (o elenco di account separati da virgole) all'elenco di esclusione. GUID Email o Account sono accettabili</dd>
  <dt>--excludes-remove</dt>
  <dd>Rimozione di un account (o elenco di account separati da virgole) dall'elenco di esclusione, revocando la visibilità alla voce. Se l'account è stato impostato dagli amministratori globali, gli amministratori dell'account non possono rimuovere l'account. GUID Email o Account sono accettabili</dd>
  <dt>--owner</dt>
  <dd>Modifica del proprietario di un oggetto. GUID Email o Account sono accettabili.</dd>
  <dt>--restrict</dt>
  <dd>Modifica della restrizione della visibilità dell'oggetto su 'Privato'</dd>
  <dt>--unrestrict</dt>
  <dd>Modifica della restrizione della visibilità dell'oggetto su 'Pubblico'</dd>  
  <dt>-c</dt>
  <dd>Oggetto JSON valido che contiene i parametri di configurazione specifici per il catalogo, fornito incorporato o in un file. Per un elenco dei parametri di configurazione supportati, consulta la documentazione per la specifica voce di catalogo.</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Imposta la visibilità della risorsa `j402-dnf1i` dal file JSON:

```
ibmcloud catalog entry-visibility-set 'j402-dnf1i' -c @visibility.json
```

## ibmcloud catalog service-marketplace
{: #ibmcloud_catalog_service_marketplace}
Elenca le offerte di servizio nel marketplace

```
ibmcloud catalog service-marketplace [--cf] [--rc] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--cf</dt>
  <dd>Mostra solo i servizi Cloud Foundry</dd>
  <dt>--rc</dt>
  <dd>Mostra solo i servizi compatibili con RC</dd>
  <dt>--global</dt>
  <dd>Opera in ambito globale</dd>
</dl>

<strong>Esempi</strong>:

Mostra le offerte del servizio in ambito globale:

```
ibmcloud catalog service-marketplace --global
```

## ibmcloud catalog templates
{: #ibmcloud_catalog_templates}

Visualizza i modelli di contenitore tipo su {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud catalog templates [-d]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-d (facoltativo)</dt>
   <dd>Se viene specificata l'opzione <i>-d</i>, viene visualizzata anche la descrizione di ciascun modello. Altrimenti, vengono visualizzati solo l'ID e il nome di ciascun modello.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Visualizza le informazioni dettagliate di un modello contenitore tipo specificato.

```
ibmcloud catalog template ID_MODELLO
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ID_MODELLO (obbligatorio)</dt>
   <dd>L'ID del modello contenitore tipo. Utilizza <i>ibmcloud templates</i> per visualizzare l'ID di tutti i modelli.</dd>
   </dl>


<strong>Esempi</strong>:

Visualizza i dettagli del modello `mobileBackendStarter`:

```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crea un'applicazione cf basata sul modello specificato con l'URL e la descrizione specificati. Per impostazione predefinita, la nuova applicazione viene avviata automaticamente.

```
ibmcloud catalog template-run ID_MODELLO NOME_APPLICAZIONE_CF [-u URL] [-d DESCRIZIONE] [--no-start]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>ID_MODELLO (obbligatorio)</dt>
   <dd>Il modello su cui verrà basata l'applicazione quando verrà creata. Utilizza <i>ibmcloud templates</i> per visualizzare l'ID di tutti i modelli.</dd>
   <dt>NOME_APPLICAZIONE_CF (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf da creare.</dd>
   <dt>-u <i>URL</i> (facoltativo)</dt>
   <dd>La rotta dell'applicazione. Se non specificata, la rotta viene impostata automaticamente da {{site.data.keyword.Bluemix_notm}} in base al nome della tua applicazione e al dominio predefinito.</dd>
   <dt>-d <i>DESCRIZIONE</i> (facoltativo)</dt>
   <dd>Descrizione dell'applicazione.</dd>
   <dt>--no-start (facoltativo)</dt>
   <dd>Non avviare l'applicazione automaticamente una volta creata. Se non viene specificata, l'applicazione viene avviata automaticamente dopo la sua creazione.</dd>
   </dl>


<strong>Esempi</strong>:

Crea un'applicazione `my-app` basata sul modello `javaHelloWorld`:

```
ibmcloud catalog template-run javaHelloWorld my-app
```

Crea un'applicazione `my-ruby-app` basata sul modello `rubyHelloWorld` con la rotta `myrubyapp.chinabluemix.net` e la descrizione `La mia prima applicazione ruby su {{site.data.keyword.Bluemix_notm}}.`:

```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app -u myrubyapp.chinabluemix.net -d "My first ruby app on {{site.data.keyword.Bluemix_notm}}."
```

Crea un'applicazione `my-python-app` basata sul modello `pythonHelloWorld` senza l'avvio automatico:

```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Ottieni un sottoinsieme scelto di regioni nel formato di tua scelta.

```
ibmcloud catalog locations [-i, --id ID] [-k, --kind TIPO] [--col COLONNE] [--json] [--global] [--csv]
```

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Specifica l'area geografica per ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Ottieni un elenco di voci per il tipo specificato.</dd>
  <dt>--col</dt>
  <dd>Specifica colonne aggiuntive per la tabella. Attualmente "group", "provider" e "tags".</dd>
  <dt>--json</dt>
  <dd>Output della risposta JSON originale.</dd>
  <dt>--global</dt>
  <dd>Opera in un ambito globale.</dd>
  <dt>--csv</dt>
  <dd>File CSV di output</dd>
</dl>

## ibmcloud catalog runtime
{: #ibmcloud_catalog_runtime}

Visualizza i dettagli di un runtime. Questo comando è disponibile solo per il cloud pubblico.

```
ibmcloud catalog runtime ID_RUNTIME
```

<strong>Esempi</strong>:

Mostra i dettagli del runtime "nodejsHelloWorld":

```
catalog runtime nodejsHelloWorld
```

## ibmcloud catalog runtimes
{: #ibmcloud_catalog_runtimes}

Elenca tutti i runtime. Questo comando è disponibile solo per il cloud pubblico.

```
ibmcloud catalog runtimes [-d]
```

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-d</dt>
  <dd>Mostra la descrizione di ogni runtime</dd>
</dl>

<strong>Esempi</strong>:

Elenca tutti i runtime con le loro descrizioni:

```
ibmcloud catalog runtimes -d
```

## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

Mostra l'utilizzo mensile dell'account corrente (solo amministratore dell'account)

```
ibmcloud billing account-usage [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

<strong>Esempi</strong>:

Mostra il report su costo e utilizzo dell'account corrente per 2016-06:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

Mostra l'utilizzo mensile di un'organizzazione (solo il gestore della fatturazione dell'organizzazione o l'amministratore dell'account)

```
ibmcloud billing org-usage NOME_ORGANIZZAZIONE [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>NOME_ORGANIZZAZIONE (obbligatorio)</dt>
  <dd>Nome dell'organizzazione.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

Mostra l'utilizzo mensile di un gruppo di risorse (solo l'amministratore del gruppo di risorse o l'amministratore dell'account)

```
ibmcloud billing resource-group-usage NOME_GRUPPO [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>GROUP_NAME (obbligatorio)</dt>
  <dd>Nome del gruppo di risorse.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata utilizzando il formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

Mostra l'utilizzo mensile delle istanze della risorsa nell'account corrente.

```
ibmcloud billing resource-instances-usage [-o ORGANIZZAZIONE] [-g GRUPPO_RISORSE] [-d AAAA-MM] [--json]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-o NOME_ORGANIZZAZIONE (facoltativo)</dt>
  <dd>Filtra istanze per organizzazione.</dd>
  <dt>-g NOME_GRUPPO</dt>
  <dd>Filtra istanza per gruppo di risorse.</dd>
  <dt>-d DATA_MESE (facoltativo)</dt>
  <dd>Visualizza i dati per il mese e la data specificata tramite l'utilizzo nel formato AAAA-MM. Se non specificato, viene mostrato l'utilizzo del mese corrente.</dd>
  <dt>--json (facoltativo)</dt>
  <dd>Visualizza il risultato di utilizzo nel formato JSON.</dd>
</dl>

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

Elenca tutti i repository di plug-in registrati nella CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repos
```

<strong>Prerequisiti</strong>:  Nessuno

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

Aggiungi un nuovo repository di plug-in alla CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-add NOME_REPOSITORY URL_REPOSITORY
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>NOME_REPOSITORY (obbligatorio)</dt>
   <dd>Il nome del repository da aggiungere. Puoi definire un tuo nome per ciascun repository.</dd>
   <dt>URL_REPOSITORY (obbligatorio)</dt>
   <dd>L'URL del repository da aggiungere. L'URL del repository deve contenere il protocollo (ad esempio, http://plugins.ng.bluemix.net invece di plugins.ng.bluemix.net). http://plugins.ng.bluemix.net è il repository di plug-in ufficiale della CLI {{site.data.keyword.Bluemix_notm}}.</dd>
    </dl>


<strong>Esempi</strong>:

Aggiungi il repository di plug-in ufficiale della CLI {{site.data.keyword.Bluemix_notm}} come `bluemix-repo`:

```
ibmcloud plugin repo-add bluemix-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

Rimuovi un repository di plug-in dalla CLI {{site.data.keyword.Bluemix_notm}}.

```
ibmcloud plugin repo-remove NOME_REPOSITORY
```

<strong>Prerequisiti</strong>:  Nessuno

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>NOME_REPOSITORY (obbligatorio)</dt>
   <dd>Il nome del repository da rimuovere.</dd>
   </dl>

<strong>Esempi</strong>:

Rimuove il repository `bluemix-repo` dalla CLI {{site.data.keyword.Bluemix_notm}}:

```
ibmcloud plugin repo-remove bluemix-repo
```

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
