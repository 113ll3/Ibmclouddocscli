---

copyright:

  years: 2015, 2018

lastupdated: "2018-10-31"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:tip: .tip}
{:new_window: target="_blank"}

# Introdução à CLI do {{site.data.keyword.Bluemix_notm}}
{: #overview}

Nesse tutorial, você instala um conjunto de ferramentas do desenvolvedor do {{site.data.keyword.Bluemix}}, verifica a
instalação e configura o seu ambiente. As ferramentas do desenvolvedor do {{site.data.keyword.Bluemix}} oferecem uma
abordagem de linha de comandos para criação, desenvolvimento e implementação de aplicativos da web, de dispositivos móveis e de
microsserviço de ponta a ponta.
{:shortdesc}

Com essa instalação, você obterá a CLI do {{site.data.keyword.Bluemix_notm}} independente, mais as seguintes ferramentas:

* `Homebrew` (somente Mac)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `curl`
* Plug-in do {{site.data.keyword.dev_cli_notm}}
* Plug-in do {{site.data.keyword.IBM_notm}} {{site.data.keyword.openwhisk_short}}
* Plug-in do {{site.data.keyword.registrylong_notm}}
* Plug-in do {{site.data.keyword.containerlong_notm}}
* Plug-in do `sdk-gen`

## Antes de começar
{: #prereq}

É necessária uma
[conta do {{site.data.keyword.Bluemix_notm}}](https://console.bluemix.net/){: new_window}
![Ícone de link externo](../icons/launch-glyph.svg "Ícone de link externo") e os seguintes
requisitos do sistema:

* Se você estiver executando o Windows, algumas funções não serão suportadas se o Windows 10 Pro não estiver em
execução.
* Deve-se usar o canal estável para o Docker com uma versão mínima de 1.13.1.

## Etapa 1. Execute o comando de instalação
{: #step1}

* Para Mac e Linux, execute o comando a seguir:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}

* Para o Windows 10 Pro, execute o comando a seguir como um administrador:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}

  Clique com o botão direito no ícone do Windows PowerShell e selecione **Executar como
administrador**.
  {: tip}

  Também é possível fazer download do script do instalador por meio do nosso
[repositório GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools).

  Para obter as etapas para instalar essas ferramentas manualmente, consulte
[Reinstalando as ferramentas](/docs/cli/ts_createapps.html#appendix).

## Etapa 2. Verificar a instalação
{: #step2}

Para verificar se a CLI e as ferramentas do desenvolvedor foram instalados com êxito, execute o comando `help`:

```
ibmcloud dev help
```
{: codeblock}
<br>
A saída lista as instruções de uso, a versão atual e os comandos suportados.

## Etapa 3. Configure seu ambiente
{: #step3}

1. Conecte-se a um terminal da API em seu local do {{site.data.keyword.Bluemix_notm}}. Por exemplo, insira o comando a seguir para se conectar à localização do {{site.data.keyword.Bluemix_notm}} em Dallas:

	```
	Ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Efetue login no {{site.data.keyword.Bluemix_notm}} com seu IBMid.

	```
	ibmcloud login
	```
	{: codeblock}
    <br>

	Se as suas credenciais forem rejeitadas, talvez você esteja usando um ID federado. Consulte
[Efetuando login com um ID federado](/docs/iam/login_fedid.html#federated_id) para obter mais detalhes.
	{: tip}

3. Configure a sua organização e o espaço.

	```
	ibmcloud target --cf
	```
	{: codeblock}

	Opcionalmente, é possível usar a saída do comando anterior para configurar manualmente a organização e o espaço
com o comando a seguir:

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Próximas Etapas
{: #next-steps}

Agora você está pronto para desenvolver e implementar o seu primeiro aplicativo! Consulte
[Criando e implementando os apps usando a CLI](/docs/apps/create-deploy-cli.html) para obter mais informações.
