---

copyright:
  years: 2018, 2019
lastupdated: "2019-02-21"

keywords: monitoring, logging, cloud logging, metrics

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# {{site.data.keyword.cloud_notm}}에서 모니터링 및 로깅
{: #monitoring_logging}

## 모니터링
{: #cloud-monitoring}

{{site.data.keyword.cloud}}는 기본적으로 CPU 사용량, 메모리 사용률 및 {{site.data.keyword.containershort_notm}}의 네트워크 I/O에 대한 메트릭을 수집하고 표시합니다. {{site.data.keyword.cloud_notm}}에서 {{site.data.keyword.monitoringlong_notm}} 서비스를 사용하여 사용자 환경 및 애플리케이션에서 키 메트릭을 자동으로 수집하고 측정할 수 있습니다. 메트릭 수집에 특수 인스트루먼테이션은 필요하지 않습니다.

자세한 정보는 [{{site.data.keyword.cloud_notm}}에서 모니터링](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov)을 참조하십시오.

## 로깅
{: #cloud-logging}

{{site.data.keyword.cloud_notm}}는 기본적으로 앱, 앱 런타임 및 해당 앱이 실행되는 컴퓨팅 런타임에 대한 로그를 수집하고 표시합니다. {{site.data.keyword.cloud_notm}} 로깅 기능은 플랫폼에 통합되며, 데이터 콜렉션이 클라우드 리소스에 대해 자동으로 사용으로 설정됩니다. 

{{site.data.keyword.loganalysisfull_notm}} 서비스에서는 {{site.data.keyword.cloud_notm}} 플랫폼에 대한 로그 콜렉션 및 로그 검색 서비스를 제공하여, 선택한 서비스에서 애플리케이션 및 {{site.data.keyword.cloud_notm}} 서비스의 데이터를 자동으로 수집합니다. {{site.data.keyword.loganalysisshort}} 서비스를 사용하여 로그에 대한 작업을 수행할 때 로그 콜렉션, 로그 보존 및 로그 검색 기능을 확장할 수 있습니다.

자세한 정보는 [{{site.data.keyword.cloud_notm}}에 로그인](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov)을 참조하십시오.
