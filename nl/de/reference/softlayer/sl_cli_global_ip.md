---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Allgemeine IP-CLI-Befehle

<table summary="Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Allgemeine IP-Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">{{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur - Befehle für globales IP</th>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl globalip assign](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_assign)</td>
  <td>[ibmcloud sl globalip cancel](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_cancel)</td>
  <td>[ibmcloud sl globalip create](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_create)</td>
 <td>[ibmcloud sl globalip list](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_list)</td>
 <td>[ibmcloud sl globalip unassign](/docs/cli/reference/softlayer/sl_cli_global_ip.html#sl_globalip_unassign)</td>
 </tr>
   </tbody>
 </table>
 
 ### ibmcloud sl globalip assign
{: #sl_globalip_assign}

Globale IP einem Zielrouter oder -gerät zuordnen.
```
ibmcloud sl globalip assign IDENTIFIER TARGET
```


**Beispiele**:
```
ibmcloud sl globalip assign 12345678 9.111.123.456
```
Dieser Befehl ordnet eine IP-Adresse mit der ID 12345678 zu einem Zielgerät mit der IP-Adresse 9.111.123.456 zu.

### ibmcloud sl globalip cancel
{: #sl_globalip_cancel}

Abbruch für globale IP.
```
ibmcloud sl globalip cancel IDENTIFIER [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl globalip cancel 12345678
```
Dieser Befehl bricht die IP-Adresse mit der ID 12345678 ab.
 
 ### ibmcloud sl globalip create
{: #sl_globalip_create}

Globale IP erstellen.
```
ibmcloud sl globalip create [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--v6</dt>
<dd>IPv6-IP-Adresse bestellen.</dd>
<dt>--test</dt>
<dd>Testbestellung.</dd>
<dt>-f, --force</dt>
<dd>Operation ohne Bestätigung erzwingen.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl globalip create --v6
```
Dieser Befehl erstellt eine IPv6-Adresse.

### ibmcloud sl globalip list
{: #sl_globalip_list}

Alle globalen IPs für eigenes Konto auflisten.
```
ibmcloud sl globalip list [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>--v4</dt>
<dd>Nur IPv4 anzeigen.</dd>
<dt>--v6</dt>
<dd>Nur IPv6 anzeigen.</dd>
<dt>--order</dt>
<dd>Nach ID der Bestellung filtern, mit der diese IP-Adresse gekauft wurde.</dd>
</dl>

**Beispiele**:
```
ibmcloud sl globalip list --v4
```
Dieser Befehl listet alle IPv4-Adressen für ein aktuelles Konto auf.

### ibmcloud sl globalip unassign
{: #sl_globalip_unassign}

Zuordnung einer globalen IP zu einem Zielrouter oder -gerät aufheben.
```
ibmcloud sl globalip unassign IDENTIFIER
```


**Beispiele**:
```
ibmcloud sl globalip unassign 12345678
```
Dieser Befehl hebt die Zuordnung einer IP-Adresse mit der ID 12345678 zu einem Zielgerät auf.
