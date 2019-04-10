---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-15"

keywords: add cli plug-in, remove cli plug-in, cli plug-in, ibmcloud plugin, repo-add, repo-remove, plugin uninstall, plugin update

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# {{site.data.keyword.cloud_notm}} CLI プラグインの追加および削除
{: #ibmcloud_commands_settings}

{{site.data.keyword.cloud}} は、機能を拡張するためにプラグイン・フレームワークをサポートしています。 以下のコマンドを使用して、{{site.data.keyword.cloud_notm}} CLI プラグインを管理します。
{: shortdesc}

## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

{{site.data.keyword.cloud_notm}} CLI に登録されているすべてのプラグイン・リポジトリーをリストします。
```
ibmcloud plugin repos
```
{: codeblock}

<strong>前提条件</strong>: なし

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

新規プラグイン・リポジトリーを {{site.data.keyword.cloud_notm}} CLI に追加します。
```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>REPO_NAME (必須)</dt>
   <dd>追加するリポジトリーの名前。 各リポジトリーに対して任意の名前を定義できます。</dd>
   <dt>REPO_URL (必須)</dt>
   <dd>追加するリポジトリーの URL。 リポジトリー URL にはプロトコルが含まれている必要があります (例えば、plugins.cloud.ibm.com ではなく、https://plugins.cloud.ibm.com)。{{site.data.keyword.cloud_notm}} CLI の公式プラグイン・リポジトリーは https://plugins.cloud.ibm.com です。</dd>
    </dl>


<strong>例</strong>:

{{site.data.keyword.cloud_notm}} CLI の公式プラグイン・リポジトリーを `ibmcloud-repo` として追加します。
```
ibmcloud plugin repo-add ibmcloud-repo https://plugins.cloud.ibm.com
```
{: codeblock}

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

{{site.data.keyword.cloud_notm}} CLI からプラグイン・リポジトリーを削除します。
```
ibmcloud plugin repo-remove REPO_NAME
```
{: codeblock}

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>REPO_NAME (必須)</dt>
   <dd>削除するリポジトリーの名前。</dd>
   </dl>

<strong>例</strong>:

{{site.data.keyword.cloud_notm}} CLI から `ibmcloud-repo` リポジトリーを削除します。
```
ibmcloud plugin repo-remove ibmcloud-repo
```
{: codeblock}

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

追加されたすべてのリポジトリーまたは特定のリポジトリー内にある使用可能なプラグインをすべてリストします。
```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>指定されたリポジトリー内のプラグインのみをリストします。</dd>
   </dl>

<strong>例</strong>:

追加されたすべてのリポジトリー内のすべてのプラグインをリストします。

```
ibmcloud plugin repo-plugins
```

`ibmcloud-repo` リポジトリー内のすべてのプラグインをリストします。

```
ibmcloud plugin repo-plugins -r ibmcloud-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

リポジトリー内のプラグインの詳細を表示します。

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>リポジトリーの名前。 リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリーを使用します</dd>
   </dl>

<strong>例</strong>:

リポジトリー「sample-repo」内のプラグイン「IBM-Containers」の詳細をリストします

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

デフォルト・リポジトリー内のプラグイン「IBM-Containers」の詳細をリストします

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

{{site.data.keyword.cloud_notm}} CLI 内のインストールされたプラグインをすべてリストします。
```
ibmcloud plugin list
```
{: codeblock}

<strong>前提条件</strong>: なし

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

インストールされたプラグインの詳細を表示します。
```
ibmcloud plugin show PLUGIN-NAME
```

<strong>前提条件</strong>: なし

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

指定したパスまたはリポジトリーから、特定のバージョンのプラグインを {{site.data.keyword.cloud_notm}} CLI にインストールします。
```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。
バージョンが指定されない場合、コマンドは、インストール可能な最新バージョンを選択します。

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (必須)</dt>
   <dd>「-r <i>REPO_NAME</i>」が指定されない場合、指定されたローカル・パスまたはリモート URL からプラグインがインストールされます。</dd>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>プラグインのバイナリーが配置されているリポジトリーの名前。 リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。</dd>
   <dt>-v <i>VERSION</i> (オプション)</dt>
   <dd>インストールするプラグインのバージョン。 指定されていない場合は、最新バージョンのプラグインがインストールされます。 このオプションは、リポジトリーからプラグインをインストールする場合にのみ有効です。</dd>
   <dt>-f </dt>
   <dd>確認なしでプラグインのインストールを強制します。</dd>
    </dl>


{{site.data.keyword.cloud_notm}} CLI の公式リポジトリー名は、`Bluemix` です。

<strong>例</strong>:

ローカル・ファイルからプラグインをインストールします。

```
ibmcloud plugin install /downloads/new_plugin
```

リモート URL からプラグインをインストールします。

```
ibmcloud plugin install https://plugins.cloud.ibm.com/downloads/bluemix-plugins/new_plugin
```

最新バージョンの「container-service」プラグインを「Bluemix」リポジトリーからインストールするには、以下のように指定します。

```
ibmcloud plugin install container-service -r Bluemix
```

あるいは、簡単に以下のように指定します。

```
ibmcloud plugin install container-service
```

公式プラグイン・リポジトリーから、バージョン「0.1.425」の「container-service」プラグインをインストールするには、以下のように指定します。

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

リポジトリーからプラグインをアップグレードします。

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。
バージョンが指定されない場合、コマンドは、インストール可能な最新バージョンを選択します。

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>更新するプラグインの名前。 指定されない場合、コマンドは、インストールされているすべてのプラグインのアップグレードを確認します。</dd>
 <dt>-r REPO_NAME</dt>
 <dd>プラグインのバイナリーが配置されているリポジトリーの名前。 指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「Bluemix」を使用します。</dd>
 <dt>-v <i>VERSION</i> (オプション)</dt>
 <dd>更新するプラグインのバージョン。 表示されない場合、プラグインを入手可能な最新バージョンに更新してください。</dd>
 <dt>--all</dt>
 <dd>利用可能なすべてのプラグインを更新します</dd>
</dl>

<strong>例</strong>:

公式プラグイン・リポジトリー「Bluemix」内のすべての使用可能アップグレードを確認するには、以下のように指定します。

```
ibmcloud plugin update -r Bluemix
```

あるいは、簡単に以下のように指定します。

```
ibmcloud plugin update
```

公式プラグイン・リポジトリー内のプラグイン「container-service」を最新にアップグレードするには、以下のように指定します。

```
ibmcloud plugin update container-service
```

公式プラグイン・リポジトリー内のプラグイン「container-service」をバージョン「0.1.440」に更新するには、以下のように指定します。

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

指定されたプラグインを {{site.data.keyword.cloud_notm}} CLI からアンインストールします。

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>PLUGIN_NAME (必須)</dt>
   <dd>アンインストールされるプラグインの名前。</dd>
    </dl>

<strong>例</strong>:

前にインストールされた「container-service」プラグインをアンインストールします。

```
ibmcloud plugin uninstall container-service
```
