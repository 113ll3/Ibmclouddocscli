---

copyright:

  years: 2015, 2018

lastupdated: "2018-06-26"

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

Com essa instalação, você obtém a CLI do {{site.data.keyword.Bluemix_notm}}, além das seguintes ferramentas: 

* `Homebrew` (somente Mac)
* `Git`
* `Docker`
* `Helm`
* `kubectl`
* `ondulação`
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

* Se você está usando o Microsoft Windows&trade;, deve-se usar o Windows 10 ou mais recente.
* Deve-se usar o canal estável para o Docker com uma versão mínima de 1.13.1.

## Etapa 1: executar o comando de instalação
{: #step1}

* Para Mac e Linux, execute o comando a seguir:

  ```
  curl -sL https://ibm.biz/idt-installer | bash
  ```
  {: codeblock}
<br><br>

* Para Windows 10, execute o comando a seguir como um administrador:

  ```
  Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
  ```
  {: codeblock}
<br><br>
 Clique com o botão direito no ícone do Windows PowerShell e selecione **Executar como
administrador**.
  {: tip}

## Etapa 2: verificar a instalação
{: #step2}

Para verificar se a CLI e as ferramentas do desenvolvedor foram instalados com êxito, execute o comando `help`:

```
ibmcloud dev help
```
{: codeblock}
<br><br>
A saída lista as instruções de uso, a versão atual e os comandos suportados.

## Etapa 3: configurar o seu ambiente
{: #step3}

1. Conecte-se a um terminal de API em sua região do {{site.data.keyword.Bluemix_notm}}. Por exemplo, insira o comando a seguir para se conectar à região Sul dos EUA {{site.data.keyword.Bluemix_notm}}:

	```
	Ibmcloud api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Efetue login no {{site.data.keyword.Bluemix_notm}} com seu IBMid.

	```
	ibmcloud login
	```
	{: codeblock}
<br><br>
	Se as suas credenciais forem rejeitadas, talvez você esteja usando um ID federado. Consulte
[Efetuando login com um ID federado](/docs/iam/login_fedid.html#using-an-api-key) para obter mais detalhes.	{: tip}

3. Configure a sua organização e o espaço.

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Próximas Etapas
{: #next-steps}

Agora você está pronto para desenvolver e implementar o seu primeiro app! Consulte
[Criando um app da web básico com um kit do iniciador](/docs/apps/tutorials/tutorial_web.html) para obter
informações adicionais.
