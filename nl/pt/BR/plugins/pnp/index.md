---

copyright:

  years: 2016, 2018

lastupdated: "2018-06-21"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}

# Plug-in de peering de rede privada para a CLI do {{site.data.keyword.Bluemix_notm}}
{: #private_network_cli}

Use a interface da linha de comandos (CLI) de peering de rede privada para configurar e gerenciar o peering de rede privada entre dois espaços do {{site.data.keyword.Bluemix}}. O peerring de rede privada é suportado para o IBM Containers (contêineres de docker). Os espaços do {{site.data.keyword.Bluemix_notm}} podem ser localizados em diferentes zonas de disponibilidade na mesma região ou podem ser localizados nas diferentes regiões. O plug-in da CLI do peering de rede privada está disponível para uso com o plug-in do {{site.data.keyword.Bluemix_notm}} CLI.

O plug-in da CLI de peering de rede privada está disponível para os sistemas operacionais Windows, MAC e Linux. Assegure-se de usar o plug-in aplicável a você.

Antes de iniciar, crie espaços do {{site.data.keyword.Bluemix_notm}}. Assegure-se de que cada contêiner em um espaço tenha um endereço IP de uma rede diferente.

**Nota:** depois de usar o peering de rede privada com um espaço do {{site.data.keyword.Bluemix_notm}}, se você precisar excluir o espaço, primeiro exclua as conexões de peering de rede privada nesse espaço.

Para iniciar, instale o {{site.data.keyword.Bluemix_notm}} CLI. Consulte
[CLI do IBM Cloud](http://clis.ng.bluemix.net/ui/home.html) para obter detalhes.

## Instale o plug-in da CLI de peering de rede privada

**Observação**: se você tiver uma versão anterior do plug-in que está instalado, será necessário desinstalá-la. Use o comando a seguir para desinstalar o plug-in:

```
Ibmcloud plugin uninstall private-network-peering
```
### Instalar localmente
Faça download do plug-in de peering de rede privada para sua plataforma por meio do repositório de plug-ins do [{{site.data.keyword.ibmcloud_notm}} CLI ![Ícone de link externo](../../../icons/launch-glyph.svg)](http://plugins.ng.ibmcloud.net/ui/repository.html#ibmcloud-plugins){: new_window}.

Instale o plug-in de peering de rede privada usando o comando a seguir:

**Observação**: alterne para o local do plug-in ou especifique o caminho para o local do plug-in.

* Para o sistema operacional Microsoft Windows:

```
ibmcloud plugin install private-network-peering-windows-amd64.exe
```

* Para o Apple MAC OS:

```
Ibmcloud plugin install private-network-peering-darwin-amd64
```

* Para o sistema operacional Linux:

```
Ibmcloud plugin install private-network-peering-linux-amd64
```

**Observação**: enquanto estiver instalando o plug-in para o sistema operacional Linux, se for exibida uma mensagem de erro que mostra que a permissão é negada, então, execute o comando a seguir e mude as permissões:

```
chmod a+x ./private-network-peering-linux-amd64
```

### Instale por meio do repositório do {{site.data.keyword.ibmcloud_notm}}

Siga estas etapas para instalar o plug-in por meio do repositório do {{site.data.keyword.ibmcloud_notm}}:

1. Inclua o terminal de registro de plug-in: {{site.data.keyword.ibmcloud_notm}}
	```
	Ibmcloud plugin repo-add bluemix-bx http://plugins.ng.bluemix.net
	```

2. Execute o seguinte comando:

	```
	Ibmcloud plugin install private-network-peering -r bluemix-bx
	```

## Lista de comandos de peering de rede privada
Os comandos a seguir são compatíveis. Use o comando `ibmcloud network` para ver a lista de comandos disponíveis:

| Comando:     | Descrição                                    |
|-------------|------------------------------------------------|
| pnp-routers | Lista todos os roteadores disponíveis para peering        |
| pnp-create  | Cria uma conexão de peering de rede privada   |
| pnp-delete  | Exclui uma conexão de peering de rede privada   |
| pnp-show    | Lista todas as conexões de peering de rede privada  |
{: caption="Tabela 1. Comandos de peer de rede privada" caption-side="top"}


### Uso do comando
Para visualizar informações da ajuda para os comandos, execute: `ibmcloud network [command] -h`.

#### Liste todos os roteadores disponíveis para peering
```
Ibmcloud network pnp-routers [ -- verbose (ou -v) ]
```

#####Parâmetros opcionais
{: #op1}

* **--verbose (ou -v)** (sinalizador): visualizar informações de rede detalhadas sobre cada roteador.

######Exemplo de comando
{: #ex1}

Para visualizar as informações de rede sobre todos os roteadores:

	$ ibmcloud network pnp-routers
	Listing available routers ...
	OK

	IP              NAME            COMPUTE    REGION          ORGANIZATION    SPACE
	129.41.234.246  default-router  Container  US-South        ywu@us.ibm.com  demo1
	129.41.237.172  default-router  Container  US-South        ywu@us.ibm.com  demo2
	129.41.238.212  default-router  Container  United-Kingdom  ywu@us.ibm.com  demo3


Para visualizar informações de rede detalhadas sobre todos os roteadores:


	$ ibmcloud network pnp-routers -v
	Listing available routers ...
	OK

	Router 'bce1aa25-bad0-4cf1-a831-d53c16463d06':
	FIELD          VALUE
	IP             129.41.234.246
	Name           default-router
	Compute        Container
	Region         US-South
	Organization   ywu@us.ibm.com
	Space          demo1
	Networks       172.31.0.0/16

	Router '9ea160f2-1a30-44cd-bd25-794d441b274b':
	FIELD          VALUE
	IP             129.41.237.172
	Name           default-router
	Compute        Container
	Region         US-South
	Organization   ywu@us.ibm.com
	Space          demo2
	Networks       172.25.0.0/16

	...


#### Crie uma conexão de peering de rede privada usando os endereços IP
```
ibmcloud network pnp-create <router_ip> <router_ip> <name>
```

#####Parâmetros
{: #p1}

* **router_ip**: endereços IP dos dois roteadores com os quais você deseja se conectar. É possível localizar os endereços IP usando o comando: `ibmcloud network pnp-routers`
* **name**: nome da conexão de peering de rede privada.

######Exemplo de comando
{: #ex2}

	$ ibmcloud network pnp-create 129.41.234.246 129.41.237.172 demo
	Creating private network peering connection 'demo' ...
	Connecting 'default-router(129.41.234.246)' and 'default-router(129.41.237.172)' ...
	OK

	'Demo' de conexão de peering de rede privada criada.


####Crie uma conexão de peering de rede privada usando o nome da conexão

```
ibmcloud network pnp-create -i <name>
```

#####Parâmetros
{: #p2}

* **--interactive (-i)** (sinalizador): modo interativo para selecionar roteadores.
* **name**: nome da conexão de peering de rede privada.

######Exemplo de comando
{: #ex3}

	$ ibmcloud network pnp-create -i demo
	Creating private network peering connection 'demo' ...
	List of available routers (select TWO for peering):

	#  ROUTER                          COMPUTE    REGION          ORGANIZATION    SPACE
	1  default-router(129.41.234.246)  Container  US-South        ywu@us.ibm.com  demo1
	2  default-router(129.41.237.172)  Container  US-South        ywu@us.ibm.com  demo2
	3  default-router(129.41.238.212)  Container  United-Kingdom  ywu@us.ibm.com  demo3

	Select first router for peering> 1 	Select second router for
peering> 2

	Connecting 'default-router(129.41.234.246)' and 'default-router(129.41.237.172)' ...
	OK

	'Demo' de conexão de peering de rede privada criada.


#### Liste todas as conexões de peering de rede privada
```
Ibmcloud network pnp-show [ -- verbose (ou -v) ]
```

#####Parâmetros opcionais
{: #op2}

* **--verbose (ou -v)** (sinalizador): visualizar informações de rede detalhadas sobre cada roteador.

######Exemplo de comando
{: #ex4}

Visualizar informações básicas:

	$ ibmcloud network pnp-show
	Listing private network peering connections ...
	OK

	ID                                    NAME  STATUS  ROUTER1                         ROUTER2
	17b1c3c7-d614-4fc5-9afe-961e38ee79f8  demo  Active  default-router(129.41.234.246)  default-router(129.41.237.172)

Visualize informações detalhadas:

	$ ibmcloud network pnp-show -v
	Listing private network peering connections ...
	OK

	Connection 'bedbc077-8040-41cc-a4aa-d9ce09a2e8ec':
	FIELD              VALUE
	Name               demo
	Status             Active
	Router1 Name       default-router
	Router1 IP         129.41.234.246
	Router1 Networks   172.31.0.0/16
	Router2 Name       default-router
	Router2 IP         129.41.237.172
	Router2 Networks   172.25.0.0/16


#### Exclua uma conexão de peering de rede privada
```
ibmcloud network pnp-delete [--force (or -f)] <connection_id>
```
#####Parâmetros
{: #p3}
* **connection_id**: um ou mais IDs de conexão separados por uma vírgula.

#####Parâmetros opcionais
{: #op3}

* **--force (ou -f)** (sinalizador): exclui a conexão sem solicitar uma confirmação.

######Exemplo de comando:
{: #ex5}

Exclua uma conexão:

	$ ibmcloud network pnp-delete 17b1c3c7-d614-4fc5-9afe-961e38ee79f8
	Warning: deleted connections cannot be restored.
	Are you sure you want to delete the connection? (yes/no)> yes

	Deleting private network peering connection '17b1c3c7-d614-4fc5-9afe-961e38ee79f8' ...
	OK

	Private network peering connection '17b1c3c7-d614-4fc5-9afe-961e38ee79f8' deleted.


Exclua várias conexões:

```
ibmcloud network pnp-delete [-f] <connection_id>,<connection_id>,<connection_id>
```
