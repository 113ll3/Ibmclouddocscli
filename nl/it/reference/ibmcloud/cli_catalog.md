---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, catalog offerings, search catalog, ibmcloud catalog, ibmcloud catalog search, catalog entry, query templates, runtimes, geolocations, datacenter, catalog template, catalog locations

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Ricerca e gestione delle offerte di catalogo
{: #ibmcloud_catalog}

Utilizza i seguenti comandi per gestire le voci del catalogo {{site.data.keyword.cloud}}, i template di query, i runtime e le geolocalizzazioni dei data center.
{: shortdesc}
  
## ibmcloud catalog search
{: #ibmcloud_catalog_search}

Cerca voci del catalogo:
```
ibmcloud catalog search <QUERY> [-r, --region REGIONE] [-k, --kind TIPO] [-p, --price PREZZO] [-t, --tag TAG] [--sort-by PROPRIETÀ] [--col COLONNE] [--reverse] [--output TIPO] [--csv] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-r, --region</dt>
  <dd>Specifica la regione geografica in cui cercare. Attualmente sono supportate solo "us-south" e "united-kingdom"</dd>
  <dt>-k, --kind</dt>
  <dd>Filtra in base al tipo di risorse. Attualmente sono supportati solo "service-cf", "iaas", "runtime", "template" e "dashboard"</dd>
  <dt>-p, --price</dt>
  <dd>Filtra in base al prezzo. Attualmente sono supportati solo "free", "paygo" e "ibmcloud-subscription"</dd>
  <dt>-t, --tag</dt>
  <dd>Filtra in base alla tag.</dd>
  <dt>--sort-by</dt>
  <dd>Proprietà in base a cui ordinare</dd>
  <dt>--col</dt>
  <dd>Specifica colonne aggiuntive per la tabella. Attualmente "group", "provider" e "tags"</dd>
  <dt>--reverse</dt>
  <dd>Indica se invertire la sequenza di ordinamento</dd>
  <dt>--output TIPO (facoltativo)</dt>
  <dd>--output valore  Specifica il TIPO di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--id'.</dd>
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
ibmcloud catalog entry ID [--children] [--output TIPO] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>--children</dt>
  <dd>Ottieni tutti gli elementi secondari per la voce di catalogo</dd>
  <dt>--output TIPO (facoltativo)</dt>
  <dd>--output valore  Specifica il TIPO di output, al momento è supportato solo JSON.</dd>
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

Crea una nuova voce di catalogo (solo amministratore catalogo di un account):
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

Aggiorna una voce di catalogo esistente (solo editor o amministratore di catalogo di un account):
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
ibmcloud catalog delete `j402-dnf1i`
```

## ibmcloud catalog entry-visibility
{: #ibmcloud_catalog_entry_visibility}

Ottieni la visibilità per una voce di catalogo (solo amministratore di catalogo di un account)
```
ibmcloud catalog entry-visibility ID  [--output TIPO] [--global]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
<dl>
  <dt>-json</dt>
  <dd>Genera in output la risposta JSON originale</dd>
  <dt>--output TIPO (facoltativo)</dt>
  <dd>--output valore  Specifica il TIPO di output, al momento è supportato solo JSON.</dd>
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

Aggiorna la visibilità di una voce di catalogo esistente (solo amministratore di catalogo di un account):
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

Elenca le offerte di servizio nel marketplace:
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

Visualizza i template di contenitore tipo su {{site.data.keyword.cloud_notm}}.
```
ibmcloud catalog templates [-d]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:

   <dl>
   <dt>-d (facoltativo)</dt>
   <dd>Se viene specificata l'opzione <i>-d</i>, viene visualizzata anche la descrizione di ciascun template. Altrimenti, vengono visualizzati solo l'ID e il nome di ciascun template.</dd>
   </dl>

## ibmcloud catalog template
{: #ibmcloud_catalog_template}

Visualizza le informazioni dettagliate di un template di contenitore tipo specificato.
```
ibmcloud catalog template TEMPLATE_ID
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>TEMPLATE_ID (obbligatorio)</dt>
   <dd>L'ID del template di contenitore tipo. Utilizza <i>ibmcloud templates</i> per visualizzare l'ID di tutti i template.</dd>
   </dl>


<strong>Esempi</strong>:

Visualizza i dettagli del template `mobileBackendStarter`:
```
ibmcloud catalog template mobileBackendStarter
```

## ibmcloud catalog template-run
{: #ibmcloud_catalog_template_run}

Crea un'applicazione cf basata sul template specificato con l'URL e la descrizione specificati. Per impostazione predefinita, la nuova applicazione viene avviata automaticamente.

```
ibmcloud catalog template-run TEMPLATE_ID CF_APP_NAME [-n HOSTNAME] [-d DOMAINNAME] [-desc DESCRIPTION] [--no-start]
```

<strong>Prerequisiti</strong>:  Endpoint, Accesso, Destinazione

<strong>Opzioni del comando</strong>:
   <dl>
   <dt>TEMPLATE_ID (obbligatorio)</dt>
   <dd>Il template su cui è basata l'applicazione quando viene creata. Utilizza <i>ibmcloud templates</i> per visualizzare l'ID di tutti i template.</dd>
   <dt>CF_APP_NAME (obbligatorio)</dt>
   <dd>Il nome dell'applicazione cf da creare.</dd>
   <dt>-n<i>HOSTNAME</i></dt>
   <dd>Il nome host dell'applicazione CF. Se non specificata, la rotta viene impostata automaticamente da {{site.data.keyword.cloud_notm}} in base al nome della tua applicazione e al dominio predefinito.</dd>
   <dt>-d<i>DOMAINNAME</i></dt>
   <dd>Il dominio dell'applicazione CF. Se non specificata, la rotta viene impostata automaticamente da {{site.data.keyword.cloud_notm}} in base al nome della tua applicazione e al dominio predefinito.</dd>
   <dt>--desc <i>DESCRIPTION</i> (facoltativo)</dt>
   <dd>Descrizione dell'applicazione.</dd>
   <dt>--no-start (facoltativo)</dt>
   <dd>Non avviare l'applicazione automaticamente dopo la sua creazione. Se non viene specificata, l'applicazione viene avviata automaticamente dopo la sua creazione.</dd>
   </dl>


<strong>Esempi</strong>:

Crea un'applicazione `my-app` basata sul template `javaHelloWorld`:
```
ibmcloud catalog template-run javaHelloWorld my-app
```

Crea un'applicazione `my-ruby-app` basata sul template `rubyHelloWorld` con una descrizione:
```
ibmcloud catalog template-run rubyHelloWorld my-ruby-app --desc "My first ruby app on IBM Cloud."
```

Crea un'applicazione `my-python-app` basata sul template `pythonHelloWorld` senza l'avvio automatico:
```
ibmcloud catalog template-run pythonHelloWorld my-python-app --no-start
```

## ibmcloud catalog locations
{: #ibmcloud_catalog_locations}

Ottieni un sottoinsieme scelto di regioni nel formato di tua scelta.
```
ibmcloud catalog locations [-i, --id ID] [-k, --kind TIPO] [--col COLONNE] [--output TIPO] [--global] [--csv]
```

<strong>Opzioni del comando</strong>:

<dl>
  <dt>-i, --id</dt>
  <dd>Specifica l'area geografica per ID.</dd>
  <dt>-k, --kind</dt>
  <dd>Ottieni un elenco di voci per il tipo specificato.</dd>
  <dt>--col</dt>
  <dd>Specifica colonne aggiuntive per la tabella. Attualmente "group", "provider" e "tags".</dd>
  <dt>--output TIPO (facoltativo)</dt>
  <dd>--output valore  Specifica il TIPO di output, al momento è supportato solo JSON. Questa opzione è esclusiva con '--id'.</dd>
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
