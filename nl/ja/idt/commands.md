---
copyright:
years: 2017, 2018
lastupdated: "2018-04-17"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:screen: .screen}  
{:codeblock: .codeblock}  
{:pre: .pre}  

# {{site.data.keyword.dev_cli_notm}} CLI (bx dev) コマンド
{: #idt-cli}

バージョン: 1.2.0
リリース: 2018 年 3 月 8 日

以下の {{site.data.keyword.dev_cli_notm}} CLI (bx dev) コマンドを使用して、プロジェクトを作成し、プロジェクトをデプロイ、デバッグ、およびテストします。

- [build](#build): ローカル・コンテナー内にプロジェクトをビルドします。
- [code](#code): プロジェクトからコードをダウンロードします。
- [console](#console): プロジェクトの IBM Cloud コンソールを開きます。
- [create](#create): 新規プロジェクトを作成し、オプションでサービスを追加できます。
- [debug](#debug): ローカル・コンテナー内でアプリケーションをデバッグします。
- [delete](#delete): スペースからプロジェクトを削除します。
- [deploy](#deploy): アプリケーションを IBM Cloud にデプロイします。
- [enable](#enable): 既存のプロジェクトに IBM Cloud ファイルを追加します。
- [get-credentials](#get-credentials): バインドされたサービスを使用可能にするためにプロジェクトによって必要とされる資格情報を取得します。
- [help](#help): IDT の構文と引数に関するヘルプ。
- [list](#list): スペース内のすべての IBM Cloud プロジェクトをリストします。
- [run](#run): ローカル・コンテナー内でアプリケーションを実行します。
- [shell](#shell): ローカル・コンテナーにシェルを開きます。
- [status](#status): CLI で使用されるコンテナーの状況をチェックします。
- [stop](#stop): コンテナーを停止します。
- [test](#test): ローカル・コンテナー内でアプリケーションをテストします。
- [view](#view): テストや表示目的で、デプロイされたアプリの URL を表示します。
- [複合コマンド](#compound): 1 つのコマンド・ライン・ステートメント内で複数のコマンドを実行します。



## build
{: #build}

`build` コマンドを使用して、アプリケーションをビルドできます。 `test`、`debug`、および `run` の各コマンドでは、コンパイル済みプロジェクトが検出される必要があるため、まず `build` 操作を事前に実行する必要があります。  

`run` を除くすべての用途に関して、アプリケーションをビルドするときは、`build-cmd-debug` 構成エレメントを使用します。 デバッグ用のアプリケーションをビルドする際は、コマンド・ライン・オプション `--debug` を指定します。  `run` コマンドで使用するためのアプリケーションをビルドするときは、`build-cmd-run` 構成エレメントを使用します。

複数のコンテナーを使用してビルドするには、`cli-config.yml` で指定されている [Compose](https://docs.docker.com/compose/overview/) ファイルがプロジェクトに含まれているか、`dockerfile-tools` コマンド・パラメーターを使用して、このファイルを提供できなければなりません。詳しくは、[Compose ファイル](/docs/apps/projects/compose_file.html)を参照してください。

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、アプリケーションをビルドします。  

```
bx dev build [--debug]
```
{: codeblock}


[Build コマンド・パラメーター](#command-parameters)


## code
{: #code}

`code` コマンドを使用して、以前に作成されたプロジェクトをアプリケーションのテンプレート・コードおよび {{site.data.keyword.Bluemix_notm}} の構成ファイルとともにダウンロードします。  以前に作成したプロジェクトの 2 次コピーを抽出する必要がある場合に便利です。

以下のコマンドを実行して、指定したプロジェクトからコードをダウンロードします。

```
bx dev code <projectName>
```
{: codeblock}


## console
{: #console}

`console` コマンドを使用して、Web ブラウザーに IBM Cloud 上のアプリケーションの Web コンソールを開きます。  `bx dev console` コマンドはプロジェクトのフォルダー内から実行できます。そうすると、CLI によって、現行ディレクトリーと同じプロジェクト ID を持つ、IBM Cloud 上の一致するプロジェクトの検索が試行されます。 一致する名前を検出できない場合、システムは、指定されたプロジェクトの代わりに IBM Cloud の Web and Mobile ダッシュボードを開きます。

プロジェクト名を指定できます。そうすると、CLI は、フォルダー/アプリケーション名に基づいたマッチングをスキップします。 この場合、CLI は、指定されたプロジェクトのコンソールを Web ブラウザーに開きます。  

以下のコマンドを実行して、Web ブラウザーにアプリケーションの Web コンソールを開きます。

```
bx dev console [projectName]
```
{: codeblock}


## create
{: #create}

プロジェクトを作成し、リソース・タイプ、言語、スターター・キット、および DevOps ツールチェーンのオプションなど、すべての情報を求めるプロンプトを出します。 プロジェクトは現行ディレクトリー内に作成されます。

現行ディレクトリー内にプロジェクトを作成し、プロジェクトにサービスを関連付けるには、以下のコマンドを実行します。

```
bx dev create
```
{: codeblock}


## debug
{: #debug}

`debug` コマンドによって、アプリケーションをデバッグできます。 まず、`--debug` 引数を指定した build コマンドを使用して、プロジェクトに対するビルドが実行される必要があります。 `debug` コマンドを開始すると、コンテナーが開始され、それによりデバッグ・ポート (複数可) が提供されます。ポートは、cli-config.yml 内の `container-port-map-debug` 値で定義されるか、コマンド・ラインで指定されます。 お好みのデバッグ・ツールをポートに接続すれば、通常どおりアプリケーションをデバッグできます。

まず、プロジェクトをコンパイルします。

```
bx dev build --debug
```
{: codeblock}

開始するには、現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、アプリケーションをデバッグします。

```
bx dev debug
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
* 使用法: `bx dev debug --container-port-map-debug 7777:7777`

#### `build-cmd-debug`
{: #build-cmd-debug}

* デバッグ用のコードをビルドするために使用されるパラメーター。
* 使用法: `bx dev debug --build-cmd-debug build.command.sh`

#### `debug-cmd`
{: #debug-cmd}

* ツール・コンテナー内のデバッグを起動するコマンドを指定するために使用されるパラメーター。 `build-cmd-debug` によってアプリケーションがデバッグ・モードで開始された場合、このパラメーターを使用します。
* 使用法: `bx dev debug --debug-cmd /the/debug/command`



## delete
{: #delete}

`delete` コマンドを使用して、{{site.data.keyword.Bluemix}} スペースからプロジェクトを削除します。 パラメーターなしでコマンドを実行して、使用可能なプロジェクトをリストし、削除するプロジェクトを番号付きリストから選択できます。 プロジェクト・コードおよびディレクトリーはローカル・ディスク・スペースからは削除されません。

以下のコマンドを実行して、{{site.data.keyword.Bluemix}} からプロジェクトを削除します。

```
bx dev delete <projectName>
```
{: codeblock}


**注:** {{site.data.keyword.Bluemix}} サービスは、削除**されません**。


## deploy
{: #deploy}

アプリケーションは、Cloud Foundry アプリケーションまたはコンテナーとしてデプロイできます。

Cloud Foundry アプリケーションとして {{site.data.keyword.Bluemix}} にデプロイする場合、`manifest.yml` ファイルがプロジェクトのルート・ディレクトリーに存在する必要があります。

アプリケーションをコンテナーとしてデプロイする場合、[Kubernetes](https://kubernetes.io/) と [Helm](https://github.com/kubernetes/helm) をローカルにインストールする必要があります。 Helm クライアント・バージョンが Helm サーバー・バージョンよりも新しくないことを確認してください。 `helm version` を実行することで、それら両方のバージョンを確認できます。 クライアント・バージョンには、v2.4.2 を使用することを推奨します。

以下の例に示すように、`cli-config.yml` 内で、Helm チャートの場所を `chart-path` プロパティーに定義し、`deploy-target` エレメントを `container` に設定し、`deploy-image-target` を構成するように選択できます。 `cli-config.yml` 内の `deploy-image-target` エレメントが、`chart/values.yml` ファイル内の `repository` エレメントおよび `tag` エレメントの代わりに使用されます。 具体的にデプロイ先を {{site.data.keyword.Bluemix}} にするには、構成エレメント `ibm-cluster` に、[チュートリアル: クラスターの作成](/docs/containers/cs_tutorials.html#cs_cluster_tutorial)の説明に従って {{site.data.keyword.Bluemix}} 内に作成した Kubernetes クラスターの名前を設定します。

プロビジョニング、構成、および Kubernetes クラスターへのデプロイについて詳しくは、[Deploy a scalable web application on Kubernetes](/docs/tutorials/scalable-webapp-kubernetes.html#deploy-a-scalable-web-application-on-kubernetes) チュートリアルを参照してください。

```
    chart-path: "chart/myapplication"

    deploy-target: "container"

    deploy-image-target: "registry.<IBM Cloud Region>.bluemix.net/<Container Registry Namespace>/<App-Name>"

    ibm-cluster: "mycluster"
```

これらを cli-config.yml 内に定義しない場合、パラメーター `-t container` を指定してデプロイする必要があり、その他すべての値について、プロンプトが出されます。

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、アプリケーションをビルドします。  

```
bx dev build
```
{: codeblock}

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、プロジェクトをデプロイします。

```
bx dev deploy
```
{: codeblock}


### deploy コマンド・パラメーター
{: #deploy-parameters}

以下のパラメーターを `deploy` コマンドに指定して使用するか、プロジェクトの `cli-config.yml` ファイルを直接更新することで使用できます。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `chart-path`
{: #chart-path}

* コンテナー・デプロイメントの場合に使用されるパラメーターで、デプロイメントに使用する Helm チャートの場所を指定します。
* 使用法 `bx dev deploy --chart-path [/the/path]`

#### `deploy-target`
{: #deploy-target}

* 実行するデプロイメントのタイプを指示するために使用するオプションのパラメーター。  デフォルトのデプロイメント・タイプは、ビルドパックです。
* 使用法 `bx dev deploy -t|--target buildpack|container`

#### `deploy-image-target`
{: #deploy-image-target}

* デプロイメントのターゲット・イメージ名として (例えば、Docker レジストリーにタグ付けするため)、コンテナー・デプロイメントで使用されるパラメーター。  値にバージョンを含めることはできません (例えば、image-name:{version} などにはできません)。バージョンは、`deploy` によって自動的に増やされ、追加されます。
* 使用法 `bx dev deploy --deploy-image-target [image-name]`

#### `ibm-cluster`
{: #ibm-cluster}

* {{site.data.keyword.Bluemix}} へのコンテナー・デプロイメントの場合に、Kubernetes クラスターの名前を定義するために使用されるオプションのパラメーター。
* 使用法 `bx dev deploy --ibm-cluster [cluster-name]`


## enable
{: #enable}

既存のプロジェクトを {{site.data.keyword.Bluemix_notm}} デプロイメントに対応できるようにします。 `enable` コマンドは、既存プロジェクトの言語の自動検出を試み、その後、必要な追加情報を求めるプロンプトを出します。 これにより、ローカル Docker コンテナー、CloudFoundry デプロイメント、または Kubernetes/コンテナー・デプロイメントのために使用できるファイルが生成され、追加されます。

以下のコマンドを実行して、現行ディレクトリー内の既存のプロジェクトを {{site.data.keyword.Bluemix_notm}} デプロイメントに対応できるようにします。

```
bx dev enable
```
{: codeblock}

必要なファイルの存在によって、有効なプロジェクト構造のために必要なプロジェクト言語検出が行われます。  

* `package.json` ファイルが存在すると、Node.js プロジェクトと識別されます。
* `package.swift` ファイルが存在すると、Swift プロジェクトと識別されます。
* `setup.py` ファイルまたは `requirements.txt` ファイルのいずれかが存在すると、Python プロジェクトと識別されます。
* `pom.xml` ファイルまたは `build.gradle` ファイルのいずれかが存在すると、Java プロジェクトと識別されます。
	* `pom.xml` が存在すると、Maven プロジェクトと識別されます。
	* `build.gradle` が存在すると、Gradle プロジェクトと識別されます。

オプションで、検出されたプロジェクト言語を `--language` 引数を使用してオーバーライドすることもできます。  ただし、サポートされるのは有効かつ完全なプロジェクトのみです。 enable コマンドによってソース・コードが変更されることはありません。

言語オプションは以下のとおりです。
* node
* swift
* python
* java-ee (Java - Java EE と解釈されます)
* java-mp (Java - Java MicroProfile と解釈されます)
* java-spring (Java - Spring フレームワークと解釈されます)

`bx dev enable` コマンドを使用して作成されるファイルのうち、プロジェクト・フォルダー内にある既存のファイルとの間でネーミングに競合が生じるファイルは、`.merge` ファイル拡張子を使用して保存されます。  

### enable コマンド・パラメーター
{: #enable-parameters}

以下のパラメーターを `enable` コマンドに指定して使用するか、プロジェクトの `cli-config.yml` ファイルを直接更新することで使用できます。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `language`
{: #enable-language}

* 使用可能にするプロジェクトの言語を指定するために使用されるパラメーター。
* 使用法 `bx dev enable -l|--language [language]`

#### `force`
{: #enable-force}

* 既に使用可能になっているプロジェクトの再使用可能化を強制するために使用されるパラメーター。
* 使用法 `bx dev enable -f|--force`


## get-credentials
{: #get-credentials}

バインドされたサービスを使用可能にするためにプロジェクトによって必要とされる資格情報を取得します。


## help
{: #help}

アクションも引数も渡されない場合、または help アクションが指定された場合、デフォルトで、このコマンドは一般的なヘルプ・テキストを表示します。 表示される一般ヘルプには、基本の引数の説明と、使用可能なアクションのリストが含まれます。  

以下のコマンドを実行して、一般的なヘルプ情報を表示します。

```
bx dev help
```
{: codeblock}


## list
{: #list}

スペース内にあるすべての {{site.data.keyword.Bluemix_notm}} プロジェクトをリストできます。

以下のコマンドを実行して、プロジェクトをリストします。

```
bx dev list
```
{: codeblock}


<!--
## edit
{: #edit}

You can edit a project, such as changing the name, pattern or starter type, or adding services to your project. Run the following command:

```
bx dev edit
```
{: codeblock}
-->


## run
{: #run}

`run` コマンドによって、アプリケーションを実行できます。 まず、`build` コマンドを使用して、プロジェクトに対するビルドが実行される必要があります。 `run` コマンドを起動すると、実行コンテナーが開始され、`container-port-map` パラメーターで定義されたポートが公開されます。 このステップを実行するためのエントリー・ポイントが実行コンテナー Dockerfile に含まれていない場合は、`run-cmd` パラメーターを使用してアプリケーションを起動できます。

複数のコンテナーを使用して実行するには、プロジェクトに [Compose](https://docs.docker.com/compose/overview/) ファイルが含まれているか (`cli-config.yml` 内に指定されているか)、`dockerfile-run` コマンド・パラメーターを使用して、このファイルを指定する必要があります。 詳しくは、[Compose ファイル](/docs/apps/projects/compose_file.html)を参照してください。

まず、プロジェクトをコンパイルします。

```
bx dev build
```
{: codeblock}

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、アプリケーションを開始します。

```
bx dev run
```
{: codeblock}

セッションを終了するには、`CTRL-C` を使用します。


### run コマンド・パラメーター
{: #run-parameters}

以下のパラメーターは、`run` コマンド専用のパラメーターで、
実行コンテナー内でのアプリケーションの管理を支援するものです。
その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `container-name-run`
{: #container-name-run}

* 実行コンテナーのコンテナー名。
* 使用法: `bx dev run --container-name-run [<projectName>]`

#### `container-path-run`
{: #container-path-run}

* 実行時に共有するコンテナー内の場所。
* 使用法: `bx dev run --container-path-run [/path/to/app]`

#### `host-path-run`
{: #host-path-run}

* 実行時にコンテナー内で共有するホスト・システム上の場所。
* 使用法: `bx dev run --host-path-run [/path/to/app/bin]`

#### `dockerfile-run`
{: #dockerfile-run}

* 実行コンテナーの Dockerfile。
* 複数のコンテナーを使用して実行する予定の場合、これは Compose ファイルにする必要があります。
* 複数の Compose ファイルを使用するには、ファイル名のコンマ区切りリストを二重引用符で囲んでください。
* 使用法: `bx dev run --dockerfile-run [/path/to/Dockerfile]`
* 使用法: `bx dev run --dockerfile-run "/path/to/compose/file, /path/to/another/compose/file, ..."`

#### `image-name-run`
{: #image-name-run}

* `dockerfile-run` から作成するイメージ。
* 使用法: `bx dev run --image-name-run [/path/to/image-name]`

#### `run-cmd`
{: #run-cmd}

* 実行コンテナー内でコードを実行するために使用されるパラメーター。 イメージによってアプリケーションが開始される場合、このパラメーターを使用します。
* 使用法: `bx dev run --run-cmd [/the/run/command]`


## shell
{: #shell}

`shell` コマンドを使用すると、実行コンテナーまたはツール・コンテナー内でシェルを開くことができます。

以下のように、単純にこのコマンドを実行します。

```
bx dev shell
```

そうすると、{{site.data.keyword.dev_cli_short}} CLI によって、対話式シェルがアプリケーションの Docker コンテナーに開かれます。 シェル・コマンドのデフォルトのターゲット・コンテナーは、`cli-config.yml` ファイルの `container-shell-target` 値によって定義され、有効な値は、`run` または `tools` です。 この値が定義されていない場合、または無効値が指定されている場合、`shell` コマンドは、デフォルトで `tools` コンテナーをターゲットとします。 シェル・コマンドは、対応する Dockerfile 内の `WORKDIR` 命令によって指定されたディレクトリーにコンテナーを開きます。 `WORKDIR` が Dockerfile 内にリストされていない場合、コンテナーのルートが作業ディレクトリーとして使用されます。 詳しくは、[このリファレンス](https://docs.docker.com/engine/reference/builder/#workdir)を参照してください。

代わりの方法として、`run` または `tools` のいずれかを引数としてコマンドに渡すこともできます。そうすると、そのコンテナーが開始され、シェルはそのコンテナーに開かれます。 同様に、`container-name` パラメーターを使用して、シェルを開くコンテナーの名前を渡すことができます。 ただし、このフラグは、実行中のコンテナーがないときに限って使用するようにしてください。 `run` 引数および `tools` 引数のほうが柔軟性が高く、その時点でいずれかのコンテナーが実行中の場合、コンテナーの切り替えが可能です。 例えば、ツール・コンテナーが実行中の場合に `bx dev shell run` を実行すると、`tools` コンテナーは停止し、`run` コンテナーが開始されます。その逆も可能です。

`shell` コマンドを実行したときにターゲットの `run` コンテナーまたは `tools` コンテナーがまだ実行されていない場合、そこでターゲット・コンテナーが開始されます。 しかし、Dockerfile 内のデフォルトの `Cmd` または `Entrypoint` はオーバーライドされ、サーバー・プロセスが開始される代わりに、直接シェルで起動されます。 これで、`run` コンテナーまたは `tools` コンテナーを開始でき、任意のコマンドまたはカスタム・コマンドを独自に使用してサーバーを手動で開始できるようになります。


`container-shell` パラメーターを使用して、開く必要があるシェル実行可能を指定することもできます。 デフォルトでは、`/bin/sh` が使用されます。 bash シェルを使用することを希望する場合は、`container-shell` の値が `/bin/bash` になるように指定してください。ただし、bash は、必ずしもすべての種類の Linux で自動的に使用可能であるとは限らない点に留意してください。

フラグの先にさらに引数を追加してコマンドに渡した場合、それらの引数はすべて、シェルが開かれたときに実行するコマンドとして解析されます。 実行すべきコマンドを提供した場合、コンテナー内のシェルは、コマンドの実行をもって終了し、ユーザーの端末に戻ります。

例えば、`bx dev shell tools ls` と呼び出すことにより、ツール・コンテナー・シェル内で Linux `ls` コマンドを実行できます。   また、引数を引用符で囲むことにより、シェル・コマンド実行に渡す追加のフラグを指定することもできます。例えば、`bx dev shell "ls -la"` のようにできます。

### shell コマンド・パラメーター
{: #shell-parameters}

#### `container-name`
{: #container-name}

* シェルを開くコンテナーの名前。
* 使用法: `bx dev shell --container-name [<container-name>]`

#### `container-shell`
{: #container-shell}

* コンテナー内で実行するシェルを指定します (デフォルトは /bin/sh)。
* 使用法: `bx dev shell --container-shell [path/to/shell]`


## status
{: #status}

`container-name-run` および `container-name-tools` で定義された、{{site.data.keyword.dev_cli_short}} CLI によって使用されるコンテナーの状況を照会できます。

現行プロジェクト・ディレクトリー内で以下のコマンドを実行して、コンテナーの状況をチェックします。

```
bx dev status
```
{: codeblock}


[status コマンド・パラメーター](#command-parameters)


## stop
{: #stop}

`stop` コマンドによって、コンテナーを停止できます。

`cli-config.yml` ファイルに定義されているツール・コンテナーおよび実行コンテナーを停止するには、以下を実行します。

```
bx dev stop
```
{: codeblock}

`cli-config.yml` ファイルに定義されていないコンテナーを停止するには、追加のコマンド・ライン・パラメーターを指定して、コンテナーをオーバーライドできます。  `cli-config.yml` ファイル内にも、コマンド・ラインにもコンテナーが指定されていない場合、stop コマンドは単純に戻ります。

### stop コマンド・パラメーター
{: #stop-parameters}

`stop` コマンドでは、以下のパラメーターが使用されます。 その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `container-name-run`
{: #container-name-run}

* 実行コンテナーのコンテナー名。
* 使用法: `bx dev stop --container-name-run [<projectName>]`

#### `container-name-tools`
{: #container-name-tools}

* ツール・コンテナーのコンテナー名。
* 使用法: `bx dev stop --container-name-tools [<projectName>]`



## test
{: #test}

`test` コマンドによって、アプリケーションをテストできます。 まず、`build --debug` コマンドを使用して、プロジェクトに対するビルドが実行される必要があります。 その後、ツール・コンテナーを使用して、アプリケーションの `test-cmd` が起動されます。

まず、プロジェクトをコンパイルします。

```
bx dev build --debug
```
{: codeblock}

以下のコマンドを実行して、アプリケーションをテストします。

```
bx dev test
```
{: codeblock}


### test コマンド・パラメーター
{: #test-parameters}

以下のパラメーターは、`test` コマンド専用です。  その他のコマンドと共有される[追加のパラメーター](#command-parameters)もあります。

#### `test-cmd`
{: #test-cmd}

* ツール・コンテナー内でコードをテストするコマンドを指定するために使用されるパラメーター。
* 使用法: `bx dev test --test-cmd /the/test/command`


## view
{: #view}

`view` コマンドによって、アプリケーションがデプロイされた先の URL を表示できます。 このコマンドは、表示対象のアプリケーションのルート・ディレクトリーで実行してください。 `view` コマンドにより、ユーザーのデフォルト・ブラウザーでも URL が開かれます。

Cloud Foundry にデプロイされたアプリケーションの場合、URL は、アプリケーションのホスト名とドメインから構成されます。

Kubernetes にデプロイされたアプリケーションの場合、URL は、デプロイ先のノードの IP アドレスとパブリック・ポートから構成されます。 コマンドが、アプリのデプロイ先が Kubernetes であると判断した場合、CLI ツールによって確認を求めるプロンプトが出されます。 アプリケーションの実際のデプロイ先が Kubernetes ではなかったことを指定すると、Cloud Foundry URL が表示されます。 Kubernetes にデプロイされたアプリケーションの URL が表示されることを予期していたときに、コマンドがそれを表示しなかった場合は、`cli-config.yml` に `chart-path` のエントリーが含まれていることを確認するか、[ここ](#chart-path)に示されているとおり、コマンド・ラインからエントリーを提供してください。

以下のコマンドを実行して、アプリケーションの URL を表示します。

```
bx dev view
```
{: codeblock}

### view コマンド・パラメーター
{: #view-parameters}

以下のパラメーターは、`view` コマンド専用です。

#### `deploy-target`

* プロンプトをバイパスするために、デプロイメントのタイプを指示するために使用するオプションのパラメーター。
* 使用法 `bx dev view -t|--target buildpack|container`


#### `no-open`
{: #no-open}

* ブラウザーを開かないように指定するために使用されるパラメーター。
* 使用法: `bx dev view --no-open`


#### `web-app-root`
{: #web-app-root}

* Kubernetes アプリ URL に追加するプロジェクトのルート。
* 使用法: `bx dev view --web-app-root [root]`


#### `ibm-cluster`
{: #ibm-cluster}

* ターゲットがコンテナー・デプロイメントの場合に、Kubernetes クラスターの名前を定義するために使用されるオプションのパラメーター。
* 使用法 `bx dev view --ibm-cluster [cluster-name]`


## 複合コマンド
{: #compound}

IDT コマンドを区切り文字 `/` で分離することで、複数のコマンドを 1 つのコマンド・ライン・ステートメントで実行できます。 複合コマンドを指定した後に、追加のコマンド・ライン・フラグを指定できます。  以下に、複合コマンドの使用法の例を示します。

```
bx dev build/run
bx dev build/deploy --trace -t buildpack
bx dev build/debug --debug --trace
bx dev build/deploy/view -t container --trace
```
{: codeblock}

フラグはすべて、最後のコマンドの後に続く必要があり、そのフラグが関連付けられたすべてのコマンドに適用されます。 上記の例の場合、`--trace` フラグは、3 つすべてのコマンドに適用されます、`-t` は、最後の 2 つのコマンドにしか適用されず、`build` コマンドには適用されません。

この機能で使用できるコマンドは、次のとおりです。
`build、debug、deploy、get-credentials、run、stop、test、view`

いずれかのコマンドが何らかの理由で失敗すると、後続のコマンドは実行されません。 `debug` または `run` の後にいずれかのコマンドが続く場合、現在の端末ウィンドウからプロセスを強制終了する以外の方法で `debug` または `run` が終了した場合にのみ、それらのコマンドは続行されます。 `CTRL+C` はプロセスを強制終了することになるので、後続のコマンドは実行されません。 例えば、別の端末ウィンドウから `bx dev stop` を実行して、実行中のコンテナーを停止すると、次のコマンドの実行を続行できます。


## build、debug、run、および test 用のパラメーター
{: #command-parameters}

以下のパラメーターを `build|debug|run|test` コマンドに指定して使用するか、プロジェクトの `cli-config.yml` ファイルを直接更新することで使用できます。 [`debug`](#debug-parameters) コマンドおよび [`run`](#run-parameters) コマンドでは、追加のパラメーターが使用可能です。

**注**: コマンド・ラインで入力されたコマンド・パラメーターは、`cli-config.yml` 構成よりも優先されます。

#### `config-file`  
{: #config-file}

* コマンドで使用する cli-config.yml ファイルを指定します。
* 使用法: `bx dev <build|debug|run|status|stop|test> --config-file cli-config.yml`

#### `container-name-run`  
{: #container-name-run}

* 実行コンテナーのコンテナー名。
* 使用法: `bx dev <run|status|stop> --container-name-run [<projectName>]`

#### `container-name-tools`  
{: #container-name-tools}

* ツール・コンテナーのコンテナー名。
* 使用法: `bx dev <build|debug|run|status|stop|test> --container-name-tools [<projectName>]`

#### `host-path-tools`
{: #host-path-tools}

* build、debug、test で共有するホスト上の場所。
* 使用法: `bx dev <build|debug|run|test> --host-path-tools [/path/to/build/tools]`

#### `container-path-tools`
{: #container-path-tools}

* build、debug、test で共有するコンテナー内の場所。
* 使用法: `bx dev <build|debug|run|test> --container-path-tools [/path/for/build]`

#### `container-port-map`
{: #container-port-map}

* コンテナーのポート・マッピング。 最初の値は、ホスト OS で使用するポートで、2 番目の値は、コンテナーのポートです [host-port:container-port]。
* 使用法: `bx dev <build|debug|run|test> --container-port-map [8090:8090,9090:9090]`

#### `dockerfile-tools`
{: #dockerfile-tools}

* ツール・コンテナーの Dockerfile。
* 使用法: `bx dev <build|debug|run|test> --dockerfile-tools [path/to/dockerfile]`

#### `image-name-tools`
{: #image-name-tools}

* `dockerfile-tools` から作成するイメージ。
* 使用法: `bx dev <build|debug|run|test> --image-name-tools [path/to/image-name]`

#### `container-mounts-run`
{: #container-mounts-run}

* このオプションを使用して、ホスト・システムと実行コンテナーの間のマウントを定義します。
* このリストの先頭に、`host-path-run` と `container-path-run` の値が挿入されます。
* ベスト・プラクティスとして、また、予期しない結果を回避するためにも、build と run では同じマウント設定を使用してください。
* 使用法: `bx dev <build|run|test> --container-mounts-run [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `container-mounts-tools`
{: #container-mounts-tools}

* このオプションを使用して、ホスト・システムとツール・コンテナーの間のマウントを定義します。
* このリストの先頭に、`host-path-tools` と `container-path-tools` の値が挿入されます。* ベスト・プラクティスとして、また、予期しない結果を回避するためにも、build と debug では同じマウント設定を使用してください。
* 使用法: `bx dev <build|debug|test> --container-mounts-tools [/relative/path/to/host/dir:/absolute/path/to/container/dir, etc.]`

#### `build-cmd-run`
{: #build-cmd-run}

* デバッグ以外のすべての用途のコードをビルドするコマンドを指定するために使用されるパラメーター。
* 使用法: `bx dev <build|debug|run|test> --build-cmd-run [some.build.command]`

#### `trace`
{: #trace}

* このパラメーターを使用して、詳細出力を提供します。
* 使用法: `bx dev <build|debug|run|test> --trace`

