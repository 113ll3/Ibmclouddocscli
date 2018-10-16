---

copyright:

  years: 2018


lastupdated: "2018-10-04"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# プラグイン
{: #ibmcloud_commands_settings}

以下のコマンドを使用して、{{site.data.keyword.Bluemix_notm}} CLI プラグインを管理します。
{: shortdesc}

<table summary="{{site.data.keyword.Bluemix_notm}} CLI プラグインを管理するために使用できる ibmcloud コマンド。">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud plugin repo-add](cli_plugin.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_plugin.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_plugin.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_plugin.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list](cli_plugin.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_plugin.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_plugin.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_plugin.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update](cli_plugin.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud plugin repos](cli_plugin.html#ibmcloud_plugin_repos)</td>
</tr>
 </tbody>
 </table>


 ## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

{{site.data.keyword.Bluemix_notm}} CLI に登録されているすべてのプラグイン・リポジトリーをリストします。

```
ibmcloud plugin repos
```

<strong>前提条件</strong>: なし

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

新規プラグイン・リポジトリーを {{site.data.keyword.Bluemix_notm}} CLI に追加します。

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>REPO_NAME (必須)</dt>
   <dd>追加するリポジトリーの名前。 各リポジトリーに対して任意の名前を定義できます。</dd>
   <dt>REPO_URL (必須)</dt>
   <dd>追加するリポジトリーの URL。 リポジトリー URL にはプロトコルが含まれている必要があります (例えば、plugins.ng.bluemix.net ではなく、http://plugins.ng.bluemix.net)。 {{site.data.keyword.Bluemix_notm}} CLI の公式プラグイン・リポジトリーは http://plugins.ng.bluemix.net です。</dd>
    </dl>


<strong>例</strong>:

{{site.data.keyword.Bluemix_notm}} CLI の公式プラグイン・リポジトリーを `IBM Cloud-repo` として追加します。

```
ibmcloud plugin repo-add IBM Cloud-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

{{site.data.keyword.Bluemix_notm}} CLI からプラグイン・リポジトリーを削除します。

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>REPO_NAME (必須)</dt>
   <dd>削除するリポジトリーの名前。</dd>
   </dl>

<strong>例</strong>:

{{site.data.keyword.Bluemix_notm}} CLI から `IBM Cloud-repo` リポジトリーを削除します。

```
ibmcloud plugin repo-remove IBM Cloud-repo
```

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

`IBM Cloud-repo` リポジトリー内のすべてのプラグインをリストします。

```
ibmcloud plugin repo-plugins -r IBM Cloud-repo
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

{{site.data.keyword.Bluemix_notm}} CLI 内のインストールされたプラグインをすべてリストします。

```
ibmcloud plugin list
```

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

指定したパスまたはリポジトリーから、特定のバージョンのプラグインを {{site.data.keyword.Bluemix_notm}} CLI にインストールします。

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「IBM Cloud」を使用します。バージョンが指定されない場合、コマンドは、インストール可能な最新バージョンを選択します。

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME (必須)</dt>
   <dd>「-r <i>REPO_NAME</i>」が指定されない場合、指定されたローカル・パスまたはリモート URL からプラグインがインストールされます。</dd>
   <dt>-r <i>REPO_NAME</i> (オプション)</dt>
   <dd>プラグインのバイナリーが配置されているリポジトリーの名前。 リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「IBM Cloud」を使用します。</dd>
   <dt>-v <i>VERSION</i> (オプション)</dt>
   <dd>インストールするプラグインのバージョン。 指定されていない場合は、最新バージョンのプラグインがインストールされます。 このオプションは、リポジトリーからプラグインをインストールする場合にのみ有効です。</dd>
   <dt>-f </dt>
   <dd>確認なしでプラグインのインストールを強制します。</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI の公式リポジトリー名は、`IBM Cloud` です。

<strong>例</strong>:

ローカル・ファイルからプラグインをインストールします。

```
ibmcloud plugin install /downloads/new_plugin
```

リモート URL からプラグインをインストールします。

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

最新バージョンの「container-service」プラグインを「IBM Cloud」リポジトリーからインストールするには、以下のように指定します。

```
ibmcloud plugin install container-service -r IBM Cloud
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

リポジトリーが指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「IBM Cloud」を使用します。バージョンが指定されない場合、コマンドは、インストール可能な最新バージョンを選択します。

<strong>前提条件</strong>: なし

<strong>コマンド・オプション</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>更新するプラグインの名前。 指定されない場合、コマンドは、インストールされているすべてのプラグインのアップグレードを確認します。</dd>
 <dt>-r REPO_NAME</dt>
 <dd>プラグインのバイナリーが配置されているリポジトリーの名前。 指定されない場合、コマンドは、デフォルトのプラグイン・リポジトリー「IBM Cloud」を使用します。</dd>
 <dt>-v <i>VERSION</i> (オプション)</dt>
 <dd>更新するプラグインのバージョン。 表示されない場合、プラグインを入手可能な最新バージョンに更新してください。</dd>
 <dt>--all</dt>
 <dd>利用可能なすべてのプラグインを更新します</dd>
</dl>

<strong>例</strong>:

公式プラグイン・リポジトリー「IBM Cloud」内の使用可能なすべてのアップグレードを確認するには、以下のように指定します。

```
ibmcloud plugin update -r IBM Cloud
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

指定されたプラグインを {{site.data.keyword.Bluemix_notm}} CLI からアンインストールします。

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
