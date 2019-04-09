---

copyright:

  years: 2017, 2018

lastupdated: "2018-11-30"



---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools for Visual Studio Code
{: #ibm-dev-tools-for-vscode}

A extensão do IBM Cloud Developer Tools para o Visual Studio Code é uma extensão para o editor que fornece acesso aos recursos da CLI do desenvolvedor da IBM diretamente dentro da paleta de comandos do editor do Visual Studio Code. Ela permite que você acesse rapidamente um subconjunto de comandos `ibmcloud dev` para ambos os fluxos de trabalho, Docker e CloudFoundry, incluindo a implementação do app, iniciando/interrompendo/reiniciando os apps no {{site.data.keyword.Bluemix}}, visualizando logs de app remoto e mais – tudo sem a necessidade de sair do contexto do editor.
{:shortdesc}

![Captura de tela da tela de download da extensão IBM Developer Tools.](vscode.png "Tela de download da extensão dentro do Visual Studio Code")

## Dependências
{: #dependencies}

Para usar a extensão do IBM Cloud Developer Tools para o Visual Studio Code, você precisa da [CLI do {{site.data.keyword.Bluemix_notm}}](/docs/cli/index.html#overview) e do plug-in da CLI do {{site.data.keyword.Bluemix_notm}} que está instalado em seu sistema.

## Instalação
{: #installation}

A maneira mais simples de instalar a extensão do IBM Cloud Developers Tools é usar o comando 'quick open' do Visual Studio Code:

1. Abra a paleta de comandos 'quick open' usando as combinações de teclas a seguir de dentro do editor:

  * **Mac:** `cmd + p`
  * **Windows/Linux:** `ctrl + p`

2. Insira o comando `ext install ibm-developer` e pressione Enter para instalar a extensão do IBM Cloud Developer Tools dentro do editor do Visual Studio Code.

Como alternativa, é possível instalar a extensão do IBM Cloud Developer Tools por meio da janela de gerenciamento "Extensões":

1. Abra a barra lateral de **Extensões** dentro do editor do Visual
Studio Code e, em seguida, procure usando a sequência `publisher:IBM Developer`. A extensão do IBM Cloud Developer Tools é exibida nos resultados da procura.  
2. Clique no botão **Instalar** para começar a instalação.

Também é possível acessar a [extensão do IBM Cloud Developer Tools diretamente dentro do Visual Studio Code Marketplace](https://marketplace.visualstudio.com/items?itemName=IBM.ibm-developer){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").

## Uso
{: #usage}

Você inicia os comandos de extensão usando a paleta de comandos do Visual Studio Code.

Primeiramente, abra a paleta de comandos usando a combinação de teclas a seguir:

* **Mac:** `cmd + shift + p`
* **Windows/Linux:** `ctrl + shift + p`

Em seguida, insira ou selecione o comando que deseja iniciar. É possível digitar 'ibmcloud' na paleta de comandos para ver a lista de todos os comandos disponíveis.

### Usando os fluxos de trabalho do IBM Developer Extension for Docker (contêineres do Docker)
{: #usage-docker}

É possível começar a usar os fluxos de trabalho `ibmcloud dev` em apenas algumas etapas:
* Crie um projeto usando um dos dois métodos a seguir:
  * Use o [console da web do {{site.data.keyword.Bluemix_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window}![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e faça download do código gerado
  * Use o Plug-in da CLI do Developer Tools do {{site.data.keyword.Bluemix_notm}} e gere um projeto usando o comando [ibmcloud dev create](/docs/cli/idt/commands.html#create).
* Abra a pasta do projeto localmente no editor do Visual Studio Code
* Use o comando `ibmcloud dev build` para construir o app em uma imagem do Docker
* Use o comando `ibmcloud dev debug` para executar o app no Docker local para desenvolvimento
> Nota: para depurar um aplicativo Node.js que está em execução dentro do contêiner do Docker local, é necessário [incluir uma configuração de depuração para o contêiner local](https://github.com/IBM-Bluemix/ibm-developer-extension-vscode#debugging-nodejs-apps-within-the-local-docker-container){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo").
* Use o comando `ibmcloud dev run` para executar o app no Docker local no modo de liberação
* Use o comando `ibmcloud dev deploy` para implementar o aplicativo em um tempo de execução do Cloud Foundry no {{site.data.keyword.Bluemix_notm}}

### Usando os fluxos de trabalho do IBM Developer Extension for Cloud Foundry
{: #usage-cloud-foundry}

Para usuários que estejam implementando atualmente apps nos tempos de execução do Cloud Foundry no IBM
{{site.data.keyword.Bluemix_notm}}, também há suporte para o conjunto de operações do
`cf`.

É possível iniciar a utilização dos fluxos de trabalho do CloudFoundry em apenas algumas etapas:
* Crie um novo aplicativo CloudFoundry
  * Use o [console da web do {{site.data.keyword.Bluemix_notm}}](https://{DomainName}/developer/appservice/starter-kits){: new_window}![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e faça download do código de início
  * Crie um novo aplicativo CloudFoundry manualmente
* Abra a pasta do projeto localmente no editor do Visual Studio Code
* Use `ibmcloud cf apps` para listar todos os seus aplicativos
* Use `ibmcloud cf push` para enviar por push uma compilação de seu aplicativo para o tempo de execução do Cloud Foundry
* Use ibmcloud `cf <start/stop/restage/restart>` para mudar o status de seu aplicativo
* Use `ibmcloud cf logs` para visualizar o fluxo de logs em tempo real de seu aplicativo
  * Use `ibmcloud cf logs` para parar o fluxo de logs
