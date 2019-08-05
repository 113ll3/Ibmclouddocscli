---

copyright:
  years: 2018, 2019
lastupdated: "2019-07-29"

keywords: cli, ibmcloud billing, view account, view usage, account usage, resource groups, resources, org-usage

subcollection: cloud-cli

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:tip: .tip}

# 계정, 조직, 리소스 그룹 및 리소스의 사용량 보기 
{: #ibmcloud_billing}

다음 명령을 사용하여 리소스 사용 및 비용 청구 정보를 검색하십시오.
{: shortdesc}
 
## ibmcloud billing account-usage
{: #ibmcloud_billing_account_usage}

현재 계정의 월별 사용량 표시(계정 관리자 전용):
```
ibmcloud billing account-usage [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜의 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
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

조직의 월별 사용량 표시(계정 관리자 또는 조직 비용 청구 관리자 전용): 
```
ibmcloud billing org-usage ORG_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>ORG_NAME(필수)</dt>
  <dd>조직의 이름입니다.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜의 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud billing resource-group-usage
{: #ibmcloud_billing_resource_group_usage}

리소스 그룹의 월별 사용량 표시(계정 관리자 또는 리소스 그룹 관리자 전용):
```
ibmcloud billing resource-group-usage GROUP_NAME [-d YYYY-MM] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>GROUP_NAME(필수)</dt>
  <dd>리소스 그룹의 이름.</dd>
  <dt>-d MONTH_DATE(선택사항)</dt>
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜의 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud billing resource-instances-usage
{: #ibmcloud_billing_resource_instances_usage}

현재 계정의 월별 리소스 인스턴스 사용량 표시:
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
  <dd>YYYY-MM 형식을 사용하여 지정된 월 및 날짜의 데이터를 표시합니다. 지정되지 않으면 현재 월의 사용량이 표시됩니다.</dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>

## ibmcloud billing enterprise-usage
{: #ibmcloud_billing_enterprise_usage}

엔터프라이즈 사용량 보고서 표시: 
```
ibmcloud billing enterprise-usage [--account-group ACCOUNT_GROUP_NAME | --account-group-id ACCOUNT_GROUP_ID | --account ACCOUNT_NAME | --account-id ACCOUNT_ID] [--month MONTH] [--children] [--output FORMAT]
```

<strong>전제조건</strong>: 엔드포인트, 로그인

<strong>명령 옵션</strong>:

<dl>
  <dt>--account ACCOUNT_NAME(선택사항)</dt>
  <dd>대상 계정의 이름입니다. </dd>
  <dt>--account-id ACCOUNT_ID(선택사항)</dt>
  <dd>대상 계정의 ID입니다. </dd>
  <dt>--account-group ACCOUNT_GROUP_NAME(선택사항)</dt>
  <dd>대상 계정 그룹의 이름입니다. </dd>
  <dt>--account-group-id ACCOUNT_GROUP_ID(선택사항)</dt>
  <dd>대상 계정 그룹의 ID입니다. </dd>
  <dt>--children(선택사항)</dt>
  <dd>하위 사용량 보고서를 표시합니다. </dd>
  <dt>--month MONTH(선택사항)</dt>
  <dd>대상 월입니다. 기본값은 현재 월입니다. </dd>
  <dt>--output FORMAT(선택사항)</dt>
  <dd>출력 형식을 지정합니다. 이제 JSON만 지원됩니다.</dd>
</dl>
