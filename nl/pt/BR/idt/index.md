---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-04"

keywords: cli, developing apps, deploying apps, create apps, ibmcloud dev enable, ibmcloud dev create, local containers, ibmcloud dev run, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Desenvolvendo e implementando seus apps
{: #developing}

O desenvolvendo de apps nativos do Cloud usando a CLI do {{site.data.keyword.dev_cli_notm}} segue
um fluxo bastante simples:

1. [ Criar ou ativar um app ](#idt-create).
2. [Codifique, construa e execute](#code-build-run) o seu app localmente usando contêineres.
3. [ Implemente ](#cli-deploy)  seu app para o  {{site.data.keyword.cloud_notm}}.

## Criar ou ativar um app
{: #idt-create}

Há diversas maneiras pelas quais é possível criar um app.
- [Console da web de serviços de aplicativo](https://cloud.ibm.com/developer/appservice/dashboard) para apps genéricos da web e microsserviços
- [Painel do Watson](https://cloud.ibm.com/developer/watson/dashboard) para criar apps do iniciador ativado para recursos com base no Watson.
    - Outros painéis baseados no segmento de mercado ou na tecnologia estão disponíveis no menu
"Hamburger" na página inicial do {{site.data.keyword.cloud_notm}}. Todos têm uma abordagem semelhante de usar Kits do iniciador para criar novos apps.
- Comando [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) das CLIs do {{site.data.keyword.dev_cli_notm}} para criar um novo app.
- Comando [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) das CLIs do {{site.data.keyword.dev_cli_notm}} para ativar rapidamente a nuvem em um app existente do lado do servidor.

Para qualquer um dos métodos de criação anteriores, o fluxo é semelhante. É possível escolher o tipo de projeto, a linguagem de implementação e o padrão de app a serem usados. Também é possível optar por incluir serviços em seu app, como autenticação ou persistência. Finalmente, é possível escolher ativar o recurso do DevOps para o app que fornece uma cadeia de ferramentas completa de controle de fonte e comunicações de equipe e um pipeline que é acionado em cada confirmação para validar, construir e implementar o seu app no {{site.data.keyword.cloud_notm}}.

![Fluxo de criação de amostra usando a CLI do {{site.data.keyword.dev_cli_notm}}](create_flow.png "Fluxo de criação de amostra usando a CLI do {{site.data.keyword.dev_cli_notm}}") <br> Figura 2. Fluxo de criação de amostra usando a CLI do {{site.data.keyword.dev_cli_notm}}

A CLI do {{site.data.keyword.dev_cli_notm}} trabalha estreitamente junto para fornecer uma experiência contínua durante o desenvolvimento. Os projetos que são criados dentro de qualquer um dos consoles da web fornecem um botão **Fazer download de código** para fazer download do código-fonte gerado para a sua estação de trabalho para mais desenvolvimento.

### Comandos úteis da CLI
{: #helpful}

Os comandos da CLI a seguir ajudam a trabalhar com seu projeto e com os consoles da web:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) para puxar diretamente um
código-fonte gerado por apps para a sua estação de trabalho
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) para abrir seu navegador para a página do projeto do app atual no {{site.data.keyword.cloud_notm}}
- Comando [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) para criar um novo app.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) para excluir o app atual da área do projeto do {{site.data.keyword.cloud_notm}}.
- Comando [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) para ativação de nuvem em um app do lado do servidor existente.
- [`get-credenciais`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) para obter
credenciais que são necessárias pelo projeto para ativar o uso de serviços de limite.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) para listar todos os apps que você criou na organização/no espaço atualmente selecionado, por meio da CLI ou dos consoles.

### Explorando a estrutura do projeto do app
{: #exploring-project}

Os projetos que são criados ou ativados para uso com a ferramenta são fornecidos com configurações
pré-definidas contidas no arquivo `cli-config.yml`. O `cli-config.yml` tem entradas padrão que são usadas pelos comandos da ferramenta que podem ser substituídas por valores que são passados através da linha de comandos.

### Blogs e vídeos de referência
{: #ref1}

- Vídeo: [Instalando ferramentas de desenvolvedor do {{site.data.keyword.cloud_notm}} no Ubuntu Linux](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
- Blog: [Ativar projetos existentes para o IBM Cloud com a CLI do IBM Cloud Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

## Codificar, construir e executar
{: #code-build-run}

Uma vez que o seu projeto for criado, caberá a você transformá-lo em algo útil. O fluxo geral consiste em editar o código-fonte e, em seguida, executar [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) para compilar o app dentro de um contêiner local específico para a linguagem e a configuração de seu app. Dependendo da linguagem de apps e do gerador que é usado, há um ou mais contêineres padronizados para suportar
construção e execução localmente. Normalmente, há um contêiner de "ferramentas" para construções e depuração local. Esse contêiner tem ferramentas extras e recursos para auxiliá-lo no desenvolvimento. Há também um contêiner de "execução" que simula de perto o ambiente de tempo de execução real de seu app quando ele é implementado na nuvem, no ambiente de contêiner baseado no Cloud Foundry ou no Kubernetes da IBM.

Você está livre para usar qualquer IDE ou editor que preferir para codificar o seu aplicativo. Oferecemos uma extensão para o editor do Microsoft Visual Studio Code (VSCode) que permite acessar todos os comandos do IDE diretamente de dentro do editor.

Quando o projeto for construído, execute o seu app usando [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) ou [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug). Isso executa o app dentro do contêiner adequado. Alguns padrões de apps suportam múltiplos contêineres externos para os seus apps. Eles são iniciados e configurados automaticamente durante a execução ou depuração. Há também um comando [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) que executa quaisquer casos de teste que estão associados ao app.

### Como os contêineres locais são usados
{: #local-containers}

A CLI do {{site.data.keyword.dev_cli_long}} usa dois contêineres para construir e testar o seu aplicativo. O primeiro é o contêiner de ferramentas, que contém os utilitários necessários para construir e testar seu aplicativo. O Dockerfile para esse contêiner é definido pelo parâmetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Você pode pensar nisso como um contêiner de desenvolvimento, pois ele contém as ferramentas normalmente usadas para o desenvolvimento de um tempo de execução específico.

O segundo contêiner é o contêiner de execução. Esse contêiner tem um formato adequado para ser implementado para uso, por exemplo, no {{site.data.keyword.cloud}}. Como resultado, um ponto de entrada que inicia seu aplicativo é definido. Ao selecionar para executar o aplicativo por meio da CLI do {{site.data.keyword.dev_cli_short}},
ele usa esse contêiner. O Dockerfile para esse contêiner é definido pelo parâmetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

### Comandos úteis da CLI
{: #helpful2}

Os comandos da CLI a seguir ajudam você a trabalhar com o seu projeto durante os ciclos de código, construção e execução:
- [`build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) construa o projeto em um contêiner local.
- [`debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug) depure o seu aplicativo em um contêiner local.
- [`run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) execute o seu aplicativo em um contêiner local.
- [`shell`](/docs/cli/idt?topic=cloud-cli-idt-cli#shell) abra um shell em um contêiner local.
- [`status`](/docs/cli/idt?topic=cloud-cli-idt-cli#status) verifique o status dos contêineres usados pela CLI do {{site.data.keyword.dev_cli_notm}}.
- [`stop`](/docs/cli/idt?topic=cloud-cli-idt-cli#stop) Pare um contêiner
- [`test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) teste o seu aplicativo em um contêiner local.

### Depurando apps locais
{: #ref2}

- [Depurando apps locais](/docs/cli/idt?topic=cloud-cli-local-debug#local-debug)

## Implementação
{: #cli-deploy}

Sob um ambiente nativo de nuvem adequado, você usa um pipeline do DevOps totalmente funcional para gerenciar todas as implementações e uma riqueza de outros recursos. Durante o fluxo de criação, é possível configurar seu app para usar o DevOps do IBM Cloud. Se você não estiver pronto para usar o DevOps integrado, então, você usa [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) manualmente em seu app ou usa o comando de implementação dentro de seu próprio pipeline do DevOps.  

### Comandos úteis da CLI
{: #helpful3}

Os comandos da CLI a seguir ajudam a trabalhar com seu projeto durante o processo de implementação:
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) abre o console do {{site.data.keyword.cloud_notm}} para um projeto.
- [ ` deploy ` ](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy)  Implemente um aplicativo no  {{site.data.keyword.cloud_notm}}.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) visualize a URL de seu projeto.

### Blogs e vídeos de referência
{: #ref3}

- Blog: [Implementando no {{site.data.keyword.cloud_notm}} Private com a CLI do {{site.data.keyword.cloud_notm}} Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
- Blog: [Implementando no Kubernetes no {{site.data.keyword.cloud_notm}} com a CLI do {{site.data.keyword.cloud_notm}} Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
