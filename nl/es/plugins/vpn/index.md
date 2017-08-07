---

copyright:

  years: 2015, 2017

lastupdated: "2017-01-12"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}


# Plug-in de CLI de VPN para la CLI cf


Puede utilizar la interfaz de línea de mandatos (CLI) para configurar y gestionar su servicio de {{site.data.keyword.vpn_full}}. El plug-in de CLI de {{site.data.keyword.vpn_short}} está disponible en dos versiones: una para su uso con el plug-in de CLI de Cloud Foundry y la otra para su uso con el plug-in de CLI de {{site.data.keyword.Bluemix}}. Ambas versiones del plugin proporcionan las mismas funciones.
{:shortdesc}

El plug-in de {{site.data.keyword.vpn_short}} está disponible para los sistemas operativos Windows, MAC y Linux. Asegúrese de utilizar el aplicable a su caso.

A continuación se muestran instrucciones para trabajar con el plugin de CLI de Cloud Foundry (cf). Para utilizar el plugin con el plugin de CLI de {{site.data.keyword.Bluemix_notm}}, consulte [Plug-in de {{site.data.keyword.vpn_short}} para la CLI de {{site.data.keyword.Bluemix_notm}}](https://console.{DomainName}/docs/cli/plugins/bx_vpn/index.html).

## Instalar el plug-in de CLI cf
Antes de empezar, instale la CLI cf. Consulte [Interfaz de línea de mandatos de Cloud Foundry](https://console.{DomainName}/docs/cli/downloads.html) para obtener detalles.

##Instalar el plug-in de CLI de VPN
**Nota:** si tiene una versión anterior del plug-in de CLI de {{site.data.keyword.vpn_short}} instalada, primero debe desinstalarla. Utilice el mandato:

```
cf uninstall-plugin vpn
```

### Instalar localmente

1. Descargue el plug-in de {{site.data.keyword.vpn_short}} para la plataforma de [IBM Bluemix CLI Plug-in Repository](http://plugins.ng.bluemix.net/ui/repository.html#cf-plugins).
2. Instale el plug-in de {{site.data.keyword.vpn_short}} utilizando el siguiente mandato:
**Nota:** conmute a la ubicación del plug-in de {{site.data.keyword.vpn_short}} o especifique la vía de acceso a la ubicación de plug-in.

	- Para sistemas operativos MS Windows:

	```
	cf install-plugin vpn_windows64.exe
	```

	- Para Apple MAC OS:

	```
	cf install-plugin vpn_mac_os_amd64
	```

	- Para sistemas operativos Linux:

	```
	cf install-plugin vpn_linuxamd64
	```


### Instalar desde el repositorio de Bluemix

1. Añada el repositorio de Bluemix en los repositorios de CLI de Cloud Foundry. Utilice el siguiente mandato:

	```
	cf add-plugin-repo bluemix http://plugins.ng.bluemix.net
	```
2. Ejecute el mandato siguiente:

	```
	cf install-plugin vpn -r bluemix
	```
## Lista de mandatos del servicio IBM VPN

### cf vpn-create connection

Crea una conexión VPN.

```
cf vpn-create connection <nombre de conexión> -g <nombre de pasarela> -k <clave compartida previamente> -subnets ["<subred/máscaras>"] -cip <dirección IP de pasarela de cliente> -d <descripción> -peer_id <ID de igual> -admin_state <estado admin> -dpd-action <acción> -gateway_ip <dirección IP> -i <estado iniciador> -dpd-timeout <valor> -dpd-interval <valor> -ike <nombre> -ipsec <nombre>
```
#### Parámetros
{: #p1}

**nombre de conexión:** nombre de la conexión.

**nombre de pasarela:** nombre de la pasarela.

**-k:** clave compartida previamente.

**subred/máscara:** dirección de subred remota en formato CIDR.

**dirección IP de pasarela de cliente:** dirección IP de punto final remoto del túnel VPN.

##### Parámetros opcionales:
{: #op1}

**-d:** descripción de los parámetros especificados.

**-peer_id:** ID del igual remoto. Otro punto final del túnel VPN.

**-admin_state:** estado de la conexión VPN. Valores: UP o DOWN.

**-dpd-action:** acción a realizar cuando el igual se detecta como inactivo. Valores: hold; clear; disabled; restart; restart-by-peer. Valor predeterminado: hold

**-gateway_ip:** dirección IP del punto final de túnel de VPN local.

**-i:** estado del iniciador. Valor predeterminado: bidireccional.

**-dpd-timeout:** valor de tiempo de espera en segundos tras el cual la sesión se termina.  Rango: 6 - 86400 segundos. Valor predeterminado: 120 segundos. El valor de intervalo de estado activo debe ser superior que el valor de intervalo de estado activo.

**-dpd-interval:** intervalo de estado activo en segundos. Enviar mensajes de estado activo
en el intervalo configurado para comprobar el estado activo del igual. Rango: 5-86399 segundos. Valor predeterminado: 15 segundos.

**-ike:** nombre de la política IKE.

**-ipsec:** nombre de la política IPsec.


### cf vpn-create ike

Crea una política IKE.

```
cf vpn-create ike <nombre de política> -g <nombre de pasarela> -d <descripción> -pfs <grupo> -e <algoritmo de cifrado> -lv <valor de duración> -auth <algoritmo de autorización>
```
#### Parámetros
{: #p2}

**nombre de política:** nombre de la política IKE.

**nombre de pasarela:** nombre de la pasarela.

##### Parámetros opcionales:
{: #op2}

**-d:** descripción de los parámetros especificados.

**-pfs:** identificador de grupo Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor predeterminado: Group2

**-e:** algoritmo de cifrado. Valores: aes-128; aes-192; aes-256; 3des. Valor predeterminado: aes-128

**-lv:** El valor de duración de la asociación de seguridad IKE. Rango: 60 - 86400 segundos. Valor predeterminado: 86400 segundos

**-auth:** algoritmo de autorización. Valores: sha1 o sha256


### cf vpn-create ipsec

Crea una política IPsec.

```
cf vpn-create ipsec <nombre de política> -g <nombre de pasarela> -d <descripción> -pfs <grupo> -e <algoritmo de cifrado> -lv <valor de duración> -auth <algoritmo de autorización>
```
#### Parámetros
{: #p3}

**nombre de política:** nombre de la política IPsec.

**nombre de pasarela:** nombre de la pasarela.

##### Parámetros opcionales:
{: #op3}

**-d:** descripción de los parámetros especificados.

**-pfs:** identificador de grupo Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor predeterminado: Group2

**-e:** algoritmo de cifrado. Valores: aes-128; aes-192; aes-256; 3des. Valor predeterminado: aes-128

**-lv:** El valor de duración de la asociación de seguridad. Rango: 60 - 86400 segundos. Valor predeterminado: 3600 segundos

**-auth:** algoritmo de autorización. Valores: sha1 o sha256

### cf vpn-create gateway

Crea una pasarela VPN.

```
cf vpn-create gateway <nombre de pasarela> -t <tipo> -gateway_ip <dirección IP> -subnets <dirección de subred>
```
#### Parámetros
{: #p4}

**nombre de pasarela:** nombre de la pasarela.

**-t:** los contenedores para los que quiere habilitar el servicio. Valores: allSingleContainers; allContainerGroups; allContainers. Valor predeterminado: ningún valor predeterminado; debe especificar un tipo.

#####Parámetros opcionales:
{: #op4}

**-gateway_ip:** dirección IP de la pasarela.

**-subnets:** dirección de subred en formato CIDR.

### cf vpn-show gateways

Muestra información sobre las pasarelas actuales.

```
cf vpn-show gateways
```
### cf vpn-show ikes

Muestra información sobre las conexiones IKE actuales.

```
cf vpn-show ikes
```
### cf vpn-show ipsecs

Muestra información sobre las conexiones IPsec actuales.

```
cf vpn-show ipsecs
```
### cf vpn-show connections

Muestra información sobre todas las conexiones actuales.

```
cf vpn-show connections
```
### cf vpn-show ike

Muestra información sobre una conexión IKE.

```
cf vpn-show ike <nombre de política>
```
### cf vpn-show ipsec

Muestra información sobre una conexión IPsec.

```
cf vpn-show ipsec <nombre de política>
```
### cf vpn-show gateway

Muestra información de conexión sobre una pasarela.

```
cf vpn-show gateway <nombre de pasarela>
```
### cf vpn-show connection

Muestra toda la información sobre una conexión particular.

```
cf vpn-show connection <nombre de conexión>
```
### cf vpn-delete

Suprime una conexión, política o pasarela existente.

```
cf vpn-delete ike <nombre de política>
```

```
cf vpn-delete ipsec <nombre de política>
```

```
cf vpn-delete connection <nombre de conexión>
```

```
cf vpn-delete gateway <nombre de pasarela>
```


### cf vpn-update connection

Actualiza una conexión VPN existente.

```
cf vpn-update connection <nombre de conexión> -g <nombre de pasarela> -cip <dirección IP de pasarela de cliente> -subnets ["<subred/máscara>"] -k <clave compartida previamente> -d <descripción> -peer_id <ID de igual> -admin_state <estado admin> -dpd-action <acción> -gateway_ip <dirección IP> -i <estado de iniciador> -dpd-timeout <valor> -dpd-interval <valor> -ike <nombre> -ipsec <nombre>
```
#### Parámetros
{: #p5}

**nombre de conexión:** nombre de la conexión.


##### Parámetros opcionales:
{: #op5}

**nombre de pasarela:** nombre de la pasarela.

**dirección IP de pasarela de cliente:** dirección IP de punto final remoto del túnel VPN.

**subred/máscara:** dirección de subred en formato CIDR.

**-k:** clave compartida previamente.

**-d:** descripción de los parámetros especificados.

**-peer_id:** ID del igual remoto. Otro punto final del túnel VPN.

**-admin_state:** estado de la conexión VPN. Valores: UP o DOWN.

**-dpd-action:** acción a realizar cuando el igual se detecta como inactivo. Valores: hold; clear; disabled; restart; restart-by-peer. Valor predeterminado: hold

**-gateway_ip:** dirección IP del punto final de túnel de VPN local.

**-i:** estado del iniciador. Valor predeterminado: bidireccional.

**-dpd-timeout:** valor de tiempo de espera en segundos tras el cual la sesión se termina. Rango: 6 - 86400 segundos. Valor predeterminado: 120 segundos

**-dpd-interval:** intervalo de estado activo en segundos. Enviar mensajes de estado activo
en el intervalo configurado para comprobar el estado activo del igual. Rango: 5-86399 segundos. Valor predeterminado: 15 segundos.

**-ike:** nombre de la política IKE.

**-ipsec:** nombre de la política IPsec.


### cf vpn-update ike

Actualiza una política IKE.

```
cf vpn-update ike <nombre de política> -g <nombre de pasarela> -d <descripción> -pfs <grupo> -e <algoritmo de cifrado> -lv <valor de duración> -auth <algoritmo de autorización>
```
#### Parámetros
{: #p6}

**nombre de política:** nombre de la política IKE.

##### Parámetros opcionales:
{: #op6}

**nombre de pasarela:** nombre de la pasarela.

**-d:** descripción de los parámetros especificados.

**-pfs:** identificador de grupo Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor predeterminado: Group2

**-e:** algoritmo de cifrado. Valores: aes-128; aes-192; aes-256; 3des. Valor predeterminado: aes-128

**-lv:** El valor de duración de la asociación de seguridad IKE. Rango: 60 - 86400 segundos. Valor predeterminado: 86400 segundos

**-auth:** algoritmo de autorización. Valores: sha1 o sha256


### cf vpn-update ipsec

Actualiza una política IPsec.

```
cf vpn-update ipsec <nombre de política> -g <nombre de pasarela> -d <descripción> -pfs <grupo> -e <algoritmo de cifrado> -lv <valor de duración> -auth <algoritmo de autorización>
```
#### Parámetros
{: #p7}

**nombre de política:** nombre de la política IPsec.


##### Parámetros opcionales:
{: #op7}

**nombre de pasarela:** nombre de la pasarela.

**-d:** descripción de los parámetros especificados.

**-pfs:** identificador de grupo Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor predeterminado: Group2

**-e:** algoritmo de cifrado. Valores: aes-128; aes-192; aes-256; 3des. Valor predeterminado: aes-128

**-lv:** El valor de duración de la asociación de seguridad. Rango: 60 - 86400 segundos. Valor predeterminado: 3600 segundos

**-auth:** algoritmo de autorización. Valores: sha1 o sha256

### cf vpn-update gateway

Actualiza una pasarela VPN existente.

```
cf vpn-update gateway <nombre de pasarela> -t <tipo> -gateway_ip <dirección IP> -subnets <dirección de subred>
```
#### Parámetros
{: #p8}

**nombre de pasarela:** nombre de la pasarela.

#####Parámetros opcionales:
{: #op8}

**-t:** los contenedores para los que quiere habilitar el servicio. Valores: allSingleContainers; allContainerGroups; allContainers. Valor predeterminado: ningún valor predeterminado; debe especificar un tipo.

**-gateway_ip:** dirección IP de la pasarela.

**-subnets:** dirección de subred en formato CIDR.

# rellinks
## general
{: #general}
* [Servicio IBM VPN](/docs/services/vpn/index.html)
* [CLI de Cloud Foundry ![icono de enlace externo](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}
