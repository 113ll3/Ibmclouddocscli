---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Comandi per gestire il Virtual Server dell'infrastruttura {{site.data.keyword.Bluemix_notm}} 

<table summary="Comandi generali dell'infrastruttura {{site.data.keyword.Bluemix_notm}} riportati in ordine alfabetico  con dei link a ulteriori informazioni sul comando">

<caption>Tabella 1. Comandi di server virtuale dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</caption>
 <thead>
 <th colspan="6">Comandi di server virtuale dell'infrastruttura {{site.data.keyword.Bluemix_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl vs cancel](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_cancel)</td>
 <td>[ibmcloud sl vs capture](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_capture)</td>
 <td>[ibmcloud sl vs create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_create)</td>
 <td>[ibmcloud sl vs options](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_options)</td>
 <td>[ibmcloud sl vs credentials](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_credentials)</td>
 <td>[ibmcloud sl vs detail](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_detail)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs dns-sync](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_dns_sync)</td>
 <td>[ibmcloud sl vs edit](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_edit)</td>
 <td>[ibmcloud sl vs host-create](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_create)</td>
 <td>[ibmcloud sl vs host-list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_host_list)</td>
 <td>[ibmcloud sl vs list](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_list)</td>
 <td>[ibmcloud sl vs pause](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_pause)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs power-off](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_off)</td>
 <td>[ibmcloud sl vs power-on](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_power_on)
 <td>[ibmcloud sl vs ready](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_ready)</td>
 <td>[ibmcloud sl vs reboot](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reboot)</td>
 <td>[ibmcloud sl vs reload](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_reload)</td>
 <td>[ibmcloud sl vs rescue](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_rescue)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl vs resume](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_resume)</td>
 <td>[ibmcloud sl vs upgrade](/docs/cli/reference/ibmcloud/cli_virtual_server.html#sl_vs_upgrade)</td>
</tr>
   </tbody>
 </table>

 ### ibmcloud sl vs cancel
{: #sl_vs_cancel}

Annulla l'istanza del server virtuale.
```
ibmcloud sl vs cancel IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs cancel 12345678
```
Questo comando annulla l'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs capture
{: #sl_vs_capture}

Acquisisci l'istanza del server virtuale in un'immagine.
```
ibmcloud sl vs capture IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Obbligatorio. Nome dell'immagine.</dd>
<dt>--all</dt>
<dd>Acquisisce tutti i dischi appartenenti al quanto.</dd>
<dt>--note</dt>
<dd>Aggiunge una nota da associare all'immagine.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs capture 12345678 -n mycloud --all --note testing
```
Questo comando acquisisce l'istanza del server virtuale con ID 12345678 con tutti i dischi in un'immagine denominata "mycloud" con la nota "testing".

### ibmcloud sl vs create
{: #sl_vs_create}

Crea un'istanza del server virtuale.
```
ibmcloud sl vs create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Obbligatorio. Parte host dell'FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Obbligatorio. Parte dominio dell'FQDN</dd>
<dt>-c, --cpu</dt>
<dd>Obbligatorio. Numero di core della CPU.</dd>
<dt>-m, --memory</dt>
<dd>Obbligatorio. Memoria in megabyte.</dd>
<dt>--flavor</dt>
<dd>Nome chiave caratteristica Virtual Server pubblico.</dd>
<dt>-d, --datacenter</dt>
<dd>Obbligatorio. Nome breve del datacenter.</dd>
<dt>-o, --os</dt>
<dd>Codice di installazione SO. Suggerimento: puoi specificare <OS>_LATEST.</dd>
<dt>--image</dt>
<dd>ID immagine. Vedi: 'ibmcloud sl image list' per riferimento.</dd>
<dt>--billing</dt>
<dd>Frequenza di fatturazione. Il valore predefinito è: hourly. Le opzioni sono: hourly, monthly.</dd>
<dt>--dedicated</dt>
<dd>Crea un Virtual Server dedicato (nodo privato).</dd>
<dt>--host-id</dt>
<dd>ID host su cui eseguire il provisioning di un Virtual Server dedicato.</dd>
<dt>--san</dt>
<dd>Utilizza l'archiviazione SAN invece del disco locale.</dd>
<dt>--test</dt>
<dd>Non creare effettivamente il server virtuale.</dd>
<dt>--export</dt>
<dd>Esporta le opzioni in un file modello.</dd>
<dt>-i, --postinstall</dt>
<dd>Script di post installazione da scaricare.</dd>
<dt>-k, --key</dt>
<dd>Gli ID delle chiavi SSH da aggiungere all'utente root (più ricorrenze consentite).</dd>
<dt>--disk</dt>
<dd>Dimensioni disco (più ricorrenze consentite).</dd>
<dt>--private</dt>
<dd>Forza il server virtuale ad avere accesso solo alla rete privata.</dd>
<dt>--like</dt>
<dd>Utilizza la configurazione da un server virtuale esistente.</dd>
<dt>-n, --network</dt>
<dd>Velocità della porta di rete in Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Tag da aggiungere all'istanza (più ricorrenze consentite).</dd>
<dt>-t, --template</dt>
<dd>Un file modello che specifica i valori predefiniti delle opzioni della riga di comando.</dd>
<dt>-u, --userdata</dt>
<dd>Stringa di metadati definita dall'utente.</dd>
<dt>-F, --userfile</dt>
<dd>Leggi dati utente dal file.</dd>
<dt>--vlan-public</dt>
<dd>L'ID della VLAN pubblica in cui desideri venga posizionato il server virtuale.</dd>
<dt>--vlan-private</dt>
<dd>L'ID della VLAN privata in cui desideri venga posizionato il virtual server-</dd>
<dt>-S, --public-security-group</dt>
<dd>ID gruppo di sicurezza da associare all'interfaccia pubblica (sono consentite più ricorrenze).</dd>
<dt>-s, --private-security-group</dt>
<dd>ID gruppo di sicurezza da associare all'interfaccia privata (sono consentite più ricorrenze).</dd>
<dt>--wait</dt>
<dd>Attendi finché il server virtuale non ha terminato il provisioning fino a X secondi prima di ritornare.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs create -H myvsi -D ibm.com -c 4 -m 4096 -d dal10 -o UBUNTU_16_64 --disk 100 --disk 1000 --vlan-public 413
```
Questo comando ordina un'istanza del server virtuale con nome host myvsi, dominio ibm.com, 4 core della cpu, 4096M di memoria, ubicata nel datacenter: dal10,

### ibmcloud sl vs options
{: #sl_vs_options}

Elenca le opzioni per la creazione dell'istanza del server virtuale.
```
ibmcloud sl vs options [OPZIONI]
```


**Esempi**:
```
ibmcloud sl vs options
```
Questo comando elenca tutte le opzioni per la creazione di un'istanza del server virtuale, ad es. datacenter, cpu, memoria, so, disco, velocità di rete, ecc.

### ibmcloud sl vs credentials
{: #sl_vs_credentials}

Elenca le credenziali dell'istanza del server virtuale.
```
ibmcloud sl vs credentials IDENTIFICATIVO [OPZIONI]
```


**Esempi**:
```
ibmcloud sl vs credentials 12345678
```
Questo comando elenca tutte le coppie di nome utente e password dell'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs detail
{: #sl_vs_detail}

Ottieni i dettagli per un'istanza del server virtuale.
```
ibmcloud sl vs detail IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--passwords</dt>
<dd>Mostra le password (fai attenzione a occhi indiscreti)..</dd>
<dt>--price</dt>
<dd>Mostra i prezzi associati.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs details 12345678
```
Questo comando elenca informazioni dettagliate sull'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs dns-sync
{: #sl_vs_dns_sync}

Sincronizza i record DNS per un'istanza del server virtuale.
```
ibmcloud sl vs dns-sync IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-a, --a-record</dt>
<dd>Sincronizza il record A per l'host</dd>
<dt>--aaaa-record</dt>
<dd>Sincronizza il record AAAA per l'host.</dd>
<dt>--ptr</dt>
<dd>Sincronizza il record PTR per l'host.</dd>
<dt>--ttl</dt>
<dd>Imposta il TTL per i record A e/o PTR; il valore predefinito è: 7200.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs dns-sync 12345678 --a-record --ttl 3600
```
Questo comando sincronizza il record A (indirizzo IP V4) dell'istanza del server virtuale con ID 12345678 con il server DNS e imposta il ttl di questo record A su 3600.

### ibmcloud sl vs edit
{: #sl_vs_edit}

Modifica i dettagli di un'istanza del server virtuale.
```
ibmcloud sl vs edit IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-D, --domain</dt>
<dd>Parte dominio dell'FQDN</dd>
<dt>-H, --hostname</dt>
<dd>Parte host dell'FQDN. Esempio: server.</dd>
<dt>-g, --tag</dt>
<dd>Tag da impostare o stringa vuota per rimuovere tutto.</dd>
<dt>-u, --userdata</dt>
<dd>Stringa di metadati definita dall'utente.</dd>
<dt>-F, --userfile</dt>
<dd>Leggi dati utente dal file.</dd>
<dt>--public-speed</dt>
<dd>Velocità della porta pubblica; le opzioni sono: 0,10,100,1000,10000.</dd>
<dt>--private-speed</dt>
<dd>Velocità della porta privata; le opzioni sono: 0,10,100,1000,10000.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs edit 12345678 -D ibm.com -H myapp --tag testcli --public-speed 1000
```
Questo comando aggiorna l'istanza del server virtuale con ID 12345678 e ne imposta il dominio su "ibm.com", il nome host su "myapp" e la tag su "testcli",

### ibmcloud sl vs host-create
{: #sl_vs_host_create}

Crea un host per i server virtuali dedicati.
```
ibmcloud sl vs host-create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Obbligatorio. Parte host dell'FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Obbligatorio. Parte dominio dell'FQDN</dd>
<dt>-d, --datacenter</dt>
<dd>Obbligatorio. Nome breve del datacenter.</dd>
<dt>-s, --size</dt>
<dd>La dimensione dell'host dedicato; attualmente è disponibile solo una singola dimensione: 56_CORES_X_242_RAM_X_1_4_TB.</dd>
<dt>-b, --billing</dt>
<dd>Frequenza di fatturazione. Il valore predefinito è: hourly. Le opzioni sono: hourly, monthly.</dd>
<dt>-v, --vlan-private</dt>
<dd>L'ID della VLAN privata su cui desideri posizionare l'host dedicato. Vedi: 'ibmcloud sl vlan list' per riferimento.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

### ibmcloud sl vs host-list
{: #sl_vs_host_list}

Elenca gli host dedicati sul tuo account.
```
ibmcloud sl vs host-list [OPZIONI]
```


<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Filtra per nome dell'host dedicato.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtra per datacenter dell'host dedicato.</dd>
<dt>--owner</dt>
<dd>Filtra per proprietario dell'host dedicato.</dd>
<dt>--order</dt>
<dd>Filtra per ID dell'ordine di acquisto dell'host dedicato.</dd>
</dl>

### ibmcloud sl vs list
{: #sl_vs_list}

Elenca le istanze del server virtuale per il tuo account.
```
ibmcloud sl vs list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filtra per numero di core CPU.</dd>
<dt>-D, --domain</dt>
<dd>Filtra per parte dominio del nome di dominio completo.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtra per nome breve del datacenter.</dd>
<dt>-H, --hostname</dt>
<dd>Filtra per parte host del nome di dominio completo.</dd>
<dt>-m, --memory</dt>
<dd>Filtra per memoria in megabyte.</dd>
<dt>-n, --network</dt>
<dd>Filtra per velocità della porta di rete in Mbps.</dd>
<dt>-P, --public-ip</dt>
<dd>Filtra per indirizzo IP pubblico.</dd>
<dt>-p, --private-ip</dt>
<dd>Filtra per indirizzo IP privato.</dd>
<dt>--hourly</dt>
<dd>Mostra solo le istanze orarie.</dd>
<dt>--monthly</dt>
<dd>Mostra solo le istanze mensili.</dd>
<dt>-g, --tag</dt>
<dd>Filtra in base alle tag (sono consentite più ricorrenze).</dd>
<dt>-o, --order</dt>
<dd>Filtra per ID dell'ordine di acquisto dell'istanza.</dd>
<dt>--owner</dt>
<dd>Filtra per ID dell'utente proprietario delle istanze.</dd>
<dt>--sortby</dt>
<dd>Colonna in base alla quale ordinare; il valore predefinito è:hostname, le opzioni sono:id,hostname,domain,datacenter,cpu,memory,public_ip,private_ip.</dd>
<dt>--columns</dt>
<dd>Colonne da visualizzare, il valore predefinito è:id,hostname,public_ip,private_ip,datacenter,action, le opzioni sono: guid,power_state,created_by,tags.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs list --domain ibm.com --hourly --sortby memory
```
Questo comando elenca tutte le istanze del server virtuale con fatturazione oraria sull'account corrente filtrando per dominio uguale "ibm.com" e ordinandole per memoria.

### ibmcloud sl vs pause
{: #sl_vs_pause}

Metti in pausa un'istanza del server virtuale attiva.
```
ibmcloud sl vs pause IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs pause 12345678 -f
```
Questo comando mette in pausa l'istanza del server virtuale con ID 12345678 senza richiedere conferma.

### ibmcloud sl vs power-off
{: #sl_vs_power_off}

Disattiva un'istanza del server virtuale attiva.
```
ibmcloud sl vs power-off IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--hard</dt>
<dd>Esegue un arresto forzato.</dd>
<dt>--soft</dt>
<dd>Esegue un arresto non forzato.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs power-off 12345678 --soft
```
Questo comando esegue un arresto semplice dell'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs power-on
{: #sl_vs_power_on}

Attiva un'istanza del server virtuale.
```
ibmcloud sl vs power-on IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs power-on 12345678
```
Questo comando esegue un avvio dell'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs ready
{: #sl_vs_ready}

Verifica se un'istanza del server virtuale è pronta per l'utilizzo.
```
ibmcloud sl vs ready IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--wait</dt>
<dd>Attendi finché il server virtuale non ha terminato il provisioning fino a X secondi prima di ritornare.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs ready 12345678 --wait 30
```
Questo comando verifica lo stato dell'istanza del server virtuale con ID 12345678 per vedere se è pronta per l'utilizzo continuo e attende fino a 30 secondi.

### ibmcloud sl vs reboot
{: #sl_vs_reboot}

Riavvia un'istanza del server virtuale attiva.
```
ibmcloud sl vs reboot IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--hard</dt>
<dd>Esegue un riavvio forzato.</dd>
<dt>--soft</dt>
<dd>Esegue un riavvio non forzato.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs reboot 12345678 --hard
```
Questo comando esegue un riavvio forzato dell'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs reload
{: #sl_vs_reload}

Ricarica il sistema operativo su un'istanza del server virtuale.
```
ibmcloud sl vs reload IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Script di post installazione da scaricare.</dd>
<dt>--image</dt>
<dd>ID immagine. L'impostazione predefinita è l'utilizzo del sistema operativo corrente.</dd>
<dt>Vedi:</dt>
<dd>'ibmcloud sl image list' per riferimento.</dd>
<dt>-k, --key</dt>
<dd>Gli ID delle chiavi SSH da aggiungere all'utente root (più ricorrenze consentite).</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs reload 12345678
```
Questo comando ricarica il sistema operativo corrente per l'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs rescue
{: #sl_vs_rescue}

Riavvia un'istanza del server virtuale in un'immagine di salvataggio.
```
ibmcloud sl vs rescue IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs rescue 12345678
```
Questo comando riavvia l'istanza del server virtuale con ID 12345678 in un'immagine di salvataggio.

### ibmcloud sl vs resume
{: #sl_vs_resume}

Riprendi un'istanza del server virtuale in pausa.
```
ibmcloud sl vs resume IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs resume 12345678
```
Questo comando riprende l'istanza del server virtuale con ID 12345678.

### ibmcloud sl vs upgrade
{: #sl_vs_upgrade}

Aggiorna un'istanza del server virtuale.
```
ibmcloud sl vs upgrade IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Numero di core della CPU.</dd>
<dt>--private</dt>
<dd>Il core della CPU sarà su un server host dedicato</dd>
<dt>-m, --memory</dt>
<dd>Memoria in megabyte.</dd>
<dt>--network</dt>
<dd>Velocità della porta di rete in Mbps.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

**Esempi**:
```
ibmcloud sl vs upgrade 12345678 -c 8 -m 8192 --network 1000
```
Questo comando aggiorna l'istanza del server virtuale con ID 12345678 e imposta il numero di core della CPU su 8, la memoria su 8192M e la velocità della porta di rete su 1000 Mbps.
