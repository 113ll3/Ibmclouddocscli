---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Allgemeine CLI-Befehle (ibmcloud sl)
{: #softlayer_cli}

Das Plug-in für {{site.data.keyword.BluSoftlayer}} wurde in die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle integriert. Sie müssen das Plug-in nicht mehr installieren.
{: tip}

Verwenden Sie die Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} in der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle (CLI), um die SoftLayer-Services zu konfigurieren und zu verwalten.

Ab Mai 2018 wird an Stelle der {{site.data.keyword.Bluemix_notm}}-CLI-Befehle `bluemix` und `bx` künftig der Befehl `ibmcloud` verwendet. Sie können die CLI-Befehle `bluemix` und `bx` jedoch auch weiterhin noch so lange verwenden, bis sie zu einem späteren Zeitpunkt entfernt werden.
{: tip}

Zu Beginn installieren Sie die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle. Details hierzu finden Sie in [IBM Cloud-Befehlszeilenschnittstelle (CLI) ![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}.

Eine umfassende Liste mit den Befehlen der {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle finden Sie in [{{site.data.keyword.Bluemix_notm}}-Befehle (ibmcloud)](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli).

Folgende Befehle werden unterstützt. Verwenden Sie den Befehl `ibmcloud sl`, um die Liste der verfügbaren Befehle anzuzeigen:

<table summary="Allgemeine Befehle mit Links zu weiteren Informationen über den Befehl, in alphabetischer Reihenfolge">
<caption>Tabelle 1. Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</caption>
 <thead>
 <th colspan="6">Allgemeine Befehle der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}}</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 Zur Anzeige der Hilfeinformationen für die Befehle führen Sie folgenden Befehl aus `ibmcloud sl [command] -h`
 
 ## ibmcloud sl init
{: #sl_init}

Konfigurationseinstellungen initialisieren, die für die Verbindung zur {{site.data.keyword.BluSoftlayer_notm}}-Infrastrukturumgebung verwendet werden. Die Konfiguration enthält den Benutzernamen, den API-Schlüssel oder das Kennwort, das Konto und den Endpunkt.
```
ibmcloud sl init [OPTIONEN]
```

<strong>Befehlsoptionen:</strong>
<dl>
<dt>-a, --api-endpoint</dt>
<dd>URL des API-Endpunkts für die {{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur, Standardwert: https://api.softlayer.com/rest/v3.1 für API-Schlüssel-Authentifizierung, https://api.softlayer.com/mobile/v3.1 für IBMid-Authentifizierung.</dd>
<dt>-u, --sl-user</dt>
<dd>Gen1-Infrastruktur - Benutzername</dd>
<dt>-p, --sl-password</dt>
<dd>Das Kennwort oder der API-Schlüssel</dd>
<dt>-c, --account-id</dt>
<dd>Die Konto-ID</dd>
<dt>-q, --security-question-id</dt>
<dd>Die ID der Sicherheitsfrage für die Authentifizierung; wenden Sie sich an den Kontoeigner, wenn sie nicht bekannt ist.</dd>
<dt>-w, --security-question-answer</dt>
<dd>Die Antwort auf die Sicherheitsfrage für die Authentifizierung; wenden Sie sich an den Kontoeigner, wenn sie nicht bekannt ist.</dd>
<dt>-s, --security-code</dt>
<dd>Der vom Sicherheitsanbieter generierte Sicherheitscode, wenn die 2-Faktor-Authentifizierung aktiviert ist.</dd>
<dt>-v, --security-vendor</dt>
<dd>Der Sicherheitsanbieter, der den Sicherheitscode für die Authentifizierung bereitstellt; Optionen: VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>Das Authentifizierungstoken, wenn die Telefonauthentifizierung aktiviert ist.</dd>
</dl>

Beispiel: Mit dem Benutzernamen und dem Kennwort/API-Schlüssel der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} anmelden.
```
$ ibmcloud sl init
Konfiguration der Authentifizierung der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} auswählen:
1. Mit dem Benutzernamen und dem Kennwort/API-Schlüssel der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} anmelden.
2. Single Sign-On für {{site.data.keyword.Bluemix_notm}} verwenden.
Geben Sie eine Zahl > 1 ein.
Softlayer-API-Endpunkt-URL: [https://api.softlayer.com/rest/v3.1]>
Benutzername: []> user@example.com
API-Schlüssel oder Kennwort: []> abcd

API-Endpunkt:    https://api.softlayer.com/rest/v3.1
Benutzername:    user@example.com
API-Schlüssel:   xxxxxxxxxx
```
Beispiel: {{site.data.keyword.Bluemix_notm}}-Single Sign-on für die Softlayer-Anmeldung verwenden.
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Als Ziel ausgewähltes Benutzerkonto (65ce8074c6c62b5)

API-Endpunkt:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south
Benutzer:       user@example.com
Konto:          Beispielbenutzerkonto (65ce8074c6c62b5)
Keine Organisation oder keinen Bereich als Ziel ausgewählt, verwenden Sie 'ibmcloud target --cf oder ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Wählen Sie aus, wie die Authentifizierung der Infrastruktur für {{site.data.keyword.BluSoftlayer_notm}} konfiguriert werden soll:
1. Mit dem SoftLayer-Benutzernamen und dem Kennwort/API-Schlüssel anmelden
2. IBM Cloud Single-Sign-On verwenden
Geben Sie eine Zahl ein > 2
URL des API-Endpunkts der {{site.data.keyword.BluSoftlayer_notm}}-Infrastruktur: [https://api.softlayer.com/mobile/v3.1]>
Für Konto festlegen: 123456
OK

{{site.data.keyword.BluSoftlayer_notm}} API-Endpunkt der Infrastruktur:    https://api.softlayer.com/mobile/v3.1

Konto-ID:                  123456
Benutzer-ID:               user@example.com
IMS-Token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

Hilfeinformationen für alle Befehle für den Betrieb der Infrastrukturumgebung von {{site.data.keyword.BluSoftlayer_notm}} anzeigen.
```
ibmcloud sl help
```
