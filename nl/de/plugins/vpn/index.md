---

copyright:

  years: 2015, 2017

lastupdated: "2017-01-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}


# VPN-CLI-Plug-in für die Befehlszeilenschnittstelle 'cf'
{: #vpn_cli_for_cf}


Sie können den {{site.data.keyword.vpn_full}}-Service mit der Befehlszeilenschnittstelle (CLI) konfigurieren und verwalten. Das CLI-Plug-in für {{site.data.keyword.vpn_short}} ist in zwei Versionen verfügbar: für die Verwendung mit dem Plug-in für die Cloud Foundry-Befehlszeilenschnittstelle und für die Verwendung mit dem Plug-in für die {{site.data.keyword.Bluemix}}-Befehlszeilenschnittstelle. Von beiden Versionen des Plug-ins werden dieselben Funktionen bereitgestellt.
{:shortdesc}

Das {{site.data.keyword.vpn_short}}-Plug-in ist für Windows-, MAC- und Linux-Betriebssysteme verfügbar. Stellen Sie sicher, dass Sie das für Sie geeignete Plug-in verwenden.

Die nachfolgenden Anweisungen sind für das Plug-in für die Cloud Foundry-Befehlszeilenschnittstelle vorgesehen. Informationen zur Verwendung des Plug-ins mit dem Plug-in für {{site.data.keyword.Bluemix_notm}} CLI finden Sie unter [{{site.data.keyword.vpn_short}}-Plug-in für {{site.data.keyword.Bluemix_notm}}-CLI ![Symbol für externen Link](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/plugins/bx_vpn/index.html){: new_window}. 

## Plug-in für die Befehlszeilenschnittstelle 'cf' installieren
Vor dem Beginn müssen Sie die Befehlszeilenschnittstelle 'cf' installieren. Weitere Informationen finden Sie unter [Cloud Foundry-Befehlszeilenschnittstelle  ![Symbol für externen Link](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}.

## CLI-Plug-in für VPN installieren
**Hinweis:** Wenn Sie eine Vorgängerversion des installierten {{site.data.keyword.vpn_short}}-CLI-Plug-ins besitzen, müssen Sie sie zunächst deinstallieren. Verwenden Sie den folgenden Befehl:

```
cf uninstall-plugin vpn
```

### Lokal installieren

1. Laden Sie das {{site.data.keyword.vpn_short}}-Plug-in für Ihre Plattform aus dem [ {{site.data.keyword.Bluemix_notm}} CLI-Plug-in-Repository![Symbol für externen Link](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/repository.html#cf-plugins){: new_window} herunter.
2. Installieren Sie das {{site.data.keyword.vpn_short}}-Plug-in mit folgendem Befehl:
**Hinweis:** Wechseln Sie entweder zur Position des {{site.data.keyword.vpn_short}}-Plug-ins oder geben Sie sein Verzeichnis an.

	- Für das Betriebssystem MS Windows:

	```
	cf install-plugin vpn_windows64.exe
	```

	- Für das Betriebssystem Apple MAC:

	```
	cf install-plugin vpn_mac_os_amd64
	```

	- Für das Betriebssystem Linux:

	```
	cf install-plugin vpn_linuxamd64
	```


### Aus dem {{site.data.keyword.Bluemix_notm}}-Repository installieren

1. Fügen Sie das {{site.data.keyword.Bluemix_notm}}-Repository zu den Cloud Foundry-CLI-Repositorys hinzu. Verwenden Sie den folgenden Befehl:

	```
	cf add-plugin-repo bluemix http://plugins.ng.bluemix.net
	```
2. Führen Sie den folgenden Befehl aus:

	```
	cf install-plugin vpn -r bluemix
	```
##Liste der Befehle des VPN-Service

### cf vpn-create connection

Erstellt eine VPN-Verbindung.

```
cf vpn-create connection <Verbindungsname> -g <Gateway-Name> -k <vorab_verteilter_Schlüssel> -subnets ["<Teilnetz/Maske>"] -cip <IP-Adresse_des_Kundengateways> -d <Beschreibung> -peer_id <Peer_ID> -admin_state <Administrationsstatus> -dpd-action <Aktion> -gateway_ip <IP-Adresse> -i <Initiatorstatus> -dpd-timeout <Wert> -dpd-interval <Wert> -ike <Name> -ipsec <Name>
```
#### Parameter
{: #p1}

**Verbindungsname:**
Der Name der Verbindung. 

**-g:**
Der Name des Gateways. 

**-k:**
Der vorab verteilte Schlüssel. 

**Teilnetz/Maske:**
Die Adresse des fernen Teilnetzes im CIDR-Format.

**IP-Adresse_des_Kundengateways:**
Die IP-Adresse des fernen Endpunkts des VPN-Tunnels. 

##### Optionale Parameter:
{: #op1}

**-d:** Die Beschreibung der angegebenen Parameter.

**-peer_id:** Die ID des fernen Peers. Der andere Endpunkt des VPN-Tunnels.

**-admin_state:** Der Status der VPN-Verbindung. Werte: UP oder DOWN.

**-dpd-action:** Die auszuführende Aktion, wenn der Peer als inaktiv erkannt wird. Werte: hold; clear; disabled; restart; restart-by-peer. Standardwert: hold

**-gateway_ip:** Die IP-Adresse des lokalen VPN-Tunnelendpunkts.

**-i:** Der Status des Initiators. Standardwert: bi-directional.

**-dpd-timeout:** Der Wert für das Zeitlimit in Sekunden, nach dessen Ablauf die Sitzung beendet wird.  Bereich: 6 - 86400 Sekunden. Standardwert: 120 Sekunden. Der Keepalive-Zeitlimitwert muss höher als der Wert des Keepalive-Intervalls sein.

**-dpd-interval:** Das Keepalive-Intervall in Sekunden. Sendet Keepalive-Nachrichten im konfigurierten Intervall, um den Aktivitätszustand des Peers zu prüfen. Bereich: 5-86399 Sekunden. Standardwert: 15 Sekunden.

**-ike:** Der Name der IKE-Richtlinie.

**-ipsec:** Der Name der IPsec-Richtlinie.


### cf vpn-create ike

Erstellt eine IKE-Richtlinie.

```
cf vpn-create ike <Richtlinienname> -g <Gateway-Name> -d <Beschreibung> -pfs <Gruppe> -e <Verschlüsselungsalgorithmus> -lv <Lebensdauerwert> -auth <Autorisierungsalgorithmus>
```
#### Parameter
{: #p2}

**Richtlinienname:**
Der Name der IKE-Richtlinie.

**Gateway-Name:**
Der Name des Gateways. 

##### Optionale Parameter:
{: #op2}

**-d:** Die Beschreibung der angegebenen Parameter.

**-pfs:** Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Werte: Group2; Group5; Group14. Standardwert: Group2

**-e:** Der Verschlüsselungsalgorithmus. Werte: aes-128; aes-192; aes-256; 3des. Standardwert: aes-128

**-lv:** Der Lebensdauerwert der IKE-Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden. Standardwert: 86400 Sekunden.

**-auth:** Der Autorisierungsalgorithmus. Werte: sha1 oder sha256


### cf vpn-create ipsec

Erstellt eine IPsec-Richtlinie.

```
cf vpn-create ipsec <Richtlinienname> -g <Gateway-Name> -d <Beschreibung> -pfs <Gruppe> -e <Verschlüsselungsalgorithmus> -lv <Lebensdauerwert> -auth <Autorisierungsalgorithmus>
```
#### Parameter
{: #p3}

**Richtlinienname:**
Der Name der IPsec-Richtlinie.

**Gateway-Name:**
Der Name des Gateways. 

##### Optionale Parameter:
{: #op3}

**-d:** Die Beschreibung der angegebenen Parameter.

**-pfs:** Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Werte: Group2; Group5; Group14. Standardwert: Group2

**-e:** Der Verschlüsselungsalgorithmus. Werte: aes-128; aes-192; aes-256; 3des. Standardwert: aes-128

**-lv:** Der Lebensdauerwert der Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden. Standardwert: 3600 Sekunden.

**-auth:** Der Autorisierungsalgorithmus. Werte: sha1 oder sha256

### cf vpn-create gateway

Erstellt ein VPN-Gateway.

```
cf vpn-create gateway <Gateway-Name> -t <Typ> -gateway_ip <IP-Adresse> -subnets <Teilnetzadresse>
```
#### Parameter
{: #p4}

**-g:**
Der Name des Gateways. 

**-t:** Die Container, für die der Service aktiviert werden soll. Werte: allSingleContainers; allContainerGroups; allContainers. Kein Standardwert; Sie müssen einen Typ angeben.

#####Optionale Parameter:
{: #op4}

**-gateway_ip:**
Die IP-Adresse des Gateways.

**-subnets:**
Die Teilnetzadresse im CIDR-Format.

### cf vpn-show gateways

Zeigt Informationen zu den aktuellen Gateways an.

```
cf vpn-show gateways
```
### cf vpn-show ikes

Zeigt Informationen zu den aktuellen IKE-Verbindungen an.

```
cf vpn-show ikes
```
### cf vpn-show ipsecs

Zeigt Informationen zu den aktuellen IPsec-Verbindungen an.

```
cf vpn-show ipsecs
```
### cf vpn-show connections

Zeigt Informationen zu allen aktuellen Verbindungen an.

```
cf vpn-show connections
```
### cf vpn-show ike

Zeigt Informationen zu einer IKE-Verbindung an.

```
cf vpn-show ike <Richtlinienname>
```
### cf vpn-show ipsec

Zeigt Informationen zu einer IPsec-Verbindung an.

```
cf vpn-show ipsec <Richtlinienname>
```
### cf vpn-show gateway

Zeigt Verbindungsinformationen zu einem Gateway an.

```
cf vpn-show gateway <Gateway-Name>
```
### cf vpn-show connection

Zeigt alle Informationen zu einer bestimmten Verbindung an.

```
cf vpn-show connection <Verbindungsname>
```
### cf vpn-delete

Löscht eine Verbindung, eine Richtlinie oder ein Gateway.

```
cf vpn-delete ike <Richtlinienname>
```

```
cf vpn-delete ipsec <Richtlinienname>
```

```
cf vpn-delete connection <Verbindungsname>
```

```
cf vpn-delete gateway <Gateway-Name>
```


### cf vpn-update connection

Aktualisiert eine vorhandene VPN-Verbindung.

```
cf vpn-update connection <Verbindungsname> -g <Gateway-Name> -cip <IP-Adresse_des_Kundengateways> -subnets ["<Teilnetz/Maske>"] -k <vorab_verteilter_Schlüssel> -d <Beschreibung> -peer_id <Peer-ID> -admin_state <Administrationsstatus> -dpd-action <Aktion> -gateway_ip <IP-Adresse> -i <Initiatorstatus> -dpd-timeout <Wert> -dpd-interval <Wert> -ike <Name> -ipsec <Name>
```
#### Parameter
{: #p5}

**Verbindungsname:**
Der Name der Verbindung.


##### Optionale Parameter:
{: #op5}

**Gateway-Name:**
Der Name des Gateways. 

**IP-Adresse_des_Kundengateways:**
Die IP-Adresse des fernen Endpunkts des VPN-Tunnels. 

**-subnets:**
Die Teilnetzadresse im CIDR-Format.

**-k:**
Der vorab verteilte Schlüssel. 

**-d:** Die Beschreibung der angegebenen Parameter.

**-peer_id:** Die ID des fernen Peers. Der andere Endpunkt des VPN-Tunnels.

**-admin_state:** Der Status der VPN-Verbindung. Werte: UP oder DOWN.

**-dpd-action:** Die auszuführende Aktion, wenn der Peer als inaktiv erkannt wird. Werte: hold; clear; disabled; restart; restart-by-peer. Standardwert: hold

**-gateway_ip:** Die IP-Adresse des lokalen VPN-Tunnelendpunkts.

**-i:** Der Status des Initiators. Standardwert: bi-directional.

**-dpd-timeout:** Der Wert für das Zeitlimit in Sekunden, nach dessen Ablauf die Sitzung beendet wird. Bereich: 6 - 86400 Sekunden. Standardwert: 120 Sekunden

**-dpd-interval:** Das Keepalive-Intervall in Sekunden. Sendet Keepalive-Nachrichten im konfigurierten Intervall, um den Aktivitätszustand des Peers zu prüfen. Bereich: 5-86399 Sekunden. Standardwert: 15 Sekunden.

**-ike:** Der Name der IKE-Richtlinie.

**-ipsec:** Der Name der IPsec-Richtlinie.


### cf vpn-update ike

Aktualisiert eine IKE-Richtlinie.

```
cf vpn-update ike <Richtlinienname> -g <Gateway-Name> -d <Beschreibung> -pfs <Gruppe> -e <Verschlüsselungsalgorithmus> -lv <Lebensdauerwert> -auth <Autorisierungsalgorithmus>
```
#### Parameter
{: #p6}

**Richtlinienname:**
Der Name der IKE-Richtlinie.

##### Optionale Parameter:
{: #op6}

**-g:**
Der Name des Gateways. 

**-d:** Die Beschreibung der angegebenen Parameter.

**-pfs:** Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Werte: Group2; Group5; Group14. Standardwert: Group2

**-e:** Der Verschlüsselungsalgorithmus. Werte: aes-128; aes-192; aes-256; 3des. Standardwert: aes-128

**-lv:** Der Lebensdauerwert der IKE-Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden. Standardwert: 86400 Sekunden.

**-auth:** Der Autorisierungsalgorithmus. Werte: sha1 oder sha256


### cf vpn-update ipsec

Aktualisiert eine IPsec-Richtlinie.

```
cf vpn-update ipsec <Richtlinienname> -g <Gateway-Name> -d <Beschreibung> -pfs <Gruppe> -e <Verschlüsselungsalgorithmus> -lv <Lebensdauerwert> -auth <Autorisierungsalgorithmus>
```
#### Parameter
{: #p7}

**Richtlinienname:**
Der Name der IPsec-Richtlinie.


##### Optionale Parameter:
{: #op7}

**-g:**
Der Name des Gateways. 

**-d:** Die Beschreibung der angegebenen Parameter.

**-pfs:** Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Werte: Group2; Group5; Group14. Standardwert: Group2

**-e:** Der Verschlüsselungsalgorithmus. Werte: aes-128; aes-192; aes-256; 3des. Standardwert: aes-128

**-lv:** Der Lebensdauerwert der Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden. Standardwert: 3600 Sekunden.

**-auth:** Der Autorisierungsalgorithmus. Werte: sha1 oder sha256

### cf vpn-update gateway

Aktualisiert ein vorhandenes VPN-Gateway.

```
cf vpn-update gateway <Gateway-Name> -t <Typ> -gateway_ip <IP-Adresse> -subnets <Teilnetzadresse>
```
#### Parameter
{: #p8}

**Gateway-Name:**
Der Name des Gateways. 

#####Optionale Parameter:
{: #op8}

**-t:** Die Container, für die der Service aktiviert werden soll. Werte: allSingleContainers; allContainerGroups; allContainers. Kein Standardwert; Sie müssen einen Typ angeben.

**-gateway_ip:**
Die IP-Adresse des Gateways.

**-subnets:**
Die Teilnetzadresse im CIDR-Format.

# rellinks
## general
{: #general}
* [IBM VPN-Service](/docs/services/vpn/index.html)
* [Cloud Foundry-Befehlszeilenschnittstelle ![Symbol für externen Link](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}
