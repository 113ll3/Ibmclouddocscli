---

copyright:

  years: 2018

lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# IBM Developer Tools para IDEs do Jetbrains
{: #ibm-dev-tools-for-jetbrains}

O IBM Developer Extension para IDEs do Jetbrains, que incluem IntelliJ, WebStorm, Android Studio e
outros, fornece novas entradas de menu para acessar diretamente os comandos da CLI do IDT de dentro do IDE. Ele permite que acesse rapidamente um subconjunto de comandos `bx dev` para ambos os fluxos de trabalho Docker e CloudFoundry, incluindo a implementação do app, iniciar/parar/reiniciar apps no {{site.data.keyword.Bluemix_notm}}, visualizar logs de app remoto e muito mais, tudo sem a necessidade de sair do contexto do editor.
{:shortdesc}

![Captura de tela do IBM Developer Tools em execução no IDE WebStorm.](jetbrains.png "Exemplo do menu IDT em execução no IDE WebStorm")

## Dependências
{: #dependencies}

Para usar a extensão do IBM Developer Tools para IDEs baseados em Jetbrains, a
[CLI do IBM Cloud Developer Tools](index.html) precisa estar instalada em seu sistema.

## Instalação
{: #installation}

A maneira mais simples de instalar a extensão IBM Developers Tools para o IDE do Jetbrains é acessar a página [Jetbrains do repositório Github do IDT](https://github.com/IBM-Cloud/ibm-cloud-developer-tools/tree/master/jetbrains) e seguir as instruções.

## Uso
{: #usage}

É possível iniciar com um app do lado do servidor existente e ativá-lo para o IBM Cloud ou usar a CLI do IDT para criar um novo app por meio de um StarterKit (bx dev create). 
Quando você tiver seu projeto de apps, abra-o em seu IDE do JetBrains.

Se você tiver um app do lado do servidor genérico, selecione Ferramentas > IBM Cloud Developer Tools > Ativar app para o IBM Cloud. 
Isso verifica todos os arquivos necessários e inclui quaisquer arquivos que estejam ausentes, o que permite
construir o app localmente e implementá-lo no IBM Cloud usando um app do Cloud Foundry ou dentro de um cluster do Kubernetes.

Desenvolva seu app nativo de nuvem usando as ações básicas de construção/execução/implementação no
menu IDT. Se você precisar executar ações que não estão no menu, abra a guia Terminal e insira os comandos
desejados manualmente.

