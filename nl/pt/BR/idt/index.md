---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-29"

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

O desenvolvimento de aplicativos nativos de nuvem com a CLI do {{site.data.keyword.dev_cli_notm}} segue um fluxo bastante simples:

1. [Crie ou ative um app para implementação](#idt-create).
2. [Codifique, construa e execute](#code-build-run) seu app localmente usando contêineres.
3. [Implemente](#cli-deploy) seu app no {{site.data.keyword.cloud_notm}}.

## Criar ou ativar um app para implementação de nuvem
{: #idt-create}

Há diversas maneiras pelas quais é possível criar um app.
- [Console da web de serviços de aplicativo](https://cloud.ibm.com/developer/appservice/dashboard) para apps genéricos da web e microsserviços
- [Painel do Watson](https://cloud.ibm.com/developer/watson/dashboard) para criar apps do iniciador ativado para recursos com base no Watson.
    - Outros painéis baseados no segmento de mercado ou na tecnologia estão disponíveis no menu
"Hamburger" na página inicial do {{site.data.keyword.cloud_notm}}. Todos adotam uma abordagem semelhante a usar kits do iniciador para criar novos apps.
- Comando [`ibmcloud dev create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) das CLIs do {{site.data.keyword.dev_cli_notm}} para criar um novo app.
- Comando [`ibmcloud dev enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) das CLIs do {{site.data.keyword.dev_cli_notm}} para ativar rapidamente a nuvem em um app existente do lado do servidor.

Para qualquer um dos métodos de criação anteriores, o fluxo é semelhante. Selecione o tipo de projeto, a linguagem de implementação e o padrão de app a serem usados. Também é possível optar por incluir serviços em seu app, como autenticação ou persistência. Finalmente, é possível incluir o recurso DevOps no app, que fornece uma cadeia de ferramentas completa de controle de versão e comunicações de equipe. Incluindo um pipeline que é acionado em cada confirmação para validar, construir e implementar seu app para o {{site.data.keyword.cloud_notm}}.

![Amostra de fluxo de criação que usaa CLI do {{site.data.keyword.dev_cli_notm}}](create_flow.png "Amostra de fluxo de criação que usa a CLI do {{site.data.keyword.dev_cli_notm}}") <br> Figura 2. Amostra de fluxo de criação que usa a CLI do {{site.data.keyword.dev_cli_notm}}


A CLI do {{site.data.keyword.dev_cli_notm}} trabalha estreitamente junto para fornecer uma experiência suave durante o desenvolvimento. Os projetos que são criados nos consoles da web fornecem um botão **Fazer download de código** para fazer download do código-fonte
gerado para sua estação de trabalho para desenvolvimento adicional.

### Comandos úteis da CLI
{: #helpful}

Os comandos da CLI `ibmcloud dev` a seguir ajudam a trabalhar com seu projeto
e os consoles da web:
- [`code`](/docs/cli/idt?topic=cloud-cli-idt-cli#code) Use para fazer download de um código-fonte de apps em sua estação de trabalho.
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) Abre seu navegador na página do projeto do app atual no {{site.data.keyword.cloud_notm}}.
- [`create`](/docs/cli/idt?topic=cloud-cli-idt-cli#create) O comando para criar um novo app.
- [`delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#delete) Usado para excluir o app atual da área do projeto do {{site.data.keyword.cloud_notm}}.
- [`enable`](/docs/cli/idt?topic=cloud-cli-idt-cli#enable) O comando
para habilitar na nuvem um app existente no lado do servidor.
- [`get-credentials`](/docs/cli/idt?topic=cloud-cli-idt-cli#get-credentials) Para obter credenciais que são requeridas pelo projeto para ativar o uso de serviços de limite.
- [`list`](/docs/cli/idt/?topic=cloud-cli-idt-cli#list) Para
listar todos os apps que são criados na organização e no espaço selecionados atualmente, na CLI ou nos consoles.

### Explorando a estrutura do projeto do app
{: #exploring-project}

Os projetos que são criados ou ativados para uso com as ferramentas do desenvolvedor vêm com configurações pré-configuradas encapsuladas no arquivo `cli-config.yml`. O `cli-config.yml` possui entradas padrão que são usadas pelos comandos `ibmcloud dev` que você pode substituir por valores que são passados por meio da linha de comandos.

### Blogs e vídeos de referência
{: #ref1}

- Vídeo: [Instalando ferramentas de desenvolvedor do {{site.data.keyword.cloud_notm}} no Ubuntu Linux&trade;](https://www.youtube.com/watch?v=sr7KjHAKpEs){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
- Blog: [Enable existing projects for IBM Cloud with the {{site.data.keyword.dev_cli_short}} CLI](https://www.ibm.com/blogs/bluemix/2017/09/enable-existing-projects-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")

## Codificar, construir e executar
{: #code-build-run}

Uma vez que o seu projeto for criado, caberá a você transformá-lo em algo útil. O fluxo geral consiste em editar o código-fonte e, em seguida, executar [`ibmcloud dev build`](/docs/cli/idt?topic=cloud-cli-idt-cli#build) para compilar o app dentro de um contêiner local específico para a linguagem e a configuração de seu app. Dependendo de seu idioma e do gerador de apps que é usado, há um ou mais contêineres que são definidos por padrão para suportar a construção e a execução localmente. Normalmente, há um contêiner de "ferramentas" para construções e depuração local. Esse contêiner tem ferramentas extras e recursos para auxiliá-lo no desenvolvimento. Há também um contêiner de "execução" que imita o ambiente de tempo de execução de seu app quando ele é implementado na nuvem, no Cloud Foundry ou no ambiente de contêiner baseado em Kubernetes da IBM.

Você é livre para usar qualquer IDE ou editor que preferir para codificar seu aplicativo. O {{site.data.keyword.IBM_notm}} oferece uma extensão para o editor do Microsoft&trade;
Visual Studio Code (VSCode) que permite acessar todos os comandos IDE diretamente no editor.

Quando o projeto for construído, execute seu app usando [`ibmcloud dev run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run) ou [`ibmcloud dev debug`](/docs/cli/idt?topic=cloud-cli-idt-cli#debug). O app é executado dentro do contêiner adequado. Alguns padrões de apps suportam múltiplos contêineres externos para os seus apps. Os apps iniciam e configuram automaticamente durante a execução ou depuração. Há também um comando [`ibmcloud dev test`](/docs/cli/idt?topic=cloud-cli-idt-cli#test) que executa quaisquer casos de teste que estão associados ao app.

### Como os contêineres locais são usados
{: #local-containers}

A CLI do {{site.data.keyword.dev_cli_long}} usa dois contêineres para construir e testar o seu aplicativo. O primeiro é o contêiner de ferramentas, que contém os utilitários necessários para construir e testar seu aplicativo. O Dockerfile para esse contêiner é definido pelo parâmetro [`dockerfile-tools`](/docs/cli/idt?topic=cloud-cli-idt-cli#command-parameters). Você pode pensar nisso como um contêiner de desenvolvimento, pois ele contém as ferramentas normalmente usadas para o desenvolvimento de um tempo de execução específico.

O segundo contêiner é o contêiner de execução. Esse contêiner tem um formato adequado para ser implementado para uso, por exemplo, no {{site.data.keyword.cloud}}. Como resultado, um ponto de entrada que inicia seu aplicativo é definido. Ao selecionar para executar o aplicativo por meio da CLI do {{site.data.keyword.dev_cli_short}},
ele usa esse contêiner. O Dockerfile para esse contêiner é definido pelo parâmetro [`dockerfile-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#run-parameters).

### Comandos úteis da CLI
{: #helpful2}

Os comandos da CLI a seguir ajudam a depurar seu projeto:
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

Em um ambiente nativo de nuvem adequado, você usa um pipeline do DevOps totalmente funcional
para gerenciar todas as implementações e uma riqueza de outros recursos. Durante o fluxo de criação, é possível configurar seu app para usar o DevOps do IBM Cloud. Se você não estiver pronto para usar o DevOps integrado, poderá executar manualmente o [`ibmcloud dev deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) para implementar seu app ou usar o comando `deploy` em seu próprio pipeline do DevOps.

### Comandos úteis da CLI
{: #helpful3}

Os comandos da CLI a seguir ajudam a trabalhar com seu projeto durante o processo de implementação:
- [`console`](/docs/cli/idt?topic=cloud-cli-idt-cli#console) abre o console do {{site.data.keyword.cloud_notm}} para um projeto.
- [`deploy`](/docs/cli/idt?topic=cloud-cli-idt-cli#deploy) Para implementar um aplicativo no {{site.data.keyword.cloud_notm}}.
- [`view`](/docs/cli/idt?topic=cloud-cli-idt-cli#view) visualize a URL de seu projeto.

### Blogs e vídeos de referência
{: #ref3}

- Blog: [Implementando no {{site.data.keyword.cloud_notm}} Private com a CLI do {{site.data.keyword.cloud_notm}} Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/deploying-ibm-cloud-private-ibm-cloud-developer-tools-cli/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
- Blog: [Implementando no Kubernetes no {{site.data.keyword.cloud_notm}} com a CLI do {{site.data.keyword.cloud_notm}} Developer Tools](https://www.ibm.com/blogs/bluemix/2017/09/deploying-kubernetes-ibm-cloud-ibm-cloud-developer-tools-cli/){: new_window} ![Ícone de link externo](../../icons/launch-glyph.svg "Ícone de link externo")
