---

copyright:

   years: 2017, 2018

lastupdated: "2018-08-28"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}
{:tip: .tip}

# {{site.data.keyword.dev_cli_notm}} CLI プラグイン (ibmcloud dev) コマンド
{: #idt-cli}

バージョン: 1.2.0
リリース: 2018 年 3 月 8 日

2018 年 5 月、{{site.data.keyword.Bluemix_notm}} CLI コマンドは `bluemix` および `bx` から `ibmcloud` に変更されました。 ただし、後日削除されるまで、`bluemix` および `bx` CLI CLI コマンドを引き続き使用できます。
{: tip}

以下の {{site.data.keyword.dev_cli_notm}} CLI (ibmcloud dev) コマンドを使用して、アプリケーションの作成、管理、デプロイ、デバッグ、およびテストを行います。

- [build](#build): ローカル・コンテナー内にアプリケーションをビルドします。
- [code](#code): アプリケーションのコードをダウンロードします。
- [console](#console): アプリケーションの IBM Cloud コンソールを開きます。
- [create](#create): 新規アプリケーションを作成し、オプションでサービスを追加できます。
- [debug](#debug): ローカル・コンテナー内でアプリケーションをデバッグします。
- [delete](#delete): スペースからアプリケーションを削除します。
- [deploy](#deploy): アプリケーションを IBM Cloud にデプロイします。
- [diag](#diag): インストール済みの従属物に関するバージョン情報を表示します。
- [edit](#edit): 既存のアプリケーションにサービスを追加、あるいは既存のアプリケーションからサービスを削除します。
- [enable](#enable): IBM Cloud Developer Tools で使用するために、既存のアプリケーションを更新します。
- [get-credentials](#get-credentials): 接続された IBM Cloud サービスを使用可能にするためにアプリケーションによって必要とされる資格情報を取得します。
- [help](#help): CLI の構文と引数に関するヘルプ。
- [list](#list): リソース・グループ内のすべての IBM Cloud アプリケーションをリストします。
- [run](#run): ローカル・コンテナー内でアプリケーションを実行します。
- [shell](#shell): ローカル・コンテナーにシェルを開きます。
- [status](#status): CLI で使用されるコンテナーの状況をチェックします。
- [stop](#stop): コンテナーを停止します。
- [test](#test): ローカル・コンテナー内でアプリケーションをテストします。
- [view](#view): テストや表示目的で、デプロイされたアプリケーションの URL を表示します。
- [compound commands](#compound): 単一のコマンド・ライン・ステートメント内で複数のコマンドを実行します。



## build
{: #build}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`build` コマンドを使用して、アプリケーションをビルドできます。 `test`、`debug`、および `run` の各コマンドでは、コンパイル済みアプリケーションが検出される必要があるため、`build` 操作を事前に実行する必要があります。  

`run` を除くすべての用途に関して、アプリケーションをビルドするときは、`build-cmd-debug` 構成エレメントを使用します。 デバッグ用のアプリケーションをビルドする際は、コマンド・ライン・オプション `--debug` を指定します。  `run` コマンドで使用するためのアプリケーションをビルドするときは、`build-cmd-run` 構成エレメントを使用します。

複数のコンテナーを使用してビルドするには、`cli-config.yml` で指定されている [Compose](https://docs.docker.com/compose/overview/) ファイルがアプリケーションに含まれているか、`dockerfile-tools` コマンド・パラメーターを使用して、このファイルを提供できなければなりません。 詳しくは、[Compose ファイル](/docs/apps/projects/compose_file.html)を参照してください。

現行アプリケーション・ディレクトリー内で以下のコマンドを実行して、アプリケーションをビルドします。  

```
ibmcloud dev build [--debug]
```
{: codeblock}



## code
{: #code}

`code` コマンドを使用して、以前に作成されたアプリケーションをアプリケーションのテンプレート・コードおよび {{site.data.keyword.Bluemix_notm}} の構成ファイルとともにダウンロードします。  以前に作成したアプリケーションの 2 次コピーを抽出する必要がある場合に便利です。

以下のコマンドを実行して、指定したアプリケーションからコードをダウンロードします。

```
ibmcloud dev code <applicationName>
```
{: codeblock}


## console
{: #console}

`console` コマンドを使用して、Web ブラウザーに IBM Cloud 上のアプリケーションの Web コンソールを開きます。  `ibmcloud dev console` コマンドはアプリケーションのフォルダー内から実行できます。そうすると、CLI によって、現行ディレクトリーと同じアプリケーション ID を持つ、IBM Cloud 上の一致するアプリケーションの検索が試行されます。 一致する名前を検出できない場合、システムは、指定されたアプリケーションの代わりに IBM Cloud の Web and Mobile ダッシュボードを開きます。

アプリケーション名を指定できます。そうすると、CLI は、フォルダー/アプリケーション名に基づいたマッチングをスキップします。 この場合、CLI は、指定されたアプリケーションのコンソールを Web ブラウザーに開きます。  

以下のコマンドを実行して、Web ブラウザーにアプリケーションの Web コンソールを開きます。

```
ibmcloud dev console [applicationName]
```
{: codeblock}


## create
{: #create}

アプリケーションを作成し、リソース・タイプ、言語、スターター・キット、および DevOps ツールチェーンのオプションなど、すべての情報を求めるプロンプトを出します。 アプリケーションは現行ディレクトリー内に作成されます。

現行ディレクトリー内にアプリケーションを作成し、プロジェクトにサービスを関連付けるには、以下のコマンドを実行します。

```
ibmcloud dev create
```
{: codeblock}


## debug
{: #debug}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`debug` コマンドによって、アプリケーションをデバッグできます。 まず、`--debug` 引数を指定した build コマンドを使用して、アプリケーションに対するビルドが実行される必要があります。 `debug` コマンドを開始すると、コンテナーが開始され、それによりデバッグ・ポート (複数可) が提供されます。ポートは、cli-config.yml 内の `container-port-map-debug` 値で定義されるか、コマンド・ラインで指定されます。 お好みのデバッグ・ツールをポートに接続すれば、通常どおりアプリケーションをデバッグできます。

まず、アプリケーションをコンパイルします。

```
ibmcloud dev build --debug
```
{: codeblock}

開始するには、現行アプリケーション・ディレクトリー内で以下のコマンドを実行して、アプリケーションをデバッグします。

```
ibmcloud dev debug
```
{: codeblock}

デバッグするには、デバッグ・ツールを指定のポートに接続します。

デバッグ・セッションを終了するには、`CTRL-C` を使用します。


### debug コマンド・パラメーター
{: #debug-parameters}

以下のパラメーターは、`debug` コマンド専用のパラメーターで、アプリケーションのデバッグを支援するものです。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `container-port-map-debug`
{: #port-map-debug}

* デバッグ・ポートのポート・マッピング。 最初の値は、ホスト OS で使用するポートで、2 番目の値は、コンテナーのポートです [host-port:container-port]。
* 使用法: `ibmcloud dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* デバッグ用のコードをビルドするために使用されるパラメーター。
* 使用法: `ibmcloud dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* ツール・コンテナー内のデバッグを起動するコマンドを指定するために使用されるパラメーター。 `build-cmd-debug` によってアプリケーションがデバッグ・モードで開始された場合、このパラメーターを使用します。
* 使用法: `ibmcloud dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

`delete` コマンドを使用して、{{site.data.keyword.Bluemix}} スペースからアプリケーションを削除します。 パラメーターなしでコマンドを実行して、使用可能なアプリケーションをリストし、削除するアプリケーションを番号付きリストから選択できます。 アプリケーション・コードおよびディレクトリーはローカル・ディスク・スペースからは削除されません。

以下のコマンドを実行して、{{site.data.keyword.Bluemix}} からアプリケーションを削除します。

```
ibmcloud dev delete <applicationName>
```
{: codeblock}


**注:** {{site.data.keyword.Bluemix}} サービスは、削除**されません**。


## deploy
{: #deploy}

アプリケーションは、Cloud Foundry アプリケーションまたはコンテナーとしてデプロイできます。

Cloud Foundry アプリケーションとして {{site.data.keyword.Bluemix}} にデプロイする前に、`manifest.yml` ファイルがアプリケーションのルート・ディレクトリーに存在する必要があります。

アプリケーションをコンテナーとしてデプロイする前に、[Kubernetes](https://kubernetes.io/) と [Helm](https://github.com/kubernetes/helm) をローカルにインストールする必要があります。 Helm クライアント・バージョンが Helm サーバー・バージョンよりも新しくないことを確認してください。 `helm version` を実行することで、それら両方のバージョンを確認できます。 クライアント・バージョンには、v2.4.2 を使用することを推奨します。

アプリケーションを Kubernetes にデプロイするには、 `cli-config.yml` 内で `deploy-target` に `container` を指定するか、パラメーター `-t container` を使用する必要があります。

Kubernetes デプロイメントの構成に必要なその他パラメーターは、以下に示すように `cli-config.yml` 内に指定することも、コマンド・ライン引数を使用することもできます。 これらを `cli-config.yml` 内に定義しない場合、パラメーター `-t container` を指定してデプロイする必要があり、その他すべての値について、プロンプトが出されます。

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

以下の例に示すように、`cli-config.yml` 内で、Helm チャートの場所を `chart-path` プロパティーに定義し、`deploy-image-target` を構成するように選択できます。 `cli-config.yml` 内の `deploy-image-target` エレメントが、`chart/values.yml` ファイル内の `repository` エレメントおよび `tag` エレメントの代わりに使用されます。 具体的にデプロイ先を {{site.data.keyword.Bluemix}} にするには、構成エレメント `ibm-cluster` に、[チュートリアル: クラスターの作成](/docs/containers/cs_tutorials.html#cs_cluster_tutorial)の説明に従って {{site.data.keyword.Bluemix}} 内に作成した Kubernetes クラスターの名前を設定します。

プロビジョニング、構成、および Kubernetes クラスターへのデプロイについて詳しくは、[Deploy a scalable web application on Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes) チュートリアルを参照してください。

現行アプリケーション・ディレクトリー内で以下のコマンドを実行して、アプリケーションをビルドします。  

```
ibmcloud dev build
```
{: codeblock}

現行アプリケーション・ディレクトリー内で次のコマンドを実行して、アプリケーションをデプロイします。

```
ibmcloud dev deploy
```
{: codeblock}


### deploy コマンド・パラメーター
{: #deploy-parameters}

以下のパラメーターを `deploy` コマンドに指定して使用するか、アプリケーションの `cli-config.yml` ファイルを直接更新することで使用できます。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `chart-path`
{: #chart-path}

* コンテナー・デプロイメントの場合に使用されるパラメーターで、デプロイメントに使用する Helm チャートの場所を指定します。
* 使用法 `ibmcloud dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* 実行するデプロイメントのタイプを指示するために使用するオプションのパラメーター。  デフォルトのデプロイメント・タイプは、ビルドパックです。
* 使用法 `ibmcloud dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* デプロイメントのターゲット・イメージ名として (例えば、Docker レジストリーにタグ付けするため)、コンテナー・デプロイメントで使用されるパラメーター。  値にバージョンを含めることはできません (例えば、image-name:{version} などにはできません)。バージョンは、`deploy` によって自動的に増やされ、追加されます。
* 使用法 `ibmcloud dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* {{site.data.keyword.Bluemix}} へのコンテナー・デプロイメントの場合に、Kubernetes クラスターの名前を定義するために使用されるオプションのパラメーター。
* 使用法 `ibmcloud dev deploy --ibm-cluster [cluster-name]`

#### `host`
{: #host}

* Cloud Foundry にデプロイする場合に、アプリケーションのホスト名を定義するために使用されるオプションのパラメーター。
* 使用法 `ibmcloud dev deploy --host [hostname]`

#### `ドメイン (domain)`
{: #domain}

* Cloud Foundry にデプロイする場合に、アプリケーションのドメインを定義するために使用されるオプションのパラメーター。
* 使用法 `ibmcloud dev deploy --domain [domain]`


## diag
{: #diag}

このコマンドは、{{site.data.keyword.dev_cli_notm}} CLI のインストール済みの従属物のバージョン情報を表示するための診断として使用されます。これは、従属物が欠落しているかどうかの判別または問題のデバッグに特に役立ちます。

インストール済みの従属物のバージョンを表示するには、次のコマンドを実行します。

```
ibmcloud dev diag
```
{: codeblock}


## edit
{: #edit}

新しいサービスを追加したり、既存のサービスを接続および切断したり、既存のサービスを削除したりして、アプリケーションを編集します。 アプリケーション・ディレクトリーのルートで次のコマンドを実行します。

```
ibmcloud dev edit
```
{: codeblock}

アカウントに既存のサービスがない場合、このコマンドによって、サービス・グループのリストが表示され、ここからアプリケーションに接続するサービスを選択できます。

ただし、アカウントに既存のサービスがある場合は、このコマンドによってその既存のサービスのリストが表示され、各サービスがアプリケーションに接続されているかどうかが示されます。

接続済みサービスを選択すると、アプリケーションからサービスを切断したり、アカウントからサービスを削除したりするためのオプションが示され、接続先のすべてのアプリケーションからそのサービスを切断することができます。

切断されているサービスを選択すると、そのサービスをアプリケーションに接続するオプションと、アカウントからサービスを削除するオプションが示されます。 既存のサービスを接続すると、そのサービスの使用を開始するために、資格情報ファイルやソース・コードなどのファイルもダウンロードされます。

また、アプリケーションに新しいサービスを追加するオプションを選択することもできます。 このオプションを選択すると、サービス選択のプロンプトが表示され、新しいサービスの使用を開始するために、資格情報ファイルやソース・コードなどの追加ファイルがダウンロードされます。



## enable
{: #enable}

既存のアプリケーションを {{site.data.keyword.Bluemix_notm}} デプロイメントに対応できるようにします。 `enable` コマンドは、既存アプリケーションの言語の自動検出を試み、その後、必要な追加情報を求めるプロンプトを出します。 これにより、ローカル Docker コンテナー、CloudFoundry デプロイメント、または Kubernetes/コンテナー・デプロイメントのために使用できるファイルが生成され、追加されます。

以下のコマンドを実行して、現行ディレクトリー内の既存のアプリケーションを {{site.data.keyword.Bluemix_notm}} デプロイメントに対応できるようにします。

```
ibmcloud dev enable
```
{: codeblock}

必要なファイルの存在によって、有効なプロジェクト構造のために必要なアプリケーション言語検出が行われます。  

* `package.json` ファイルが存在すると、Node.js アプリケーションと識別されます。
* `package.swift` ファイルが存在すると、Swift アプリケーションと識別されます。
* `setup.py` ファイルまたは `requirements.txt` ファイルのいずれかが存在すると、Python アプリケーションと識別されます。
* `pom.xml` ファイルまたは `build.gradle` ファイルのいずれかが存在すると、Java アプリケーションと識別されます。
	* `pom.xml` が存在すると、Maven アプリケーションと識別されます。
	* `build.gradle` が存在すると、Gradle アプリケーションと識別されます。

オプションで、検出されたアプリケーション言語を `--language` 引数を使用してオーバーライドすることもできます。  ただし、サポートされるのは有効かつ完全なアプリケーションのみです。 enable コマンドによってソース・コードが変更されることはありません。

言語オプションは以下のとおりです。
* node
* swift
* python
* java-ee (Java - Java EE と解釈されます)
* java-mp (Java - Java MicroProfile と解釈されます)
* java-spring (Java - Spring フレームワークと解釈されます)

`ibmcloud dev enable` コマンドを使用して作成されるファイルのうち、アプリケーション・フォルダー内にある既存のファイルとの間でネーミングに競合が生じるファイルは、`.merge` ファイル拡張子を使用して保存されます。  

### enable コマンド・パラメーター
{: #enable-parameters}

以下のパラメーターを `enable` コマンドに指定して使用するか、アプリケーションの `cli-config.yml` ファイルを直接更新することで使用できます。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `language`
{: #enable-language}

* 使用可能にするアプリケーションの言語を指定するために使用されるパラメーター。
* 使用法 `ibmcloud dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* 既に使用可能になっているアプリケーションの再使用可能化を強制するために使用されるパラメーター。
* 使用法 `ibmcloud dev enable -f|--force`


## get-credentials
{: #get-credentials}

接続済みサービスを使用可能にするためにアプリケーションで必要な資格情報を取得します。


## help
{: #help}

アクションも引数も渡されない場合、または help アクションが指定された場合、デフォルトで、このコマンドは一般的なヘルプ・テキストを表示します。 表示される一般ヘルプには、基本の引数の説明と、使用可能なアクションのリストが含まれます。  

以下のコマンドを実行して、一般的なヘルプ情報を表示します。

```
ibmcloud dev help
```
{: codeblock}


## list
{: #list}

リソース・グループ内のすべての {{site.data.keyword.Bluemix_notm}} アプリケーションをリストできます。

以下のコマンドを実行して、アプリケーションをリストします。

```
ibmcloud dev list
```
{: codeblock}


## run
{: #run}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`run` コマンドによって、アプリケーションを実行できます。 まず、`build` コマンドを使用して、アプリケーションに対するビルドが実行される必要があります。 `run` コマンドを起動すると、実行コンテナーが開始され、`container-port-map` パラメーターで定義されたポートが公開されます。 このステップを実行するためのエントリー・ポイントが実行コンテナー Dockerfile に含まれていない場合は、`run-cmd` パラメーターを使用してアプリケーションを起動できます。

複数のコンテナーを使用して実行するには、アプリケーションに [Compose](https://docs.docker.com/compose/overview/) ファイルが含まれているか (`cli-config.yml` 内に指定されているか)、`dockerfile-run` コマンド・パラメーターを使用して、このファイルを指定する必要があります。 詳しくは、[Compose ファイル](/docs/apps/projects/compose_file.html)を参照してください。

まず、アプリケーションをコンパイルします。

```
ibmcloud dev build
```
{: codeblock}

現行アプリケーション・ディレクトリー内で以下のコマンドを実行して、アプリケーションを開始します。

```
ibmcloud dev run
```
{: codeblock}

セッションを終了するには、`CTRL-C` を使用します。


### run コマンド・パラメーター
{: #run-parameters}

以下のパラメーターは、`run` コマンド専用のパラメーターで、
実行コンテナー内でのアプリケーションの管理を支援するものです。
その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `container-name-run`
{: #container-name-run2}

* 実行コンテナーのコンテナー名。
* 使用法: `ibmcloud dev run --container-name-run [<applicationName>]`

#### `container-path-run`
{: #container-path-run}

* 実行時に共有するコンテナー内の場所。
* 使用法: `ibmcloud dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* 実行時にコンテナー内で共有するホスト・システム上の場所。
* 使用法: `ibmcloud dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* 実行コンテナーの Dockerfile。
* 複数のコンテナーを使用して実行する予定の場合、これは Compose ファイルにする必要があります。
* 複数の Compose ファイルを使用するには、ファイル名のコンマ区切りリストを二重引用符で囲んでください。
* 使用法: `ibmcloud dev run --dockerfile-run [/path/to/Dockerfile]`
* 使用法: `ibmcloud dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* `dockerfile-run` から作成するイメージ。
* 使用法: `ibmcloud dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* 実行コンテナー内でコードを実行するために使用されるパラメーター。 イメージによってアプリケーションが開始される場合、このパラメーターを使用します。
* 使用法: `ibmcloud dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`shell` コマンドを使用すると、実行コンテナーまたはツール・コンテナー内でシェルを開くことができます。

以下のように、単純にこのコマンドを実行します。

```
ibmcloud dev shell
```

そうすると、{{site.data.keyword.dev_cli_short}} CLI によって、対話式シェルがアプリケーションの Docker コンテナーに開かれます。 シェル・コマンドのデフォルトのターゲット・コンテナーは、`cli-config.yml` ファイルの `container-shell-target` 値によって定義され、有効な値は、`run` または `tools` です。 この値が定義されていない場合、または無効値が指定されている場合、`shell` コマンドは、デフォルトで `tools` コンテナーをターゲットとします。 シェル・コマンドは、対応する Dockerfile 内の `WORKDIR` 命令によって指定されたディレクトリーにコンテナーを開きます。 `WORKDIR` が Dockerfile 内にリストされていない場合、コンテナーのルートが作業ディレクトリーとして使用されます。 詳しくは、[このリファレンス](https://docs.docker.com/engine/reference/builder/#workdir)を参照してください。

代わりの方法として、`run` または `tools` のいずれかを引数としてコマンドに渡すこともできます。そうすると、そのコンテナーが開始され、シェルはそのコンテナーに開かれます。 同様に、`container-name` パラメーターを使用して、シェルを開くコンテナーの名前を渡すことができます。 ただし、このフラグは、実行中のコンテナーがないときに限って使用するようにしてください。 `run` 引数および `tools` 引数のほうが柔軟性が高く、その時点でいずれかのコンテナーが実行中の場合、コンテナーの切り替えが可能です。 例えば、ツール・コンテナーが実行中の場合に `ibmcloud dev shell run` を実行すると、`tools` コンテナーは停止し、`run` コンテナーが開始されます。その逆も可能です。

`shell` コマンドを実行したときにターゲットの `run` コンテナーまたは `tools` コンテナーがまだ実行されていない場合、そこでターゲット・コンテナーが開始されます。 しかし、Dockerfile 内のデフォルトの `Cmd` または `Entrypoint` はオーバーライドされ、サーバー・プロセスが開始される代わりに、直接シェルで起動されます。 これで、`run` コンテナーまたは `tools` コンテナーを開始でき、任意のコマンドまたはカスタム・コマンドを独自に使用してサーバーを手動で開始できるようになります。


`container-shell` パラメーターを使用して、開く必要があるシェル実行可能を指定することもできます。 デフォルトでは、`/bin/sh` が使用されます。 bash シェルを使用することを希望する場合は、`container-shell` の値が `/bin/bash` になるように指定してください。ただし、bash は、必ずしもすべての種類の Linux で自動的に使用可能であるとは限らない点に留意してください。

フラグの先にさらに引数を追加してコマンドに渡した場合、それらの引数はすべて、シェルが開かれたときに実行するコマンドとして解析されます。 実行すべきコマンドを提供した場合、コンテナー内のシェルは、コマンドの実行をもって終了し、ユーザーの端末に戻ります。

例えば、`ibmcloud dev shell tools ls` と呼び出すことにより、ツール・コンテナー・シェル内で Linux `ls` コマンドを実行できます。   また、引数を引用符で囲むことにより、シェル・コマンド実行に渡す追加のフラグを指定することもできます。例えば、`ibmcloud dev shell "ls -la"` のようにできます。

### shell コマンド・パラメーター
{: #shell-parameters}

#### `container-name`
{: #container-name}

* シェルを開くコンテナーの名前。
* 使用法: `ibmcloud dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* コンテナー内で実行するシェルを指定します (デフォルトは /bin/sh)。
* 使用法: `ibmcloud dev shell --container-shell [path/to/shell]`


## status
{: #status}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`container-name-run` および `container-name-tools` で定義された、{{site.data.keyword.dev_cli_short}} CLI によって使用されるコンテナーの状況を照会できます。

現行アプリケーション・ディレクトリー内で以下のコマンドを実行して、コンテナーの状況をチェックします。

```
ibmcloud dev status
```
{: codeblock}


[status コマンド・パラメーター](#command-parameters)


## stop
{: #stop}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`stop` コマンドによって、コンテナーを停止できます。

`cli-config.yml` ファイルに定義されているツール・コンテナーおよび実行コンテナーを停止するには、以下を実行します。

```
ibmcloud dev stop
```
{: codeblock}

`cli-config.yml` ファイルに定義されていないコンテナーを停止するには、追加のコマンド・ライン・パラメーターを指定して、コンテナーをオーバーライドできます。  `cli-config.yml` ファイル内にも、コマンド・ラインにもコンテナーが指定されていない場合、stop コマンドは単純に戻ります。

### stop コマンド・パラメーター
{: #stop-parameters}

`stop` コマンドでは、以下のパラメーターが使用されます。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `container-name-run`
{: #container-name-run}

* 実行コンテナーのコンテナー名。
* 使用法: `ibmcloud dev stop --container-name-run [<applicationName>]`

#### `container-name-tools`
{: #container-name-tools}

* ツール・コンテナーのコンテナー名。
* 使用法: `ibmcloud dev stop --container-name-tools [<applicationName>]`



## test
{: #test}

Windows &trade; を使用する場合、Windows 10 Pro 以降を実行する必要があります。

`test` コマンドによって、アプリケーションをテストできます。 まず、`build --debug` コマンドを使用して、アプリケーションに対するビルドが実行される必要があります。 その後、ツール・コンテナーを使用して、アプリケーションの `test-cmd` が起動されます。

まず、アプリケーションをコンパイルします。

```
ibmcloud dev build --debug
```
{: codeblock}

以下のコマンドを実行して、アプリケーションをテストします。

```
ibmcloud dev test
```
{: codeblock}


### test コマンド・パラメーター
{: #test-parameters}

以下のパラメーターは、`test` コマンド専用です。  その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `test-cmd`
{: #test-cmd}

* ツール・コンテナー内でコードをテストするコマンドを指定するために使用されるパラメーター。
* 使用法: `ibmcloud dev test --test-cmd /the/test/command`


## view
{: #view}

`view` コマンドによって、アプリケーションがデプロイされた先の URL を表示できます。 このコマンドは、表示対象のアプリケーションのルート・ディレクトリーで実行してください。 `view` コマンドにより、ユーザーのデフォルト・ブラウザーでも URL が開かれます。

Cloud Foundry にデプロイされたアプリケーションの場合、URL は、アプリケーションのホスト名とドメインから構成されます。

Kubernetes にデプロイされたアプリケーションの場合、URL は、デプロイ先のノードの IP アドレスとパブリック・ポートから構成されます。 コマンドが、アプリのデプロイ先が Kubernetes であると判断した場合、CLI ツールによって確認を求めるプロンプトが出されます。 アプリケーションの実際のデプロイ先が Kubernetes ではなかったことを指定すると、Cloud Foundry URL が表示されます。 Kubernetes にデプロイされたアプリケーションの URL が表示されることを予期していたときに、コマンドがそれを表示しなかった場合は、`cli-config.yml` に `chart-path` のエントリーが含まれていることを確認するか、[ここ](#chart-path)に示されているとおり、コマンド・ラインからエントリーを提供してください。

以下のコマンドを実行して、アプリケーションの URL を表示します。

```
ibmcloud dev view
```
{: codeblock}

### view コマンド・パラメーター
{: #view-parameters}

以下のパラメーターは、`view` コマンド専用です。

#### `deploy-target`

* プロンプトをバイパスするために、デプロイメントのタイプを指示するために使用するオプションのパラメーター。
* 使用法 `ibmcloud dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* ブラウザーを開かないように指定するために使用されるパラメーター。
* 使用法: `ibmcloud dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Cloud Foundry および Kubernetes アプリ URL に追加するプロジェクトのルート。
* 使用法: `ibmcloud dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster2}

* ターゲットがコンテナー・デプロイメントの場合に、Kubernetes クラスターの名前を定義するために使用されるオプションのパラメーター。
* 使用法 `ibmcloud dev view --ibm-cluster [cluster-name]`


## 複合コマンド
{: #compound}

{{site.data.keyword.Bluemix_notm}} 開発者ツール・コマンドを区切り文字 `/` で分離することで、複数のコマンドを 1 つのコマンド・ライン・ステートメントで実行できます。 複合コマンドを指定した後に、追加のコマンド・ライン・フラグを指定できます。  以下に、複合コマンドの使用法の例を示します。

```
ibmcloud dev build/run
ibmcloud dev build/deploy --trace -t buildpack
ibmcloud dev build/debug --debug --trace
ibmcloud dev build/deploy/view -t container --trace
```
{: codeblock}

フラグはすべて、最後のコマンドの後に続く必要があり、そのフラグが関連付けられたすべてのコマンドに適用されます。 上記の最後の例では、`--trace` フラグは、3 つすべてのコマンドに適用されますが、`-t` は、最後の 2 つのコマンドにしか適用されず、`build` コマンドには適用されません。

この機能で使用できるコマンドは、次のとおりです。
`build、debug、deploy、get-credentials、run、stop、test、view`

いずれかのコマンドが何らかの理由で失敗すると、後続のコマンドは実行されません。

`debug` または `run` の後にいずれかのコマンドが続く場合、現在の端末ウィンドウからプロセスを強制終了する以外の方法で `debug` または `run` が終了した場合にのみ、それらのコマンドは続行されます。 `CTRL+C` はプロセスを強制終了することになるので、後続のコマンドは実行されません。 例えば、別の端末ウィンドウから `ibmcloud dev stop` を実行して、実行中のコンテナーを停止すると、次のコマンドの実行を続行できます。


## build、debug、run、および test 用のパラメーター
{: #command-parameters}

以下のパラメーターを `build|debug|run|test` コマンドに指定して使用するか、アプリケーションの `cli-config.yml` ファイルを直接更新することで使用できます。 [`debug`](#debug-parameters) コマンドおよび [`run`](#run-parameters) コマンドでは、追加のパラメーターが使用可能です。

**注**: コマンド・ラインで入力されたコマンド・パラメーターは、`cli-config.yml` 構成よりも優先されます。

#### `config-file`  
{: #config-file}

* コマンドで使用する cli-config.yml ファイルを指定します。
* 使用法: `ibmcloud dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run1}

* 実行コンテナーのコンテナー名。
* 使用法: `ibmcloud dev <run|status|stop> --container-name-run [<applicationName>]`

#### `container-name-tools`  
{: #container-name-tools1}

* ツール・コンテナーのコンテナー名。
* 使用法: `ibmcloud dev <build|debug|run|status|stop|test> --container-name-tools [<applicationName>]`

#### `host-path-tools`
{: #host-path-tools}

* build、debug、test で共有するホスト上の場所。
* 使用法: `ibmcloud dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* build、debug、test で共有するコンテナー内の場所。
* 使用法: `ibmcloud dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* コンテナーのポート・マッピング。 最初の値は、ホスト OS で使用するポートで、2 番目の値は、コンテナーのポートです [host-port:container-port]。
* 使用法: `ibmcloud dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* ツール・コンテナーの Dockerfile。
* 使用法: `ibmcloud dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* `dockerfile-tools` から作成するイメージ。
* 使用法: `ibmcloud dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* このオプションを使用して、ホスト・システムと実行コンテナーの間のマウントを定義します。
* このリストの先頭に、`host-path-run` と `container-path-run` の値が挿入されます。
* ベスト・プラクティスとして、また、予期しない結果を回避するためにも、build と run では同じマウント設定を使用してください。
* 使用法: `ibmcloud dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* このオプションを使用して、ホスト・システムとツール・コンテナーの間のマウントを定義します。
* このリストの先頭に、`host-path-tools` と `container-path-tools` の値が挿入されます。* ベスト・プラクティスとして、また、予期しない結果を回避するためにも、build と debug では同じマウント設定を使用してください。
* 使用法: `ibmcloud dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* デバッグ以外のすべての用途のコードをビルドするコマンドを指定するために使用されるパラメーター。
* 使用法: `ibmcloud dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* このパラメーターを使用して、詳細出力を提供します。
* 使用法: `ibmcloud dev <build|debug|run|test> --trace`
