---
copyright:

  years: 2018

lastupdated: "2018-06-21"

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
comandos para desenvolver aplicativos da web, de dispositivos móveis e de microsserviço de ponta a ponta. Comece a usar rapidamente o conjunto de ferramentas recomendado executando um dos scripts a seguir.
{: shortdesc}

## Pré-requisitos para o {{site.data.keyword.dev_cli_notm}}
{: #prereq}

Inscreva-se para o [{{site.data.keyword.Bluemix_notm}}](http://ibm.biz/ibm-registration).

*  Se você está usando o Microsoft Windows&trade;, deve-se usar o Windows 10 ou mais recente.

* Use o canal estável para Docker, com uma versão mínima de 1.13.1.

## Como instalar o {{site.data.keyword.dev_cli_notm}}
{: #installation}

Para instalar o conjunto de ferramentas, é possível executar o comando relevante para iniciar o instalador. Isso instala as ferramentas recomendadas a seguir para desenvolvimento do {{site.data.keyword.Bluemix_notm}} (caso ainda não estejam instaladas): `Homebrew` (Mac somente), `Git`, `Docker`, `Helm`, `kubectl`, `curl`, CLI do {{site.data.keyword.Bluemix_notm}}, plug-in {{site.data.keyword.dev_cli_notm}}, plug-in Cloud Functions, plug-in Container Registry, plug-in Container Service e plug-in `sdk-gen`. Para instalar, use
estas etapas de instalação:

**Mac e Linux:**

```
curl -sL https://ibm.biz/idt-installer | bash
```
{: codeblock}


**Windows 10:**

* Nota: abra o Windows PowerShell clicando com o botão direito no ícone PowerShell e selecionando "Executar como Administrador".

```
Set-ExecutionPolicy Unrestricted; iex(New-Object Net.WebClient).DownloadString('http://ibm.biz/idt-win-installer')
```
{: codeblock}

## Verifique a instalação
Para verificar a instalação, execute o comando `help`:

```
ibmcloud dev help
```
{: codeblock}

Se a instalação for bem-sucedida, a saída deverá listar instruções de uso, a versão atual e os comandos suportados.

A seção [Reinstalando ferramentas](/docs/troubleshoot/ts_createapps.html#appendix) contém informações para instalar todas as dependências individualmente.

## Configurar o seu ambiente
{: #configure-environment}

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

	**Nota:** se suas credenciais forem rejeitadas, talvez você esteja usando um ID federado. Siga essas etapas para autenticar usando o ID federado.

	1. Efetue login no [{{site.data.keyword.iamshort}} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")](https://www.bluemix.net/iam/#/apikeys){: new_window}.
	2. Selecione **Criar chave API**.
		* Insira um nome e uma descrição da apiKey
	3. Faça download da apiKey.
	4. Abra o arquivo e copie o valor do campo `apiKey`.
	5. Efetue login usando o seguinte comando:

		```
		ibmcloud login --apikey <value>
		```
		{: codeblock}

3. Configure sua ORGANIZAÇÃO e ESPAÇO usando:

	```
	ibmcloud target -o <value> -s <value>
	```
	{: codeblock}

## Saiba mais
{: #learn}

Agora que você tem a sua CLI do {{site.data.keyword.dev_cli_short}} instalada, é possível aprender como ser
eficaz com essa ferramenta poderosa:
- [Introdução ao IDT CLI](index.html)
- [IDT (ibmcloud dev) comandos](commands.html)
- [Developer Tools para código VS](vscode.html)
- [Developer Tools para IDEs do Jetbrains](jetbrains.html)

Consulte os [tutoriais](/docs/apps/tutorials/tutorial_bff.html) que mostram como criar aplicativos nativos
em nuvem que usam a CLI do {{site.data.keyword.dev_cli_short}}.

## Leitura adicional
{: #learn-more}

Os recursos a seguir podem ser úteis ao desenvolver aplicativos nativos em nuvem com o IBM Developer Tools CLI:

- [Página de entrada principal do IBM Cloud Developer Tools](https://www.ibm.com/cloud/cli) - página de produto principal para o IDT CLI
- [Instalador do IBM Developer Tools](https://github.com/IBM-Bluemix/ibm-cloud-developer-tools) - repositório GitHub público com instruções detalhadas de instalação
- [IBM Cloud App Service](https://console.bluemix.net/developer/appservice) - página do console do IBM Cloud, que é um complemento para as ferramentas IDT para criar e gerenciar aplicativos nativos em nuvem
- [Relatar problemas no GitHub](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/issues)
- [Folga da Tecnologia do IBM Cloud - #canal de ferramentas do desenvolvedor](https://ibm-cloud-tech.slack.com) - Solicite o acesso da equipe [aqui](https://slack-invite-ibm-cloud-tech.mybluemix.net/)

**Linguagem em foco**

- [Node.js no IBM Cloud](https://developer.ibm.com/node/cloud/)
- [Spring @ IBM Cloud](https://developer.ibm.com/java/spring/)
- [Swift @ IBM](https://developer.ibm.com/swift)

**Blogs e tutoriais**

- 
[Implementando
para o IBM Cloud Private com a CLI do IBM Cloud Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/)
- [Ativar projetos existentes para o IBM Cloud com o IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/)
- [Implementando para o Kubernetes no IBM Cloud com o IBM Cloud Developer Tools CLI](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/)
