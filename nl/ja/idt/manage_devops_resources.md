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

# CLI による DevOps リソースの管理
{: #managing-devops-resources-cli}

[{{site.data.keyword.dev_cli_notm}} CLI](/docs/cli?topic=cloud-cli-getting-started) を使用して、コマンド・ラインから直接 DevOps リソースを管理できます。CLI を使用して、DevOps ツールチェーン、パイプライン、パイプライン・ログを表示する方法について説明します。
{: shortdesc}

## 始める前に
{: #set-toolchain-view}

ツールチェーンは、現在ターゲットにしているリソース・グループに応じたものが表示されます。以下のコマンドを使用すると、現在ターゲットにしているリソース・グループを確認できます。必要に応じて変更することもできます。

* 現在ターゲットにしているリソース・グループを表示するには、以下を実行します。
  ```
  ibmcloud target
  ``` 
  {: codeblock}

* リソース・グループが設定されていない場合、または、リソース・グループを変更する場合には、以下を実行します。 
  ```
  ibmcloud target -g [resource-group]
  ```
  {: codeblock}

## ツールチェーンの表示
{: #viewing-toolchains}

ツールチェーンの情報をコマンド・ラインで表示できます。ブラウザーで表示することもできます。

* ターゲット・リソース・グループに含まれているツールチェーンを表示するには、以下を実行します。
  ```
  ibmcloud dev toolchains
  ```
  {: codeblock}

* 特定のツールチェーンの詳細を表示するには、以下を実行します。
  ```
  ibmcloud dev toolchain-get [toolchain-name]
  ```
  {: codeblock}

* ツールチェーンの詳細をブラウザーで表示するには、以下を実行します。
  ```
  ibmcloud dev toolchain-open [toolchain-name]
  ```
  {: codeblock}  

## パイプラインの表示
{: #viewing-pipeline}

パイプラインを呼び出すために必要な詳細情報を取得するには、`ibmcloud dev toolchains` を実行してツールチェーンの名前を取得します。名前が既にわかっている場合は、`ibmcloud dev toolchain-get[toolchain-name]` を実行して、ツールチェーンの詳細情報を取得します。 

* パイプラインとそのステージの詳細情報を取得するには、パイプラインとその ID を確認して以下のコマンドを実行します。
  ```
  ibmcloud dev pipeline-get [pipelineID]
  ```
  {: codeblock}

* 前のコマンドのパイプライン ID を使用して、パイプラインを実行できます。
  ```
  ibmcloud dev pipeline-run [pipelineID]
  ```
  {: codeblock}

  このコマンドによって、ステージとそのジョブの実行が呼び出されます。正常に実行されると、選択したステージの各ジョブが実行されます。

## パイプライン・ログの表示
{: #viewing-pipeline-logs}

* パイプラインの実行ログを表示するには、以下を実行します。
  ```
  ibmcloud dev pipeline-log [pipelineID]
  ```
  {: codeblock}

* ステージでログをフィルタリングするには、前のコマンドにステージ ID を追加して実行します。
  ```
  ibmcloud dev pipeline-log [pipelineID] --stage-id [stageID]
  ```
  {: codeblock}

## 便利な DevOps コマンド
{: #helpful-devops-commands}

次の `ibmcloud dev` コマンドを使用して、DevOps リソースを管理できます。

### ツールチェーンに関するコマンド
- [`toolchains`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchains) ターゲット・リソース・グループに含まれているツールチェーンのリストを表示します。
- [`toolchain-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-get) ターゲット・リソース・グループに含まれている、選択したツールチェーンの詳細情報を表示します。
- [`toolchain-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-open) 選択したツールチェーンをブラウザーで開きます。
- [`toolchain-delete`](/docs/cli/idt?topic=cloud-cli-idt-cli#toolchain-delete) ツールチェーンを削除します。

### パイプラインに関するコマンド
- [`pipeline-get`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-get) ツールチェーンのパイプラインの詳細情報を表示します。
- [`pipeline-run`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-run) パイプラインを実行します。
- [`pipeline-open`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-open) パイプラインをブラウザーで開きます。
- [`pipeline-log`](/docs/cli/idt?topic=cloud-cli-idt-cli#pipeline-log) パイプラインの実行ログを表示します。

詳細については、完全な `ibmcloud dev` [コマンド・リファレンス](/docs/cli/idt?topic=idt-cli)を参照してください。
