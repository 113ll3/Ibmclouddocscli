---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# CF アプリとアプリ関連ドメイン、経路、および証明書の管理
{: #ibmcloud_commands_apps}

<table summary="CF アプリとアプリ関連ドメイン、経路、および証明書を管理するために使用できる ibmcloud コマンド。">
<caption>表 1. CF アプリとアプリ関連ドメイン、経路、および証明書を管理するためのコマンド</caption>
 <thead>
 <th colspan="5">CF アプリとアプリ関連ドメイン、経路、および証明書を管理するためのコマンド</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud app push](cli_cf_apps.html#ibmcloud_app_push)</td>
 <td>[ibmcloud app list](cli_cf_apps.html#ibmcloud_app_list)</td>
 <td>[ibmcloud app show](cli_cf_apps.html#ibmcloud_app_show)</td>
 <td>[ibmcloud app delete](cli_cf_apps.html#ibmcloud_app_delete)</td>
 <td>[ibmcloud app rename](cli_cf_apps.html#ibmcloud_app_rename)</td>
 </tr>
 <tr>
 <td>[ibmcloud app start](cli_cf_apps.html#ibmcloud_app_start)</td>
 <td>[ibmcloud app stop](cli_cf_apps.html#ibmcloud_app_stop)</td>
 <td>[ibmcloud app restart](cli_cf_apps.html#ibmcloud_app_restart)</td>
 <td>[ibmcloud app restage](cli_cf_apps.html#ibmcloud_app_restage)</td>
 <td>[ibmcloud app instance-restart](cli_cf_apps.html#ibmcloud_app_instance_restart)</td>
 </tr>
 <tr>
 <td>[ibmcloud app events](cli_cf_apps.html#ibmcloud_app_events)</td>
 <td>[ibmcloud app files](cli_cf_apps.html#ibmcloud_app_files)</td>
 <td>[ibmcloud app logs](cli_cf_apps.html#ibmcloud_app_logs)</td>
 <td>[ibmcloud app env](cli_cf_apps.html#ibmcloud_app_env)</td>
 <td>[ibmcloud app env-set](cli_cf_apps.html#ibmcloud_app_env_set)</td>
 </tr>
 <tr>
 <td>[ibmcloud app env-unset](cli_cf_apps.html#ibmcloud_app_env_unset)</td>
 <td>[ibmcloud app stacks](cli_cf_apps.html#ibmcloud_app_stacks)</td>
 <td>[ibmcloud app stack-show](cli_cf_apps.html#ibmcloud_app_stack_show)</td>
 <td>[ibmcloud app manifest-create](cli_cf_apps.html#ibmcloud_app_manifest_create)</td>
 <td>[ibmcloud app domain-cert](cli_cf_apps.html#ibmcloud_app_domain_cert)</td>
 </tr>
 <tr>
  <td>[ibmcloud app domain-cert-add](cli_cf_apps.html#ibmcloud_app_domain_cert_add)</td>
  <td>[ibmcloud app domain-cert-remove](cli_cf_apps.html#ibmcloud_app_domain_cert_remove)</td>
  <td>[ibmcloud app domains](cli_cf_apps.html#ibmcloud_app_domains)</td>
  <td>[ibmcloud app domain-create](cli_cf_apps.html#ibmcloud_app_domain_create)</td>
  <td>[ibmcloud app domain-delete](cli_cf_apps.html#ibmcloud_app_domain_delete)</td>
 </tr>
 <tr>
  <td>[ibmcloud app shared-domain-create](cli_cf_apps.html#ibmcloud_app_shared_domain_create)</td>
  <td>[ibmcloud app shared-domain-delete](cli_cf_apps.html#ibmcloud_app_shared_domain_delete)</td>
  <td>[ibmcloud app routes](cli_cf_apps.html#ibmcloud_app_routes)</td>
  <td>[ibmcloud app route-check](cli_cf_apps.html#ibmcloud_app_route_check)</td>
  <td>[ibmcloud app route-map](cli_cf_apps.html#ibmcloud_app_route_map)</td>
 </tr>
 <tr>
  <td>[ibmcloud app route-unmap](cli_cf_apps.html#ibmcloud_app_route_unmap)</td>
  <td>[ibmcloud app route-create](cli_cf_apps.html#ibmcloud_app_route_create)</td>
  <td>[ibmcloud app route-delete](cli_cf_apps.html#ibmcloud_app_route_delete)</td>
  <td>[ibmcloud app orphaned-routes-delete](cli_cf_apps.html#ibmcloud_app_orphaned_routes_delete)</td>
  <td></td>
 </tr>
  </tbody>
 </table>

 ## ibmcloud app push
{: #ibmcloud_app_push}

このコマンドの機能とオプションは [cf push![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window} コマンドと同じです。

## ibmcloud app list
{: #ibmcloud_app_list}

このコマンドの機能とオプションは [cf apps![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window} コマンドと同じです。

## ibmcloud app show
{: #ibmcloud_app_show}

このコマンドの機能とオプションは [cf app![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window} コマンドと同じです。

## ibmcloud app delete
{: #ibmcloud_app_delete}

このコマンドの機能とオプションは [cf delete![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window} コマンドと同じです。

## ibmcloud app rename
{: #ibmcloud_app_rename}

このコマンドの機能とオプションは [cf rename![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window} コマンドと同じです。

## ibmcloud app start
{: #ibmcloud_app_start}

このコマンドの機能とオプションは [cf start![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window} コマンドと同じです。

## ibmcloud app stop
{: #ibmcloud_app_stop}

このコマンドの機能とオプションは [cf stop![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window} コマンドと同じです。

## ibmcloud app restart
{: #ibmcloud_app_restart}

このコマンドの機能とオプションは [cf restart![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window} コマンドと同じです。

## ibmcloud app restage
{: #ibmcloud_app_restage}


このコマンドの機能とオプションは [cf restage![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window} コマンドと同じです。

## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


このコマンドの機能とオプションは [cf restart-app-instance![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window} コマンドと同じです。

## ibmcloud app events
{: #ibmcloud_app_events}

このコマンドの機能とオプションは [cf events![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window} コマンドと同じです。

## ibmcloud app files
{: #ibmcloud_app_files}

このコマンドの機能とオプションは [cf files![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window} コマンドと同じです。

## ibmcloud app logs
{: #ibmcloud_app_logs}

このコマンドの機能とオプションは [cf logs![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window} コマンドと同じです。

## ibmcloud app env
{: #ibmcloud_app_env}

このコマンドの機能とオプションは [cf env![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window} コマンドと同じです。

## ibmcloud app env-set
{: #ibmcloud_app_env_set}

このコマンドの機能とオプションは [cf set-env![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window} コマンドと同じです。

## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

このコマンドの機能とオプションは [cf unset-env![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window} コマンドと同じです。

## ibmcloud app stacks
{: #ibmcloud_app_stacks}

このコマンドの機能とオプションは [cf stacks![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window} コマンドと同じです。

## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

このコマンドの機能とオプションは [cf stack![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window} コマンドと同じです。

## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

このコマンドの機能とオプションは [cf create-app-manifest![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window} コマンドと同じです。

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

ドメインの証明書情報をリストします。

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>前提条件</strong>: エンドポイント、ログイン

<strong>コマンド・オプション</strong>:
<dl>
<dt>DOMAIN_NAME (必須)</dt>
<dd>証明書をホストするドメイン。</dd>
</dl>


<strong>例</strong>:

ドメイン `ibmcxo-eventconnect.com` の証明書情報を表示するには、次のように指定します。

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

現在の組織内の、指定したドメインに証明書を追加します。

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:
   <dl>
   <dt>DOMAIN (必須)</dt>
   <dd>証明書を追加するドメイン。</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i> (必須)</dt>
   <dd>秘密鍵ファイル・パス。</dd>
   <dt>-c <i>CERT_FILE</i> (必須)</dt>
   <dd>証明書ファイル・パス。</dd>
   <dt>-p <i>PASSWORD</i> (オプション)</dt>
   <dd>証明書のパスワード。</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i> (オプション)</dt>
   <dd>中間証明書ファイル・パス。</dd>
   <dt>-t <i>TRUST_STORE_FILE</i> (オプション)</dt>
   <dd>トラストストア・ファイル。</dd>
   </dl>


<strong>例</strong>:

ドメイン `ibmcxo-eventconnect.com` に証明書を追加するには、以下のように指定します。

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

現在の組織内の、指定したドメインから証明書を削除します。

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>DOMAIN (必須)</dt>
   <dd>証明書を削除するドメイン。</dd>
   <dt>-f (オプション)</dt>
   <dd>確認なしで削除を強制します。</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

このコマンドの機能とオプションは [cf routes![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window} コマンドと同じです。

## ibmcloud app route-check
{: #ibmcloud_app_route_check}

このコマンドの機能とオプションは [cf check-route![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window} コマンドと同じです。

## ibmcloud app route-map
{: #ibmcloud_app_route_map}

指定されたドメインおよびホスト名を持つ経路を既存 cf アプリケーションまたはコンテナー・グループにマップします。

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (必須)</dt>
   <dd>経路によってマップされる cf アプリケーションまたはコンテナー・
グループの名前。</dd>
   <dt>DOMAIN (必須)</dt>
   <dd>経路のドメイン。 例えば、mychinabluemix.net または chinabluemix.net などです。 </dd>
   <dt>-n <i>HOST_NAME</i> (オプション)</dt>
   <dd>経路のホスト名。 指定されない場合、ホスト名は、デフォルトで、アプリケーション名またはコンテナー・グループ名に設定されます。</dd>
   </dl>

<strong>例</strong>:

指定されたドメインで `my-app` に経路をマップします。

```
ibmcloud app route-map my-app mychinabluemix.net
```

指定されたドメインとホスト名で「my-container-group」に経路をマップします。

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

指定された経路を既存 cf アプリケーションまたはコンテナー・グループからマップ解除します。

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>前提条件</strong>: エンドポイント、ログイン、ターゲット

<strong>コマンド・オプション</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME (必須)</dt>
   <dd>cf アプリケーションまたはコンテナー・グループの名前。</dd>
   <dt>DOMAIN (必須)</dt>
   <dd>経路のドメイン (例えば、mychinabluemix.net または chinabluemix.net)。</dd>
   <dt>-n <i>HOST_NAME</i> (オプション)</dt>
   <dd>経路のホスト名。 指定されない場合、ホスト名は、デフォルトで、アプリケーション名またはコンテナー・グループ名に設定されます。</dd>
   </dl>

<strong>例</strong>:

`my-app.mychinabluemix.net` を `my-app` からマップ解除するには、以下のように指定します。

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

`abc.chinabluexmix.net` を `my-container-group` からマップ解除するには、以下のように指定します。

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-create
{: #ibmcloud_app_route_create}

このコマンドの機能とオプションは [cf create-route![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window} コマンドと同じです。

## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

このコマンドの機能とオプションは [cf delete-route![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window} コマンドと同じです。

## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

このコマンドの機能とオプションは [cf delete-orphaned-routes![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window} コマンドと同じです。

## ibmcloud app domains
{: #ibmcloud_app_domains}

このコマンドの機能とオプションは [cf domains![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window} コマンドと同じです。

## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

このコマンドの機能とオプションは [cf create-domain![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window} コマンドと同じです。

## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

このコマンドの機能とオプションは [cf delete-domain![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window} コマンドと同じです。

## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

このコマンドの機能とオプションは [cf create-shared-domain![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window} コマンドと同じです。

## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

このコマンドの機能とオプションは [cf delete-shared-domain![外部リンク・アイコン](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window} コマンドと同じです。
