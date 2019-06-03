---

copyright:
  years: 2017, 2019
lastupdated: "2019-05-21"

keywords: cli, ibm cloud developer tools, visual studio code, install developer tools, developer extension, vscode cli, vscode plugin, cloud foundry vscode

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Visual Studio Code
{: #ibm-dev-tools-for-vscode}

A extensão do IBM Cloud Developer Tools para o Visual Studio Code fornece acesso aos recursos da CLI do desenvolvedor da IBM diretamente dentro da paleta de comandos do editor do Visual Studio Code. É possível acessar rapidamente um subconjunto de comandos `ibmcloud dev` para os fluxos de trabalho do Docker e do Cloud Foundry, incluindo implementação de app, iniciar/interromper/reiniciar apps no {{site.data.keyword.cloud}}, visualizar logs de app remotos e mais – tudo sem a necessidade de deixar o contexto do editor.
{:shortdesc}

![Captura de tela da tela de download da extensão IBM Developer Tools.](vscode.png "Tela de download da extensão dentro do Visual Studio Code")

## Dependências
{: #vscode-dependencies}

Para usar a extensão do IBM Cloud Developer Tools para o Visual Studio Code, serão necessários a CLI do [{{site.data.keyword.cloud_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) e o plug-in da CLI do {{site.data.keyword.cloud_notm}} que estiverem instalados em seu sistema.

## Instalação
{: #vscode-installation}

A maneira mais simples de instalar a extensão do {{site.data.keyword.dev_cli_notm}} é usar o comando 'quick open' do Visual Studio Code:

1. Abra a paleta de comandos 'quick open' usando as combinações de teclas a seguir de dentro do editor:

  * **Mac:** `cmd + p`
  * **Windows/Linux:** `ctrl + p`

2. Insira o comando `ext install ibm-developer` e pressione Enter para instalar a extensão do {{site.data.keyword.dev_cli_notm}} dentro do editor do Visual Studio Code.

Ou é possível instalar a extensão do {{site.data.keyword.dev_cli_notm}} por meio da janela de gerenciamento "Extensões":

1. Abra a barra lateral **Extensões** no editor do Visual Studio Code e, em seguida, procure usando a sequência `publisher:IBM Developer`. A extensão do {{site.data.keyword.dev_cli_notm}} será exibida nos resultados da procura.  
2. Clique em  ** Instalar **  para iniciar a instalação.

Também é possível acessar a [extensão do IBM Cloud Developer Tools diretamente dentro do Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").

## Uso
{: #vscode-usage}

Você inicia os comandos de extensão usando a paleta de comandos do Visual Studio Code.

Primeiramente, abra a paleta de comandos usando a combinação de teclas a seguir:

* **Mac:** `cmd + shift + p`
* **Windows/Linux:** `ctrl + shift + p`

Em seguida, insira ou selecione o comando que deseja iniciar. É possível digitar 'ibmcloud' na paleta de comandos para ver a lista de todos os comandos disponíveis.

### Usando os fluxos de trabalho do IBM Developer Extension for Docker (contêineres do Docker)
{: #usage-docker}

É possível começar a usar os fluxos de trabalho `ibmcloud dev` em apenas algumas etapas:
* Crie um projeto usando um dos dois métodos a seguir:
  * Use o [{{site.data.keyword.cloud_notm}}console da web](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e faça download do código gerado
  * Use o Plug-in da CLI do Developer Tools do {{site.data.keyword.cloud_notm}} e gere um projeto usando o comando [ibmcloud dev create](/docs/cli/idt?topic=cloud-cli-idt-cli#create).
* Abra a pasta do projeto localmente no editor do Visual Studio Code
* Use o comando `ibmcloud dev build` para construir o app em uma imagem do Docker
* Use o comando `ibmcloud dev debug` para executar o app no Docker local para desenvolvimento
> Nota: para depurar um aplicativo Node.js que está em execução dentro do contêiner do Docker local, é necessário [incluir uma configuração de depuração para o contêiner local](https://github.com/IBM-Cloud/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").
* Use o comando `ibmcloud dev run` para executar o app no Docker local no modo de liberação
* Use o comando `ibmcloud dev deploy` para implementar o app em um tempo de execução do Cloud Foundry no {{site.data.keyword.cloud_notm}}

### Usando os fluxos de trabalho do IBM Developer Extension for Cloud Foundry
{: #usage-cloud-foundry}

Para usuários que estiverem implementando atualmente apps para tempos de execução do Cloud Foundry no {{site.data.keyword.cloud_notm}}, também há suporte para o conjunto de operações `cf`.

É possível começar a usar os fluxos de trabalho do Cloud Foundry em apenas algumas etapas:
* Criar um novo app do Cloud Foundry
  * Use o [{{site.data.keyword.cloud_notm}}console da web](https://{DomainName}/developer/appservice/starter-kits){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e faça download do código de início
  * Crie um novo app do Cloud Foundry manualmente
* Abra a pasta do projeto localmente no editor do Visual Studio Code
* Use `ibmcloud cf apps` para listar todos os seus apps
* Use `ibmcloud cf push` para enviar por push uma construção de seu app para o tempo de execução do Cloud Foundry
* Use ibmcloud `cf <start/stop/restage/restart>` para mudar o status de seu app
* Use `ibmcloud cf logs` para visualizar o fluxo de logs em tempo real de seu app
  * Use `ibmcloud cf logs` para parar o fluxo de logs
