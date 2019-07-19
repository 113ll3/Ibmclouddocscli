---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-27"

keywords: ibm cloud developer tools, jetbrains, jetbrains ides, intellij, webstorm, android studio, ibmcloud dev, view remote logs, ibmcloud docker commands

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools para IDEs do Jetbrains
{: #ibm-dev-tools-for-jetbrains}

A extensão de ferramentas do desenvolvedor do {{site.data.keyword.cloud}} para IDEs do Jetbrains, que incluem `IntelliJ`, `WebStorm`, `Android Studio` e mais, fornece novas entradas de menu para acessar diretamente os comandos da CLI do {{site.data.keyword.dev_cli_notm}} de dentro do IDE. É possível acessar rapidamente um subconjunto de comandos `ibmcloud dev` para os fluxos de trabalho do Docker e do Cloud Foundry, incluindo implementação de app, iniciar/interromper/reiniciar apps no {{site.data.keyword.cloud_notm}}, visualizar logs de app remotos e mais – tudo sem a necessidade de deixar o contexto do editor.
{:shortdesc}

Exemplo de menu de ferramentas do desenvolvedor do ![Captura de tela do IBM Cloud Developer Tools em execução no WebStorm IDE.](jetbrains.png "{{site.data.keyword.cloud_notm}} em execução no WebStorm IDE")


## Dependências
{: #jetbrains-dependencies}

Para utilizar a extensão de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}} para IDEs baseados no Jetbrains, é necessária [ a CLI do {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-ibmcloud-cli#ibmcloud-cli) instalada em seu sistema.

## Instalação
{: #jetbrains-installation}

A melhor maneira de instalar a extensão de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}} para o IDE do Jetbrains é acessar a página do [Jetbrains do repositório do Github de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}}](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo") e seguir as instruções.

## Uso
{: #jetbrains-usage}

É possível iniciar com um app do lado do servidor existente e ativá-lo para o {{site.data.keyword.cloud_notm}} ou usar a CLI do {{site.data.keyword.dev_cli_notm}} para criar um novo app por meio de um Kit do iniciador (ibmcloud dev create). Quando você tiver o projeto do seu app, abra-o em seu IDE do JetBrains.

Se você tiver um app genérico do lado do servidor, selecione Ferramentas > IBM Cloud Developer Tools > Ativar app para o {{site.data.keyword.cloud_notm}}. Isso verifica todos os arquivos necessários e inclui qualquer um que esteja ausente no app localmente e implementa-o no {{site.data.keyword.cloud_notm}} usando um app Cloud Foundry ou dentro de um cluster Kubernetes.

Desenvolva o seu app nativo de nuvem usando as ações básicas de construção, execução e implementação por meio do menu de ferramentas do desenvolvedor do {{site.data.keyword.cloud_notm}}. Se for necessário executar ações que não estiverem no menu, simplesmente abra a guia Terminal e insira os comandos desejados manualmente.
