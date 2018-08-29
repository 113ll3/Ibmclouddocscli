---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# cf 앱 및 앱 관련 도메인, 라우트 및 인증서 관리
{: #ibmcloud_commands_apps}

<table summary="cf 앱 및 앱 관련 도메인, 라우트, 인증서를 관리하는 데 사용할 수 있는 ibmcloud 명령입니다. ">
<caption>표 1. 앱 및 앱 관련 도메인, 라우트 및 인증서 관리를 위한 명령</caption>
 <thead>
 <th colspan="5">cf 앱 및 앱 관련 도메인, 라우트 및 인증서 관리를 위한 명령</th>
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

이 명령은 [cf push ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/push.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app list
{: #ibmcloud_app_list}

이 명령은 [cf apps ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/apps.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app show
{: #ibmcloud_app_show}

이 명령은 [cf app ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/app.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app delete
{: #ibmcloud_app_delete}

이 명령은 [cf delete ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app rename
{: #ibmcloud_app_rename}

이 명령은 [cf rename ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/rename.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app start
{: #ibmcloud_app_start}

이 명령은 [cf start ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/start.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app stop
{: #ibmcloud_app_stop}

이 명령은 [cf stop ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stop.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app restart
{: #ibmcloud_app_restart}

이 명령은 [cf restart ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app restage
{: #ibmcloud_app_restage}


이 명령은 [cf restage ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restage.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app instance-restart
{: #ibmcloud_app_instance_restart}


이 명령은 [cf restart-app-instance ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/restart-app-instance.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app events
{: #ibmcloud_app_events}

이 명령은 [cf events ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/events.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app files
{: #ibmcloud_app_files}

이 명령은 [cf files ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/files.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app logs
{: #ibmcloud_app_logs}

이 명령은 [cf logs ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/logs.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app env
{: #ibmcloud_app_env}

이 명령은 [cf env ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/env.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app env-set
{: #ibmcloud_app_env_set}

이 명령은 [cf set-env ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/set-env.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app env-unset
{: #ibmcloud_app_env_unset}

이 명령은 [cf unset-env ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/unset-env.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app stacks
{: #ibmcloud_app_stacks}

이 명령은 [cf stacks ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stacks.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app stack-show
{: #ibmcloud_app_stack_show}

이 명령은 [cf stack ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/stack.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app manifest-create
{: #ibmcloud_app_manifest_create}

이 명령은 [cf create-app-manifest ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-app-manifest.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app domain-cert
{: #ibmcloud_app_domain_cert}

도메인의 인증서 정보를 나열합니다.

```
ibmcloud app domain-cert DOMAIN_NAME
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
<dl>
<dt>DOMAIN_NAME(필수)</dt>
<dd>인증서를 호스팅하는 도메인입니다.</dd>
</dl>


<strong>예제</strong>:

`ibmcxo-eventconnect.com` 도메인의 인증서 정보를 봅니다.

```
ibmcloud app domain-cert ibmcxo-eventconnect.com
```

## ibmcloud app domain-cert-add
{: #ibmcloud_app_domain_cert_add}

현재 조직의 지정된 도메인에 인증서를 추가합니다.

```
ibmcloud app domain-cert-add DOMAIN -k PRIVATE_KEY_FILE -c CERT_FILE [-p PASSWORD] [-i INTERMEDIATE_CERT_FILE] [-t TRUST_STORE_FILE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:
   <dl>
   <dt>DOMAIN(필수)</dt>
   <dd>인증서가 추가되는 도메인입니다.</dd>
   <dt>-k <i>PRIVATE_KEY_FILE</i>(필수)</dt>
   <dd>개인 키 파일 경로입니다.</dd>
   <dt>-c <i>CERT_FILE</i>(필수)</dt>
   <dd>인증서 파일 경로입니다.</dd>
   <dt>-p <i>PASSWORD</i>(선택사항)</dt>
   <dd>인증서의 비밀번호입니다.</dd>
   <dt>-i <i>INTERMEDIATE_CERT_FILE</i>(선택사항)</dt>
   <dd>중간 인증서 파일 경로입니다.</dd>
   <dt>-t <i>TRUST_STORE_FILE</i>(선택사항)</dt>
   <dd>신뢰 저장소 파일입니다.</dd>
   </dl>


<strong>예제</strong>:

인증서를 도메인 `ibmcxo-eventconnect.com`에 추가합니다.

```
ibmcloud app domain-cert-add ibmcxo-eventconnect.com -k key_file.key -c cert_file.crt -p 123 -i inter_cert.cert
```

## ibmcloud app domain-cert-remove
{: #ibmcloud_app_domain_cert_remove}

현재 조직의 지정된 도메인에서 인증서를 제거합니다.

```
ibmcloud app domain-cert-remove DOMAIN [-f]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>DOMAIN(필수)</dt>
   <dd>인증서가 제거되는 도메인입니다.</dd>
   <dt>-f(선택사항)</dt>
   <dd>확인 없이 강제 삭제합니다.</dd>
   </dl>

## ibmcloud app routes
{: #ibmcloud_app_routes}

이 명령은 [cf routes ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/routes.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app route-check
{: #ibmcloud_app_route_check}

이 명령은 [cf check-route ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/check-route.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app route-map
{: #ibmcloud_app_route_map}

지정된 도메인과 호스트 이름이 있는 기존의 cf 애플리케이션 또는 컨테이너 그룹에 라우트를 맵핑합니다.

```
ibmcloud app route-map CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME(필수)</dt>
   <dd>라우트로 맵핑되는 cf 애플리케이션 또는 컨테이너 그룹의 이름입니다.</dd>
   <dt>DOMAIN(필수)</dt>
   <dd>라우트의 도메인입니다. 예: mychinabluemix.net 또는 chinabluemix.net. </dd>
   <dt>-n <i>HOST_NAME</i>(선택사항)</dt>
   <dd>라우트의 호스트 이름입니다. 값을 제공하지 않으면 호스트 이름이 기본적으로 앱 이름 또는 컨테이너 그룹 이름으로 설정됩니다.</dd>
   </dl>

<strong>예제</strong>:

라우트를 지정된 도메인이 있는 `my-app`으로 맵핑합니다.

```
ibmcloud app route-map my-app mychinabluemix.net
```

라우트를 지정된 도메인과 호스트 이름이 있는 'my-container-group'으로 맵핑합니다.

```
ibmcloud app route-map my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-unmap
{: #ibmcloud_app_route_unmap}

기존의 cf 애플리케이션이나 컨테이너 그룹과 지정된 라우트의 맵핑을 해제합니다.

```
ibmcloud app route-unmap CF_APP_NAME|CONTAINER_GROUP_NAME  DOMAIN  [-n HOST_NAME]
```

<strong>전제조건</strong>: 엔드포인트, 로그인, 대상

<strong>명령 옵션</strong>:

   <dl>
   <dt>CF_APP_NAME|CONTAINER_GROUP_NAME(필수)</dt>
   <dd>cf 애플리케이션 또는 컨테이너 그룹의 이름입니다.</dd>
   <dt>DOMAIN(필수)</dt>
   <dd>라우트의 도메인입니다(예: mychinabluemix.net 또는 chinabluemix.net).</dd>
   <dt>-n <i>HOST_NAME</i>(선택사항)</dt>
   <dd>라우트의 호스트 이름입니다. 값을 제공하지 않으면 호스트 이름이 기본적으로 앱 이름 또는 컨테이너 그룹 이름으로 설정됩니다.</dd>
   </dl>

<strong>예제</strong>:

`my-app`에서 `my-app.mychinabluemix.net`을 맵핑 해제합니다.

```
ibmcloud app route-unmap my-app mychianbluemix.net
```

`my-container-group`에서 `abc.chinabluexmix.net`을 맵핑 해제합니다.

```
ibmcloud app route-unmap my-container-group chinabluemix.net -n abc
```

## ibmcloud app route-create
{: #ibmcloud_app_route_create}

이 명령은 [cf create-route ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-route.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app route-delete
{: #ibmcloud_app_route_delete}

이 명령은 [cf delete-route ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-route.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app orphaned-routes-delete
{: #ibmcloud_app_orphaned_routes_delete}

이 명령은 [cf delete-orphaned-routes ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-orphaned-routes.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app domains
{: #ibmcloud_app_domains}

이 명령은 [cf domains ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/domains.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app domain-create
{: #ibmcloud_app_domain_create}

이 명령은 [cf create-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app domain-delete
{: #ibmcloud_app_domain_delete}

이 명령은 [cf delete-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app shared-domain-create
{: #ibmcloud_app_shared_domain_create}

이 명령은 [cf create-shared-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/create-shared-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.

## ibmcloud app shared-domain-delete
{: #ibmcloud_app_shared_domain_delete}

이 명령은 [cf delete-shared-domain ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://cli.cloudfoundry.org/en-US/cf/delete-shared-domain.html){: new_window} 명령과 동일한 기능 및 옵션을 가집니다.
