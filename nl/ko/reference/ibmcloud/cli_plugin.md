---

copyright:

  years: 2018


lastupdated: "2018-10-04"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 플러그인
{: #ibmcloud_commands_settings}

다음 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} CLI 플러그인을 관리하십시오.
{: shortdesc}

<table summary="{{site.data.keyword.Bluemix_notm}} CLI 플러그인을 관리하는 데 사용할 수 있는 ibmcloud 명령.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud plugin repo-add](cli_plugin.html#ibmcloud_plugin_repo_add)</td>
  <td>[ibmcloud plugin repo-remove](cli_plugin.html#ibmcloud_plugin_repo_remove)</td>
  <td>[ibmcloud plugin repo-plugins](cli_plugin.html#ibmcloud_plugin_repo_plugins)</td>
  <td>[ibmcloud plugin repo-plugin](cli_plugin.html#ibmcloud_plugin_repo_plugin)</td>
  <td>[ibmcloud plugin list
](cli_plugin.html#ibmcloud_plugin_list)</td>
</tr>
<tr>
  <td>[ibmcloud plugin show](cli_plugin.html#ibmcloud_plugin_show)</td>
  <td>[ibmcloud plugin install](cli_plugin.html#ibmcloud_plugin_install)</td>
  <td>[ibmcloud plugin uninstall](cli_plugin.html#ibmcloud_plugin_uninstall)</td>
  <td>[ibmcloud plugin update
](cli_plugin.html#ibmcloud_plugin_update)</td>
  <td>[ibmcloud plugin repos](cli_plugin.html#ibmcloud_plugin_repos)</td>
</tr>
 </tbody>
 </table>


 ## ibmcloud plugin repos
{: #ibmcloud_plugin_repos}

{{site.data.keyword.Bluemix_notm}} CLI에 등록된 모든 플러그인 저장소를 나열합니다.

```
ibmcloud plugin repos
```

<strong>전제조건</strong>: 없음

## ibmcloud plugin repo-add
{: #ibmcloud_plugin_repo_add}

{{site.data.keyword.Bluemix_notm}} CLI에 새 플러그인 저장소를 추가합니다.

```
ibmcloud plugin repo-add REPO_NAME REPO_URL
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>REPO_NAME(필수)</dt>
   <dd>추가되는 저장소의 이름입니다. 각 저장소의 고유 이름을 정의할 수 있습니다.</dd>
   <dt>REPO_URL(필수)</dt>
   <dd>추가되는 저장소의 URL입니다. 저장소 URL에는 프로토콜이 포함되어 있어야 합니다(예: plugins.ng.bluemix.net이 아닌 http://plugins.ng.bluemix.net). 다음이 {{site.data.keyword.Bluemix_notm}} CLI의 공식 플러그인 저장소입니다. http://plugins.ng.bluemix.net</dd>
    </dl>


<strong>예제</strong>:

{{site.data.keyword.Bluemix_notm}} CLI의 공식 플러그인 저장소를 `IBM Cloud-repo`로 추가합니다.

```
ibmcloud plugin repo-add IBM Cloud-repo http://plugins.ng.bluemix.net
```

## ibmcloud plugin repo-remove
{: #ibmcloud_plugin_repo_remove}

{{site.data.keyword.Bluemix_notm}} CLI에서 플러그인 저장소를 제거합니다.

```
ibmcloud plugin repo-remove REPO_NAME
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>REPO_NAME(필수)</dt>
   <dd>제거되는 저장소의 이름입니다.</dd>
   </dl>

<strong>예제</strong>:

{{site.data.keyword.Bluemix_notm}} CLI에서 `IBM Cloud-repo` 저장소를 제거합니다.

```
ibmcloud plugin repo-remove IBM Cloud-repo
```

## ibmcloud plugin repo-plugins
{: #ibmcloud_plugin_repo_plugins}

추가된 모든 저장소 또는 특정 저장소에서 사용 가능한 모든 플러그인을 나열합니다.

```
ibmcloud plugin repo-plugins [-r REPO_NAME]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i>(선택사항)</dt>
   <dd>지정된 저장소의 플러그인만 나열합니다.</dd>
   </dl>

<strong>예제</strong>:

모든 추가된 저장소의 플러그인을 나열합니다.

```
ibmcloud plugin repo-plugins
```

`IBm Cloud-repo` 저장소의 모든 플러그인을 나열합니다.

```
ibmcloud plugin repo-plugins -r IBM Cloud-repo
```

## ibmcloud plugin repo-plugin
{: #ibmcloud_plugin_repo_plugin}

저장소의 플러그인 세부사항을 표시합니다.

```
ibmcloud plugin repo-plugin PLUGIN_NAME [-r REPO_NAME]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>-r <i>REPO_NAME</i>(선택사항)</dt>
   <dd>저장소 이름. 저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소를 사용합니다.</dd>
   </dl>

<strong>예제</strong>:

"sample-repo" 저장소의 "IBM-Containers" 플러그인 세부사항 나열:

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

기본 저장소의 "IBM-Containers" 플러그인 세부사항 나열

```
ibmcloud plugin repo-plugin IBM-Containers -r sample-repo
```

## ibmcloud plugin list
{: #ibmcloud_plugin_list}

{{site.data.keyword.Bluemix_notm}} CLI의 설치된 모든 플러그인을 나열합니다.

```
ibmcloud plugin list
```

<strong>전제조건</strong>: 없음

## ibmcloud plugin show
{: #ibmcloud_plugin_show}

설치된 플러그인의 세부사항을 표시합니다.

```
ibmcloud plugin show PLUGIN-NAME
```

<strong>전제조건</strong>: 없음

## ibmcloud plugin install
{: #ibmcloud_plugin_install}

지정된 경로 또는 저장소의 {{site.data.keyword.Bluemix_notm}} CLI에 특정 버전의 플러그인을 설치합니다.

```
ibmcloud plugin install PLUGIN_PATH|PLUGIN_NAME [-r REPO_NAME] [-v VERSION]
```

```
ibmcloud plugin install LOCAL-PATH/TO/PLUGIN | URL [-f]
```

저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소 'IBM Cloud'를 사용합니다.
버전이 지정되지 않은 경우 명령은 설치할 최신의 사용 가능한 버전을 선택합니다.

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>PLUGIN_PATH|PLUGIN_NAME(필수)</dt>
   <dd>-r <i>REPO_NAME</i>이 지정되지 않은 경우 플러그인은 지정된 로컬 경로 또는 원격 URL에서 설치됩니다.</dd>
   <dt>-r <i>REPO_NAME</i>(선택사항)</dt>
   <dd>플러그인 2진이 있는 저장소의 이름입니다. 저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소 'IBM Cloud'를 사용합니다.</dd>
   <dt>-v <i>VERSION</i>(선택사항)</dt>
   <dd>설치될 플러그인의 버전입니다. 제공되지 않은 경우 최신 버전의 플러그인이 설치됩니다. 이 옵션은 저장소에서 플러그인을 설치하는 경우에만 유효합니다.</dd>
   <dt>-f </dt>
   <dd>확인 없이 플러그인 설치를 강제 실행합니다.</dd>
    </dl>


{{site.data.keyword.Bluemix_notm}} CLI의 공식 저장소 이름은 `IBM Cloud`입니다.

<strong>예제</strong>:

로컬 파일에서 플러그인 설치:

```
ibmcloud plugin install /downloads/new_plugin
```

원격 URL에서 플러그인 설치:

```
ibmcloud plugin install http://plugins.ng.bluemix.net/downloads/new_plugin
```

'IBM Cloud' 저장소에서 최신 버전의 'container-service' 플러그인을 설치합니다.

```
ibmcloud plugin install container-service -r IBM Cloud
```

또는 단순히

```
ibmcloud plugin install container-service
```

공식 플러그인 저장소에서 버전 '0.1.425'의 'container-service' 플러그인 설치:

```
ibmcloud plugin install container-service -v 0.1.425
```

## ibmcloud plugin update
{: #ibmcloud_plugin_update}

저장소에서 플러그인을 업그레이드합니다.

```
ibmcloud plugin update [PLUGIN NAME] [-r REPO_NAME] [-v VERSION] [--all]
```

저장소가 지정되지 않은 경우 명령은 기본 플러그인 저장소 'IBM Cloud'를 사용합니다.
버전이 지정되지 않은 경우 명령은 설치할 최신의 사용 가능한 버전을 선택합니다.

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
 <dt>PLUGIN NAME</dt>
 <dd>업데이트할 플러그인의 이름입니다. 지정되지 않은 경우, 이 명령은 설치된 모든 플러그인의 업그레이드를 확인합니다.</dd>
 <dt>-r REPO_NAME</dt>
 <dd>플러그인 2진이 있는 저장소의 이름입니다. 지정되지 않은 경우 명령은 기본 플러그인 저장소 'IBM Cloud'를 사용합니다.</dd>
 <dt>-v <i>VERSION</i>(선택사항)</dt>
 <dd>업데이트되는 플러그인의 버전입니다. 제공되지 않은 경우 최신 사용 가능 버전으로 플러그인을 업데이트합니다.</dd>
 <dt>--all</dt>
 <dd>사용 가능한 플러그인 모두 업데이트</dd>
</dl>

<strong>예제</strong>:

공식 플러그인 저장소 'IBM Cloud'에서 사용 가능한 모든 업그레이드 확인:

```
ibmcloud plugin update -r IBM Cloud
```

또는 단순히

```
ibmcloud plugin update
```

공식 플러그인 저장소의 플러그인 'container-service'를 최신으로 업그레이드:

```
ibmcloud plugin update container-service
```

공식 플러그인 저장소의 플러그인 'container-service'를 버전 '0.1.440'으로 업데이트:

```
ibmcloud plugin update container-service -v 0.1.440
```

## ibmcloud plugin uninstall
{: #ibmcloud_plugin_uninstall}

{{site.data.keyword.Bluemix_notm}} CLI에서 지정된 플러그인을 설치 제거합니다.

```
ibmcloud plugin uninstall PLUGIN_NAME
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>PLUGIN_NAME(필수)</dt>
   <dd>설치 제거될 플러그인의 이름입니다.</dd>
    </dl>

<strong>예제</strong>:

이전에 설치된 'container-service' 플러그인 설치 제거:

```
ibmcloud plugin uninstall container-service
```
