---

copyright:

  years: 2018


lastupdated: "2018-08-21"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# Cloud Foundry Enterprise Environments 관리(시범)
{: #ibmcloud_commands_cfee}

<table summary="Cloud Foundry Enterprise Environments 관리(시범)">
<caption>표 1. Cloud Foundry Enterprise Environments 관리(시범)</caption>
 <thead>
 <th colspan="5">Cloud Foundry Enterprise Environments 관리(시범)</th>
 </thead>
 <tbody>
 <tr>
 <td>[ibmcloud cfee environments](cli_cfee.html#ibmcloud_cfee_environments)</td>
 <td>[ibmcloud cfee environment](cli_cfee.html#ibmcloud_cfee_environment)</td>
 </tr>
 </tbody>
 </table>

 ## ibmcloud cfee environments
{: #ibmcloud_cfee_environments}

CFEE 환경을 나열합니다.

```
ibmcloud cfee environments
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

## ibmcloud cfee environment
{: #ibmcloud_cfee_environment}

CFEE 환경의 세부사항을 표시합니다.

```
ibmcloud cfee environment NAME [--id]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:
  <dl>
   <dt>--id</dt>
   <dd>ID만 표시합니다.</dd>
  </dl>

<strong>예제</strong>:

CFEE 환경 env_example의 세부사항 표시:

```
ibmcloud cfee environment env_example
```

CFEE 환경 env_example의 ID 표시:

```
ibmcloud cfee environment env_example --id
```
