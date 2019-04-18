---



copyright:

  years: 2015，2018

lastupdated: "2018-06-21"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# VPN-Plug-in für {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle

*Version:* 1.4.0

Sie können den {{site.data.keyword.vpn_full}}-Service mit der Befehlszeilenschnittstelle konfigurieren und verwalten. Das CLI-Plug-in für VPN ist in zwei Versionen verfügbar: für die Verwendung mit dem Plug-in für die Cloud Foundry-Befehlszeilenschnittstelle und für die Verwendung mit dem Plug-in für die {{site.data.keyword.Bluemix}}-Befehlszeilenschnittstelle. Von beiden Versionen des Plug-ins werden dieselben Funktionen bereitgestellt.
{:shortdesc}

Das VPN-Plug-in ist für Windows-, MAC- und Linux-Betriebssysteme verfügbar. Stellen Sie sicher, dass Sie das für Sie geeignete Plug-in verwenden.

Die nachfolgenden Anweisungen sind für das Plug-in für die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle vorgesehen. Informationen zur Verwendung des Plug-ins mit der Plug-in für die Cloud Foundry-Befehlszeilenschnittstelle (cf) finden Sie unter [VPN-CLI-Plug-in für cf-Befehlszeilenschnittstelle](../vpn/index.html).


In der nachfolgenden Liste werden alle vom VPN-Plug-in für die {{site.data.keyword.Bluemix_notm}}-Befehlszeilenschnittstelle unterstützten Befehle mit Namen, Optionen, Verwendungen, Voraussetzungen, Beschreibungen und Beispielen aufgeführt. Informationen zum Installieren des VPN-Plug-ins finden Sie unter [IBM Cloud-Befehlszeilenschnittstelle erweitern](../../index.html#cli_bluemix_ext).

**Hinweis:** Unter *Voraussetzungen* wird aufgelistet, welche Aktionen vor der Verwendung des Befehls ausgeführt werden müssen. Zu den Voraussetzungen könnten eine oder mehrere der folgenden Aktionen gehören:
<dl>
<dt>**Endpunkt**</dt>
<dd>Vor der Verwendung des Befehls muss mittels `ibmcloud api` ein API-Endpunkt festgelegt werden.</dd>
<dt>**Anmeldung**</dt>
<dd>Vor der Verwendung dieses Befehls ist die Anmeldung über den Befehl `ibmcloud login` erforderlich.</dd>
<dt>**Ziel**</dt>
<dd>Vor der Verwendung dieses Befehls muss der Befehl `ibmcloud target` zum Festlegen einer Organisation oder eines Bereichs verwendet werden.</dd>
</dl>


## ibmcloud vpn connection-create
Erstellt eine VPN-Verbindung.

```
ibmcloud vpn connection-create CONNECTION_NAME -g GATEWAY_NAME -k PRESHARED_KEY -subnets "SUBNET/MASK" -cip CUSTOMER_GATEWAY_IP_ADDRESS [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state ADMIN_STATE] [-dpd-action ACTION] [-gateway_ip IP_ADDRESS] [-i INITIATOR_STATE] [-dpd-timeout VALUE] [-dpd-interval VALUE] [-ike NAME] [-ipsec NAME]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*CONNECTION_NAME* (erforderlich): Der Name der Verbindung.

-g *GATEWAY_NAME* (erforderlich): Der Name des Gateways.

-k *PRESHARED_KEY* (erforderlich): Der vorab verteilte Schlüssel.

-subnets "*SUBNET*/*MASK*" (erforderlich): Die Adresse des fernen Teilnetzes im CIDR-Format.

-cip *CUSTOMER_GATEWAY_IP_ADDRESS* (erforderlich): Die IP-Adresse des fernen Endpunkts des VPN-Tunnels.

-d *DESCRIPTION* (optional): Die Beschreibung der angegebenen Parameter.

-peer_id *PEER_ID* (optional): Die ID des fernen Peers. Der andere Endpunkt des VPN-Tunnels.

-admin_state *ADMIN_STATE* (optional): Der Status der VPN-Verbindung. Gültige Werte: `UP` oder `DOWN`.

-dpd-action *ACTION* (optional): Die auszuführende Aktion, wenn der Peer als inaktiv erkannt wird. Gültige Werte: `hold`, `clear`, `disabled`, `restart` oder `restart-by-peer`. Standardwert: `hold`.

-gateway_ip *IP_ADDRESS* (optional): Die IP-Adresse des lokalen VPN-Tunnelendpunkts.

-i *INITIATOR_STATE* (optional): Der Status des Initiators. Standardwert: `bi-directional`.

-dpd-timeout *VALUE*  (optional): Der Wert für das Zeitlimit in Sekunden, nach dessen Ablauf die Sitzung beendet wird. Bereich: 6 - 86400 Sekunden. Standardwert: `120` Sekunden.

-dpd-interval *VALUE* (optional): Das Keepalive-Intervall in Sekunden. Sendet Keepalive-Nachrichten im konfigurierten Intervall, um den Aktivitätszustand des Peers zu prüfen. Bereich: 5-86399 Sekunden. Standardwert: `15` Sekunden.

-ike *NAME* (optional): Der Name der IKE-Richtlinie.

-ipsec *NAME* (optional): Der Name der IPSec-Richtlinie.

**Beispiele**:

Neue VPN-Verbindung mit dem Namen `my_connection` erstellen:
```
ibmcloud vpn connection-create my_connection -g my_gateway -k 123456 -subnets "192.168.10.0/24" -cip 162.135.1.1
```


## ibmcloud vpn ike-create
Erstellt eine IKE-Richtlinie.

```
ibmcloud vpn ike-create POLICY_NAME -g GATEWAY_NAME [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der IKE-Richtlinie.

-g *GATEWAY_NAME* (erforderlich): Der Name des Gateways.

-d *DESCRIPTION* (optional): Die Beschreibung der angegebenen Parameter.

-pfs *GROUP* (optional): Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Gültige Werte: `Group2`, `Group5` oder `Group14`. Standardwert: `Group2`.

-e *ENCRYPTION_ALGORITHM* (optional): Der Verschlüsselungsalgorithmus. Gültige Werte: `aes-128`, `aes-192`, `aes-256` oder `3des`. Standardwert: `aes-128`.

-lv *LIFETIME_VALUE* (optional): Der Lebensdauerwert der IKE-Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden. Standardwert: `86400` Sekunden.

**Beispiele**:

Neue IKE-Richtlinie mit dem Namen `my_ike` erstellen:
```
ibmcloud vpn ike-create my_ike -g my_gateway
```


## ibmcloud vpn ipsec-create
Erstellt eine IPSec-Richtlinie.

```
ibmcloud vpn ipsec-create POLICY_NAME -g GATEWAY_NAME [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der IPSec-Richtlinie.

-g *GATEWAY_NAME* (erforderlich): Der Name des Gateways.

-d *DESCRIPTION* (optional): Die Beschreibung der angegebenen Parameter.

-pfs *GROUP* (optional): Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Gültige Werte: `Group2`, `Group5` oder `Group14`. Standardwert: `Group2`.

-e *ENCRYPTION_ALGORITHM* (optional): Der Verschlüsselungsalgorithmus. Gültige Werte: `aes-128`, `aes-192`, `aes-256` oder `3des`. Standardwert: `aes-128`.

-lv *LIFETIME_VALUE* (optional): Der Lebensdauerwert der Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden. Standardwert: `3600` Sekunden.

**Beispiele**:

IPSec-Richtlinie mit dem Namen `my_policy` erstellen:
```
ibmcloud vpn ipsec-create my_policy -g my_gateway
```


## ibmcloud vpn gateway-create
Erstellt ein VPN-Gateway.

```
ibmcloud vpn gateway-create GATEWAY_NAME -t TYPE [-gateway_ip IP_ADDRESS] [-subnets SUBNET_ADDRESS]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*GATEWAY_NAME* (erforderlich): Der Name des Gateways.

-t *TYPE* (erforderlich): Die Container, für die der Service aktiviert werden soll. Gültige Werte: `allSingleContainers`, `allContainerGroups` oder `allContainers`. Kein Standardwert; Sie müssen einen Typ angeben.

-gateway_ip *IP_ADDRESS* (optional): Die IP-Adresse des Gateways.

-subnets *SUBNET_ADDRESS* (optional): Die Teilnetzadresse im CIDR-Format.

**Beispiele**:

Gateway mit dem Namen `my_gateway` und dem Typ `allContainerGroups` erstellen:
```
ibmcloud vpn gateway-create my_gateway -t allContainerGroups
```


## ibmcloud vpn connections
Zeigt Informationen zu allen aktuellen Verbindungen an.

```
ibmcloud vpn connections
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel


## ibmcloud vpn ikes
Zeigt Informationen zu den aktuellen IKE-Verbindungen an.

```
ibmcloud vpn ikes
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel


## ibmcloud vpn ipsecs
Zeigt Informationen zu den aktuellen IPSec-Verbindungen an.

```
ibmcloud vpn ipsecs
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel


## ibmcloud vpn gateways
Zeigt Informationen zu den aktuellen Gateways an.

```
ibmcloud vpn gateways
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel


## ibmcloud vpn connection
Zeigt alle Informationen zu einer bestimmten Verbindung an.

```
ibmcloud vpn connection CONNECTION_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*CONNECTION_NAME* (erforderlich): Der Name der anzuzeigenden Verbindung.


## ibmcloud vpn ike
Zeigt Informationen zu einer IKE-Verbindung an.

```
ibmcloud vpn ike POLICY_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der anzuzeigenden IKE-Richtlinie.


## ibmcloud vpn ipsec
Zeigt Informationen zu einer IPSec-Verbindung an.

```
ibmcloud vpn ipsec POLICY_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der anzuzeigenden IPSec-Richtlinie.


## ibmcloud vpn gateway
Zeigt Verbindungsinformationen zu einem Gateway an.

```
ibmcloud vpn gateway GATEWAY_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*GATEWAY_NAME* (erforderlich): Der Name des anzuzeigenden Gateways.


## ibmcloud vpn connection-delete
Löscht eine vorhandene Verbindung.

```
ibmcloud vpn connection-delete CONNECTION_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*CONNECTION_NAME* (erforderlich): Der Name der zu löschenden Verbindung.


## ibmcloud vpn ike-delete
Löscht eine vorhandene IKE-Richtlinie.

```
ibmcloud vpn ike-delete POLICY_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der zu löschenden IKE-Richtlinie.


## ibmcloud vpn ipsec-delete
Löscht eine vorhandene IPSec-Richtlinie.

```
ibmcloud vpn ipsec-delete POLICY_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der zu löschenden IPSec-Richtlinie.


## ibmcloud vpn gateway-delete
Löscht ein vorhandenes Gateway.

```
ibmcloud vpn gateway-delete GATEWAY_NAME
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*GATEWAY_NAME* Der Name des zu löschenden Gateways.


## ibmcloud vpn connection-update
Aktualisiert eine vorhandene VPN-Verbindung.

```
ibmcloud vpn connection-update CONNECTION_NAME [-g GATEWAY_NAME] [-k PRESHARED_KEY] [-subnets "SUBNET/MASK"] [-cip CUSTOMER_GATEWAY_IP_ADDRESS] [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state ADMIN_STATE] [-dpd-action ACTION] [-gateway_ip IP_ADDRESS] [-i INITIATOR_STATE] [-dpd-timeout VALUE] [-dpd-interval VALUE] [-ike NAME] [-ipsec NAME]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*CONNECTION_NAME* (erforderlich): Der Name der Verbindung.

-g *GATEWAY_NAME* (optional): Der Name des Gateways.

-k *PRESHARED_KEY* (optional): Der vorab verteilte Schlüssel.

-subnets "*SUBNET*/*MASK*" (optional): Die Teilnetzadresse im CIDR-Format.

-cip *CUSTOMER_GATEWAY_IP_ADDRESS* (optional): Die IP-Adresse des fernen Endpunkts des VPN-Tunnels.

-d *DESCRIPTION* (optional): Die Beschreibung der angegebenen Parameter.

-peer_id *PEER_ID* (optional): Die ID des fernen Peers. Der andere Endpunkt des VPN-Tunnels.

-admin_state *ADMIN_STATE* (optional): Der Status der VPN-Verbindung. Gültige Werte: `UP` oder `DOWN`.

-dpd-action *ACTION* (optional): Die auszuführende Aktion, wenn der Peer als inaktiv erkannt wird. Gültige Werte: `hold`, `clear`, `disabled`, `restart` oder `restart-by-peer`.

-gateway_ip *IP_ADDRESS* (optional): Die IP-Adresse des lokalen VPN-Tunnelendpunkts.

-i *INITIATOR_STATE* (optional): Der Status des Initiators.

-dpd-timeout *VALUE*  (optional): Der Wert für das Zeitlimit in Sekunden, nach dessen Ablauf die Sitzung beendet wird. Bereich: 6 - 86400 Sekunden.

-dpd-interval *VALUE* (optional): Das Keepalive-Intervall in Sekunden. Sendet Keepalive-Nachrichten im konfigurierten Intervall, um den Aktivitätszustand des Peers zu prüfen. Bereich: 5-86399 Sekunden.

-ike *NAME* (optional): Der Name der IKE-Richtlinie.

-ipsec *NAME* (optional): Der Name der IPSec-Richtlinie.


## ibmcloud vpn ike-update
Aktualisiert eine IKE-Richtlinie.

```
ibmcloud vpn ike-update POLICY_NAME [-g GATEWAY_NAME] [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der IKE-Richtlinie.

-g *GATEWAY_NAME* (optional): Der Name des Gateways.

-d *DESCRIPTION* (optional): Die Beschreibung der angegebenen Parameter.

-pfs *GROUP* (optional): Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Gültige Werte: `Group2`, `Group5` oder `Group14`.

-e *ENCRYPTION_ALGORITHM* (optional): Der Verschlüsselungsalgorithmus. Gültige Werte: `aes-128`, `aes-192`, `aes-256` oder `3des`.

-lv *LIFETIME_VALUE* (optional): Der Lebensdauerwert der IKE-Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden.


## ibmcloud vpn ipsec-update
Aktualisiert eine IPSec-Richtlinie.

```
ibmcloud vpn ipsec-update POLICY_NAME [-g GATEWAY_NAME] [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*POLICY_NAME* (erforderlich): Der Name der IPSec-Richtlinie.

-g *GATEWAY_NAME* (optional): Der Name des Gateways.

-d *DESCRIPTION* (optional): Die Beschreibung der angegebenen Parameter.

-pfs *GROUP* (optional): Die Diffie-Hellman-Gruppen-ID (DH-Gruppen-ID). Gültige Werte: `Group2`, `Group5` oder `Group14`.

-e *ENCRYPTION_ALGORITHM* (optional): Der Verschlüsselungsalgorithmus. Gültige Werte: `aes-128`, `aes-192`, `aes-256` oder `3des`.

-lv *LIFETIME_VALUE* (optional): Der Lebensdauerwert der Sicherheitszuordnung. Bereich: 60 - 86400 Sekunden.


## ibmcloud vpn gateway-update
Aktualisiert ein vorhandenes VPN-Gateway.

```
ibmcloud vpn gateway-update GATEWAY_NAME [-t TYPE] [-gateway_ip IP_ADDRESS] [-subnets SUBNET_ADDRESS]
```

**Voraussetzungen**:  Endpunkt, Anmeldung, Ziel

**Befehlsoptionen**:

*GATEWAY_NAME* (erforderlich): Der Name des Gateways.

-t *TYPE* (optional): Die Container, für die der Service aktiviert werden soll. Gültige Werte: `allSingleContainers`, `allContainerGroups` oder `allContainers`.

-gateway_ip *IP_ADDRESS* (optional): Die IP-Adresse des Gateways.

-subnets *SUBNET_ADDRESS* (optional): Die Teilnetzadresse im CIDR-Format.
