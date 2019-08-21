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

# Gestión de recursos de DevOps con la CLI
{: #managing-devops-resources-cli}

Puede utilizar la [CLI de {{site.data.keyword.dev_cli_notm}}](/docs/cli?topic=cloud-cli-getting-started) para gestionar recursos de DevOps directamente desde la línea de mandatos. Aprenda a utilizar la CLI para ver cadenas de herramientas de DevOps, conductos y registros de conductos.
{: shortdesc}

## Antes de empezar
{: #set-toolchain-view}

La vista de cadenas de herramientas depende del grupo de recursos de destino actual. Utilice los mandatos siguientes para identificar el grupo de recursos de destino actual y para cambiarlo si lo desea.

* Para ver el grupo de recursos de destino actual, ejecute:
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* Si no se ha definido ningún grupo de recursos, o si desea cambiar el grupo de recursos, ejecute: 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## Visualización de una cadena de herramientas
{: #viewing-toolchains}

Puede ver información de la cadena de herramientas desde la línea de mandatos o puede verla en un navegador.

* Para ver las cadenas de herramientas del grupo de recursos de destino, ejecute:
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* Para ver detalles sobre dicha cadena de herramientas, ejecute:
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* Para ver los detalles de la cadena de herramientas en el navegador, ejecute:
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## Visualización de un conducto
{: #viewing-pipeline}

Para obtener los detalles necesarios para invocar un conducto, ejecute `ibmcloud dev toolchains` para obtener el nombre de la cadena de herramientas. Si ya se conoce el nombre, ejecute `ibmcloud dev toolchain-get [toolchain-name]` para obtener los detalles de la cadena de herramientas. 

* Para obtener los detalles de un conducto y sus etapas, identifique el conducto y su ID para ejecutar el mandato siguiente:
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* Utilizando el ID de conducto del mandato anterior, puede ejecutar el conducto:
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  Este mandato invoca una ejecución de la etapa y sus trabajos. Una ejecución correcta da como resultado la ejecución del trabajo para cada trabajo en la etapa seleccionada.

## Visualización de los registros de un conducto
{: #viewing-pipeline-logs}

* Para ver los registros de la ejecución de un conducto, ejecute:
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* Para filtrar los registros por etapa, aplique el mandato anterior y añada el ID de la etapa:
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## Mandatos útiles de DevOps
{: #helpful-devops-commands}

Utilice los siguientes mandatos `ibmcloud dev` para gestionar los recursos de DevOps.

### Mandatos de cadena de herramientas
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) Ver una lista de las cadenas de herramientas del grupo de recursos de destino.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) Ver los detalles de una cadena de herramientas seleccionada en el grupo de recursos de destino.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) Abrir la cadena de herramientas seleccionada en el navegador.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) Suprimir una cadena de herramientas.

### Mandatos de conducto
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) Ver los detalles del conducto de una cadena de herramientas.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) Ejecutar un conducto.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) Abrir el conducto en el navegador.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) Ver los registros de la ejecución de un conducto.

Para obtener más información revise la [consulta de mandatos](/docs/cli/idt?topic=idt-cli) completa de `ibmcloud dev`.
