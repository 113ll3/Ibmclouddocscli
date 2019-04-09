---



copyright:

  years: 2017

lastupdated: "2017-12-08"


---

{:codeblock: .codeblock}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:new_window: target="_blank"}

# {{site.data.keyword.registrylong_notm}} CLI
{: #containerregcli}

{{site.data.keyword.registrylong}} CLI は、レジストリーと、{{site.data.keyword.Bluemix_notm}} アカウント用のリソースを管理するためのプラグインです。
{: shortdesc}

** の前提条件**
* レジストリー・コマンドを実行する前に、`bx login` コマンドを使用して {{site.data.keyword.Bluemix_notm}} にログインし、アクセス・トークンを生成して、セッションを認証します。

{{site.data.keyword.registrylong_notm}} CLI の使用方法については、『[{{site.data.keyword.registrylong_notm}} の概説](../../../services/Registry/index.html)』を参照してください。

<table summary="{{site.data.keyword.registrylong_notm}} の管理">
<caption>表 1. {{site.data.keyword.registrylong_notm}} を管理するためのコマンド
</caption>
 <thead>
 <th colspan="5">レジストリーを管理するためのコマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[bx cr api](#bx_cr_api)</td>
 <td>[bx cr build](#bx_cr_build)</td>
 <td>[bx cr info](#bx_cr_info)</td>
 <td>[bx cr image-inspect](#bx_cr_image_inspect)</td>
 <td>[bx cr image-list (bx cr images)](#bx_cr_image_list)</td>
 </tr>
 <tr>
 <td>[bx cr image-rm](#bx_cr_image_rm)</td>
 <td>[bx cr login
](#bx_cr_login)</td>
 <td>[bx cr namespace-add](#bx_cr_namespace_add)</td>
 <td>[bx cr namespace-list (bx cr namespaces)](#bx_cr_namespace_list)</td>
 <td>[bx cr namespace-rm](#bx_cr_namespace_rm)</td>
 </tr>
 <tr>
 <td>[bx cr plan](#bx_cr_plan)</td>
 <td>[bx cr plan-upgrade](#bx_cr_plan_upgrade)</td>
 <td>[bx cr quota](#bx_cr_quota)</td>
 <td>[bx cr quota-set](#bx_cr_quota_set)</td>
 <td>[bx cr region](#bx_cr_region)</td>
 </tr>
 <tr>
 <td>[bx cr region-set](#bx_cr_region_set)</td>
 <td>[bx cr token-add](#bx_cr_token_add)</td>
 <td>[bx cr token-get](#bx_cr_token_get)</td>
 <td>[bx cr token-list (bx cr tokens)](#bx_cr_token_list)</td>
 <td>[bx cr token-rm](#bx_cr_token_rm)</td>
 </tr><tr>
 <td>[bx cr vulnerability-assessment (bx cr va)](#bx_cr_va)</td>
 </tr>
 </tbody></table>



## bx cr api
{: #bx_cr_api}

コマンドの実行対象のレジストリー API エンドポイントに関する詳細を返します。

```
bx cr api
```
{: codeblock}


## bx cr build
{: #bx_cr_build}

{{site.data.keyword.registrylong_notm}} 内で Docker イメージをビルドします。

```
bx cr build [--no-cache] [--pull] [--quiet | -q] [--build-arg KEY=VALUE ...] [--file FILE | -f FILE] --tag TAG DIRECTORY
```
{: codeblock}

**パラメーター**
<dl>
<dt>DIRECTORY</dt>
<dd>Dockerfile と前提条件ファイルが含まれている、ビルド・コンテキストの場所。</dd>
<dt>--no-cache</dt>
<dd>(オプション)  指定されている場合、前のビルドからのキャッシュされたイメージ層はこのビルドで使用されません。</dd>
<dt>--pull</dt>
<dd>(オプション) 指定されている場合、一致するタグを持つイメージがビルド・ホスト上に既に存在していても、基本イメージがプルされます。</dd>
<dt>--quiet、-q</dt>
<dd>(オプション) 指定されている場合、エラーが発生しない限り、ビルド出力は抑止されます。</dd>
<dt> --build-arg KEY=VALUE</dt>
<dd>(オプション) 「KEY=VALUE」のフォーマットで追加のビルド引数を指定します。 このパラメーターを複数回含めることにより、複数のビルド引数を指定できます。 Dockerfile 内の鍵に一致する ARG 行を指定するとき、各ビルド引数の値は環境変数として使用できます。</dd>
<dt>--file FILE、-f FILE</dt>
<dd>(オプション) 複数ビルドに対して同じファイルを使用する場合は、異なる Dockerfile のパスを選択できます。 ビルド・コンテキストに対する Dockerfile の相対位置を指定します。 指定がない場合、デフォルトは `PATH/Dockerfile` です。ここで、PATH はビルド・コンテキストのルートです。</dd>
<dt>--tag TAG、-t TAG</dt>
<dd>ビルドするイメージのフルネーム。これには、レジストリーの URL と名前空間が含まれます。</dd>
</dl>


## bx cr info
{: #bx_cr_info}

ログイン先のレジストリーの名前とアカウントを表示します。

```
bx cr info
```
{: codeblock}


## bx cr image-inspect
{: #bx_cr_image_inspect}

特定のイメージに関する詳細を表示します。

```
bx cr image-inspect [--format FORMAT] IMAGE [IMAGE...]
```
{: codeblock}

**パラメーター**
<dl>
<dt>--format FORMAT</dt>
<dd>(オプション) Go テンプレートを使用して、出力エレメントをフォーマットします。

 

詳しくは、[{{site.data.keyword.registrylong_notm}} コマンドの CLI 出力のフォーマット設定およびフィルター操作](../../../services/Registry/registry_cli_reference.html#registry_cli_listing)を参照してください。

</dd>
<dt>IMAGE</dt>
<dd>レポートを取得するイメージの名前。 このコマンドでは、それぞれのイメージを、名前の間をスペースで区切ってリストすることにより、複数のイメージを検査できます。


<p>イメージの名前を調べるには、`bx cr image-list` を実行します。 リポジトリー列とタグ列のコンテンツを組み合わせて、イメージ名を `repository:tag` の形式で作成します。 イメージ名にタグが指定されていない場合、`latest` というタグが付いたイメージが検査されます。 </p> 

</dd>
</dl>


## bx cr image-list (bx cr images)
{: #bx_cr_image_list}

{{site.data.keyword.Bluemix_notm}} アカウント内のすべてのイメージを表示します。

<p>**注:** イメージ名は、リポジトリー列とタグ列のコンテンツを `repository:tag` の形式で組み合わせたものです。 </p> 

```
 bx cr image-list [--no-trunc] [--format FORMAT] [-q, --quiet] [--restrict RESTRICTION] [--include-ibm] 
```
{: codeblock}

**パラメーター**
<dl>
<dt>--no-trunc</dt>
<dd>(オプション) イメージ・ダイジェストを切り捨てません。</dd>
<dt>--format FORMAT</dt>
<dd>(オプション) Go テンプレートを使用して、出力エレメントをフォーマットします。

 

詳しくは、[{{site.data.keyword.registrylong_notm}} コマンドの CLI 出力のフォーマット設定およびフィルター操作](../../../services/Registry/registry_cli_reference.html#registry_cli_listing)を参照してください。

</dd>
<dt>-q, --quiet</dt>
<dd>(オプション) 各イメージが、`repository:tag` というフォーマットでリストされます。</dd>
<dt>--restrict RESTRICTION</dt>
<dd>(オプション) 指定された名前空間内または名前空間およびリポジトリー内のイメージのみを表示するように出力を制限します。 </dd>
<dt>--include-ibm</dt>
<dd>(オプション) {{site.data.keyword.IBM_notm}} 提供のパブリック・イメージを出力に含めます。 このオプションを指定しない場合、デフォルトではプライベート・イメージのみがリストされます。</dd>
</dl>



## bx cr image-rm
{: #bx_cr_image_rm}

指定された 1 つ以上のイメージをレジストリーから削除します。

```
bx cr image-rm IMAGE [IMAGE...]
```
{: codeblock}

**パラメーター**
<dl>
<dt>IMAGE</dt>
<dd>レポートを取得するイメージの名前。 このコマンドでは、それぞれのイメージを、名前の間をスペースで区切ってリストすることにより、複数のイメージを同時に削除できます。


<p>イメージの名前を調べるには、`bx cr image-list` を実行します。 リポジトリー列とタグ列のコンテンツを組み合わせて、イメージ名を `repository:tag` の形式で作成します。 イメージ名にタグが指定されていない場合、`latest` とタグ付けされたイメージはデフォルトで削除されます。</p> 

</dd>
</dl>


## bx cr login
{: #bx_cr_login}

このコマンドはレジストリーに対して `docker login` コマンドを実行します。 `docker login` コマンドは、レジストリーに対して `docker push` または `docker pull` のコマンドを実行できるようにするために必要です。 このコマンドは、その他の `bx cr` コマンドを実行するためには必要ではありません。 Docker がインストールされていない場合、このコマンドはエラー・メッセージを返します。

```
bx cr login
```
{: codeblock}


## bx cr namespace-add
{: #bx_cr_namespace_add}

{{site.data.keyword.Bluemix_notm}} アカウントに名前空間を追加します。

```
bx cr namespace-add NAMESPACE
```
{: codeblock}

**パラメーター**
<dl>
<dt>NAMESPACE</dt>
<dd>追加する名前空間。 名前空間は、同じ地域内のすべての {{site.data.keyword.Bluemix_notm}} アカウントにわたって固有でなければなりません。</dd>
</dl>


## bx cr namespace-list (bx cr namespaces)
{: #bx_cr_namespace_list}

{{site.data.keyword.Bluemix_notm}} アカウントが所有するすべての名前空間を表示します。

```
bx cr namespace-list
```
{: codeblock}


## bx cr namespace-rm
{: #bx_cr_namespace_rm}

{{site.data.keyword.Bluemix_notm}} アカウントから名前空間を削除します。 名前空間を削除すると、この名前空間内のイメージが削除されます。

```
bx cr namespace-rm NAMESPACE
```
{: codeblock}

**パラメーター**
<dl>
<dt>NAMESPACE</dt>
<dd>削除する名前空間。</dd>
</dl>


## bx cr plan
{: #bx_cr_plan}

価格プランを表示します。

```
bx cr plan
```
{: codeblock}


## bx cr plan-upgrade
{: #bx_cr_plan_upgrade}

標準プランにアップグレードします。

プランについて詳しくは、[レジストリー・プラン (Registry plans)](../../../services/Registry/registry_overview.html#registry_plans) を参照してください。

```
bx cr plan-upgrade [PLAN]
```
{: codeblock}

**パラメーター**
<dl>
<dt>プラン</dt>
<dd>アップグレード先の価格プランの名前。 PLAN を指定しない場合、デフォルトは `standard` です。</dd>
</dl>


## bx cr quota
{: #bx_cr_quota}

トラフィックおよびストレージの現在の割り当て量、およびそれらの割り当て量に対する使用量情報を表示します。

```
bx cr quota
```
{: codeblock}


## bx cr quota-set
{: #bx_cr_quota_set}

指定された割り当て量を変更します。

```
bx cr quota-set [--traffic TRAFFIC] [--storage STORAGE]
```
{: codeblock}

**パラメーター**
<dl>
<dt>--traffic TRAFFIC</dt>
<dd>(オプション) トラフィック割り当て量を、指定された値 (M バイト単位) に変更します。 トラフィックを設定する権限がない場合や現在の価格プランを超える値を設定した場合、操作は失敗します。</dd>
<dt>--storage STORAGE</dt>
<dd>(オプション) ストレージ割り当て量を、指定された値 (M バイト単位) に変更します。 ストレージ割り当て量を設定する権限がない場合や現在の価格プランを超える値を設定した場合、操作は失敗します。</dd>
</dl>


## bx cr region
{: #bx_cr_region}

ターゲットの地域とレジストリーを表示します。

```
bx cr region
```
{: codeblock}

詳しくは、『[地域](../../../services/Registry/registry_overview.html#registry_regions)』を参照してください。


## bx cr region-set
{: #bx_cr_region_set}

{{site.data.keyword.registrylong_notm}} コマンドのターゲット地域を設定します。 使用可能な地域をリストするには、パラメーターなしでコマンドを実行します。

```
bx cr region-set [REGION]
```
{: codeblock}

**パラメーター**
<dl>
<dt>REGION</dt>
<dd>(オプション) ターゲット地域の名前。例えば、`us-south` などです。

 

詳しくは、『[地域](../../../services/Registry/registry_overview.html#registry_regions)』を参照してください。

</dd>
</dl>


## bx cr token-add
{: #bx_cr_token_add}

レジストリーへのアクセスを制御するために使用できるトークンを追加します。

```
bx cr token-add [--description DESCRIPTION] [-q, --quiet] [--non-expiring] [--readwrite]
```

{: codeblock}


**パラメーター**
<dl>
<dt>--description DESCRIPTION</dt>
<dd>(オプション) トークンの説明としての値を指定します。これは、`bx cr token-list` を実行すると表示されます。 トークンが {{site.data.keyword.containerlong_notm}} によって自動的に作成される場合、この説明は、Kubernetes クラスター名に設定されます。 この場合、クラスターが除去されると、トークンは自動的に削除されます。</dd>
<dt>-q, --quiet</dt>
<dd>(オプション) 周囲のテキストを含めずに、トークンのみを表示します。</dd>
<dt>--non-expiring</dt>
<dd>(オプション) 有効期限が切れないアクセス権限を指定してトークンを作成します。 このパラメーターを設定しないと、デフォルトでは、トークンからのアクセスは 24 時間後に期限切れになります。</dd>
<dt>--readwrite</dt>
<dd>(オプション) 読み取り権限および書き込み権限を付与するトークンを作成します。 このオプションを指定しないと、デフォルトでは、アクセス権限は読み取り専用になります。</dd>
</dl>


## bx cr token-get
{: #bx_cr_token_get}

指定されたトークンをレジストリーから取得します。

```
bx cr token-get TOKEN
```

{: codeblock}

**パラメーター**
<dl>
<dt>TOKEN</dt>
<dd>(オプション) 取得するトークンの固有 ID。</dd>
</dl>


## bx cr token-list (bx cr tokens)
{: #bx_cr_token_list}

{{site.data.keyword.Bluemix_notm}} アカウント用に存在するすべてのトークンを表示します。

```
bx cr token-list --format FORMAT
```
{: codeblock}

**パラメーター**
<dl>
<dt>--format FORMAT</dt>
<dd>(オプション) Go テンプレートを使用して、出力エレメントをフォーマットします。

 

詳しくは、[{{site.data.keyword.registrylong_notm}} コマンドの CLI 出力のフォーマット設定およびフィルター操作](../../../services/Registry/registry_cli_reference.html#registry_cli_listing)を参照してください。

</dd>
</dl>


## bx cr token-rm
{: #bx_cr_token_rm}

指定された 1 つ以上のトークンを削除します。

```
bx cr token-rm TOKEN [TOKEN...]
```
{: codeblock}

**パラメーター**
<dl>
<dt>TOKEN</dt>
<dd>(オプション) TOKEN には、トークン自体またはトークンの固有 ID (`bx cr token-list` で表示される) のいずれかを指定できます。 複数のトークンを、スペースで区切って指定できます。</dd>
</dl>


## bx cr vulnerability-assessment (bx cr va)
{: #bx_cr_va}

イメージの脆弱性評価レポートを表示します。

```
bx cr vulnerability-assessment [--extended | -e] [--vulnerabilities | -v] [--configuration-issues | -c] [--output FORMAT | -o FORMAT] IMAGE [IMAGE...] 
```
{: codeblock}

**パラメーター**
<dl>
<dt>IMAGE</dt>
<dd>レポートを取得するイメージの名前。 このレポートは、イメージに、既知のパッケージ脆弱性があるかどうかを報告します。 このコマンドでは、それぞれのイメージを、名前の間をスペースで区切ってリストすることにより、複数のイメージのレポートを同時に要求できます。


<p>イメージの名前を調べるには、`bx cr image-list` を実行します。 リポジトリー列とタグ列のコンテンツを組み合わせて、イメージ名を `repository:tag` の形式で作成します。 イメージ名にタグが指定されていない場合、レポートは `latest` というタグが付いたイメージを評価します。 </p> 

<p>以下のオペレーティング・システムがサポートされています。



<ul>

<li>Alpine</li>
<li>CentOS</li>
<li>Debian</li>
<li>Red Hat Enterprise Linux (RHEL)</li>
<li>Ubuntu</li>
</ul>

</p>

詳しくは、[Managing image security with Vulnerability Advisor](../../../services/va/va_index.html) を参照してください。

</dd>
<dt>--output FORMAT、-o FORMAT</dt>
<dd>(オプション) コマンド出力は選択された形式で返されます。 デフォルトの形式は `text` です。 以下の形式がサポートされています。



<ul>

<li>`text`</li>
<li>`json`</li>
</ul>

</dd>
<dt>--vulnerabilities、-v</dt>
<dd>(オプション) コマンド出力は脆弱性のみを表示するよう制限されます。</dd>
<dt>--configuration-issues、-c</dt>
<dd>(オプション) コマンド出力は構成の問題のみを表示するよう制限されます。</dd>
<dt>--extended、-e </dt>
<dd>(オプション) コマンド出力は脆弱なパッケージのフィックスについての追加情報を表示します。</dd>

</dl>

