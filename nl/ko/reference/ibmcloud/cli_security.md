---

copyright:

  years: 2018


lastupdated: "2018-08-30"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# {{site.data.keyword.Bluemix_notm}} 인프라 SSH 키 및 인증서

다음 명령을 사용하여 {{site.data.keyword.Bluemix_notm}} 인프라 SSH 키 및 인증서를 관리하십시오.
{: shortdesc}

<table summary="명령에 대한 자세한 정보를 제공하는 링크가 있는 알파벳순으로 정렬된 {{site.data.keyword.Bluemix_notm}} 인프라 보안 명령">
 <thead>
 </thead>
 <tbody>
 <tr>
  <td>[ibmcloud sl security sshkey-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_add)</td>
  <td>[ibmcloud sl security sshkey-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_edit)</td>
  <td>[ibmcloud sl security sshkey-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_list)</td>
  <td>[ibmcloud sl security sshkey-print](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_print)</td>
  <td>[ibmcloud sl security sshkey-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_sshkey_remove)</td>
 </tr>
 <tr>
  <td>[ibmcloud sl security cert-add](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_add)</td>
  <td>[ibmcloud sl security cert-edit](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_edit)</td>
  <td>[ibmcloud sl security cert-download](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_download)</td>
  <td>[ibmcloud sl security cert-list](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_list)</td>
  <td>[ibmcloud sl security cert-remove](/docs/cli/reference/ibmcloud/cli_security.html#sl_security_cert_remove)</td>
 </tr>
   </tbody>
 </table>

 ## ibmcloud sl security sshkey-add
{: #sl_security_sshkey_add}

새 SSH 키를 추가합니다.
```
ibmcloud sl security sshkey-add LABEL [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --in-file</dt>
<dd>이 키를 위해 가져올 id_rsa.pub 파일.</dd>
<dt>-k, --key</dt>
<dd>실제 SSH 키.</dd>
<dt>--note</dt>
<dd>키와 연관되는 추가 참고.</dd>
</dl>

**예제**:
```
ibmcloud sl security sshkey-add -f ~/.ssh/id_rsa.pub --note mykey
```
이 명령은 ~/.ssh/id_rsa.pub 파일에서 "mykey" 참고가 지정된 SSH 키를 추가합니다.

## ibmcloud sl security sshkey-edit
{: #sl_security_sshkey_edit}

SSH 키를 편집합니다.
```
ibmcloud sl security sshkey-edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--label</dt>
<dd>키의 새 레이블.</dd>
<dt>--note</dt>
<dd>키의 새 참고.</dd>
</dl>

**예제**:
```
ibmcloud sl security sshkey-edit 12345678 --label Bluemix --note testing
```
이 명령은 ID가 12345678인 SSH 키를 업데이트하고 레이블을 "Bluemix"로 설정하고 참고를 "testing"으로 설정합니다.

## ibmcloud sl security sshkey-list
{: #sl_security_sshkey_list}

계정의 SSH 키를 나열합니다.
```
ibmcloud sl security sshkey-list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id,label,fingerprint,notes.</dd>
</dl>

**예제**:
```
ibmcloud sl security sshkey-list --sortby label
```
이 명령은 현재 계정의 모든 SSH 키를 나열하고 레이블별로 정렬합니다.

## ibmcloud sl security sshkey-print
{: #sl_security_sshkey_print}

SSH 키를 화면에 인쇄합니다.
```
ibmcloud sl security sshkey-print IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --out-file</dt>
<dd>공용 SSH 키가 이 파일에 작성됩니다.</dd>
</dl>

**예제**:
```
ibmcloud sl security sshkey-print 12345678 -f ~/mykey.pub
```
이 명령은 ID와 레이블 그리고 ID가 12345678인 SSH 키의 참고를 표시하고 공개 키를 ~/mykey.pub 파일에 작성합니다.

## ibmcloud sl security sshkey-remove
{: #sl_security_sshkey_remove}

SSH 키를 영구 제거합니다.
```
ibmcloud sl security sshkey-remove IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl security sshkey-remove 12345678 -f
```
이 명령은 확인 요청 없이 ID가 12345678인 SSH 키를 제거합니다.

## ibmcloud sl security cert-add
{: #sl_security_cert_add}

SSL 인증서 세부사항을 추가하고 업로드합니다.
```
ibmcloud sl security cert-add [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--crt</dt>
<dd>인증 파일.</dd>
<dt>--csr</dt>
<dd>인증서 서명 요청 파일.</dd>
<dt>--icc</dt>
<dd>중간 인증서 파일.</dd>
<dt>--key</dt>
<dd>개인 키 파일.</dd>
<dt>--notes</dt>
<dd>추가 참고.</dd>
</dl>

**예제**:
```
ibmcloud sl security cert-add --crt ~/ibm.com.cert --key ~/ibm.com.key
```
이 명령은 도메인 ibm.com에 대한 인증서 파일 ~/ibm.com.cert 및 개인 키 파일 ~/ibm.com.key를 추가합니다.

## ibmcloud sl security cert-edit
{: #sl_security_cert_edit}

SSL 인증서를 편집합니다.
```
ibmcloud sl security cert-edit IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--crt</dt>
<dd>인증 파일.</dd>
<dt>--csr</dt>
<dd>인증서 서명 요청 파일.</dd>
<dt>--icc</dt>
<dd>중간 인증서 파일.</dd>
<dt>--key</dt>
<dd>개인 키 파일.</dd>
<dt>--notes</dt>
<dd>추가 참고.</dd>
</dl>

**예제**:
```
ibmcloud sl security cert-edit 12345678 --key ~/ibm.com.key
```
이 명령은 ID가 12345678인 인증서를 편집하고 해당 개인 키를 ~/ibm.com.key 파일로 업데이트합니다.

## ibmcloud sl security cert-download
{: #sl_security_cert_download}

SSL 인증서 및 키 파일을 다운로드합니다.
```
ibmcloud sl security cert-download IDENTIFIER
```


**예제**:
```
ibmcloud sl security cert-download 12345678
```
이 명령은 ID가 12345678인 인증서에 대해 현재 디렉토리에 4개 파일을 다운로드합니다. 4개 파일은 인증서 파일, 인증서 서명 요청 파일, 중간 인증서 파일 및 개인 키 파일입니다.

## ibmcloud sl security cert-list
{: #sl_security_cert_list}

계정의 SSL 인증서를 나열합니다.
```
ibmcloud sl security cert-list [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>--status</dt>
<dd>이 상태의 인증서 표시. 기본값: all, options are: all,valid,expired.</dd>
<dt>--sortby</dt>
<dd>정렬 기준 열, 옵션: id,common_name,days_until_expire,notes.</dd>
</dl>

**예제**:
```
ibmcloud sl security cert-list --status valid --sortby days_until_expire
```
이 명령은 현재 계정의 모든 유효한 인증서를 나열하고 유효성 검증일 기준으로 정렬합니다.

## ibmcloud sl security cert-remove
{: #sl_security_cert_remove}

SSL 인증서를 제거합니다.
```
ibmcloud sl security cert-remove IDENTIFIER [OPTIONS]
```

<strong>명령 옵션</strong>:
<dl>
<dt>-f, --force</dt>
<dd>확인 없이 조작 강제 실행.</dd>
</dl>

**예제**:
```
ibmcloud sl security cert-remove 12345678
```
이 명령은 ID가 12345678인 인증서를 제거합니다.
