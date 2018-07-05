---

copyright:

  years: 2018


lastupdated: "2018-06-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 일반 CLI(ibmcloud sl) 명령
{: #softlayer_cli}

{{site.data.keyword.BluSoftlayer}} 플러그인은 {{site.data.keyword.Bluemix_notm}} CLI에 병합되었습니다. 더 이상 플러그인을 설치할 필요가 없습니다.
{: tip}

SoftLayer 서비스를 구성하고 관리하려면 {{site.data.keyword.Bluemix_notm}} 명령행 인터페이스(CLI)에서 {{site.data.keyword.BluSoftlayer_notm}} 인프라 명령을 사용하십시오.

2018년 5월부터 {{site.data.keyword.Bluemix_notm}} CLI 명령은 `bluemix` 및 `bx`에서 `ibmcloud`로 변경되었습니다. 하지만 `bluemix` 및 `bx` CLI 명령은 나중에 제거할 때까지 사용할 수 있습니다.
{: tip}

시작하려면 {{site.data.keyword.Bluemix_notm}} CLI를 설치하십시오. 세부사항은
[IBM Cloud CLI ![외부 링크 아이콘](../../../icons/launch-glyph.svg)](http://clis.ng.bluemix.net/ui/home.html){: new_window}를 참조하십시오.

{{site.data.keyword.Bluemix_notm}} CLI 명령의 전체 목록은 [{{site.data.keyword.Bluemix_notm}} (ibmcloud) 명령](docs/cli/reference/bluemix_cli/bx_cli.html#ibmcloud_cli)을 참조하십시오.

다음 명령이 지원됩니다. 사용 가능한 명령의 목록을 보려면 `ibmcloud sl` 명령을 사용하십시오.

<table summary="해당 명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 일반 명령">
<caption>표 1. 일반 {{site.data.keyword.BluSoftlayer_notm}} 인프라 명령</caption>
 <thead>
 <th colspan="6">일반 {{site.data.keyword.BluSoftlayer_notm}} 인프라 명령</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud sl init](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_init)</td>
 <td>[ibmcloud sl help](/docs/cli/reference/softlayer/sl_cli_cmds.html#sl_help)</td>
   </tbody>
 </table>
 
 명령에 대한 도움말 정보를 보려면 `ibmcloud sl [command] -h`를 실행하십시오.
 
 ## ibmcloud sl init
{: #sl_init}

{{site.data.keyword.BluSoftlayer_notm}} 인프라 환경에 연결하는 데 사용되는 구성 설정을 초기화하십시오. 구성에는 사용자 이름, API 키 또는 비밀번호, 계정 및 엔드포인트가 포함됩니다.
```
ibmcloud sl init [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-a, --api-endpoint</dt>
<dd>{{site.data.keyword.BluSoftlayer_notm}} 인프라 API 엔드포인트 URL. 기본값: https://api.softlayer.com/rest/v3.1 (API 키 인증의 경우), https://api.softlayer.com/mobile/v3.1 (IBM ID 인증의 경우).</dd>
<dt>-u, --sl-user</dt>
<dd>Gen1 인프라 사용자 이름.</dd>
<dt>-p, --sl-password</dt>
<dd>비밀번호 또는 API 키.</dd>
<dt>-c, --account-id</dt>
<dd>계정 ID.</dd>
<dt>-q, --security-question-id</dt>
<dd>인증에 사용되는 보안 질문 ID. 모르는 경우 계정 소유자에게 문의하십시오.</dd>
<dt>-w, --security-question-answer</dt>
<dd>인증에 사용되는 보안 질문의 대답. 모르는 경우 계정 소유자에게 문의하십시오.</dd>
<dt>-s, --security-code</dt>
<dd>2단계 인증이 사용되는 경우 보안 공급업체에서 생성한 보안 코드.</dd>
<dt>-v, --security-vendor</dt>
<dd>인증을 위해 보안 코드를 제공하는 보안 공급업체. 옵션: VERISIGN,TOTP,PHONE_FACTOR.</dd>
<dt>-t, --auth-token</dt>
<dd>전화 인증이 사용되는 경우 인증 토큰.</dd>
</dl>

예: {{site.data.keyword.BluSoftlayer_notm}} 인프라 사용자 이름 및 비밀번호/API 키로 로그인
```
$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:
1. Login with {{site.data.keyword.BluSoftlayer_notm}} infrastructure user name and password/API key
2. Use {{site.data.keyword.Bluemix_notm}} Single-Sign-On
Enter a number>1
Softlayer API endpoint URL: [https://api.softlayer.com/rest/v3.1]>
Username: []> user@example.com
API key or password: []> abcd

API endpoint:    https://api.softlayer.com/rest/v3.1   
User name:       user@example.com   
API Key:         xxxxxxxxxx
```
예: {{site.data.keyword.Bluemix_notm}} Single-Sign-On을 사용하여 Softlayer에 로그인
```
$ ibmcloud login -a api.ng.bluemix.net -u user@example.com -p xxxxxxx -c 65ce8074c6c62b5
API endpoint: api.ng.bluemix.net
Authenticating...
OK

Targeted account example user's Account (65ce8074c6c62b5)

API endpoint:   https://api.ng.bluemix.net (API version: 2.54.0)   
Region:         us-south   
User:           user@example.com   
Account:        example user's Account (65ce8074c6c62b5)   
No org or space targeted, use 'ibmcloud target --cf or ibmcloud target -o ORG -s SPACE'


$ ibmcloud sl init
Choose how to configure {{site.data.keyword.BluSoftlayer_notm}} infrastructure authentication:

1. Login with Softlayer user name and password/API key
2. Use IBM Cloud Single-Sign-On
Enter a number> 2
{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint URL: [https://api.softlayer.com/mobile/v3.1]>
Setting account to: 123456
OK

{{site.data.keyword.BluSoftlayer_notm}} infrastructure API endpoint:    https://api.softlayer.com/mobile/v3.1   

Account ID:                123456   
User ID:                   user@example.com  
IMS token:                 xxxxxxxxxx
```

## ibmcloud sl help
{: #sl_help}

{{site.data.keyword.BluSoftlayer_notm}} 인프라 환경을 운영하기 위한 모든 명령에 대한 도움말 정보를 봅니다.
```
ibmcloud sl help
```
