---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, classic infrastructure, ipsec, vpn, ibmcloud sl ipsec, tunnel, vpn access, encryption, vpn tunnel cli, ipsec vpn tunnel

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione dei tunnel VPN IPSec
{: #sl-manage-ipsec-vpn-tunnels}

L'accesso VPN {{site.data.keyword.cloud}} consente agli utenti di gestire tutti i server in remoto e in modo sicuro sulla rete privata {{site.data.keyword.cloud_notm}}. Una connessione VPN dalla tua ubicazione alla rete privata ti offre la possibilità di gestione fuori banda e di recupero del server tramite un tunnel VPN crittografato.

Utilizza i seguenti comandi per gestire i tunnel VPN IPSec nel servizio VPN IPSec dell'infrastruttura classica {{site.data.keyword.cloud_notm}}.
{: shortdesc}

## ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Annulla un contesto tunnel VPN IPSec.
```
ibmcloud sl ipsec cancel ID_CONTESTO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--immediate</dt>
<dd>Annulla l'IPSec immediatamente invece che a una ricorrenza di fatturazione.</dd>
<dt>--reason</dt>
<dd>Un motivo facoltativo per l'annullamento.</dd>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl ipsec config
{: #sl_ipsec_config}

Richiede la configurazione di un contesto tunnel.
```
ibmcloud sl ipsec config ID_CONTESTO [OPZIONI]
```

## ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Elenca i dettagli del contesto tunnel VPN IPSec.
```
ibmcloud sl ipsec detail ID_CONTESTO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Include risorse aggiuntive; le opzioni sono: at,is,rs,sr,ss.</dd>
</dl>

## ibmcloud sl ipsec list
{: #sl_ipsec_list}

Elenca i contesti tunnel VPN IPSec.
```
ibmcloud sl ipsec list [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--order</dt>
<dd>Filtra in base all'ID dell'ordine che ha acquistato l'IPSEC.</dd>
</dl>

## ibmcloud sl ipsec order
{: #sl_ipsec_order}

Ordina un tunnel VPN IPSec.
```
ibmcloud sl ipsec order [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Obbligatorio. Nome breve del datacenter per l'IPSEC, ad es. dal09.</dd>
</dl>

## ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Aggiunge una sottorete a un contesto tunnel IPSec.
```
ibmcloud sl ipsec subnet-add ID_CONTESTO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>Identificativo di sottorete da aggiungere (obbligatorio).</dd>
<dt>-t, --subnet-type</dt>
<dd>Tipo di sottorete da aggiungere (obbligatorio); le opzioni sono: internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>Identificativo di rete della sottorete da creare.</dd>
</dl>

## ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Rimuove una sottorete da un contesto tunnel IPSEC.
```
ibmcloud sl ipsec subnet-remove ID_CONTESTO ID_SOTTORETE TIPO_SOTTORETE [OPZIONI]
```

## ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Aggiunge una traduzione di indirizzo a un tunnel IPSec.
```
ibmcloud sl ipsec translation-add ID_CONTESTO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Indirizzo IP statico (obbligatorio).</dd>
<dt>-r, --remote-ip</dt>
<dd>Indirizzo IP remoto (obbligatorio).</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>

## ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Rimuove una voce di traduzione da un IPSec.
```
ibmcloud sl ipsec translation-remove ID_CONTESTO ID_CONVERSIONE [OPZIONI]
```

## ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Aggiorna una traduzione di indirizzo per un IPSec.
```
ibmcloud sl ipsec translation-update ID_CONTESTO ID_CONVERSIONE [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Indirizzo IP statico (obbligatorio).</dd>
<dt>-r, --remote-ip</dt>
<dd>Indirizzo IP remoto (obbligatorio).</dd>
<dt>-n, --note</dt>
<dd>Nota.</dd>
</dl>

## ibmcloud sl ipsec update
{: #sl_ipsec_update}

Aggiorna proprietà del contesto tunnel.
```
ibmcloud sl ipsec update ID_CONTESTO [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Nome descrittivo.</dd>
<dt>-r, --remote-peer</dt>
<dd>Indirizzo IP peer remoto.</dd>
<dt>-k, --preshared-key</dt>
<dd>Chiave precondivisa.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Autenticazione fase 1; le opzioni sono: MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Crittografia fase 1; le opzioni sono: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Gruppo diffie hellman fase 1; le opzioni sono: 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Durata chiave fase 1; l'intervallo è 120-172800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Autenticazione fase 2; le opzioni sono: MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Crittografia fase 2; le opzioni sono: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Gruppo diffie hellman fase 2; le opzioni sono: 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>PFC (perfect forward secrecy) fase 2; l'intervallo è 0-1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Durata chiave fase 2; l'intervallo è 120-172800.</dd>
</dl>
