---

copyright:

  years: 2018


lastupdated: "2018-07-31"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Befehle zur Verwaltung von IPSec VPN der {{site.data.keyword.Bluemix_notm}}-Infrastruktur

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.Bluemix_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">

<caption>Tabelle 1. IPSec-VPN-Befehle der {{site.data.keyword.Bluemix_notm}}-Infrastruktur</caption>
 <thead>
 <th colspan="6">Infrastruktur für {{site.data.keyword.Bluemix_notm}} - IPSec-VPN-Befehle</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl ipsec cancel](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_cancel)</td>
 <td>[ibmcloud sl ipsec config](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_config)</td>
 <td>[ibmcloud sl ipsec detail](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_detail)</td>
 <td>[ibmcloud sl ipsec list](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_list)</td>
 <td>[ibmcloud sl ipsec order](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_order)</td>
 <td>[ibmcloud sl ipsec subnet-add](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_subnet_add)</td>
 </tr>
 <tr>
 <td>[ibmcloud sl ipsec subnet-remove](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_subnet_remove)</td>
 <td>[ibmcloud sl ipsec translation-add](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_translation_add)</td>
 <td>[ibmcloud sl ipsec translation-remove](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_translation_remove)</td>
 <td>[ibmcloud sl ipsec translation-update](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_translation_update)</td>
 <td>[ibmcloud sl ipsec update](/docs/cli/reference/ibmcloud/cli_ipsec_vpn.html#sl_ipsec_update)</td>
 </tr>
   </tbody>
 </table>

 ### ibmcloud sl ipsec cancel
{: #sl_ipsec_cancel}

Abbruch für IPSec-VPN-Tunnelkontext.
```
ibmcloud sl ipsec cancel CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--immediate</dt>
<dd>IPSec sofort abbrechen statt am Rechnungsstichtag.</dd>
<dt>--reason</dt>
<dd>Ein optionaler Grund für den Abbruch.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

### ibmcloud sl ipsec config
{: #sl_ipsec_config}

Konfiguration von Tunnelkontext anfordern.
```
ibmcloud sl ipsec config CONTEXT_ID [OPTIONEN]
```

### ibmcloud sl ipsec detail
{: #sl_ipsec_detail}

Details für IPSec-VPN-Tunnelkontext auflisten.
```
ibmcloud sl ipsec detail CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-i, --include</dt>
<dd>Zusätzliche Ressourcen einschließen. Optionen: at,is,rs,sr,ss.</dd>
</dl>

### ibmcloud sl ipsec list
{: #sl_ipsec_list}

IPSec-VPN-Tunnelkontexte auflisten.
```
ibmcloud sl ipsec list [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der IPSec gekauft wurde.</dd>
</dl>

### ibmcloud sl ipsec order
{: #sl_ipsec_order}

IPSec-VPN-Tunnel bestellen.
```
ibmcloud sl ipsec order [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-d, --datacenter</dt>
<dd>Erforderlich. Kurzname des Rechenzentrums für IPSec, z. B. dal09.</dd>
</dl>

### ibmcloud sl ipsec subnet-add
{: #sl_ipsec_subnet_add}

Teilnetz zu IPSec-Tunnelkontext hinzufügen.
```
ibmcloud sl ipsec subnet-add CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --subnet-id</dt>
<dd>ID des hinzuzufügenden Teilnetzes, erforderlich.</dd>
<dt>-t, --subnet-type</dt>
<dd>Typ des hinzuzufügenden Teilnetzes, erforderlich. Optionen: internal,remote,service.</dd>
<dt>-n, --network</dt>
<dd>ID des zu erstellenden Teilnetzes.</dd>
</dl>

### ibmcloud sl ipsec subnet-remove
{: #sl_ipsec_subnet_remove}

Teilnetz aus IPSEC-Tunnelkontext entfernen.
```
ibmcloud sl ipsec subnet-remove CONTEXT_ID SUBNET_ID SUBNET_TYPE [OPTIONEN]
```

### ibmcloud sl ipsec translation-add
{: #sl_ipsec_translation_add}

Adressumsetzung zu IPSec-Tunnel hinzufügen.
```
ibmcloud sl ipsec translation-add CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Statische IP-Adresse, erforderlich.</dd>
<dt>-r, --remote-ip</dt>
<dd>Ferne IP-Adresse, erforderlich.</dd>
<dt>-n, --note</dt>
<dd>Hinweis.</dd>
</dl>

### ibmcloud sl ipsec translation-remove
{: #sl_ipsec_translation_remove}

Umsetzungseintrag aus IPSec entfernen.
```
ibmcloud sl ipsec translation-remove CONTEXT_ID TRANSLATION_ID [OPTIONEN]
```

### ibmcloud sl ipsec translation-update
{: #sl_ipsec_translation_update}

Adressumsetzung für IPSec aktualisieren.
```
ibmcloud sl ipsec translation-update CONTEXT_ID TRANSLATION_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-s, --static-ip</dt>
<dd>Statische IP-Adresse, erforderlich.</dd>
<dt>-r, --remote-ip</dt>
<dd>Ferne IP-Adresse, erforderlich.</dd>
<dt>-n, --note</dt>
<dd>Hinweis.</dd>
</dl>

### ibmcloud sl ipsec update
{: #sl_ipsec_update}

Eigenschaften für Tunnelkontext aktualisieren.
```
ibmcloud sl ipsec update CONTEXT_ID [OPTIONEN]
```

<strong>Befehlsoptionen</strong>:
<dl>
<dt>-n, --name</dt>
<dd>Anzeigename.</dd>
<dt>-r, --remote-peer</dt>
<dd>Ferne Peer-IP-Adresse.</dd>
<dt>-k, --preshared-key</dt>
<dd>Vorab verteilter Schlüssel.</dd>
<dt>-a, --phase1-auth</dt>
<dd>Authentifizierung der Phase 1; Optionen: MD5,SHA1,SHA256.</dd>
<dt>-c, --phase1-crypto</dt>
<dd>Verschlüsselung der Phase 1; Optionen: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-d, --phase1-dh</dt>
<dd>Diffie-Hellman-Gruppe der Phase 1; Optionen: 0,1,2,5.</dd>
<dt>-t, --phase1-key-ttl</dt>
<dd>Schlüssellebenszyklus für Phase 1; Bereich: 120-172800.</dd>
<dt>-u, --phase2-auth</dt>
<dd>Authentifizierung der Phase 2; Optionen: MD5,SHA1,SHA256.</dd>
<dt>-y, --phase2-crypto</dt>
<dd>Verschlüsselung der Phase 2; Optionen: DES,3DES,AES128,AES192,AES256.</dd>
<dt>-e, --phase2-dh</dt>
<dd>Diffie-Hellman-Gruppe der Phase 2; Optionen: 0,1,2,5.</dd>
<dt>-f, --phase2-forward-secrecy</dt>
<dd>Absolute vorwärts gerichtete Sicherheit für Phase 2; Bereich: 0-1.</dd>
<dt>-l, --phase2-key-ttl</dt>
<dd>Schlüssellebenszyklus für Phase 2; Bereich: 120-172800.</dd>
</dl>
