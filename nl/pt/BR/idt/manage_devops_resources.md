---

copyright:
  years: 2019
lastupdated: "2019-06-27"

keywords: cli, ibmcloud dev toolchains, ibmcloud dev toolchain-get, ibmcloud dev toolchain-delete, ibmcloud dev toolchain-open, ibmcloud dev pipeline-get, ibmcloud dev pipeline-invoke, ibmcloud dev pipeline-log, ibmcloud dev pipeline-open, ibmcloud dev, cli blog, cli video, cli reference

subcollection: cloud-cli

---

{:new_window: target="_blank"}  
{:shortdesc: .shortdesc}  
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# Gerenciando recursos do DevOps com a CLI
{: #managing-devops-resources-cli}

É possível usar a [CLI do {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-getting-started) para gerenciar recursos do DevOps diretamente da linha de comandos. Aprenda a usar a CLI para visualizar cadeias de ferramentas, pipelines e logs de pipeline do DevOps.
{: shortdesc}

## Antes de começar
{: #set-toolchain-view}

A visualização da cadeia de ferramentas depende do atual grupo de recursos de destino. Use os comandos a seguir para identificar o seu atual grupo de recursos de destino e mude-o se desejar.

* Para visualizar o atual grupo de recursos de destino, execute:
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* Se nenhum grupo de recursos estiver configurado ou se você desejar mudar o grupo de recursos, execute: 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## Visualizando uma cadeia de ferramentas
{: #viewing-toolchains}

É possível visualizar as informações da cadeia de ferramentas por meio da linha de comandos ou visualizá-las em um navegador.

* Para visualizar cadeias de ferramentas no grupo de recursos de destino, execute:
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* Para visualizar os detalhes sobre essa cadeia de ferramentas, execute:
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* Para visualizar os detalhes da cadeia de ferramentas no navegador, execute:
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## Visualizando um pipeline
{: #viewing-pipeline}

Para obter os detalhes necessários para chamar um pipeline, execute `ibmcloud dev toolchains` para obter o nome da cadeia de ferramentas. Se o nome já for conhecido, execute `ibmcloud dev toolchain-get [toolchain-name]` para obter os detalhes da cadeia de ferramentas. 

* Para obter os detalhes de um pipeline e seus estágios, identifique o pipeline e seu ID para executar o comando a seguir:
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* Usando o ID do pipeline do comando anterior, é possível executar o pipeline:
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  Esse comando chama uma execução do estágio e suas tarefas. Uma execução bem-sucedida resulta na execução da tarefa para cada tarefa no estágio selecionado.

## Visualizando logs de pipeline
{: #viewing-pipeline-logs}

* Para visualizar os logs de uma execução de pipeline, execute:
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* Para filtrar os logs por estágio, aplique o comando anterior e inclua o ID do estágio:
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## Comandos úteis do DevOps
{: #helpful-devops-commands}

Use os comandos `ibmcloud dev` a seguir para gerenciar os recursos do DevOps.

### Comandos da cadeia de ferramentas
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) Visualize uma lista de cadeias de ferramentas no grupo de recursos de destino.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) Visualize os detalhes de uma cadeia de ferramentas selecionada no grupo de recursos de destino.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) Abra a cadeia de ferramentas selecionada no navegador.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) Exclua uma cadeia de ferramentas.

### Comandos de pipeline
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) Visualize os detalhes de pipeline de uma cadeia de ferramentas.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) Execute um pipeline.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) Abra o pipeline no navegador.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) Visualize os logs de execução de um pipeline.

Para obter mais informações, consulte a [referência completa de comando](/docs/cli/idt?topic=idt-cli) `ibmcloud dev`.
