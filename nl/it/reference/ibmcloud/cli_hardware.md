---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic infrastructure, bare metal, ibmcloud sl hardware, hardware, power-cycle, firmware

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Creazione e gestione di server bare metal
{: #sl-manage-bare-metal}

{{site.data.keyword.baremetal_long}} sono server fisici a singolo tenant che ti forniscono le prestazioni e il controllo con un accesso di basso livello alle risorse hardware. I server bare metal forniscono la potenza pura che richiedi per i tuoi carichi di lavoro che presentano un uso intensivo del processore e dell'I/O del disco. Questi server sono forniti con il pacchetto più completo di funzioni e servizi standard.

Utilizza i seguenti comandi per gestire i server hardware bare metal dell'infrastruttura classica {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl hardware cancel
{: #sl_hardware_cancel}

Annulla un server hardware.
```
ibmcloud sl hardware cancel IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-i, --immediate</dt>
<dd>Annulla il server immediatamente (invece che a una ricorrenza di fatturazione).</dd>
<dt>-r, --reason</dt>
<dd>Un motivo di annullamento facoltativo. Vedi 'ibmcloud sl hardware cancel-reasons' per un elenco di opzioni disponibili.</dd>
<dt>-c, --comment</dt>
<dd>Un commento facoltativo da aggiungere al ticket di annullamento.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl hardware cancel-reasons
{: #sl_hardware_cancel_reasons}

Visualizza un elenco di motivi di annullamento.
```
ibmcloud sl hardware cancel-reasons
```

## ibmcloud sl hardware create
{: #sl_hardware_create}

Ordina/crea un server hardware.
```
ibmcloud sl hardware create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Parte host del nome di dominio completo, obbligatorio.</dd>
<dt>-D, --domain</dt>
<dd>Parte dominio del nome di dominio completo, obbligatorio.</dd>
<dt>-s, --size</dt>
<dd>Dimensione hardware, obbligatorio.</dd>
<dt>-o, --os</dt>
<dd>Codice di installazione del sistema operativo, obbligatorio.</dd>
<dt>-d, --datacenter</dt>
<dd>Nome breve del datacenter, obbligatorio.</dd>
<dt>-p, --port-speed</dt>
<dd>Velocità della porta, obbligatorio.</dd>
<dt>-b, --billing</dt>
<dd>Frequenza di fatturazione, oraria o mensile; se non specificata, il valore predefinito è oraria.</dd>
<dt>-i, --post-install</dt>
<dd>Script di post installazione da scaricare.</dd>
<dt>-k, --key</dt>
<dd>Chiavi SSH da aggiungere all'utente root, più ricorrenze consentite.</dd>
<dt>-n, --no-public</dt>
<dd>Solo rete privata.</dd>
<dt>-e, --extra</dt>
<dd>Ulteriori opzioni, più ricorrenze consentite.</dd>
<dt>-t, --test</dt>
<dd>Non creare effettivamente il server virtuale.</dd>
<dt>-m, --template</dt>
<dd>Un file template che specifica i valori predefiniti delle opzioni della riga di comando.</dd>
<dt>-x, --export</dt>
<dd>Esporta le opzioni in un file template.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl hardware create-options
{: #sl_hardware_create_options}

Opzioni di ordine del server per un determinato chassis.
```
ibmcloud sl hardware create-options
```

## ibmcloud sl hardware credentials
{: #sl_hardware_credentials}

Elenca le credenziali del server hardware.
```
ibmcloud sl hardware credentials IDENTIFICATIVO
```

## ibmcloud sl hardware detail
{: #sl_hardware_detail}

Ottieni i dettagli per un server hardware.
```
ibmcloud sl hardware detail IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-p, --passwords</dt>
<dd>Mostra le password (fai attenzione a occhi indiscreti)..</dd>
<dt>-c, --price</dt>
<dd>Mostra i prezzi associati.</dd>
</dl>

## ibmcloud sl hardware edit
{: #sl_hardware_edit}

Modifica i dettagli del server hardware.
```
ibmcloud sl hardware edit IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-H, --hostname</dt>
<dd>Parte host dell'FQDN.</dd>
<dt>-D, --domain</dt>
<dd>Parte dominio dell'FQDN</dd>
<dt>-g, --tag</dt>
<dd>Tag da impostare o stringa vuota per rimuovere tutto.</dd>
<dt>-F, --userfile</dt>
<dd>Leggi dati utente dal file.</dd>
<dt>-u, --userdata</dt>
<dd>Stringa di metadati definita dall'utente.</dd>
<dt>-p, --public-speed</dt>
<dd>Velocità della porta pubblica; le opzioni sono: 0,10,100,1000,10000.</dd>
<dt>-v, --private-speed</dt>
<dd>Velocità della porta privata; le opzioni sono: 0,10,100,1000,10000.</dd>
</dl>

## ibmcloud sl hardware list
{: #sl_hardware_list}

Elenca i server hardware.
```
ibmcloud sl hardware list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-c, --cpu</dt>
<dd>Filtra per numero di core CPU.</dd>
<dt>-D, --domain</dt>
<dd>Filtra per dominio.</dd>
<dt>-H, --hostname</dt>
<dd>Filtra per nome host.</dd>
<dt>-d, --datacenter</dt>
<dd>Filtra per datacenter.</dd>
<dt>-m, --memory</dt>
<dd>Filtra per memoria in gigabyte.</dd>
<dt>-n, --network</dt>
<dd>Filtra per velocità della porta di rete in Mbps.</dd>
<dt>-g, --tag</dt>
<dd>Filtra per tag, più ricorrenze consentite.</dd>
<dt>-p, --public-ip</dt>
<dd>Filtra per indirizzo IP pubblico.</dd>
<dt>-v, --private-ip</dt>
<dd>Filtra per indirizzo IP privato.</dd>
<dt>-o, --order</dt>
<dd>Filtra per ID dell'ordine di acquisto del server hardware.</dd>
<dt>--owner</dt>
<dd>Filtra per ID del proprietario.</dd>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare, valore predefinito:hostname, opzione:id,guid,hostname,domain,public_ip,private_ip,datacenter,status,ipmi_ip,created,created_by.</dd>
<dt>--column</dt>
<dd>Colonna da visualizzare; valore predefinito:id,hostname,domain,public_ip,private_ip,datacenter,status; opzioni:guid,cpu,memory,os,ipmi_ip,created,created_by,tags.</dd>
</dl>

## ibmcloud sl hardware power-cycle
{: #sl_hardware_power_cycle}

Ciclo di alimentazione di un server.
```
ibmcloud sl hardware power-cycle IDENTIFICATIVO
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl hardware power-off
{: #sl_hardware_power_off}

Disattiva un server attivo.
```
ibmcloud sl hardware power-off IDENTIFICATIVO
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl hardware power-on
{: #sl_hardware_power_on}

Attiva un server.
```
ibmcloud sl hardware power-on IDENTIFICATIVO
```

## ibmcloud sl hardware reboot
{: #sl_hardware_reboot}

Riavvia un server attivo.
```
ibmcloud sl hardware reboot IDENTIFICATIVO [OPZIONI]
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

## ibmcloud sl hardware reload
{: #sl_hardware_reload}

Ricarica il sistema operativo su un server.
```
ibmcloud sl hardware reload IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-i, --postinstall</dt>
<dd>Script di post-installazione da scaricare, viene eseguito solo HTTPS, HTTP lascia il file in /root.</dd>
<dt>-k, --key</dt>
<dd>Gli ID della chiave SSH da aggiungere all'utente root, più ricorrenze consentite.</dd>
<dt>-b, --upgrade-bios</dt>
<dd>Esegui upgrade del BIOS.</dd>
<dt>-w, --upgrade-firmware</dt>
<dd>Esegui upgrade del firmware di tutti i dischi.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl hardware rescue
{: #sl_hardware_rescue}

Riavvia un server in un'immagine di salvataggio.
```
ibmcloud sl hardware rescue IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl hardware update-firmware
{: #sl_hardware_update_firmware}

Aggiorna il firmware del server.
```
ibmcloud sl hardware update-firmware IDENTIFICATIVO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>
