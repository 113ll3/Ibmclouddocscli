---

copyright:
  years: 2018, 2019
lastupdated: "2019-04-04"

keywords: cli, manage softlayer users, softlayer, classic infrastructure, user management, ibmcloud sl user

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:tip: .tip}

# 클래식 인프라 사용자 관리
{: #manage-sl-users}

다음 명령을 사용하여 {{site.data.keyword.cloud}} 클래식 인프라 사용자를 관리할 수 있습니다.
{: shortdesc}

## ibmcloud sl user create 
{: #sl_user_create} 

사용자를 작성하려면 다음을 수행하십시오. 
```
ibmcloud sl user create [OPTIONS] USERNAME
```

<strong>명령 옵션</strong>:
<dl>
<dt>--email</dt>
<dd>이 사용자의 이메일 주소입니다. 작성에 필수입니다. </dd>
<dt>--password</dt>
<dd>이 사용자에 대해 설정할 비밀번호입니다. 비밀번호를 제공하지 않으면 비밀번호 생성을 위한 이메일이 사용자에게 전송되고 이메일은 24시간 후에 만료됩니다. 비밀번호를 생성하려면 '-p generate' 옵션을 지정하십시오. 비밀번호는 8자 이상 문자로 대문자와 소문자, 숫자와 기호가 포함되어 있어야 합니다. </dd>
<dt>--from-user</dt>
<dd>이 사용자를 작성하기 위한 템플리트로 사용할 기본 사용자입니다. 기본값은 이 명령을 실행하는 사용자를 사용하는 것입니다. --template에 제공된 정보가 이 템플리트를 대체합니다. </dd>
<dt>--template</dt>
<dd>https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/를 설명하는 JSON 문자열입니다.</dd>
<dt>--api-key</dt>
<dd>이 사용자에 대한 API 키를 작성합니다. </dd>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>


## ibmcloud sl user delete 
{: #sl_user_delete} 

사용자의 상태를 `CANCEL_PENDING`으로 설정합니다. 그러면 계정이 즉각 비활성화되고 자동화된 내부 프로세스를 통해 계정에서 결국 제거됩니다. 
```
ibmcloud sl user delete [OPTIONS] IDENTIFIER
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

## ibmcloud sl user detail 
{: #sl_user_detail} 

사용자의 세부사항을 보려면 다음을 수행하십시오.
```
ibmcloud sl user detail [OPTIONS] IDENTIFIER
```

<strong>명령 옵션</strong>:
<dl>
<dt>--keys</dt>
<dd>사용자 API 키를 표시합니다. </dd>
<dt>--permissions</dt>
<dd>이 사용자에게 지정된 권한을 표시합니다. 마스터 사용자는 권한 없음을 표시합니다. </dd>
<dt>--hardware</dt>
<dd>이 사용자가 액세스할 수 있는 하드웨어를 표시합니다.</dd>
<dt>--virtual</dt>
<dd>이 사용자가 액세스할 수 있는 가상 게스트를 표시합니다.</dd>
<dt>--logins</dt>
<dd>지난 30일 동안 이 사용자의 로그인 히스토리를 표시합니다. </dd>
<dt>--events</dt>
<dd>이 사용자에 대한 감사 로그를 표시합니다. </dd>
</dl>

## ibmcloud sl user edit-details 
{: #sl_user_edit_details} 

사용자의 세부사항을 편집하려면 다음을 수행하십시오.
```
ibmcloud sl user edit-details [OPTIONS] IDENTIFIER
```

<strong>명령 옵션</strong>:
<dl>
<dt>--template</dt>
<dd>https://sldn.softlayer.com/reference/datatypes/SoftLayer_User_Customer/를 설명하는 JSON 문자열입니다.</dd>
</dl>

## ibmcloud sl user edit-permissions 
{: #sl_user_edit_permissions} 

특정 사용자 권한을 사용 또는 사용 안함으로 설정하려면 다음을 수행하십시오.
```
ibmcloud sl user edit-permissions [OPTIONS] IDENTIFIER
```

<strong>명령 옵션</strong>:
<dl>
<dt>--enable</dt>
<dd>선택한 권한을 사용 또는 사용 안함으로 설정합니다. 허용되는 입력은 'true' 및 'false'입니다. 기본값은 'true'입니다. </dd>
<dt>--permission</dt>
<dd>설정할 권한 `keyName`이며 여러 인스턴스가 허용됩니다. 모든 권한을 선택하려면 키워드 ALL을 사용하십시오. </dd>
<dt>--from-user</dt>
<dd>이 사용자의 권한과 일치하도록 권한을 설정합니다. 해당 권한을 추가하고 제거합니다.</dd>
</dl>

## ibmcloud sl user list 
{: #sl_user_list} 

사용자를 나열하려면 다음을 수행하십시오. 
```
ibmcloud sl user list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--column</dt>
<dd>표시할 열입니다. [옵션: id,username,email,displayName,status,hardwareCount,virtualGuestCount][default: id,username,email,displayName].</dd>
</dl>

## ibmcloud sl user permissions 
{: #sl_user_permissions} 

사용자 권한을 보려면 다음을 수행하십시오.
```
ibmcloud sl user permissions [OPTIONS] IDENTIFIER
```

