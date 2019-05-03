---

copyright:
  years: 2018, 2019
lastupdated: "2019-03-15"

keywords: general commands, ibmcloud commands, ibmcloud api, ibmcloud, cli commands, regions, target, update, ibmcloud sl

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}
{:note: .note}
{:codeblock: .codeblock}

# 일반 CLI(ibmcloud) 명령
{: #ibmcloud_cli}

{{site.data.keyword.cloud_notm}} 명령행 인터페이스(CLI)는 사용자가 {{site.data.keyword.cloud_notm}}와 상호작용할 수 있도록 네임스페이스별로 그룹화된 명령 세트를 제공합니다.

{{site.data.keyword.cloud_notm}} 명령행 클라이언트는 Cloud Foundry 명령행 클라이언트를 해당 설치에서 번들화합니다. 자신에게 직접 설치한 cf cli가 있는 경우에는 {{site.data.keyword.cloud_notm}} CLI 명령 `ibmcloud [command]`와 해당 설치의 Cloud Foundry CLI 명령 `cf [command]`를 동일한 컨텍스트에서 함께 사용하지 마십시오. cf cli를 사용하여 {{site.data.keyword.cloud_notm}} CLI 컨텍스트에서 Cloud Foundry 리소스를 관리하려면 `ibmcloud cf [command]`를 대신 사용하십시오. `ibmcloud cf api/login/logout/target`은 허용되지 않으며 대신 `ibmcloud api/login/logout/target`을 사용해야 한다는 점을 참고하십시오.

2018년 5월부터 {{site.data.keyword.cloud_notm}} CLI 명령은 `bluemix` 및 `bx`에서 `ibmcloud`로 변경되었습니다. 그러나 나중에 제거되기 전까지는 여전히 `bluemix` 및 `bx` CLI 명령을 사용할 수 있습니다.
{: tip}

다음에는 해당 이름, 인수, 옵션, 필수 소프트웨어, 설명 및 예제를 포함하여 {{site.data.keyword.cloud_notm}} CLI에서 지원하는 자세한 명령이 나열되어 있습니다.
{: shortdesc}

*전제조건*에는 명령을 사용하기 전에 필요한 조치가 나열되어 있습니다. 전제조건 조치가 없는 명령은 **없음**으로 표시됩니다. 그 밖의 경우에는 전제조건으로 다음과 같은 조치 중 하나 이상을 수행해야 할 수 있습니다.

<dl>
<dt>엔드포인트</dt>
<dd>명령을 사용하기 전에 <code>ibmcloud api</code>를 통해 API 엔드포인트를 설정해야 합니다.</dd>
<dt>로그인</dt>
<dd>이 명령을 사용하기 전에 <code>ibmcloud login</code> 명령을 사용하여 로그인해야 합니다.
 연합 ID로 로그인한 경우에는 '--sso' 옵션을 사용하여 일회성 패스코드로 인증하거나 '--apikey'를 사용하여 API 키로 인증하십시오.
</dd>
<dt>대상</dt>
<dd>이 명령을 사용하기 전에 <code>ibmcloud target</code> 명령을 사용하여 조직과 영역을 설정해야 합니다.</dd>
<dt>Docker</dt>
<dd>이 명령을 실행하려면 Docker CLI(docker)가 설치되어 있어야 합니다.</dd>
</dl>

## ibmcloud help
{: #ibmcloud_help}

첫 번째 레벨 기본 제공 명령 및 지원되는 {{site.data.keyword.cloud_notm}} CLI 네임스페이스에 대한 일반 도움말 또는 특정 기본 제공 명령 또는 네임스페이스의 도움말을 표시합니다.

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

{{site.data.keyword.cloud_notm}} CLI의 일반 도움말을 표시합니다.
```
ibmcloud help
```
{: codeblock}

`info` 명령의 도움말을 표시합니다.
```
ibmcloud help info
```
{: codeblock}

## ibmcloud api
{: #ibmcloud_api}

{{site.data.keyword.cloud_notm}} API 엔드포인트를 설정하거나 확인합니다.
```
ibmcloud api [API_ENDPOINT] [--unset] [--skip-ssl-validation]
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
   <dl>
   <dt>API_ENDPOINT(선택사항)</dt>
   <dd>대상으로 지정된 API 엔드포인트입니다(예: `https://cloud.ibm.com`). *API_ENDPOINT* 및 `--unset` 옵션 중 하나를 지정하지 않으면 현재 API 엔드포인트가 표시됩니다.</dd>
   <dt>--unset(선택사항)</dt>
   <dd>API 엔드포인트 설정을 제거합니다.</dd>
   <dt>--skip-ssl-validation(선택사항)</dt>
   <dd>HTTP 요청의 SSL 유효성 검증을 무시합니다.</dd>
   </dl>
<strong>예제</strong>:

API 엔드포인트를 cloud.ibm.com으로 설정합니다.
```
ibmcloud api cloud.ibm.com
```
{: codeblock}

```
ibmcloud api https://cloud.ibm.com --skip-ssl-validation
```
{: codeblock}

현재 API 엔드포인트를 확인합니다.
```
ibmcloud api
```
{: codeblock}

API 엔드포인트를 설정 해제합니다.
```
ibmcloud api --unset
```
{: codeblock}

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
{: codeblock}

HTTP 요청에 대한 추적 출력을 사용하도록 설정합니다.
```
ibmcloud config --trace true
```
{: codeblock}

지정된 파일 */home/usera/my_trace*에 대한 HTTP 요청 추적:
```
ibmcloud config --trace /home/usera/my_trace
```
{: codeblock}

색상 출력을 사용하지 않도록 설정합니다.
```
ibmcloud config --color false
```
{: codeblock}

로케일을 zh_Hans로 설정합니다.
```
ibmcloud config --locale zh_Hans
```
{: codeblock}

로케일 설정을 지웁니다.
```
ibmcloud config --locale CLEAR
```
{: codeblock}

## ibmcloud info
{: #ibmcloud_info}

`ibmcloud info` 명령은 CLI 버전 `0.14`부터 더 이상 사용할 수 없습니다. 최신 CLI 버전을 설치하려면 [독립형 {{site.data.keyword.cloud_notm}} CLI 설치](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)를 참조하십시오.
{: note}

## ibmcloud cf
{: #ibmcloud_cf}

임베디드 CF CLI를 호출합니다.
```
ibmcloud [-q, --quiet] cf COMMAND...
```

<strong>전제조건</strong>: 없음

<strong>명령 옵션</strong>:
<dl>
  <dt>-q, --quiet</dt>
  <dd>메시지 "cf 명령 호출 중..."을 표시하지 않음</dd>
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
{: codeblock}

## ibmcloud login
{: #ibmcloud_login}

사용자가 로그인됩니다.
```
ibmcloud login [-a API_ENDPOINT] [--sso] [-u USERNAME] [-p PASSWORD] [--apikey KEY | @KEY_FILE] [--no-iam] [-c ACCOUNT_ID | --no-account] [-g RESOURCE_GROUP] [-r REGION | --no-region] [-o ORG] [-s SPACE]
```

<strong>전제조건</strong>: 없음

<!-- staging comment for Atlas 45: might need prereq for federated ID/SSO option unless we expect them to just view the details from the cf login command -->

<strong>명령 옵션</strong>:
<dl>
  <dt> -a <i>API_ENDPOINT</i>(선택사항)</dt>
  <dd> API 엔드포인트(예: cloud.ibm.com)</dd>
  <dt> --apikey <i>API_KEY 또는 @API_KEY_FILE_PATH</i>
  <dd> API 키 컨텐츠 또는 @로 표시되는 API 키 파일의 경로</dd>
  <dt> --sso(선택사항) </dt>
  <dd> 일회성 패스코드를 사용하여 로그인 </dd>
  <dt> -u <i>USERNAME</i>(선택사항)</dt>
  <dd> 사용자 이름</dd>
  <dt> -p <i>PASSWORD</i>(선택사항)</dt>
  <dd> 비밀번호</dd>
  <dt> -c <i>ACCOUNT_ID</i>(선택사항) </dt>
  <dd> 대상 계정의 ID입니다. 이 옵션은 --no-account와 배타적입니다.</dd>
  <dt> --no-account(선택사항) </dt>
  <dd> 계정 없이 강제 로그인합니다. 이 옵션은 권장되지 않습니다. 이 옵션은 -c와 배타적입니다.</dd>
  <dt> -g <i>RESOURCE_GROUP</i>(선택사항) </dt>
  <dd> 대상 리소스 그룹의 이름</dd>
  <dt> -r REGION</dt>
  <dd> 지역 이름, 예를 들어 'us-south' 또는 'eu-gb'</dt>
  <dt> --no-region</dt>
  <dd> 지역을 대상으로 지정하지 않고 강제로 로그인합니다.</dd>
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

### 대화식 로그인

```
ibmcloud login
```
{: codeblock}

사용자 이름과 비밀번호로 로그인하고 대상 계정, 조직 및 영역을 설정하십시오.
```
ibmcloud login -u username -p password -c MyAccountID -o MyOrg -s MySpace
```

일회성 패스코드로 로그인하고 대상 계정, 조직 및 영역을 설정하십시오.
```
ibmcloud login --sso -c MyAccountID -o MyOrg -s MySpace
```

### API 키에 계정이 연관되어 있음

```
ibmcloud login --apikey api-key-string -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @filename -o MyOrg -s MySpace
```

### API에 계정이 연관되어 있지 않음

```
ibmcloud login --apikey api-key-string -c MyAccountID -o MyOrg -s MySpace
```

```
ibmcloud login --apikey @fileName -c MyAccountID -o MyOrg -s MySpace
```

<strong>참고:</strong> API 키에 연관된 계정이 있는 경우, 다른 계정으로 전환이 허용되지 않습니다.

### 일회성 패스코드 사용
```
ibmcloud login -u UserID --sso
```
{: codeblock}

그러면 CLI에서 URL 링크를 제공하고 패스코드를 요청합니다.
```
One Time Code (Get one at https://URL_Link_To_Obtain_Passcode):
```
{: screen}

브라우저에서 링크를 열어서 패스코드를 가져오십시오. 콘솔에서 제공된 패스코드를 입력하면 로그인할 수 있습니다.

## ibmcloud logout
{: #ibmcloud_logout}

사용자가 로그아웃됩니다.
```
ibmcloud logout
```
{: codeblock}

<strong>전제조건</strong>: 없음

## ibmcloud regions
{: #ibmcloud_regions}

{{site.data.keyword.Bluemix_notm}}의 모든 지역에 대한 정보를 확인합니다.
```
ibmcloud regions
```
{: codeblock}

<strong>전제조건</strong>: 엔드포인트

## ibmcloud target
{: #ibmcloud_target}


대상 계정, 지역, 조직 또는 영역을 설정하거나 봅니다.
```
ibmcloud target [-r REGION_NAME | --unset-region] [-c ACCOUNT_ID] [-g RESOURCE_GROUP] [--cf] [-o ORG] [-s SPACE]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
   <dl>
   <dt>-r <i>REGION_NAME</i>(선택사항)</dt>
   <dd>전환할 지역의 이름입니다(예: 'us-south' 또는 'eu-gb').</dd>
   <dt>--unset-region</dt>
   <dd>대상 지역 설정 취소</dd>
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
{: codeblock}

새 지역으로 전환하기:
```
ibmcloud target -r eu-gb
```
{: codeblock}

현재 계정, 지역, 조직 및 영역 보기:
```
ibmcloud target
```
{: codeblock}

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


## 일반 클래식 인프라 서비스 명령
{: #softlayer_cli}

인프라 서비스를 구성하고 관리하려면 {{site.data.keyword.cloud_notm}} 명령행 인터페이스(CLI)에서 클래식 인프라 명령을 사용하십시오.

사용 가능한 명령의 목록을 보려면 `ibmcloud sl` 명령을 실행하십시오.
```
USAGE:
   ibmcloud sl command [arguments...] [options...]

COMMANDS:
   block           Gen1 infrastructure Block Storage
   cdn             Gen1 infrastructure Content Delivery Network
   file            Gen1 infrastructure File Storage
   dns             Gen1 infrastructure Domain Name System
   globalip        Gen1 infrastructure Global IP addresses
   hardware        Gen1 infrastructure hardware servers
   image           Gen1 infrastructure Compute images
   ipsec           Gen1 infrastructure IPSEC VPN
   loadbal         Gen1 infrastructure Load balancers
   security        Gen1 infrastructure SSH Keys and SSL Certificates
   securitygroup   Gen1 infrastructure network security groups
   subnet          Gen1 infrastructure Network subnets
   ticket          Gen1 infrastructure Manage Tickets
   vlan            Gen1 infrastructure Network VLANs
   vs              Gen1 infrastructure Virtual Servers
   order           Gen1 infrastructure Orders
   user            Gen1 infrastructure Manage Users
   call-api        Call arbitrary API endpoints.
   help            Print command usage message
```
{: screen}

명령에 대한 도움말 정보를 보려면 다음을 실행하십시오.
```
ibmcloud sl [command] -h
```

`ibmcloud sl init` 명령은 CLI 버전 `0.14`부터 더 이상 사용할 수 없습니다. 최신 CLI 버전을 설치하려면 [독립형 {{site.data.keyword.cloud_notm}} CLI 설치](/docs/cli/reference/ibmcloud?topic=cloud-cli-install-ibmcloud-cli#install-ibmcloud-cli)를 참조하십시오.
{: note}

## ibmcloud sl help
{: #sl_help}

클래식 인프라 환경을 운영하기 위한 모든 명령에 대한 도움말 정보를 봅니다.
```
ibmcloud sl help
```
{: codeblock}

