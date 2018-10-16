---

copyright:

  years: 2015, 2017

lastupdated: "2018-10-04"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}


# Plug-in da CLI da VPN para a CLI do cf
{: #vpn_cli_for_cf}


É possível usar a interface da linha de comandos (CLI) para configurar e gerenciar o seu serviço do {{site.data.keyword.vpn_full}}. O plug-in da CLI do {{site.data.keyword.vpn_short}}
está disponível em duas versões: uma para uso com o plug-in da CLI do Cloud Foundry e a outra para uso com o plug-in da CLI do {{site.data.keyword.Bluemix}}. Ambas as versões do plug-in fornecem a
mesma funcionalidade.
{:shortdesc}

O plug-in do {{site.data.keyword.vpn_short}} está disponível para sistemas operacionais Windows, MAC e Linux. Assegure-se de usar aquele que for aplicável a você.

As instruções a seguir são para trabalhar com o plug-in da CLI do Cloud Foundry (cf). Para usar o plug-in com o plug-in da CLI do {{site.data.keyword.Bluemix_notm}}, consulte Plug-in do [{{site.data.keyword.vpn_short}} para CLI do {{site.data.keyword.Bluemix_notm}} ![Ícone de link externo](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/plugins/bx_vpn/index.html){: new_window}.

## Instalar o plug-in da CLI do cf
Antes de iniciar, instale o cf CLI. Consulte Interface da linha de comandos do [Cloud Foundry ![Ícone de link externo](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window} para obter detalhes.

## Instalar o plug-in da CLI da VPN
**Nota:** se você tiver uma versão anterior do plug-in {{site.data.keyword.vpn_short}} CLI que está instalado, ela deverá ser desinstalada primeiro. Utilize o comando:

```
cf uninstall-plugin vpn
```

### Instalar localmente

1. Faça download do plug-in do {{site.data.keyword.vpn_short}} para a sua plataforma no
[Repositório de plug-ins da CLI do {{site.data.keyword.Bluemix_notm}}
![Ícone de link externo](../../../icons/launch-glyph.svg)](http://plugins.ng.bluemix.net/ui/repository.html#cf-plugins){: new_window}.
2. Instale o plug-in {{site.data.keyword.vpn_short}} usando o comando a seguir:
**Nota:** alterne para o local do plug-in {{site.data.keyword.vpn_short}} ou especifique o caminho para o local do plug-in.

	- Para o OS MS Windows:

	```
	cf install-plugin vpn_windows64.exe
	```

	- Para o Apple MAC OS:

	```
	cf install-plugin vpn_mac_os_amd64
	```

	- Para o sistema operacional Linux:

	```
	cf install-plugin vpn_linuxamd64
	```


### Instale por meio do repositório do {{site.data.keyword.Bluemix_notm}}

1. Inclua o repositório do {{site.data.keyword.Bluemix_notm}} nos repositórios do Cloud Foundry CLI. Utilize o seguinte comando:

	```
	cf add-plugin-repo IBm Cloud http://plugins.ng.bluemix.net
	```
2. Execute o seguinte comando:

	```
	cf install-plugin vpn -r IBM Cloud
	```
##Lista de comandos de serviço da VPN

### cf vpn-create connection

Cria uma conexão VPN.

```
cf vpn-create connection <connection name> -g <gateway name> -k <preshared key> -subnets ["<subnet/mask>"] -cip <customer gateway IP address> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```
#### Parâmetros
{: #p1}

**connection name:**
nome da conexão.

**gateway name:** Nome do gateway.

**-k:**
chave pré-compartilhada.

**subnet/mask:**
endereço de sub-rede remoto no formato CIDR.

**customer gateway IP address:**
endereço IP do terminal remoto do túnel VPN.

##### Parâmetros opcionais:
{: #op1}

**-d:** Descrição dos parâmetros especificados.

**-peer_id:** ID do peer remoto. Outro terminal do túnel da VPN.

**-admin_state:** Status da conexão VPN. Valores: UP ou DOWN.

**-dpd-action:** Ação a ser tomada quando o peer for detectado como inativo. Valores: hold; clear; disabled; restart; restart-by-peer. Valor padrão: hold

**-gateway_ip:** Endereço IP do terminal de túnel VPN local.

**-i:** Estado do inicializador. Valor padrão: bi-directional.

**-dpd-timeout:** valor do tempo limite em segundos após o qual a sessão é finalizada. Intervalo: 6 a 86400 segundos. Valor padrão: 120 segundos. O valor do tempo limite keep-alive deve ser maior que o valor do intervalo keep-alive.

**-dpd-interval:** Intervalo keep-alive em segundos. Envie mensagens keep-alive no intervalo configurado para verificar se o peer está ativo. Intervalo: 5 a 86399 segundos. Valor padrão: 15 segundos

**-ike:** Nome da política IKE.

**-ipsec:** Nome da política IPSec.


### cf vpn-create ike

Cria uma política IKE.

```
cf vpn-create ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Parâmetros
{: #p2}

**policy name:**
nome da política IKE.

**gateway name:** Nome do gateway.

##### Parâmetros opcionais:
{: #op2}

**-d:** Descrição dos parâmetros especificados.

**-pfs:** Identificador de grupo do Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor padrão: Group2

**-e:** Algoritmo de criptografia. Valores: aes-128; aes-192; aes-256; 3des. Valor padrão: aes-128

**-lv:** Valor de tempo de vida da associação de segurança do IKE. Intervalo: 60 a 86400 segundos. Valor padrão: 86400 segundos

**-auth:** algoritmo de autorização. Valores: sha1 ou sha256


### cf vpn-create ipsec

Cria uma política IPSec.

```
cf vpn-create ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Parâmetros
{: #p3}

**policy name:** nome da política Internet Protocol Security.

**gateway name:** Nome do gateway.

##### Parâmetros opcionais:
{: #op3}

**-d:** Descrição dos parâmetros especificados.

**-pfs:** Identificador de grupo do Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor padrão: Group2

**-e:** Algoritmo de criptografia. Valores: aes-128; aes-192; aes-256; 3des. Valor padrão: aes-128

**-lv:** Valor de tempo de vida da associação de segurança. Intervalo: 60 a 86400 segundos. Valor padrão: 3600 segundos

**-auth:** algoritmo de autorização. Valores: sha1 ou sha256

### cf vpn-create gateway

Cria um gateway VPN.

```
cf vpn-create gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### Parâmetros
{: #p4}

**gateway name:** Nome do gateway.

**-t:** Contêineres para os quais você deseja ativar o serviço. Valores: allSingleContainers; allContainerGroups; allContainers. Valor padrão: nenhum valor padrão; deve-se especificar um tipo.

#####Parâmetros opcionais:
{: #op4}

**-gateway_ip:**
endereço IP do gateway.

**-subnets:**
endereço de sub-rede no formato CIDR.

### cf vpn-show gateways

Exibe informações sobre os gateways atuais.

```
cf vpn-show gateways
```
### cf vpn-show ikes

Exibe informações sobre as conexões IKE atuais.

```
cf vpn-show ikes
```
### cf vpn-show ipsecs

Exibe informações sobre as conexões IPSec atuais.

```
cf vpn-show ipsecs
```
### cf vpn-show connections

Exibe informações sobre todas as conexões atuais.

```
cf vpn-show connections
```
### cf vpn-show ike

Exibe informações sobre uma conexão IKE.

```
cf vpn-show ike <policy name>
```
### cf vpn-show ipsec

Exibe informações sobre uma conexão IPSec.

```
cf vpn-show ipsec <policy name>
```
### cf vpn-show gateway

Exibe informações de conexão de um gateway.

```
cf vpn-show gateway <gateway name>
```
### cf vpn-show connection

Exibe todas as informações sobre uma determinada conexão.

```
cf vpn-show connection <connection name>
```
### cf vpn-delete

Exclui uma conexão, política ou gateway existente.

```
cf vpn-delete ike <policy name>
```

```
cf vpn-delete ipsec <policy name>
```

```
cf vpn-delete connection <connection name>
```

```
cf vpn-delete gateway <gateway name>
```


### cf vpn-update connection

Atualiza uma conexão VPN existente.

```
cf vpn-update connection <connection name> -g <gateway name> -cip <customer gateway IP address> -subnets ["<subnet/mask>"] -k <preshared key> -d <description> -peer_id <peer ID> -admin_state <admin state> -dpd-action <action> -gateway_ip <IP address> -i <initiator state> -dpd-timeout <value> -dpd-interval <value> -ike <name> -ipsec <name>
```
#### Parâmetros
{: #p5}

**connection name:**
nome da conexão.


##### Parâmetros opcionais:
{: #op5}

**gateway name:** Nome do gateway.

**customer gateway IP address:**
endereço IP do terminal remoto do túnel VPN.

**subnet/mask:**
endereço de sub-rede no formato CIDR.

**-k:**
chave pré-compartilhada.

**-d:** Descrição dos parâmetros especificados.

**-peer_id:** ID do peer remoto. Outro terminal do túnel da VPN.

**-admin_state:** Status da conexão VPN. Valores: UP ou DOWN.

**-dpd-action:** Ação a ser tomada quando o peer for detectado como inativo. Valores: hold; clear; disabled; restart; restart-by-peer. Valor padrão: hold

**-gateway_ip:** Endereço IP do terminal de túnel VPN local.

**-i:** Estado do inicializador. Valor padrão: bi-directional.

**-dpd-timeout:** valor do tempo limite em segundos após o qual a sessão é finalizada. Intervalo: 6 a 86400 segundos. Valor padrão:
120 segundos

**-dpd-interval:** Intervalo keep-alive em segundos. Envie mensagens keep-alive no intervalo configurado para verificar se o peer está ativo. Intervalo: 5 a 86399 segundos. Valor padrão: 15 segundos

**-ike:** Nome da política IKE.

**-ipsec:** Nome da política IPSec.


### cf vpn-update ike

Atualiza uma política IKE.

```
cf vpn-update ike <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Parâmetros
{: #p6}

**policy name:**
nome da política IKE.

##### Parâmetros opcionais:
{: #op6}

**gateway name:** Nome do gateway.

**-d:** Descrição dos parâmetros especificados.

**-pfs:** Identificador de grupo do Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor padrão: Group2

**-e:** Algoritmo de criptografia. Valores: aes-128; aes-192; aes-256; 3des. Valor padrão: aes-128

**-lv:** Valor de tempo de vida da associação de segurança do IKE. Intervalo: 60 a 86400 segundos. Valor padrão: 86400 segundos

**-auth:** algoritmo de autorização. Valores: sha1 ou sha256


### cf vpn-update ipsec

Atualiza uma política IPSec.

```
cf vpn-update ipsec <policy name> -g <gateway name> -d <description> -pfs <group> -e <encryption algorithm> -lv <lifetime value> -auth <authorization algorithm>
```
#### Parâmetros
{: #p7}

**policy name:** nome da política Internet Protocol Security.


##### Parâmetros opcionais:
{: #op7}

**gateway name:** Nome do gateway.

**-d:** Descrição dos parâmetros especificados.

**-pfs:** Identificador de grupo do Diffie-Hellman (DH). Valores: Group2; Group5; Group14. Valor padrão: Group2

**-e:** Algoritmo de criptografia. Valores: aes-128; aes-192; aes-256; 3des. Valor padrão: aes-128

**-lv:** Valor de tempo de vida da associação de segurança. Intervalo: 60 a 86400 segundos. Valor padrão: 3600 segundos

**-auth:** algoritmo de autorização. Valores: sha1 ou sha256

### cf vpn-update gateway

Atualiza um gateway VPN existente.

```
cf vpn-update gateway <gateway name> -t <type> -gateway_ip <IP address> -subnets <subnet address>
```
#### Parâmetros
{: #p8}

**gateway name:** Nome do gateway.

#####Parâmetros opcionais:
{: #op8}

**-t:** Contêineres para os quais você deseja ativar o serviço. Valores: allSingleContainers; allContainerGroups; allContainers. Valor padrão: nenhum valor padrão; deve-se especificar um tipo.

**-gateway_ip:**
endereço IP do gateway.

**-subnets:**
endereço de sub-rede no formato CIDR.

# rellinks
## general
{: #general}
* [Serviço IBM VPN](/docs/services/vpn/index.html)
* [CLI do Cloud Foundry ![Ícone de link externo](../../../icons/launch-glyph.svg)](https://console.{DomainName}/docs/cli/downloads.html){: new_window}
