---

copyright:

  years: 2018

lastupdated: "2018-03-16"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools para IDEs do Jetbrains
{: #ibm-dev-tools-for-jetbrains}

O IBM Developer Extension para IDEs do Jetbrains, que incluem IntelliJ, WebStorm, Android Studio e outros, fornece as novas entradas de menu para acessar diretamente os comandos da CLI do IDT de dentro do IDE. Ele permite o acesso rápido a um subconjunto de comandos `bx dev` para os fluxos de trabalho do Docker e do CloudFoundry, incluindo implementação do app, iniciar/parar/reiniciar apps no {{site.data.keyword.Bluemix_notm}}, visualizar logs de apps remotos e muito mais, tudo sem a necessidade de sair do contexto do editor.
{:shortdesc}

![Captura de tela do IBM Developer Tools em execução no IDE WebStorm.](jetbrains.png "Exemplo do menu IDT em execução no IDE WebStorm")

## Dependências
{: #dependencies}

Para utilizar a extensão IBM Developer Tools para IDEs baseados no Jetbrains, você também precisará do [IBM Cloud Developer Tools CLI](index.html) instalado em seu sistema.

## Instalação
{: #installation}

A maneira mais simples de instalar a extensão IBM Developers Tools para o IDE do Jetbrains é acessar a página [Jetbrains do repositório Github do IDT](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) e seguir as instruções.

## Uso
{: #usage}

É possível iniciar com um app do lado do servidor existente e ativá-lo para o IBM Cloud ou usar a CLI do IDT para criar um novo app por meio de um StarterKit (bx dev create). Quando você tiver o projeto do seu app, abra-o em seu IDE do JetBrains.

Se você tiver um app do lado do servidor genérico, selecione Ferramentas > IBM Cloud Developer Tools > Ativar app para o IBM Cloud. Isso verificará e incluirá todos os arquivos necessários para permitir que você construa o app localmente, bem como implementá-lo no IBM Cloud usando como um app Cloud Foundry ou dentro de um cluster do Kubernetes.

Desenvolva seu aplicativo nativo de nuvem normalmente, usando as ações básicas construir/executar/implementar do menu IDT. Se você precisar executar ações que não estão no menu, bastará abrir a guia Terminal e inserir os comandos desejados manualmente.

