---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 일반 CLI(ibmcloud) 명령
{: #ibmcloud_cli}

버전: 0.7.1

{{site.data.keyword.Bluemix_notm}} 명령행 인터페이스(CLI)는 사용자가 {{site.data.keyword.Bluemix_notm}}와 상호작용할 수 있도록 네임스페이스별로 그룹화된 명령 세트를 제공합니다.

버전 0.5.0부터 {{site.data.keyword.Bluemix_notm}} 명령행 클라이언트는 Cloud Foundry 명령행 클라이언트를 해당 설치에서 번들화합니다. 자신에게 직접 설치한 cf cli가 있는 경우에는 {{site.data.keyword.Bluemix_notm}} CLI 명령 `ibmcloud [command]`와 해당 설치의 Cloud Foundry CLI 명령 `cf [command]`를 동일한 컨텍스트에서 함께 사용하지 마십시오. cf cli를 사용하여 {{site.data.keyword.Bluemix_notm}} CLI 컨텍스트에서 Cloud Foundry 리소스를 관리하려면 `ibmcloud cf [command]`를 대신 사용하십시오.  `ibmcloud cf api/login/logout/target`은 허용되지 않으며 대신 `ibmcloud api/login/logout/target`을 사용해야 한다는 점을 참고하십시오.

2018년 5월부터 {{site.data.keyword.Bluemix_notm}} CLI 명령은 `bluemix` 및 `bx`에서 `ibmcloud`로 변경되었습니다. 하지만 `bluemix` 및 `bx` CLI 명령은 나중에 제거할 때까지 사용할 수 있습니다.
{: tip}

다음에는 해당 이름, 인수, 옵션, 필수 소프트웨어, 설명 및 예제를 포함하여 {{site.data.keyword.Bluemix_notm}} CLI에서 지원하는 자세한 명령이 나열되어 있습니다.
{:shortdesc}

**참고:** *전제조건*에는 명령을 사용하기 전에 필요한 조치가 설명되어 있습니다. 전제조건 조치가 없는 명령은 **없음**으로 표시됩니다. 그 밖의 경우에는 전제조건으로 다음과 같은 조치 중 하나 이상을 수행해야 할 수 있습니다.

<dl>
<dt>엔드포인트</dt>
<dd>명령을 사용하기 전에 <code>bluemix api</code>를 통해 API 엔드포인트를 설정해야 합니다.</dd>
<dt>로그인</dt>
<dd>이 명령을 사용하기 전에 <code>bluemix login</code> 명령을 사용하여 로그인해야 합니다.
 연합 ID로 로그인한 경우에는 '--sso' 옵션을 사용하여 일회성 패스코드로 인증하거나 '--apikey'를 사용하여 API 키로 인증하십시오. API 키를 작성하려면 {{site.data.keyword.Bluemix_notm}} 콘솔 **관리** &gt; **보안** &gt; **플랫폼 API 키**로 이동하십시오.
</dd>
<dt>대상</dt>
<dd>이 명령을 사용하기 전에 <code>bluemix target</code> 명령을 사용하여 조직과 영역을 설정해야 합니다.</dd>
<dt>Docker</dt>
<dd>이 명령을 실행하려면 Docker CLI(docker)가 설치되어 있어야 합니다.</dd>
</dl>


자주 사용되는 ibmcloud 명령을 참조하려면 다음 표의 색인을 사용하십시오.

## 일반 ibmcloud 명령
{: #ibmcloud_commands_index}

<table summary="일반 ibmcloud 명령입니다. ">
<caption>표 1. 일반 ibmcloud 명령</caption>
 <thead>
 <th colspan="5">일반 ibmcloud 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud help
](ic_cli_cmds.html#ibmcloud_help)</td>
 <td>[ibmcloud api
](ic_cli_cmds.html#ibmcloud_api)</td>
 <td>[ibmcloud config](ic_cli_cmds.html#ibmcloud_config)</td>
 <td>[ibmcloud info
](ic_cli_cmds.html#ibmcloud_info)</td>
 <td>[ibmcloud cf](ic_cli_cmds.html#ibmcloud_cf)</td>
 </tr>
 <tr>
 <td>[ibmcloud login](ic_cli_cmds.html#ibmcloud_login) </td>
 <td>[ibmcloud logout](ic_cli_cmds.html#ibmcloud_logout) </td>
 <td>[ibmcloud regions
](ic_cli_cmds.html#ibmcloud_regions)</td>
 <td>[ibmcloud target
](ic_cli_cmds.html#ibmcloud_target)</td>
 <td>[ibmcloud update](ic_cli_cmds.html#ibmcloud_update)</td>
 </tr>
 </tbody>
 </table>
 
 ## ibmcloud help
{: #ibmcloud_help}
첫 번째 레벨 기본 제공 명령 및 지원되는 {{site.data.keyword.Bluemix_notm}} CLI 네임스페이스에 대한 일반 도움말 또는 특정 기본 제공 명령 또는 네임스페이스의 도움말을 표시합니다.

```
ibmcloud help [COMMAND|NAMESPACE]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:

   <dl>
   <dt>COMMAND|NAMESPACE(선택사항)</dt>
   <dd>해당 도움말이 표시되는 명령 또는 네임스페이스입니다. 값을 지정하지 않으면 {{site.data.keyword.Bluemix_notm}} CLI의 일반 도움말이 표시됩니다.</dd>
   </dl>



<strong>예제</strong>:

{{site.data.keyword.Bluemix_notm}} CLI의 일반 도움말을 표시합니다.

```
ibmcloud help
```

`info` 명령의 도움말을 표시합니다.

```
ibmcloud help info
```

## ibmcloud api
{: #ibmcloud_api}
{{site.data.keyword.Bluemix_notm}} API 엔드포인트를 설정하거나 확인합니다.

```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>API_ENDPOINT(선택사항)</dt>
   <dd>대상으로 지정된 API 엔드포인트입니다(예: `https://api.chinabluemix.net`). *API_ENDPOINT* 및 `--unset` 옵션 중 하나를 지정하지 않으면 현재 API 엔드포인트가 표시됩니다.</dd>
   <dt>--unset(선택사항)</dt>
   <dd>API 엔드포인트 설정을 제거합니다.</dd>
   <dt>--skip-ssl-validation(선택사항)</dt>
   <dd>HTTP 요청의 SSL 유효성 검증을 무시합니다.</dd>
   </dl>
<strong>예제</strong>:

API 엔드포인트를 api.chinabluemix.net으로 설정합니다.

```
ibmcloud api api.chinabluemix.net
```

```
ibmcloud api https://api.chinabluemix.net --skip-ssl-validation
```

현재 API 엔드포인트를 확인합니다.

```
ibmcloud api
```

API 엔드포인트를 설정 해제합니다.

```
ibmcloud api --unset
```

## ibmcloud config
{: #ibmcloud_config}


구성 파일에 기본값을 작성합니다.

```
ibmcloud config --http-timeout TIMEOUT_IN_SECONDS | --trace (true|false|path/to/file) | --color (true|false) | --locale (LOCALE|CLEAR) | --check-version (true|false)
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>--http-timeout <i>TIMEOUT_IN_SECONDS</i></dt>
   <dd>HTTP 요청의 제한시간 값입니다. 기본값은 60초입니다.</dd>
   <dt>--trace true|false|<i>path-to-file</i></dt>
   <dd>터미널 또는 지정된 파일에 대한 HTTP 요청을 추적합니다.</dd>
   <dt>--color true|false</dt>
   <dd>색상 출력을 사용하거나 사용하지 않습니다. 색상 출력은 기본적으로 사용됩니다.</dd>
   <dt>--locale <i>LOCALE|CLEAR</i></dt>
   <dd>기본 로케일을 설정합니다. LOCALE이 <i>CLEAR</i>인 경우 이전 로케일이 삭제됩니다.</dd>
   <dt>--check-version true|false</dt>
   <dd>CLI 버전 확인을 사용하거나 사용하지 않습니다.</dd>
   </dl>

이들 옵션 중에서 한 번에 하나만 지정할 수 있습니다.

<strong>예제</strong>:

HTTP 요청 제한시간을 30초로 설정합니다.

```
ibmcloud config --http-timeout 30
```

HTTP 요청에 대한 추적 출력을 사용하도록 설정합니다.

```
ibmcloud config --trace true
```

지정된 파일 */home/usera/my_trace*에 대한 HTTP 요청 추적:

```
ibmcloud config --trace /home/usera/my_trace
```

색상 출력을 사용하지 않도록 설정합니다.

```
ibmcloud config --color false
```

로케일을 zh_Hans로 설정합니다.

```
ibmcloud config --locale zh_Hans
```

로케일 설정을 지웁니다.

```
ibmcloud config --locale CLEAR
```

## ibmcloud info
{: #ibmcloud_info}

현재 지역, 클라우드 제어기 버전, 로그인과 교환 액세스 토큰의 엔드포인트 같은 유용한 엔드포인트 등 기본 {{site.data.keyword.Bluemix_notm}} 정보를 확인합니다.

```
ibmcloud info
```

<strong>전제조건</strong>: 엔드포인트

## ibmcloud cf
{: #ibmcloud_cf}

임베디드 CF CLI 호출

```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>메시지 "cf 명령 호출 중..." 끄기</dd>
</dl>

<strong>예제</strong>:

cf 앱 나열:

```
ibmcloud cf apps
```

메시지 "cf 명령 호출 중..." 없이 cf 서비스 나열:

```
ibmcloud -q cf services
```

## ibmcloud login
{: #ibmcloud_login}

사용자가 로그인됩니다.

```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [-o ORG] [-s SPACE]
```

<strong>전제조건</strong>: 없음

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>명령 옵션</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i>(선택사항)</dt>
  <dd> API 엔드포인트(예: api.ng.bluemix.net)</dd>
  <dt> --apikey <i>API_KEY 또는 @API_KEY_FILE_PATH</i>
  <dd> API 키 컨텐츠 또는 @로 표시되는 API 키 파일의 경로</dd>
  <dt> --sso(선택사항) </dt>
  <dd> 일회성 패스코드를 사용하여 로그인 </dd>
  <dt> -u <i>USERNAME</i>(선택사항)</dt>
  <dd> 사용자 이름</dd>
  <dt> -p <i>PASSWORD</i>(선택사항)</dt>
  <dd> 비밀번호</dd>
  <dt> -c <i>ACCOUNT_ID</i>(선택사항) </dt>
  <dd> 대상 계정의 ID</dd>
  <dt> -g <i>RESOURCE_GROUP</i>(선택사항) </dt>
  <dd> 대상 리소스 그룹의 이름</dd>
  <dt> -o <i>ORG</i>(선택사항)</dt>
  <dd> 대상 조직의 이름(더 이상 사용되지 않음, 'ibmcloud target -o ORG' 사용)</dd>
  <dt> -s <i>SPACE</i>(선택사항) </dt>
  <dd> 대상 영역의 이름(더 이상 사용되지 않음, 'ibmcloud target -s SPACE' 사용)</dd>
  <dt> --no-iam </dt>
  <dd> 공용 IAM 대신 로그인 서버를 통한 인증 강제 실행</dd>
  <dt> --skip-ssl-validation(선택사항) </dt>
  <dd> HTTP 요청의 SSL 유효성 검증을 무시합니다. 이 옵션은 권장되지 않습니다.</dd>
</dl>

<strong>예제</strong>:

#### 대화식 로그인

```
ibmcloud login
```

사용자 이름과 비밀번호로 로그인하고 대상 계정, 조직 및 영역을 설정하십시오.

```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

일회성 패스코드로 로그인하고 대상 계정, 조직 및 영역을 설정하십시오.

```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

API 키로 로그인하고 대상을 설정하십시오.

#### API 키에 계정이 연관되어 있음

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

#### API에 계정이 연관되어 있지 않음

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>참고:</strong> API 키에 연관된 계정이 있는 경우, 다른 계정으로 전환이 허용되지 않습니다.

#### 일회성 패스코드 사용

```
ibmcloud login -u UserID --sso
```

그러면 CLI에서 URL 링크를 제공하고 패스코드를 요청합니다.
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```

브라우저에서 링크를 열면 패스코드를 가져오도록 안내를 받게 됩니다. 콘솔에서 제공된 패스코드를 입력하면 로그인할 수 있어야 합니다.

## ibmcloud logout
{: #ibmcloud_logout}

사용자가 로그아웃됩니다.

```
ibmcloud logout
```

<strong>전제조건</strong>: 없음

## ibmcloud regions
{: #ibmcloud_regions}

{{site.data.keyword.Bluemix_notm}}의 모든 지역에 대한 정보를 확인합니다.

```
ibmcloud regions
```

<strong>전제조건</strong>: 엔드포인트

## ibmcloud target
{: #ibmcloud_target}


대상 계정, 지역, 조직 또는 영역을 설정하거나 보십시오.

```
ibmcloud target [-r REGION_NAME] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i>(선택사항)</dt>
   <dd>전환할 지역의 이름입니다(예: 'us-south' 또는 'eu-gb').</dd>
   <dt>-c <i>ACCOUNT_ID</i>(선택사항)</dt>
   <dd>대상으로 지정된 계정의 ID입니다.</dd>
   <dt>-g <i>RESOURCE_GROUP</i>(선택사항)</dt>
   <dd>리소스 그룹의 이름</dd>
   <dt>--cf</dt>
   <dd>대상 조직 및 영역을 대화식으로 선택합니다.</dd>
   <dt>-o <i>ORG_NAME</i>(선택사항)</dt>
   <dd>대상으로 지정된 조직의 이름입니다.</dd>
   <dt>-s <i>SPACE_NAME</i>(선택사항)</dt>
   <dd>대상으로 지정된 영역의 이름입니다.</dd>
   </dl>
옵션이 지정되지 않은 경우, 현재 계정, 영역, 조직 및 영역이 표시됩니다.

<strong>예제</strong>:

현재 계정, 조직 및 영역 설정하기:

```
ibmcloud target -c MyAccountID -o MyOrg -s MySpace
```

새 지역으로 전환하기:

```
ibmcloud target -r eu-gb
```

현재 계정, 지역, 조직 및 영역 보기:

```
ibmcloud target
```

## ibmcloud update
{: #ibmcloud_update}

최신 버전으로 CLI를 업데이트합니다.

```
ibmcloud update [-f]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
  <dt>-f</dt>
  <dd>확인 없이 업데이트를 강제 실행합니다. 루트 권한이 필요합니다.</dd>
</dl>
