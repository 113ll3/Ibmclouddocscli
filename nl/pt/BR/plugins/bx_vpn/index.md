---



copyright:

  years: 2015，2018

lastupdated: "2018-06-21"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Plug-in da VPN para a CLI do {{site.data.keyword.Bluemix_notm}}

*Versão:* 1.4.0

É possível usar a interface da linha de comandos (CLI) para configurar e gerenciar o seu serviço do {{site.data.keyword.vpn_full}}. O plug-in da CLI do VPN está disponível em duas versões: uma para uso com o plug-in da CLI do Cloud Foundry e a outra para uso com o plug-in da CLI do {{site.data.keyword.Bluemix}}. Ambas as versões do plug-in fornecem a
mesma funcionalidade.
{:shortdesc}

O plug-in do VPN está disponível para os sistemas operacionais Windows, MAC e Linux. Assegure-se de usar aquele que for aplicável a você.

As instruções a seguir são para trabalhar com o plug-in da CLI do {{site.data.keyword.Bluemix_notm}}. Para usar o plug-in com o plug-in da CLI do Cloud Foundry (cf), veja [Plug-in da CLI do VPN para a CLI cf](../vpn/index.html).


As informações a seguir listam todos os comandos que são suportados pelo plug-in VPN para
a CLI do {{site.data.keyword.Bluemix_notm}} e incluem seus nomes, opções, uso, pré-requisitos,
descrições e exemplos. Consulte [Estender a sua interface da linha de comandos do
IBM Cloud](../../index.html#cli_bluemix_ext) sobre como instalar o plug-in da VPN.

**Nota:** *Pré-requisitos* listam quais ações são necessárias antes de usar o comando. Os pré-requisitos podem incluir uma ou mais das ações a seguir:
<dl>
<dt>**      Nó de Extremidade
**</dt>
<dd>Um terminal de API deve ser configurado por meio de `ibmcloud api` antes de usar o comando.</dd>
<dt>**Login**</dt>
<dd>O login usando o comando `ibmcloud login` é necessário antes de usar esse comando.</dd>
<dt>**Destino **</dt>
<dd>O comando `ibmcloud target` deve ser usado para configurar uma organização e um espaço antes de usar esse comando.</dd>
</dl>


## Criar conexão vpn ibmcloud
Cria uma conexão VPN.

```
ibmcloud vpn connection-create CONNECTION_NAME -g GATEWAY_NAME -k PRESHARED_KEY -subnets "SUBNET/MASK" -cip CUSTOMER_GATEWAY_IP_ADDRESS [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state ADMIN_STATE] [-dpd-action ACTION] [-gateway_ip IP_ADDRESS] [-i INITIATOR_STATE] [-dpd-timeout VALUE] [-dpd-interval VALUE] [-ike NAME] [-ipsec NAME]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*CONNECTION_NAME* (obrigatório): nome da conexão.

-g *GATEWAY_NAME* (obrigatório): nome do gateway.

-k *PRESHARED_KEY* (obrigatório): chave pré-compartilhada.

-subnets "*SUBNET*/*MASK*" (obrigatório): endereço de sub-rede remota no formato CIDR.

-cip *CUSTOMER_GATEWAY_IP_ADDRESS* (obrigatório): endereço IP do terminal remoto do túnel da VPN.

-d *DESCRIPTION* (opcional): descrição dos parâmetros especificados.

-peer_id *PEER_ID* (opcional): ID do peer remoto. Outro terminal do túnel da VPN.

-admin_state *ADMIN_STATE* (opcional): status da conexão VPN. Um valor válido é `UP` ou `DOWN`.

-dpd-action *ACTION* (opcional): ação a ser executada quando o peer for detectado como inativo. Um valor válido é `hold`, `clear`, `disabled`, `restart` ou `restart-by-peer`. O valor padrão é `hold`.

-gateway_ip *IP_ADDRESS* (opcional): endereço IP do terminal de túnel da VPN local.

-i *INITIATOR_STATE* (opcional): estado do iniciador. O valor padrão é `bi-directional`.

-dpd-timeout *VALUE* (opcional): valor do tempo limite em segundos após o qual a sessão é finalizada. Intervalo: 6 a 86400 segundos. O valor padrão é `120` segundos.

-dpd-interval *VALUE* (opcional): intervalo keep-alive em segundos. Envie mensagens keep-alive no intervalo configurado para verificar se o peer está ativo. Intervalo: 5 a 86399 segundos. O valor padrão é `15` segundos.

-ike *NAME* (opcional): nome da política IKE.

-ipsec *NAME* (opcional): nome da política IPSec.

**Exemplos**:

Crie uma nova conexão vpn com o nome `my_connection`:
```
ibmcloud vpn connection-create my_connection -g my_gateway -k 123456 -subnets "192.168.10.0/24" -cip 162.135.1.1
```


## Create-ike vpn ibmcloud
Cria uma política IKE.

```
ibmcloud vpn ike-create POLICY_NAME -g GATEWAY_NAME [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IKE.

-g *GATEWAY_NAME* (obrigatório): nome do gateway.

-d *DESCRIPTION* (opcional): descrição dos parâmetros especificados.

-pfs *GROUP* (opcional): identificador de grupo Diffie-Hellman (DH). Um valor válido é `Group2`, `Group5` ou `Group14`. O valor padrão é `Group2`.

-e *ENCRYPTION_ALGORITHM* (opcional): algoritmo de criptografia. Um valor válido é `aes-128`, `aes-192`, `aes-256` ou `3des`. O valor padrão é `aes-128`.

-lv *LIFETIME_VALUE* (opcional): valor de tempo de vida da associação de segurança IKE. Intervalo: 60 a 86400 segundos. O valor padrão é `86400` segundos.

**Exemplos**:

Crie uma nova política IKE com o nome `my_ike`:
```
Ibmcloud vpn ike-create my_ike -g my_gateway
```


## Create-ibmcloud vpn ipsec
Cria uma política IPSec.

```
ibmcloud vpn ipsec-create POLICY_NAME -g GATEWAY_NAME [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IPSec.

-g *GATEWAY_NAME* (obrigatório): nome do gateway.

-d *DESCRIPTION* (opcional): descrição dos parâmetros especificados.

-pfs *GROUP* (opcional): identificador de grupo Diffie-Hellman (DH). Um valor válido é `Group2`, `Group5` ou `Group14`. O valor padrão é `Group2`.

-e *ENCRYPTION_ALGORITHM* (opcional): algoritmo de criptografia. Um valor válido é `aes-128`, `aes-192`, `aes-256` ou `3des`. O valor padrão é `aes-128`.

-lv *LIFETIME_VALUE* (opcional): valor de tempo de vida da associação de segurança. Intervalo: 60 a 86400 segundos. O valor padrão é `3600` segundos.

**Exemplos**:

Criar uma política IPSec com o nome `my_policy`:
```
Ibmcloud vpn ipsec-create my_policy -g my_gateway
```


## ibmcloud vpn gateway-create
Cria um gateway VPN.

```
ibmcloud vpn gateway-create GATEWAY_NAME -t TYPE [-gateway_ip IP_ADDRESS] [-subnets SUBNET_ADDRESS]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*GATEWAY_NAME* (obrigatório): nome do gateway.

-t *TYPE* (obrigatório): contêineres para os quais deseja ativar o serviço. Um valor válido é `allSingleContainers`, `allContainerGroups` ou `allContainers`. Nenhum valor padrão; deve-se especificar um tipo.

-gateway_ip *IP_ADDRESS* (opcional): endereço IP do gateway.

-subnets *SUBNET_ADDRESS* (opcional): endereço de sub-rede no formato CIDR.

**Exemplos**:

Crie um gateway com o nome `my_gateway` e digite `allContainerGroups`:
```
Ibmcloud vpn gateway-create my_gateway -t allContainerGroups
```


## ibmcloud vpn connections
Exibe informações sobre todas as conexões atuais.

```
ibmcloud vpn connections
```

**Pré-requisitos**: Terminal, Login, Destino


## ibmcloud vpn ikes
Exibe informações sobre as conexões IKE atuais.

```
ibmcloud vpn ikes
```

**Pré-requisitos**: Terminal, Login, Destino


## ibmcloud vpn ipsecs
Exibe informações sobre as conexões IPSec atuais.

```
ibmcloud vpn ipsecs
```

**Pré-requisitos**: Terminal, Login, Destino


## ibmcloud vpn gateways
Exibe informações sobre os gateways atuais.

```
ibmcloud vpn gateways
```

**Pré-requisitos**: Terminal, Login, Destino


## Conexão vpn ibmcloud
Exibe todas as informações sobre uma determinada conexão.

```
ibmcloud vpn connection CONNECTION_NAME
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*CONNECTION_NAME* (obrigatório): nome da conexão a ser exibida.


## Ibmcloud vpn ike
Exibe informações sobre uma conexão IKE.

```
Vpn ike POLICY_NAME ibmcloud
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IKE a ser exibida.


## Ibmcloud vpn ipsec
Exibe informações sobre uma conexão IPSec.

```
Vpn ipsec POLICY_NAME ibmcloud
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IPSec a ser exibida.


## Ibmcloud vpn gateway
Exibe informações de conexão de um gateway.

```
Vpn gateway GATEWAY_NAME ibmcloud
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*GATEWAY_NAME* (obrigatório): nome do gateway a ser exibido.


## Delete-conexão vpn ibmcloud
Exclui uma conexão existente.

```
Ibmcloud vpn connection-delete CONNECTION_NAME
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*CONNECTION_NAME* (obrigatório): nome da conexão a ser excluída.


## Delete-ike vpn ibmcloud
Exclui uma política IKE existente.

```
ibmcloud vpn ike-delete POLICY_NAME
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IKE a ser excluída.


## Delete-ibmcloud vpn ipsec
Exclui uma política IPSec existente.

```
Ibmcloud vpn ipsec-delete POLICY_NAME
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IPSec a ser excluída.


## Delete-gateway vpn ibmcloud
Exclui um gateway existente.

```
Ibmcloud vpn gateway-delete GATEWAY_NAME
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*GATEWAY_NAME* (obrigatório): nome do gateway a ser excluído.


## Update-conexão vpn ibmcloud
Atualiza uma conexão VPN existente.

```
ibmcloud vpn connection-update CONNECTION_NAME [-g GATEWAY_NAME] [-k PRESHARED_KEY] [-subnets "SUBNET/MASK"] [-cip CUSTOMER_GATEWAY_IP_ADDRESS] [-d DESCRIPTION] [-peer_id PEER_ID] [-admin_state ADMIN_STATE] [-dpd-action ACTION] [-gateway_ip IP_ADDRESS] [-i INITIATOR_STATE] [-dpd-timeout VALUE] [-dpd-interval VALUE] [-ike NAME] [-ipsec NAME]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*CONNECTION_NAME* (obrigatório): nome da conexão.

-g *GATEWAY_NAME* (opcional): nome do gateway.

-k *PRESHARED_KEY* (opcional): chave pré-compartilhada.

-subnets "*SUBNET*/*MASK*" (opcional): endereço de sub-rede no formato CIDR.

-cip *CUSTOMER_GATEWAY_IP_ADDRESS* (opcional): endereço IP do terminal remoto do túnel da VPN.

-d *DESCRIPTION* (opcional): descrição dos parâmetros especificados.

-peer_id *PEER_ID* (opcional): ID do peer remoto. Outro terminal do túnel da VPN.

-admin_state *ADMIN_STATE* (opcional): status da conexão VPN. Um valor válido é `UP` ou `DOWN`.

-dpd-action *ACTION* (opcional): ação a ser executada quando o peer for detectado como inativo. Um valor válido é `hold`, `clear`, `disabled`, `restart` ou `restart-by-peer`.

-gateway_ip *IP_ADDRESS* (opcional): endereço IP do terminal de túnel da VPN local.

-i *INITIATOR_STATE* (opcional): estado do iniciador.

-dpd-timeout *VALUE* (opcional): valor do tempo limite em segundos após o qual a sessão é finalizada. Intervalo: 6 a 86400 segundos.

-dpd-interval *VALUE* (opcional): intervalo keep-alive em segundos. Envie mensagens keep-alive no intervalo configurado para verificar se o peer está ativo. Intervalo: 5 a 86399 segundos.

-ike *NAME* (opcional): nome da política IKE.

-ipsec *NAME* (opcional): nome da política IPSec.


## Update-ike vpn ibmcloud
Atualiza uma política IKE.

```
ibmcloud vpn ike-update POLICY_NAME [-g GATEWAY_NAME] [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IKE.

-g *GATEWAY_NAME* (opcional): nome do gateway.

-d *DESCRIPTION* (opcional): descrição dos parâmetros especificados.

-pfs *GROUP* (opcional): identificador de grupo Diffie-Hellman (DH). Um valor válido é `Group2`, `Group5` ou `Group14`.

-e *ENCRYPTION_ALGORITHM* (opcional): algoritmo de criptografia. Um valor válido é `aes-128`, `aes-192`, `aes-256` ou `3des`.

-lv *LIFETIME_VALUE* (opcional): valor de tempo de vida da associação de segurança IKE. Intervalo: 60 a 86400 segundos.


## Update-ibmcloud vpn ipsec
Atualiza uma política IPSec.

```
ibmcloud vpn ipsec-update POLICY_NAME [-g GATEWAY_NAME] [-d DESCRIPTION] [-pfs GROUP] [-e ENCRYPTION_ALGORITHM] [-lv LIFETIME_VALUE]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*POLICY_NAME* (obrigatório): nome da política IPSec.

-g *GATEWAY_NAME* (opcional): nome do gateway.

-d *DESCRIPTION* (opcional): descrição dos parâmetros especificados.

-pfs *GROUP* (opcional): identificador de grupo Diffie-Hellman (DH). Um valor válido é `Group2`, `Group5` ou `Group14`.

-e *ENCRYPTION_ALGORITHM* (opcional): algoritmo de criptografia. Um valor válido é `aes-128`, `aes-192`, `aes-256` ou `3des`.

-lv *LIFETIME_VALUE* (opcional): valor de tempo de vida da associação de segurança. Intervalo: 60 a 86400 segundos.


## Update-ibmcloud vpn gateway
Atualiza um gateway VPN existente.

```
ibmcloud vpn gateway-update GATEWAY_NAME [-t TYPE] [-gateway_ip IP_ADDRESS] [-subnets SUBNET_ADDRESS]
```

**Pré-requisitos**: Terminal, Login, Destino

**Opções de comando**:

*GATEWAY_NAME* (obrigatório): nome do gateway.

-t *TYPE* (opcional): contêineres para os quais deseja ativar o serviço. Um valor válido é `allSingleContainers`, `allContainerGroups` ou `allContainers`.

-gateway_ip *IP_ADDRESS* (opcional): endereço IP do gateway.

-subnets *SUBNET_ADDRESS* (opcional): endereço de sub-rede no formato CIDR.
