---
copyright:

  years: 2018

lastupdated: "2018-04-17"

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# Configurando a CLI do {{site.data.keyword.dev_cli_notm}}
{: #add-cli}

A CLI do {{site.data.keyword.dev_cli_short}} é uma abordagem de linha de comandos para
criação, desenvolvimento e implementação de aplicativos para desenvolvedores que desejam usar uma linha de
comandos para desenvolver aplicativos da web, de dispositivos móveis e de microsserviço de ponta a ponta.
{: shortdesc}

## Pré-requisito
{: #prereq}

Inscreva-se para o [{{site.data.keyword.Bluemix_notm}}](https://www.bluemix.net).

*  Se você está usando o Microsoft Windows&trade;, deve-se usar o Windows 10 ou mais recente.

* Use o canal estável para Docker, com uma versão mínima de 1.13.1.

## Instalar
{: #installation}

Para instalar a ferramenta, é possível executar o comando relevante para iniciar o instalador. Isso
também instala as dependências, como a CLI do IBM Cloud, o Kubernetes, o Helm e o Docker. Para instalar, use
estas etapas de instalação:

**Mac e Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Nota: abra o Windows PowerShell clicando com o botão direito e selecionando "Executar como
administrador".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

Valide a instalação bem-sucedida do plug-in executando o comando a seguir:  

```
bx dev
```
{: codeblock}

## Configurar o seu ambiente
{: #configure-environment}

1. Conecte-se a um terminal de API em sua [{{site.data.keyword.Bluemix_notm}} região](/docs/overview/cf.html#ov_intro_reg). Por exemplo, insira o comando a seguir para se conectar à região Sul dos EUA {{site.data.keyword.Bluemix_notm}}:

	```
	bx api https://api.ng.bluemix.net
	```
	{: codeblock}

2. Efetue login no {{site.data.keyword.Bluemix_notm}} com seu IBMid.

	```
	bx login
	```
	{: codeblock}

	**Nota:** se suas credenciais forem rejeitadas, talvez você esteja usando um ID federado. Siga essas etapas para autenticar usando o ID federado.

	1. Efetue login no [{{site.data.keyword.iamshort}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Selecione **Criar chave API**.
		* Insira um nome e uma descrição da apiKey
	3. Faça download da apiKey.
	4. Abra o arquivo e copie o valor do campo `apiKey`.
	5. Efetue login usando o seguinte comando:

		```
		bx login --apikey <value>
		```
		{: codeblock}

3. Configure sua ORGANIZAÇÃO e ESPAÇO usando:

	```
	bx target -o <value> -s <value>
	```
	{: codeblock}

## Saiba mais
{: #learn}

Agora que sua CLI do {{site.data.keyword.dev_cli_short}} está instalada, é possível
aprender como ser eficiente com essa ferramenta poderosa:
- [Introdução ao IDT CLI](index.html)
- [Comandos do IDT (bx dev)](commands.html)
- [Developer Tools para código VS](vscode.html)
- [Developer Tools para IDEs do Jetbrains](jetbrains.html)

Consulte os [tutoriais](/docs/apps/tutorials/tutorial_bff.html) que mostram como criar
apps nativos de nuvem usando a CLI do {{site.data.keyword.dev_cli_short}}.

## Leitura adicional
{: #learn-more}

Os recursos a seguir podem ser úteis ao desenvolver aplicativos nativos em nuvem com o IBM Developer Tools CLI:

- [Página de entrada principal do IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - página de produto principal para o IDT CLI
- [Instalador do IBM Developer Tools](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - repositório GitHub público com instruções detalhadas de instalação
- [Serviço de aplicativo do IBM Cloud](https://console.bluemix.net/developer/appservice) - página do console do IBM Cloud que é um complemento para as ferramentas IDT para criar e gerenciar aplicativos nativos em nuvem
- [IBM Cloud Tech's Slack - #canal do developer-tools](https://ibm-cloud-tech.slack.com) - discuta as ferramentas IDT, obtenha respostas, sugira ideias e muito mais
	- [Solicitar acesso de equipe](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Linguagem em foco**

- [Node,js no IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogs e tutoriais**

- [Implementando no IBM Cloud privado com o IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Ativar projetos existentes para o IBM Cloud com o IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Implementando para o Kubernetes no IBM Cloud com o IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
