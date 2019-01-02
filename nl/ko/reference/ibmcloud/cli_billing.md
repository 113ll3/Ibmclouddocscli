---

copyright:

  years: 2018


lastupdated: "2018-11-29"
---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 계정, 조직, 리소스 그룹 및 리소스의 사용량 보기 
{: #ibmcloud_billing}

다음 명령을 사용하여 리소스 사용 및 비용 청구 정보를 검색하십시오.
{: shortdesc}

<table summary="{{site.data.keyword.Bluemix_notm}} 비용 청구 및 사용량을 관리하는 데 사용할 수 있는 ibmcloud 명령.">
 <thead>
 </thead>
 <tbody>
<tr>
  <td>[ibmcloud billing account-usage](cli_billing.html#ibmcloud_billing_account_usage)</td>
  <td>[ibmcloud billing org-usage](cli_billing.html#ibmcloud_billing_org_usage)</td>
  <td>[ibmcloud billing resource-group-usage](cli_billing.html#ibmcloud_billing_resource_group_usage)</td>
  <td>[ibmcloud billing resource-instances-usage](cli_billing.html#ibmcloud_billing_resource_instances_usage)</td>
 </tr>
 </tbody>
 </table>
 
 
 ## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

현재 계정의 월별 사용량 표시(계정 관리자만)

```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

<strong>예제</strong>:

2016년 6월에 현재 계정의 사용량 및 비용 보고서 표시:

```
ibmcloud billing account-usage -d 2016-06
```

## ibmcloud billing org-usage
{: #ibmcloud_billing_org_usage}

조직의 월별 사용량 표시(계정 관리자 또는 조직 청구 관리자만)

```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>ORG_NAME(필수)</dt>
  <dd>조직의 이름입니다.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

리소스 그룹의 월별 사용량 표시(계정 관리자 또는 리소스 그룹 관리자만)

```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>GROUP_NAME(필수)</dt>
  <dd>리소스 그룹의 이름.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

현재 계정의 월별 리소스 인스턴스 사용량을 표시합니다.

```
ibmcloud billing resource-instances-usage [-o ORG] [-g RESOURCE_GROUP] [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>-o ORG_NAME(선택사항)</dt>
  <dd>조직으로 인스턴스를 필터링합니다.</dd>
  <dt>-g GROUP_NAME</dt>
  <dd>리소스 그룹으로 인스턴스를 필터링합니다.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜에 대한 데이터를 표시하십시오. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>
