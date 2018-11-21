---

copyright:

  years: 2018


lastupdated: "2018-11-05"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry 應用程式
{: #ibmcloud_commands_apps}

請使用下列指令管理 Cloud Foundry 應用程式、網域及路徑。
{: shortdesc}

<table summary="您可以用來管理 cf 應用程式及應用程式相關網域、路徑和憑證的 ibmcloud 指令。">
<thead>
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

這個指令的功能及選項與 [cf push ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window} 指令相同。

## ibmcloud app list
{: #ibmcloud_app_list}

這個指令的功能及選項與 [cf apps ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window} 指令相同。

## ibmcloud app show
{: #ibmcloud_app_show}

這個指令的功能及選項與 [cf app ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window} 指令相同。

## ibmcloud app delete
{: #ibmcloud_app_delete}

這個指令的功能及選項與 [cf delete ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window} 指令相同。

## ibmcloud app rename
{: #ibmcloud_app_rename}

這個指令的功能及選項與 [cf rename ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window} 指令相同。

## ibmcloud app start
{: #ibmcloud_app_start}

這個指令的功能及選項與 [cf start ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window} 指令相同。

## ibmcloud app stop
{: #ibmcloud_app_stop}

這個指令的功能及選項與 [cf stop ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window} 指令相同。

## ibmcloud app restart
{: #ibmcloud_app_restart}

這個指令的功能及選項與 [cf restart ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window} 指令相同。

## ibmcloud app restage
{: #ibmcloud_app_restage}


這個指令的功能及選項與 [cf restage ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window} 指令相同。

## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


這個指令的功能及選項與 [cf restart-app-instance ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window} 指令相同。

## ibmcloud app events
{: #ibmcloud_app_events}

這個指令的功能及選項與 [cf events ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window} 指令相同。

## ibmcloud app files
{: #ibmcloud_app_files}

這個指令的功能及選項與 [cf files ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window} 指令相同。

## ibmcloud app logs
{: #ibmcloud_app_logs}

這個指令的功能及選項與 [cf logs ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window} 指令相同。

## ibmcloud app env
{: #ibmcloud_app_env}

這個指令的功能及選項與 [cf env ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window} 指令相同。

## ibmcloud app env-set
{: #ibmcloud_app_env_set}

這個指令的功能及選項與 [cf set-env ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window} 指令相同。

## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

這個指令的功能及選項與 [cf unset-env ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window} 指令相同。

## ibmcloud app stacks
{: #ibmcloud_app_stacks}

這個指令的功能及選項與 [cf stacks ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window} 指令相同。

## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

這個指令的功能及選項與 [cf stack ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window} 指令相同。

## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

這個指令的功能及選項與 [cf create-app-manifest ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window} 指令相同。

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

列出網域的憑證資訊。

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>必要條件</strong>：端點、登入

<strong>指令選項</strong>：
<dl>
<dt>DOMAIN_NAME（必要）</dt>
<dd>管理憑證的網域。</dd>
</dl>


<strong>範例</strong>：

檢視網域 `ibmcxo-eventconnect.com` 的憑證資訊：

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

將憑證新增到現行組織中的指定網域。

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：
   <dl>
   <dt>DOMAIN（必要）</dt>
   <dd>要新增憑證的網域。</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i>（必要）</dt>
   <dd>私密金鑰檔案路徑。</dd>
   <dt>-c <i>CERT_FILE</i>（必要）</dt>
   <dd>憑證檔案路徑。</dd>
   <dt>-p <i>PASSWORD</i>（選用）</dt>
   <dd>憑證的密碼。</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i>（選用）</dt>
   <dd>中繼憑證檔案路徑。</dd>
   <dt>-t <i>TRUST_STORE_FILE</i>（選用）</dt>
   <dd>信任儲存庫檔案。</dd>
   </dl>


<strong>範例</strong>：

將憑證新增到網域 `ibmcxo-eventconnect.com`：

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

從現行組織中的指定網域移除憑證。

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>DOMAIN（必要）</dt>
   <dd>要從中移除憑證的網域。</dd>
   <dt>-f（選用）</dt>
   <dd>強制刪除，而不確認。</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

這個指令的功能及選項與 [cf routes ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window} 指令相同。

## ibmcloud app route-check
{: #ibmcloud_app_route_check}

這個指令的功能及選項與 [cf check-route ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window} 指令相同。

## ibmcloud app route-map
{: #ibmcloud_app_route_map}

將路徑對映到具有所指定網域及主機名稱的現有 cf 應用程式或容器群組。

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME（必要）</dt>
   <dd>要與路徑對映之 cf 應用程式或容器群組的名稱。</dd>
   <dt>DOMAIN（必要）</dt>
   <dd>路徑的網域。例如，mychinabluemix.net 或 chinabluemix.net。</dd>
   <dt>-n <i>HOST_NAME</i>（選用）</dt>
   <dd>路徑的主機名稱。如果未提供，則依預設會將主機名稱設為應用程式名稱或容器群組名稱。</dd>
   </dl>

<strong>範例</strong>：

將路徑對映到具有指定網域的 `my-app`：

```
ibmcloud app route-map my-app mychinabluemix.net
```

將路徑對映到具有指定網域及主機名稱的 'my-container-group'：

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

從現有的 cf 應用程式或容器群組中取消對映指定的路徑。

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>必要條件</strong>：端點、登入、目標

<strong>指令選項</strong>：

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME（必要）</dt>
   <dd>cf 應用程式或容器群組的名稱。</dd>
   <dt>DOMAIN（必要）</dt>
   <dd>路徑的網域（例如 mychinabluemix.net 或 chinabluemix.net）。</dd>
   <dt>-n <i>HOST_NAME</i>（選用）</dt>
   <dd>路徑的主機名稱。如果未提供，則依預設會將主機名稱設為應用程式名稱或容器群組名稱。</dd>
   </dl>

<strong>範例</strong>：

從 `my-app` 取消對映 `my-app.mychinabluemix.net`：

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

從 `my-container-group` 取消對映 `abc.chinabluexmix.net`：

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-create
{: #ibmcloud_app_route_create}

這個指令的功能及選項與 [cf create-route ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window} 指令相同。

## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

這個指令的功能及選項與 [cf delete-route ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window} 指令相同。

## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

這個指令的功能及選項與 [cf delete-orphaned-routes ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window} 指令相同。

## ibmcloud app domains
{: #ibmcloud_app_domains}

這個指令的功能及選項與 [cf domains ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window} 指令相同。

## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

這個指令的功能及選項與 [cf create-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window} 指令相同。

## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

這個指令的功能及選項與 [cf delete-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window} 指令相同。

## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

這個指令的功能及選項與 [cf create-shared-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window} 指令相同。

## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

這個指令的功能及選項與 [cf delete-shared-domain ![外部鏈結圖示](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window} 指令相同。
