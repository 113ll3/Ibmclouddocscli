---

copyright:

  years: 2018

lastupdated: "2018-07-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Cloud Developer Tools para IDEs do Jetbrains
{: #ibm-dev-tools-for-jetbrains}

A extensão de ferramentas do desenvolvedor do {{site.data.keyword.Bluemix_notm}} para IDEs do Jetbrains, que incluem `IntelliJ`, `WebStorm`, `Android Studio` e muito mais, fornece novas entradas de menu para acessar diretamente os comandos da CLI do {{site.data.keyword.dev_cli_notm}} de dentro do IDE. Isso permite acessar rapidamente um subconjunto de comandos `ibmcloud dev` para os fluxos de trabalho do Docker e CloudFoundry, incluindo a implementação do app, iniciando/parando/reiniciando apps no {{site.data.keyword.Bluemix_notm}}, visualizando logs de app remoto e muito mais, tudo sem a necessidade de deixar o contexto do editor.
{:shortdesc}

Exemplo de menu de ferramentas do desenvolvedor do ![Captura de tela do IBM Cloud Developer Tools em execução no WebStorm IDE.](jetbrains.png "{{site.data.keyword.Bluemix_notm}} en execução no WebStorm IDE")

## Dependências
{: #dependencies}

Para utilizar a extensão de ferramentas do desenvolvedor do {{site.data.keyword.Bluemix_notm}} para IDEs baseados em Jetbrains, você também precisará da [CLI do {{site.data.keyword.dev_cli_notm}}](index.html) instalada em seu sistema.

## Instalação
{: #installation}

A maneira mais simples de instalar a extensão de ferramentas do desenvolvedor do {{site.data.keyword.Bluemix_notm}} para IDE do Jetbrains é acessar a página [Jetbrains do repositório Github de ferramentas do desenvolvedor do {{site.data.keyword.Bluemix_notm}}](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) e seguir as instruções.

## Uso
{: #usage}

É possível iniciar com um app do lado do servidor existente e ativá-lo para o {{site.data.keyword.Bluemix_notm}} ou usar a CLI do {{site.data.keyword.dev_cli_notm}} para criar um novo app por meio de um Kit do iniciador (ibmcloud dev create). Quando você tiver o projeto do seu app, abra-o em seu IDE do JetBrains.

Se você tiver um app do lado do servidor genérico, selecione Ferramentas > IBM Cloud Developer Tools > Ativar app para o IBM Cloud. Isso verificará todos os arquivos necessários e incluirá qualquer um que esteja ausente, o que permitirá construir o app localmente, bem como implementá-lo no {{site.data.keyword.Bluemix_notm}} usando um app Cloud Foundry ou dentro de um cluster do Kubernetes.

Desenvolva seu aplicativo nativo em nuvem usando as ações básicas de construção/execução/implementação no menu de ferramentas do desenvolvedor do {{site.data.keyword.Bluemix_notm}}. Se você precisar executar ações que não estão no menu, bastará abrir a guia Terminal e inserir os comandos desejados manualmente.
