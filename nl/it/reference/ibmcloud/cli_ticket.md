---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-12"

keywords: cli, manage softlayer tickets, softlayer, classic infrastructure, user management, ibmcloud sl ticket

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# Gestione dei ticket dell'infrastruttura classica
{: #manage-sl-tickets}

Utilizza i seguenti comandi per gestire i ticket dell'infrastruttura classica {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl ticket attach
{: #sl_ticket_attach} 

Per collegare dispositivi a un ticket:
```
ibmcloud sl ticket attach IDTICKET [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--hardware</dt>
<dd>L'identificativo dell'hardware da collegare.</dd>
<dt>--virtual</dt>
<dd>L'identificativo di un server virtuale da collegare.</dd>
</dl>

**Esempi**:
```
ibmcloud sl ticket attach 7676767 --hardware 8675654
```
{: codeblock}

## ibmcloud sl ticket create
{: #sl_ticket_create} 

Per creare un ticket di supporto:
```
ibmcloud sl ticket create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--attachment</dt>
<dd>Numero ID oggetto iniziale da collegare al ticket.</dd>
<dt>--rootpwd</dt>
<dd>Password root associata all'ID del dispositivo collegato.</dd>
<dt>--subject-id</dt>
<dd>Obbligatorio. L'ID oggetto da utilizzare per il ticket, immetti `ibmcloudsl ticket subjects` per ottenere l'elenco.</dd>
<dt>--title</dt>
<dd>Obbligatorio. Il titolo del ticket.</dd>
<dt>--body</dt>
<dd>Il corpo del ticket.</dd>
<dt>--priority</dt>
<dd>La priorità del ticket [1|2|3|4], da 1 (Critico) a 4 (Impatto minimo). Impostabile solo con il supporto avanzato e premium. Vedi https://www.ibm.com/cloud/support.</dd>
<dt>--attachment-type</dt>
<dd>Specifica il tipo di allegato，hardware o virtuale. L'impostazione predefinita è hardware.</dd>
</dl>

## ibmcloud sl ticket detach 
{: #sl_ticket_detach} 

Per scollegare dispositivi da un ticket:
```
ibmcloud sl ticket detach IDTICKET [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--hardware</dt>
<dd>L'identificativo dell'hardware da scollegare.</dd>
<dt>--virtual</dt>
<dd>L'identificativo di un server virtuale da scollegare.</dd>
</dl>

**Esempi**:
```
ibmcloud sl ticket detach 767676 --hardware 8675654
```
{: codeblock}

```
ibmcloud sl ticket detach 767676 --virtual 1234567
```
{: codeblock}

## ibmcloud sl ticket detail 
{: #sl_ticket_detail} 

Per visualizzare i dettagli del ticket:
```
ibmcloud sl ticket detail IDTICKET [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--count</dt>
<dd>Numero di aggiornamenti.</dd>
</dl>

**Esempi**:
```
ibmcloud sl ticket detail 767676
```
{: codeblock}

```
ibmcloud sl ticket detail 767676 --count 10
```
{: codeblock}

## ibmcloud sl ticket list 
{: #sl_ticket_list} 

Per elencare i ticket:
```
ibmcloud sl ticket list[OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--open</dt>
<dd>Visualizza solo i ticket aperti.</dd>
<dt>--closed</dt>
<dd>Visualizza solo i ticket chiusi.</dd>
</dl>

## ibmcloud sl ticket subjects 
{: #sl_ticket_subjects} 

Per elencare gli ID oggetto per la creazione dei ticket:
```
ibmcloud sl ticket subjects
```
{: codeblock}

## ibmcloud sl ticket summary 
{: #sl_ticket_summary} 

Per visualizzare le informazioni di riepilogo sui ticket:
```
ibmcloud sl ticket summary
```
{: codeblock}

## ibmcloud sl ticket update 
{: #sl_ticket_update} 

Per aggiungere un aggiornamento a un ticket esistente:
```
ibmcloud sl ticket update IDTICKET ["CONTENUTO"]
```

**Esempi**:
```
ibmcloud sl ticket update 767676 "A problem has been detected."
```
{: codeblock}

## ibmcloud sl ticket upload 
{: #sl_ticket_upload} 

Per aggiungere un allegato a un ticket esistente:
```
ibmcloud sl ticket upload IDTICKET PERCORSOFILE
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--name</dt>
<dd>Il nome dell'allegato visualizzato nel ticket.</dd>
</dl>

**Esempi**:
```
ibmcloud sl ticket upload 767676 "/home/user/screenshot.png"
```
{: codeblock}

