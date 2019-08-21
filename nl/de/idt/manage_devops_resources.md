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

# DevOps-Ressourcen mit der Befehlszeilenschnittstelle verwalten
{: #managing-devops-resources-cli}

Sie können die [{{site.data.keyword.dev_cli_notm}}-Befehlszeilenschnittstelle](/docs/cli?topic=cloud-cli-getting-started) verwenden, um DevOps-Ressourcen direkt über die Befehlszeile zu verwalten. Erfahren Sie, wie Sie die Befehlszeilenschnittstelle zum Anzeigen von DevOps-Toolchains, Pipelines und Pipelineprotokollen verwenden können.
{: shortdesc}

## Vorbereitende Schritte
{: #set-toolchain-view}

Was in der Toolchainansicht angezeigt wird, hängt von der aktuell als Ziel ausgewählten Ressourcengruppe ab. Geben Sie mit den folgenden Befehlen Ihre aktuelle Zielgruppenressource an und ändern Sie sie bei Bedarf.

* Führen Sie den folgenden Befehl aus, um die als Ziel angegebene Ressourcengruppe anzuzeigen:
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* Wenn keine Ressourcengruppe festgelegt ist oder wenn Sie die Ressourcengruppe ändern möchten, führen Sie den folgenden Befehl aus: 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## Toolchain anzeigen
{: #viewing-toolchains}

Sie können die Toolchain-Informationen über die Befehlszeile oder in einem Browser anzeigen.

* Führen Sie den folgenden Befehl aus, um Toolchains in der Zielressourcengruppe anzuzeigen:
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* Führen Sie den folgenden Befehl aus, um Details zu dieser Toolchain anzuzeigen:
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* Führen Sie den folgenden Befehl aus, um die Toolchain-Details im Browswer anzuzeigen:
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## Pipeline anzeigen
{: #viewing-pipeline}

Um die Details abzurufen, die zum Aufrufen einer Pipeline erforderlich sind, führen Sie `ibmcloud dev toolchains` aus, um den Namen der Toolchain zu erhalten. Wenn der Name bereits bekannt ist, führen Sie den Befehl `ibmcloud dev toolchain-get [toolchain-name]` aus, um die Details der Toolchain abzurufen. 

* Um die Details einer Pipeline und ihrer Stages abzurufen, geben Sie die Pipeline und deren ID an, um den folgenden Befehl auszuführen:
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* Mit der Pipeline-ID aus dem vorherigen Befehl können Sie die Pipeline ausführen:
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  Mit diesem Befehl wird eine Ausführung der Stage und ihrer Jobs aufgerufen. Eine erfolgreiche Ausführung führt zu der Jobausführung für jeden Job in der ausgewählten Stage.

## Pipelineprotokolle anzeigen
{: #viewing-pipeline-logs}

* Um die Protokolle von der Ausführung einer Pipeline anzuzeigen, führen Sie Folgendes aus:
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* Wenn Sie die Protokolle nach der Stage filtern möchten, wenden Sie den vorherigen Befehl an und fügen Sie die Stage-ID hinzu:
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## Hilfreiche DevOps-Befehle
{: #helpful-devops-commands}

Verwenden Sie die folgenden `ibmcloud dev`-Befehle, um DevOps-Ressourcen zu verwalten.

### Toolchain-Befehle
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) Zeigen Sie eine Liste der Toolchains in der Zielressourcengruppe an.
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) Zeigen Sie die Details für eine ausgewählte Toolchain in der Zielressourcengruppe an.
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) Öffnen Sie die ausgewählte Toolchain im Browser.
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) Löschen Sie eine Toolchain.

### Pipelinebefehle
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) Zeigen Sie die Details der Pipeline einer Toolchain an.
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) Führen Sie eine Pipeline aus.
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) Öffnen Sie die Pipeline im Browser.
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) Zeigen Sie die Protokolle einer Ausführung der Pipeline an.

Weitere Informationen finden Sie in der vollständigen [Befehlsreferenz](/docs/cli/idt?topic=idt-cli) zu `ibmcloud dev`.
