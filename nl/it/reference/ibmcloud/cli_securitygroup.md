---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-03"

keywords: cli, manage security groups, ingress, egress, traffic, virtual server cli, classic infrastructure cli, securitygroup, ibmcloud sl securitygroup, security group cli

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Gestione dei gruppi di sicurezza per il traffico del server virtuale
{: #sl-manage-securitygroups}

Un gruppo di sicurezza è un insieme di regole di filtro IP che definiscono come gestire il traffico in entrata (ingress) e in uscita (egress) sia alle interfacce pubbliche che a quelle private di un'istanza del server virtuale. Le regole che aggiungi a un gruppo di sicurezza sono note come regole del gruppo di sicurezza.

Utilizza i seguenti comandi per gestire un gruppo di sicurezza che utilizza il servizio Gruppo di sicurezza dell'infrastruttura classica {{site.data.keyword.cloud}}.
{: shortdesc}

## ibmcloud sl securitygroup create
{: #sl_securitygroup_create}

Crea un gruppo di sicurezza.
```
ibmcloud sl securitygroup create [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
<dt>-d, --description</dt>
<dd>La descrizione del gruppo di sicurezza.</dd>
</dl>

## ibmcloud sl securitygroup delete
{: #sl_securitygroup_delete}

Elimina il gruppo di sicurezza fornito.
```
ibmcloud sl securitygroup delete ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>

## ibmcloud sl securitygroup detail
{: #sl_securitygroup_detail}

Ottieni i dettagli su un gruppo di sicurezza.
```
ibmcloud sl securitygroup detail ID_GRUPPOSICUREZZA [OPZIONI]
```

## ibmcloud sl securitygroup edit
{: #sl_securitygroup_edit}

Modifica i dettagli di un gruppo di sicurezza.
```
ibmcloud sl securitygroup edit ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Il nome del gruppo di sicurezza.</dd>
<dt>-d, --description</dt>
<dd>La descrizione del gruppo di sicurezza.</dd>
</dl>

## ibmcloud sl securitygroup interface-add
{: #sl_securitygroup_interface_add}

Collega un'interfaccia a un gruppo di sicurezza.
```
ibmcloud sl securitygroup interface-add ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --network-component</dt>
<dd>L'ID componente di rete da associare al gruppo di sicurezza.</dd>
<dt>-s, --server</dt>
<dd>L'ID server da associare al gruppo di sicurezza.</dd>
<dt>-i, --interface</dt>
<dd>L'interfaccia del server da associare (pubblica/privata).</dd>
</dl>

## ibmcloud sl securitygroup interface-list
{: #sl_securitygroup_interface_list}

Elenca le interfacce associate al gruppo di sicurezza.
```
ibmcloud sl securitygroup interface-list ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,virtualServerId,hostname.</dd>
</dl>

## ibmcloud sl securitygroup interface-remove
{: #sl_securitygroup_interface_remove}

Scollega un'interfaccia da un gruppo di sicurezza.
```
ibmcloud sl securitygroup interface-remove ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-n, --network-component</dt>
<dd>Il componente di rete da rimuovere dal gruppo di sicurezza.</dd>
<dt>-s, --server</dt>
<dd>L'ID server da rimuovere dal gruppo di sicurezza.</dd>
<dt>-i, --interface</dt>
<dd>L'interfaccia del server da rimuovere (pubblica/privata).</dd>
</dl>

## ibmcloud sl securitygroup list
{: #sl_securitygroup_list}

Elenca i gruppi di sicurezza.
```
Elenca i gruppi di sicurezza
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,name,description,created.</dd>
</dl>

## ibmcloud sl securitygroup rule-add
{: #sl_securitygroup_rule_add}

Aggiungi una regola del gruppo di sicurezza a un gruppo di sicurezza.
```
ibmcloud sl securitygroup rule-add ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-r, --remote-ip</dt>
<dd>IP/CIDR remoto da applicare.</dd>
<dt>-s, --remote-group</dt>
<dd>L'ID del gruppo di sicurezza remoto da applicare.</dd>
<dt>-d, --direction</dt>
<dd>La direzione del traffico da applicare (ingresso, uscita), obbligatorio.</dd>
<dt>-e, --ether-type</dt>
<dd>Il tipo di ether (IPv4 o IPv6) da applicare; se non specificato il valore predefinito è IPv4.</dd>
<dt>-M, --port-max</dt>
<dd>L'associazione della porta superiore da applicare.</dd>
<dt>-m, --port-min</dt>
<dd>L'associazione della porta inferiore da applicare.</dd>
<dt>-p, --protocol</dt>
<dd>Il protocollo (icmp, tcp, udp) da applicare.</dd>
</dl>

## ibmcloud sl securitygroup rule-edit
{: #sl_securitygroup_rule_edit}

Modifica una regola del gruppo di sicurezza in un gruppo di sicurezza.
```
ibmcloud sl securitygroup rule-edit ID_GRUPPOSICUREZZA ID_REGOLA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-r, --remote-ip</dt>
<dd>IP/CIDR remoto da applicare.</dd>
<dt>-s, --remote-group</dt>
<dd>L'ID del gruppo di sicurezza remoto da applicare.</dd>
<dt>-d, --direction</dt>
<dd>La direzione del traffico da applicare (ingresso, uscita), obbligatorio.</dd>
<dt>-e, --ether-type</dt>
<dd>Il tipo di ether (IPv4 o IPv6) da applicare; se non specificato il valore predefinito è IPv4.</dd>
<dt>-M, --port-max</dt>
<dd>L'associazione della porta superiore da applicare.</dd>
<dt>-m, --port-min</dt>
<dd>L'associazione della porta inferiore da applicare.</dd>
<dt>-p, --protocol</dt>
<dd>Il protocollo (icmp, tcp, udp) da applicare.</dd>
</dl>

## ibmcloud sl securitygroup rule-list
{: #sl_securitygroup_rule_list}

Elenca le regole del gruppo di sicurezza.
```
ibmcloud sl securitygroup rule-list ID_GRUPPOSICUREZZA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>--sortby</dt>
<dd>Colonna in base a cui ordinare; le opzioni sono: id,remoteIp,remoteGroupId,direction,ethertype,portRangeMin,portRangeMax,protocol.</dd>
</dl>

## ibmcloud sl securitygroup rule-remove
{: #sl_securitygroup_rule_remove}

Rimuove una regola da un gruppo di sicurezza.
```
ibmcloud sl securitygroup rule-remove ID_GRUPPOSICUREZZA ID_REGOLA [OPZIONI]
```

<strong>Opzioni del comando</strong>:
<dl>
<dt>-f, --force</dt>
<dd>Forza l'operazione senza conferma.</dd>
</dl>
