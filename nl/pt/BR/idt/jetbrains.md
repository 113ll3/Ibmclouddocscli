---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools para IDEs do JetBrains
{: #ibm-dev-tools-for-jetbrains}

A extensão de ferramentas do desenvolvedor do {{site.data.keyword.cloud}} para IDEs do JetBrains, que inclui `IntelliJ`, `WebStorm`, `Android Studio` e mais, fornece novas entradas de menu para acessar diretamente os comandos da CLI
do {{site.data.keyword.dev_cli_notm}} dentro do IDE. É possível acessar rapidamente um subconjunto de comandos `ibmcloud dev` para os fluxos de trabalho do Docker e do Cloud Foundry, incluindo implementação do aplicativo, início/parada/reinício de apps no {{site.data.keyword.cloud_notm}}, visualização de logs do app remoto e muito mais. Todos sem a necessidade de sair do contexto do editor.
{: shortdesc}

Exemplo de menu de ferramentas do desenvolvedor do ![Captura de tela do IBM Cloud Developer Tools em execução no WebStorm IDE.](jetbrains.png "{{site.data.keyword.cloud_notm}} em execução no WebStorm IDE")


## Dependências
{: #jetbrains-dependencies}

Para usar a extensão de ferramenta do desenvolvedor do {{site.data.keyword.cloud_notm}} para IDEs baseados em JetBrains, é necessária a [CLI do {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) instalada em seu sistema.

## Instalação
{: #jetbrains-installation}

A melhor maneira de instalar a extensão de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}} para JetBrains IDE, é acessar a [página JetBrains do repositório GitHub das ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e seguir as instruções.

## Uso
{: #jetbrains-usage}

É possível iniciar com um app do lado do servidor existente e ativá-lo para a nuvem ou usar
a CLI do {{site.data.keyword.dev_cli_notm}} para criar um novo app por meio de um kit do iniciador (`ibmcloud dev create`). Quando você tiver o projeto do seu app, abra-o em seu IDE do JetBrains.

Para ativar na nuvem um app genérico do lado do servidor, selecione **Ferramentas** > **IBM Cloud Developer Tools** > **Ativar app para o {{site.data.keyword.cloud_notm}}**. Todos os arquivos requeridos são verificados e incluídos (se necessário) para implementação no {{site.data.keyword.cloud_notm}} usando um app Cloud Foundry ou dentro de um cluster do
Kubernetes.

Desenvolva seu app nativo de nuvem usando as ações básicas de construção, execução e
implementação no menu de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}}. Se for necessário executar ações que não estão no menu, simplesmente abra uma guia do terminal e insira
os comandos manualmente.
