---

copyright:
  years: 2018, 2019
lastupdated: "2019-05-21"

keywords: cli, monitoring, logging, cloud logging, metrics, monitor cpu, monitor usage, memory utilization, runtime logging

subcollection: cloud-cli

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:tip: .tip}
{:screen: .screen}
{:pre: .pre}

# {{site.data.keyword.cloud_notm}} 中的监视和日志记录
{: #monitoring_logging}

## 监视
{: #cloud-monitoring}

缺省情况下，{{site.data.keyword.cloud}} 会收集并显示 {{site.data.keyword.containershort_notm}} 的 CPU 使用率、内存利用率和网络 I/O 的度量值。您可以使用 {{site.data.keyword.cloud_notm}} 中的 {{site.data.keyword.monitoringlong_notm}} 服务从环境和应用程序自动收集并度量关键度量值。无需进行特殊检测，即可收集度量值。

有关更多信息，请参阅[在 {{site.data.keyword.cloud_notm}} 中进行监视](/docs/services/cloud-monitoring?topic=cloud-monitoring-monitoring_ov#monitoring_ov)。

## 日志记录
{: #cloud-logging}

缺省情况下，{{site.data.keyword.cloud_notm}} 会收集并显示应用程序、应用程序运行时以及运行这些应用程序的计算运行时的日志。{{site.data.keyword.cloud_notm}} 日志记录功能集成在平台中，并且会对云资源自动启用数据收集。 

{{site.data.keyword.loganalysisfull_notm}} 服务会为 {{site.data.keyword.cloud_notm}} 平台提供日志收集和日志搜索服务，并且会自动从所选服务中收集应用程序和 {{site.data.keyword.cloud_notm}} 服务的数据。{{site.data.keyword.loganalysisshort}} 服务可帮助您在使用日志时扩展日志收集、日志保留和日志搜索的功能。

有关更多信息，请参阅[在 {{site.data.keyword.cloud_notm}} 中进行日志记录](/docs/services/CloudLogAnalysis?topic=cloudloganalysis-log_analysis_ov#log_analysis_ov)。
